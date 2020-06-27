---
id: 381
title: 'Python&#8217;s zip() and dict() combo will love you right'
date: 2017-12-19T22:14:20-05:00
author: admin
layout: revision
guid: http://pythoninthewyld.com/2017/12/31/216-revision-v1/
permalink: /2017/12/31/216-revision-v1/
---
###### <span style="font-size: 14pt;">Paired data in Python is user-friendly and efficient, and I find myself using it all the time. Sometimes in the course of a workflow, we end up with with multiple simple lists of information that would be easier managed as paired data. If you find yourself in this situation, there are two simple tools that work in a really intuitive way to “zip” the lists together such that the first item of list A is paired with the first item of list B. If the lists were [“Bruce”, “Peter”] and [“Wayne”, “Paker”] the out put would match them to {“Bruce”:”Wayne”, “Peter”:”Parker”}.</span>

###### *note that Python will also accept {“Miles”:”Morales”} 🙂

**<div tabindex="-1" id="notebook" class="border-box-sizing">
  <div class="container" id="notebook-container">
    <div class="cell border-box-sizing text_cell rendered">
      <div class="prompt input_prompt">
      </div>
      
      <div class="inner_cell">
        <div class="text_cell_render border-box-sizing rendered_html">
          <h1 id="The-peanut-butter-and-jelly-of-paired-data:-zip()-and-dict()">
            The peanut-butter and jelly of paired data: zip() and dict()<a class="anchor-link" href="#The-peanut-butter-and-jelly-of-paired-data:-zip()-and-dict()">&#182;</a>
          </h1>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing text_cell rendered">
      <div class="prompt input_prompt">
      </div>
      
      <div class="inner_cell">
        <div class="text_cell_render border-box-sizing rendered_html">
          <p>
            Let's say we have two lists of names and want to store them as paired data in a dictionary. All we need to do to get a nice, tidy, dictionary out of it is the following (I'll show the running code and then go through it afterwards with a more realistic use case).
          </p>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing code_cell rendered">
      <div class="input">
        <div class="prompt input_prompt">
          In&nbsp;[2]:
        </div>
        
        <div class="inner_cell">
          <div class="input_area">
            <div class=" highlight hl-ipython3">
              <pre><span></span><span class="c1"># here are our two lists</span>
<span class="n">first</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"A"</span><span class="p">,</span><span class="s2">"B"</span><span class="p">,</span><span class="s2">"C"</span><span class="p">]</span>
<span class="n">second</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"1"</span><span class="p">,</span><span class="s2">"2"</span><span class="p">,</span><span class="s2">"3"</span><span class="p">]</span>

<span class="c1"># make a dict from the output of zipping the two iterables</span>
<span class="n">third</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="nb">zip</span><span class="p">(</span><span class="n">first</span><span class="p">,</span> <span class="n">second</span><span class="p">))</span>

<span class="c1"># iterate thorough and show we got what we were looking for</span>
<span class="k">for</span> <span class="n">item</span> <span class="ow">in</span> <span class="n">third</span><span class="p">:</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">item</span><span class="p">,</span> <span class="n">third</span><span class="p">[</span><span class="n">item</span><span class="p">])</span>
</pre>
            </div>
          </div>
        </div>
      </div>
      
      <div class="output_wrapper">
        <div class="output">
          <div class="output_area">
            <div class="prompt">
            </div>
            
            <div class="output_subarea output_stream output_stdout output_text">
              <pre>A 1
