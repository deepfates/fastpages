---
keywords: fastai
title: Archive my tweets
badges: true
categories: [code, twitter]
nb_path: _notebooks/2021-08-13-tweet-archive.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2021-08-13-tweet-archive.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>I want to extract all the tweets I've ever written and convert them to small markdown files so they show up as "posts" on this website.</p>
<p>Posts are organized by date, in the traditional blogging format. But so are tweets, kind of? They're listed chronologically anyway. Maybe I could make one post for each day, and then have all the tweets listed on that page. Each one could have its tweet ID as a header, thus having an internal link. Tweets can link to the tweets that precede them, and maybe even backlink to tweets that follow.</p>
<p>It's not quite block references, but as a way of keeping my second brain under my ownership it should work. And this way if anyone wants to cancel me they'll have a convenient search box and permalinks for it. Even if my account gets deleted, my bad takes can stay up.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">pathlib</span> <span class="kn">import</span> <span class="n">Path</span>
<span class="n">out_dir</span> <span class="o">=</span> <span class="n">Path</span><span class="p">(</span><span class="s1">&#39;../_posts/tweets/&#39;</span><span class="p">)</span>
<span class="n">posts</span> <span class="o">=</span> <span class="p">[</span><span class="n">o</span><span class="o">.</span><span class="n">name</span> <span class="k">for</span> <span class="n">o</span> <span class="ow">in</span> <span class="n">out_dir</span><span class="o">.</span><span class="n">iterdir</span><span class="p">()]</span>

<span class="n">last_date</span> <span class="o">=</span> <span class="nb">sorted</span><span class="p">(</span><span class="n">posts</span><span class="p">)[</span><span class="o">-</span><span class="mi">2</span><span class="p">][:</span><span class="mi">10</span><span class="p">]</span>

<span class="n">last_date</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;2021-08-31&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">twint</span>
<span class="kn">import</span> <span class="nn">nest_asyncio</span>
<span class="n">nest_asyncio</span><span class="o">.</span><span class="n">apply</span><span class="p">()</span>


<span class="n">c</span> <span class="o">=</span> <span class="n">twint</span><span class="o">.</span><span class="n">Config</span><span class="p">()</span>
<span class="n">c</span><span class="o">.</span><span class="n">Username</span> <span class="o">=</span> <span class="s1">&#39;deepfates&#39;</span>
<span class="n">tweets</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">c</span><span class="o">.</span><span class="n">Store_object</span> <span class="o">=</span> <span class="kc">True</span>
<span class="n">c</span><span class="o">.</span><span class="n">Store_object_tweets_list</span> <span class="o">=</span> <span class="n">tweets</span>
<span class="n">c</span><span class="o">.</span><span class="n">Since</span> <span class="o">=</span> <span class="n">last_date</span>
<span class="n">c</span><span class="o">.</span><span class="n">Hide_output</span> <span class="o">=</span> <span class="kc">True</span>
<span class="n">twint</span><span class="o">.</span><span class="n">run</span><span class="o">.</span><span class="n">Profile</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">len</span><span class="p">(</span><span class="n">tweets</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">t</span> <span class="o">=</span> <span class="n">tweets</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">t</span><span class="o">.</span><span class="n">conversation_id</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">datestamp</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">datetime</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">id</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">likes_count</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">link</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">mentions</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">photos</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">quote_url</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">replies_count</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">reply_to</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">retweet</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">retweet_date</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">retweet_id</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">retweets_count</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">source</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">thumbnail</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">timestamp</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">timezone</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">tweet</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">urls</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">user_id</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">user_id_str</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">user_rt</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">user_rt_id</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">username</span><span class="p">,</span> <span class="n">t</span><span class="o">.</span><span class="n">video</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">requests</span>
<span class="kn">import</span> <span class="nn">shutil</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">dl_image</span><span class="p">(</span><span class="n">url</span><span class="p">):</span>
    <span class="n">filename</span> <span class="o">=</span> <span class="s1">&#39;../images/&#39;</span> <span class="o">+</span> <span class="n">url</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s1">&#39;/&#39;</span><span class="p">)[</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
    <span class="n">r</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">url</span><span class="p">,</span> <span class="n">stream</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">r</span><span class="o">.</span><span class="n">status_code</span> <span class="o">==</span> <span class="mi">200</span><span class="p">:</span>
        <span class="n">r</span><span class="o">.</span><span class="n">raw</span><span class="o">.</span><span class="n">decode_content</span> <span class="o">=</span> <span class="kc">True</span>
        <span class="k">with</span> <span class="nb">open</span><span class="p">(</span><span class="n">filename</span><span class="p">,</span><span class="s1">&#39;wb&#39;</span><span class="p">)</span> <span class="k">as</span> <span class="n">f</span><span class="p">:</span>
            <span class="n">shutil</span><span class="o">.</span><span class="n">copyfileobj</span><span class="p">(</span><span class="n">r</span><span class="o">.</span><span class="n">raw</span><span class="p">,</span> <span class="n">f</span><span class="p">)</span>
        <span class="k">return</span><span class="p">(</span><span class="n">filename</span><span class="p">)</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="k">return</span><span class="p">(</span><span class="kc">None</span><span class="p">)</span>
    
<span class="c1"># hacky thing uses [1:] to shave the first &#39;.&#39; off the filename</span>
<span class="k">def</span> <span class="nf">image_template</span><span class="p">(</span><span class="n">filename</span><span class="p">):</span>
    <span class="k">return</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;![image from twitter](/</span><span class="si">{</span><span class="n">filename</span><span class="p">[</span><span class="mi">1</span><span class="p">:]</span><span class="si">}</span><span class="s1">)</span><span class="se">\n</span><span class="s1">&#39;</span><span class="p">)</span>

    
<span class="k">def</span> <span class="nf">get_tweet</span><span class="p">(</span><span class="n">t</span><span class="p">):</span>
    <span class="k">if</span> <span class="n">t</span><span class="o">.</span><span class="n">photos</span> <span class="o">==</span> <span class="p">[]:</span>
        <span class="n">img_md</span> <span class="o">=</span> <span class="s1">&#39;&#39;</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="n">img_list</span> <span class="o">=</span> <span class="p">[</span><span class="n">dl_image</span><span class="p">(</span><span class="n">url</span><span class="p">)</span> <span class="k">for</span> <span class="n">url</span> <span class="ow">in</span> <span class="n">t</span><span class="o">.</span><span class="n">photos</span><span class="p">]</span>
        <span class="n">img_md</span> <span class="o">=</span> <span class="s1">&#39;</span><span class="se">\n</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">join</span><span class="p">([</span><span class="n">image_template</span><span class="p">(</span><span class="n">o</span><span class="p">)</span> <span class="k">for</span> <span class="n">o</span> <span class="ow">in</span> <span class="n">img_list</span><span class="p">])</span>

    <span class="k">return</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;&#39;&#39;</span>
<span class="s1">#### &lt;a href = &quot;</span><span class="si">{</span><span class="n">t</span><span class="o">.</span><span class="n">link</span><span class="si">}</span><span class="s1">&quot;&gt;*</span><span class="si">{</span><span class="n">t</span><span class="o">.</span><span class="n">timestamp</span><span class="si">}</span><span class="s1">*&lt;/a&gt;</span>

<span class="s1">&lt;font size=&quot;5&quot;&gt;</span><span class="si">{</span><span class="n">t</span><span class="o">.</span><span class="n">tweet</span><span class="si">}</span><span class="s1">&lt;/font&gt;</span>

<span class="si">{</span><span class="n">img_md</span><span class="si">}</span><span class="s1"></span>

<span class="s1">🗨️ </span><span class="si">{</span><span class="n">t</span><span class="o">.</span><span class="n">replies_count</span><span class="si">}</span><span class="s1"> ♺ </span><span class="si">{</span><span class="n">t</span><span class="o">.</span><span class="n">retweets_count</span><span class="si">}</span><span class="s1"> 🤍  </span><span class="si">{</span><span class="n">t</span><span class="o">.</span><span class="n">likes_count</span><span class="si">}</span><span class="s1">   </span>

<span class="s1">---</span>
<span class="s1">    &#39;&#39;&#39;</span><span class="p">)</span>

<span class="k">def</span> <span class="nf">get_md</span><span class="p">(</span><span class="n">tweets</span><span class="p">,</span> <span class="n">date</span><span class="p">):</span>
    <span class="n">tweets_text</span> <span class="o">=</span> <span class="s1">&#39;&#39;</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">t</span> <span class="k">for</span> <span class="n">t</span> <span class="ow">in</span> <span class="n">tweets</span><span class="p">)</span>
    <span class="k">return</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;&#39;&#39;---</span>
<span class="s1">title: deepfates log </span><span class="si">{</span><span class="n">date</span><span class="si">}</span><span class="s1"></span>
<span class="s1">layout: post</span>
<span class="s1">toc: true</span>
<span class="s1">comments: false</span>
<span class="s1">search_exclude: false</span>
<span class="s1">categories: [tweets]</span>
<span class="s1">---</span>

<span class="si">{</span><span class="n">tweets_text</span><span class="si">}</span><span class="s1"></span>
<span class="s1">            &#39;&#39;&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">IPython.display</span> <span class="kn">import</span> <span class="n">Markdown</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">yesterday</span> <span class="o">=</span> <span class="n">t</span><span class="o">.</span><span class="n">datestamp</span>
<span class="n">y_tweets</span> <span class="o">=</span> <span class="p">[</span><span class="n">tw</span> <span class="k">for</span> <span class="n">tw</span> <span class="ow">in</span> <span class="n">tweets</span> <span class="k">if</span> <span class="n">tw</span><span class="o">.</span><span class="n">datestamp</span> <span class="o">==</span> <span class="n">yesterday</span><span class="p">]</span>
<span class="nb">len</span><span class="p">(</span><span class="n">y_tweets</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">Markdown</span><span class="p">(</span><span class="n">get_tweet</span><span class="p">([</span><span class="n">tw</span> <span class="k">for</span> <span class="n">tw</span> <span class="ow">in</span> <span class="n">tweets</span> <span class="k">if</span> <span class="n">tw</span><span class="o">.</span><span class="n">datestamp</span> <span class="o">==</span> <span class="n">yesterday</span><span class="p">][</span><span class="o">-</span><span class="mi">1</span><span class="p">]))</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y_sorted</span> <span class="o">=</span> <span class="nb">sorted</span><span class="p">(</span><span class="n">y_tweets</span><span class="p">,</span> <span class="n">key</span><span class="o">=</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">x</span><span class="o">.</span><span class="n">datetime</span><span class="p">)</span>
<span class="c1"># [tweet.tweet for tweet in y_sorted]</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Too many replies! Let's limit to just mine for now</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y_md</span> <span class="o">=</span> <span class="n">get_md</span><span class="p">([</span><span class="n">get_tweet</span><span class="p">(</span><span class="n">t</span><span class="p">)</span> <span class="k">for</span> <span class="n">t</span> <span class="ow">in</span> <span class="n">y_sorted</span> <span class="k">if</span> <span class="s2">&quot;@&quot;</span> <span class="ow">not</span> <span class="ow">in</span> <span class="n">t</span><span class="o">.</span><span class="n">tweet</span><span class="p">],</span> <span class="n">yesterday</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">with</span> <span class="nb">open</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;../_posts/tweets/</span><span class="si">{</span><span class="n">yesterday</span><span class="si">}</span><span class="s1">-tweets.md&#39;</span><span class="p">,</span> <span class="s1">&#39;w&#39;</span><span class="p">)</span> <span class="k">as</span> <span class="n">f</span><span class="p">:</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">y_md</span><span class="p">,</span> <span class="n">file</span><span class="o">=</span><span class="n">f</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Okay, that'll do for now. It prints a chronological page of tweets for each day. Linking, video and oter people's tweets will have to come later.</p>
<p>I'll wrap that behavior in a function and pass it my tweets and a set of dates when i have tweeted.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">write_day_page</span><span class="p">(</span><span class="n">day</span><span class="p">,</span> <span class="n">tweets</span><span class="p">):</span>
    <span class="n">tweets</span> <span class="o">=</span> <span class="p">[</span><span class="n">tw</span> <span class="k">for</span> <span class="n">tw</span> <span class="ow">in</span> <span class="n">tweets</span> <span class="k">if</span> <span class="n">tw</span><span class="o">.</span><span class="n">datestamp</span> <span class="o">==</span> <span class="n">day</span><span class="p">]</span>
    <span class="n">sorted_tweets</span> <span class="o">=</span> <span class="nb">sorted</span><span class="p">(</span><span class="n">tweets</span><span class="p">,</span> <span class="n">key</span><span class="o">=</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">x</span><span class="o">.</span><span class="n">datetime</span><span class="p">)</span>
    <span class="n">md</span> <span class="o">=</span> <span class="n">get_md</span><span class="p">([</span><span class="n">get_tweet</span><span class="p">(</span><span class="n">t</span><span class="p">)</span> <span class="k">for</span> <span class="n">t</span> <span class="ow">in</span> <span class="n">sorted_tweets</span><span class="p">],</span> <span class="n">day</span><span class="p">)</span>
    <span class="k">with</span> <span class="nb">open</span><span class="p">(</span><span class="sa">f</span><span class="s1">&#39;../_posts/tweets/</span><span class="si">{</span><span class="n">day</span><span class="si">}</span><span class="s1">-tweets.md&#39;</span><span class="p">,</span> <span class="s1">&#39;w&#39;</span><span class="p">)</span> <span class="k">as</span> <span class="n">f</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">md</span><span class="p">,</span> <span class="n">file</span><span class="o">=</span><span class="n">f</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">self_tweets</span> <span class="o">=</span> <span class="p">[</span><span class="n">t</span> <span class="k">for</span> <span class="n">t</span> <span class="ow">in</span> <span class="n">tweets</span> <span class="k">if</span> <span class="s2">&quot;@&quot;</span> <span class="ow">not</span> <span class="ow">in</span> <span class="n">t</span><span class="o">.</span><span class="n">tweet</span><span class="p">]</span>

<span class="nb">len</span><span class="p">(</span><span class="n">self_tweets</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">days</span> <span class="o">=</span> <span class="nb">set</span><span class="p">([</span><span class="n">t</span><span class="o">.</span><span class="n">datestamp</span> <span class="k">for</span> <span class="n">t</span> <span class="ow">in</span> <span class="n">self_tweets</span><span class="p">])</span>

<span class="nb">len</span><span class="p">(</span><span class="n">days</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">tqdm</span> <span class="kn">import</span> <span class="n">tqdm</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">for</span> <span class="n">day</span> <span class="ow">in</span> <span class="n">tqdm</span><span class="p">(</span><span class="n">days</span><span class="p">):</span>
    <span class="n">write_day_page</span><span class="p">(</span><span class="n">day</span><span class="p">,</span> <span class="n">self_tweets</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stderr output_text">
<pre>100%|██████████| 11/11 [00:09&lt;00:00,  1.10it/s]
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>I would also liek to do analysis to see how often I tweet. And make a big list of links. Maybe next time.</p>
<p>For now you can find these secret tweet archives by searching in the <a href="/explore">Explore</a> page</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">days</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>{&#39;2021-08-22&#39;,
 &#39;2021-08-23&#39;,
 &#39;2021-08-24&#39;,
 &#39;2021-08-25&#39;,
 &#39;2021-08-26&#39;,
 &#39;2021-08-27&#39;,
 &#39;2021-08-28&#39;,
 &#39;2021-08-29&#39;,
 &#39;2021-08-30&#39;,
 &#39;2021-08-31&#39;,
 &#39;2021-09-01&#39;}</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

</div>
 

<script type="application/vnd.jupyter.widget-state+json">
{"state": {}, "version_major": 2, "version_minor": 0}
</script>
