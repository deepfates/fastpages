-----
*(2020-12-05)*

I've decided to work on the bot I previously thought of as [[Novice]], for the design hackaton Interhackt this week. 

I'm now thinking less of the overall end-goal of a general AI that pair-programs your life with you, and more of the near-term MVP that could provide a useful service to a person or community. To me, for a start.

Not a personal assistant. I saw someone with a personal assistant the other day. He was raging mad at the post office. Guy in a suit. His personal assistant was a college-age woman who was nervously taking notes on all he was saying about the post office. Self-important guy in a rage. She had to act like he was important, like it mattered whether he got his $50 deposit back from the implacable villains of the postal service. This guy is wearing $500 shoes.

She could have helped him, and herself, and all the rest of us by just saying "why do you care so much about this?". Or even just by staring blankly at him, refusing to act like this is important. Her participation in his madness was normalizing his behavior. It would have been better if he had just been ranting to a rubber duck. At least then he might have realized how absolutely absurd he was acting.

So I don't want a personal assistant. I want an interlocutor, someone to talk to all day who will remember what we talked about tomorrow. I want a social milieu in which to store my external memory. But not a subservient lackey who never asks questions.

I want a rubber duck that asks questions. They don't have to be particularly advanced questions: just asking "what does that word mean" is enough sometimes to get me talking at length about things I didn't even realize I knew. A good interviewer listens a lot and questions a little, just enough to keep the interviewee talking. The interviewer just needs a nose for the surprising: if you find the least predictable part of a statement, ask a question about it, and repeat, you go in the direction of news, away from the direction of cliche. 

So, Berduck. A rubber duck that isn't very smart and asks a lot of questions. A chat-based interface to a knowledge-web like Obsidian or Roam, an active agent that interviews you and takes notes on your brilliant ideas. 

Berduck doesn't talk down to you, like Clippy, trying to help you with your tasks that you already know how to do. It doesn't nag you about your appointments and schedules. It just wants to know more about you: your beliefs, your life, your friends, your plans, your dreams, your skills. "What does "PyTorch" mean?", "Who is Tony you are meeting with?", "What projects are you working on today?"

And it helps you extract that later: "Berduck, what do you know about my aunt Lorraine?", or "Berduck, have I ever told you about the Hugging Face Transformers package for Python?". 

*They say you learn things best when you have to explain them to someone else. Learn what you're all about, with Berduck: the friendly AI apprentice.*

---

Okay, enough marketing fluff. How is this going to actually work?

Well, as much as I'd like to integrate directly with Roam or Obsidian or even org-roam, they're all very much in-development and their APIs aren't fully accessible. And even if I did get access to them, building into their specific visual interfaces isn't necessary for Berduck to be effective. 

Instead I'll follow the Unix philosophy and make a separate tool that communicates through text streams and files. Specifically, for now I can keep Berduck dialogues as atomic Markdown files in a folder, and use Obsidian to link the different files together and explore them later.

I keep an eye on the Python natural language processing scene, and I'm pretty confident that [Rasa](rasa.com) is the best open platform for building chatbots. It takes care of a lot of the NLP stuff under the hood, but allows me to connect any arbitrary Python code in through "custom actions". In the case of Berduck, most of the conversational structure can be operated by Rasa: it will generalize between "Hello Berduck" and "Hey" and "Good morning", on the one hand, and "I would like to kill my boss" or "Did I tell you I killed my boss?" on the other. Or whichever intents you program it to expect.

A Rasa chatbot lives in a **domain**: a world, with inputs and outputs and gradients between them. It receives *intents* from the user. These intents represent different types of message it can expect a user to send. It can extract *entities* from these intents. It can map these entities to *slots*, an internal dictionary of things it's keeping track of. The bot can do one or two things when it receives an intent: utter a *response*, or take an *action*.

**STARTED USING "WE" HERE v**

In the case of Berduck, we want to focus on the *action* of recording the notes, and the *response* of asking a good question. 

Taking notes will consist of making a Markdown file for each unit of thought, with a title and a body. The body could be a single message, or a series of messages demarcated by something like a full stop. The title could be a keyterm extracted from the phrase; it could be an entity or slot reference with a defintion in the body; it could be a representation of the bot question that triggered the response. It needs to be unique, so perhaps timestamped. Is this how Luhmann originally did it? Anyway, the user can manipulate all this afterward when exploring the database, so it's not mission-critical to get it on the first try. 

The responses will be more complex. The key to asking good questions is to look for the surprising part of a sentence. I don't know a way to easily implement that right now, though in time I think I could learn to use embeddings from various pre-trained Transformer models. Right now there's a way to do similarity in spaCy, which I do know how to use, so maybe that can help. I'll plan to use spaCy for question generation anyway, becuase I am more familiar with it than with Rasa's underlying NLP stuff. I'll use Rasa for the other part of responding, which is:

Boilerplate. Complex question generation can be the purview of a special spaCy module, but the basic function of an interviewer can be simulated with some hard-coded questions. Grabbing entities and putting them into "Who is" and "What is" formats would work pretty well. Record those with the entity as title, appending the definition in case there's anything already there.

Simple questions, then, some hardcode and some extracted programmatically and possibly some from more complex methods. But in most cases, speed of response will be more meaningful to the user, who's mostly just trying to think out loud and doesn't want to be dragged down by a slow interlocutor. 

Another method of responding, in the tradition of active listening, could be: emoji. Send an emoji or two in response to messages that aren't caught by any of the other modules, so that if it's not asking questions it's at least reacting quickly to the inputs of the user. This probably has some huge dangerous fail modes, but for a prototype those may in fact be instructive. I think this has been done before -- who did that? DeepMoji, it seems, but it's in python 2.7 and old so I'll have to train my own classifier if i want this function. In the past I did train a classifier that would measure emotional valence -- maybe I can slot this in, with some emoji hand-mapped to the different zones that a statement might be mapped to.

Didn't I do that? I sure thought I had that model around here somewhere... 

Ways to ask about a random noun:
What is blank?
When you say blank, what do you mean?
Blank is what again?
Blank?
What do you mean, blank?
What blank?
What is blank in this context?
What does blank mean?
I don't know blank, can you elaborate?

Okay, I don't have the previous sentiment classifier around right now, but I do have an emoji dataset now and a way of finding sentiment in text through spacytextblob. And I found pytextrank so I can do quick keyword extraction from texts also. I think it's time to implement these two modules, then insert them into a Rasa bot to test the workflow, and finally set up the custom action for recording to Markdown. Then do a bunch of chats with it to build up a testable knowledge base. 