B 2
C 3
</pre>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing text_cell rendered">
      <div class="prompt input_prompt">
      </div>
      
      <div class="inner_cell">
        <div class="text_cell_render border-box-sizing rendered_html">
          <p>
            That's it. What's going on here? Let's take a closer look.
          </p>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing text_cell rendered">
      <div class="prompt input_prompt">
      </div>
      
      <div class="inner_cell">
        <div class="text_cell_render border-box-sizing rendered_html">
          <p>
            Python has a "zip" function that will return a zip object of tuples (don't worry if that sounds weird; it just means it is a zip class and has our data stored in a way such that it can't be modified). It takes iteratable objects like lists as arguments, in our case, just two. It goes through the lists in order, and "zips" them together, first item to first item, second to second, and so on.
          </p>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing code_cell rendered">
      <div class="input">
        <div class="prompt input_prompt">
          In&nbsp;[5]:
        </div>
        
        <div class="inner_cell">
          <div class="input_area">
            <div class=" highlight hl-ipython3">
              <pre><span></span><span class="c1"># here are our to lists</span>
<span class="n">first</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"Christopher"</span><span class="p">,</span><span class="s2">"Jo-Vaughn"</span><span class="p">,</span><span class="s2">"Sean"</span><span class="p">,</span><span class="s2">"Sir Robert Bryson"</span><span class="p">]</span>
<span class="n">last</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"Wallace"</span><span class="p">,</span><span class="s2">"Scott"</span><span class="p">,</span><span class="s2">"Carter"</span><span class="p">,</span><span class="s2">"Hall II"</span><span class="p">]</span>

<span class="c1"># call the zip function that takes iteratable structure </span>
<span class="n">names</span> <span class="o">=</span> <span class="nb">zip</span><span class="p">(</span><span class="n">first</span><span class="p">,</span> <span class="n">last</span><span class="p">)</span>

<span class="c1"># if we print it out, we see we have a zip object and memory address</span>
<span class="nb">print</span><span class="p">(</span><span class="n">names</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="nb">type</span><span class="p">(</span><span class="n">names</span><span class="p">))</span>
</pre>
            </div>
          </div>
        </div>
      </div>
      
      <div class="output_wrapper">
        <div class="output">
          <div class="output_area">
            <div class="prompt">
            </div>
            
            <div class="output_subarea output_stream output_stdout output_text">
              <pre>&lt;zip object at 0x7f63fc990b08&gt;
&lt;class &#39;zip&#39;&gt;
</pre>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing text_cell rendered">
      <div class="prompt input_prompt">
      </div>
      
      <div class="inner_cell">
        <div class="text_cell_render border-box-sizing rendered_html">
          <p>
            While they are in the object, we can't use them as paired data directly. Fortunately, the dict() function will take a list of tuples and return a dictionary.
          </p>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing code_cell rendered">
      <div class="input">
        <div class="prompt input_prompt">
          In&nbsp;[4]:
        </div>
        
        <div class="inner_cell">
          <div class="input_area">
            <div class=" highlight hl-ipython3">
              <pre><span></span><span class="c1"># use the dict function on the zip object</span>
<span class="n">names</span> <span class="o">=</span> <span class="nb">dict</span><span class="p">(</span><span class="n">names</span><span class="p">)</span>

<span class="c1"># print out the evidence</span>
<span class="k">for</span> <span class="n">item</span> <span class="ow">in</span> <span class="n">names</span><span class="p">:</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">item</span><span class="p">,</span> <span class="n">names</span><span class="p">[</span><span class="n">item</span><span class="p">])</span>
</pre>
            </div>
          </div>
        </div>
      </div>
      
      <div class="output_wrapper">
        <div class="output">
          <div class="output_area">
            <div class="prompt">
            </div>
            
            <div class="output_subarea output_stream output_stdout output_text">
              <pre>Christopher Wallace
Jo-Vaughn Scott
Sean Carter
Sir Robert Bryson Hall II
</pre>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <div class="cell border-box-sizing text_cell rendered">
      <div class="prompt input_prompt">
      </div>
      
      <div class="inner_cell">
        <div class="text_cell_render border-box-sizing rendered_html">
          <p>
            Note that this will also work with ints and floats. That's all there is to it. Thanks for reading.
          </p>
        </div>
      </div>
    </div>
  </div>
</div>**

&nbsp;