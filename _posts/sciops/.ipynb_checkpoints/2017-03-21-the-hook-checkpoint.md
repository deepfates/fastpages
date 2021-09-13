---
title: "SCIOPS 01.01: The Hook"
description: "Hello, and welcome to the inaugural edition of SCIOPS (a cogsec newsletter)"
layout: post
toc: false
comments: false
search_exclude: false
hide: true
categories: [sciops]
---


 SCIOPS 01.01: The Hook
========================


![black and white pixels arranged in a deliberate fashion](data:image/png;base64,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)
  

Hello, and welcome to the inaugural edition of SCIOPS (a cogsec newsletter). Call me M. I'm your guide to the cyberpunk nightmare that we fondly refer to as the 21st Century.
  

  

If you're reading this letter, you probably feel worried about your brain. And you should! Your brain is in danger. There are hordes of hackers constantly trying to force their way into the squishy computer you keep behind your eyes.
  

  

These people are not villains. They are more or less like you and me: they wake up, absorb nutrients, go to work, and do the best they can to satisfy the ranking primates of their preferred corporate overlord. But regardless of their intentions, their duty is to exploit your mind. To change your behavior. To "increase engagement" or "grow brand loyalty" or "influence public perception".
  

  

Their aim is mind control. The answer is cogsec --
[cognitive security](https://ensorcel.org/what-is-cognitive-security/)
. Once you've locked your car, filtered your emails, and firewalled your computer, the next battleground is your mind. SCIOPS is an exploration of the tools of persuasion and how we can defend against them.
  

  

By now you may think I'm a tin-hat conspiracy theorist and that the best thing you can do for your brain is to avoid me. But consider this: for all the times that some wingnut said "unplug your TV, or the Man can
*watch you back,*
" how much did you believe them? What about the recent news that
[CIA actually hacked Smart TVs](https://wikileaks.com/ciav7p1/index.html#ANALYSIS)
to remotely record conversations? If you heard about that, did it change your belief about the credibility of wingnuts? If you didn't hear about that, why not? Who filters your newsfeed?
  

  

Cogsec is not the realm of illuminatoids and moon-hoaxers. It is the grey area between disinformation and fake news, between advertising and AI, between videogame addiction and the Matrix. To protect our minds, we need to see behind the scenes of the psycho-social-chemical-biological-electromagnetic-manipulation-industrial complex.
  

  

Let's try an experiment. I assure you, this is perfectly safe and has been replicated in laboratory conditions since the 1960s. If you're unwilling to experience a temporary psychological effect, you're probably paranoid enough already.
  

  

Look at the following images.
  

![red and black horizontal grid](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPAAAADwCAYAAAA+VemSAAAABmJLR0QA/wD/AP+gvaeTAAADrUlEQVR4nO3dsW3cQBBA0aGxUBXOVYY6cQXuRh2oEt+FVnKpU10VjuweNll84L0KJvnggMSA18z8GyDp2+kBgH0ChjABQ5iAIUzAELZeZ56nhwD2XP98RoIsKzSECRjCBAxhAoYwAUPY+ph5nB4C2HONz0iQZYWGMAFDmIAhTMAQJmAIW+8z99NDAHtcI0GYFRrCBAxhAoYwAUOYgCHsepu5nR4C2OMaCcKs0BAmYAgTMIQJGMIEDGHrOfN5eghgj2skCLNCQ5iAIUzAECZgCBMwhF0vM1+nhwD2uEaCMCs0hAkYwgQMYQKGMAFD2PIKGro8gSFMwBAmYAgTMIQJGMLWn5nn6SGAPY4ZIMwKDWEChjABQ5iAIUzAELZ+zDxODwHs8WsVCLNCQ5iAIUzAECZgCBMwhF0/Z26nhwD2uEaCMCs0hAkYwgQMYQKGMAFD2Po1cz89BLDHNRKEWaEhTMAQJmAIEzCECRjCru8zv08PAexxjQRhVmgIEzCECRjCBAxhAoaw9XfmeXoIYI9rJAizQkOYgCFMwBAmYAgTMIQ5ZoAwT2AIEzCECRjCBAxhAoaw9eqYAbIcM0CYFRrCBAxhAoYwAUOYgCFsfcw8Tg8B7HGNBGFWaAgTMIQJGMIEDGEChrD1PnM/PQSwxzUShFmhIUzAECZgCBMwhAkYwq63mdvpIYA9rpEgzAoNYQKGMAFDmIAhTMAQtp4zn6eHAPa4RoIwKzSECRjCBAxhAoYwAUPY9TLzdXoIYI9rJAizQkOYgCFMwBAmYAgTMIQtr6ChyxMYwgQMYQKGMAFDmIAhbP2ZeZ4eAtjjmAHCrNAQJmAIEzCECRjCBAxh68fM4/QQwB6/VoEwKzSECRjCBAxhAoYwAUPYus3cTw8B7HGNBGFWaAgTMIQJGMIEDGEChrD1y2ckyHKNBGFWaAgTMIQJGMIEDGEChrDr+8zv00MAe1wjQZgVGsIEDGEChjABQ5iAIWz9nXmeHgLY4xoJwqzQECZgCBMwhAkYwgQMYY4ZIMwTGMIEDGEChjABQ5iAIWy9OmaALMcMEGaFhjABQ5iAIUzAECZgCFsfM4/TQwB7XCNBmBUawgQMYQKGMAFDmIAhbL3P3E8PAexxjQRhVmgIEzCECRjCBAxhAoaw623mdnoIYI9rJAizQkOYgCFMwBAmYAgTMISt58zn6SGAPa6RIMwKDWEChjABQ5iAIUzAEHa9zHydHgLY4xoJwqzQECZgCBMwhAkYwgQMYf8BffZa9CN49/4AAAAASUVORK5CYII=)
![green and black horizontal grid](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPAAAADwCAYAAAA+VemSAAAABmJLR0QA/wD/AP+gvaeTAAADIElEQVR4nO3TsUmDYRSG0YuFU9g7hps4gds4gZskbZq01nEKq1gL3h8sHzjnI+ULfy48MzP3P3/Pc5v78j7muu7e57zuXua87r7msu4e57butvd5sHmd67p7O/jG08F/e5rLuvs+uKX7/34n9//P/R8GyBIwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIUzAECZgCBMwhAkYwgQMYQKGMAFDmIAhTMAQJmAIEzCECRjCBAxhAoYwAUOYgCFMwBAmYAgTMIQJGMIEDGEChjABQ5iAIewHevdf3Mz8XscAAAAASUVORK5CYII=)


 Really look at them. You don't have to focus on any particular spot, just gaze at the red one for a few seconds, and then the green one, and then the red one again. Look at them for as long as you can -- two minutes is the standard, but the longer you look the stronger the effect will be. Listen to a pop song or make some coffee or think about what you want for dinner. Keep looking. Don't skip ahead.
 


---



  


 Done? Are you sure you didn't skip ahead? Maybe a little longer.
   

  

 Okay, I believe you. If you stared back and forth at the images for long enough, you probably saw a hazy afterimage of the grid, or maybe even a hallucinatory knotwork of lines. That's perfectly normal, but it's not the point of the experiment. Scroll up to the top of this letter and look at the image there. What do you see?
   

  

 This is called the
 [McCollough effect](https://en.wikipedia.org/wiki/McCollough_effect) 
 . After "induction" (staring at the colored images), the black and white "test" image appears colored. The colors are inverted, meaning that you should see the horizontal lines tinted green and the verticals red (or pink). If you don't see it, you probably didn't stare at the induction images long enough. Try again.
   

  

 That's not the weirdest part. The difference between the McCollough effect (or ME, as it's called in the literature) and other optical illusions is longevity. With just two minutes of induction, the effect can last for over an hour. If you were to stare at the above images for 15 minutes, the effect could last for
 *over three months* 
 .
   

  

 All of which is just to make a point: when you expose your mind to internet, it can change you in ways that you can't predict and you can't shake off. This is the realm of cogsec: what do you want in your brain? Who do you trust to change your mind?
   

  

 That's it for this week. Thoughts, comments, questions? Responses to this email will be directly injected into my datastream.
   

  

 If you like this newsletter, forward it to a friend. Cogsec is a community effort.
 
  

  


 Thanks for letting me into your head,
   

 M
 

