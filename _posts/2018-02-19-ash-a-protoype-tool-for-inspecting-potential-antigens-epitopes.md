---
id: 657
title: 'ASH: A Protoype Tool For Inspecting Potential Antigens/Epitopes'
date: 2018-02-19T19:16:04-05:00
author: admin
layout: post
guid: http://pythoninthewyld.com/?p=657
permalink: /2018/02/19/ash-a-protoype-tool-for-inspecting-potential-antigens-epitopes/
total_sidebar_layout:
  - right_sidebar
categories:
  - Uncategorized
---
Hello!

I have been interested in antigens/epitopes for some time now, and this is my prototype of a tool to help and informed user take a closer look at targets of interest for projects that involve them. It works using a simple scale that compares kmers on a residue to residue basis, and scores them for distinctness based on the presence of hydrophilic or hydrophobic residues and residues of structural complexity, which are widely known factors in immonogencity. Still, in the name of diligence, sources that informed these decisions can be seen below at the bottom of the post. The github to the project is [here](https://github.com/sweeney-th/Portfolio/tree/master/ASH) . There is a [walkthrough](https://github.com/sweeney-th/Portfolio/blob/master/ASH/documentation/ASH_demo.ipynb), a readme, and a test package if you want to give it a spin. I'm actively working on this and thus very open to constructive feedback and am happy to answer questions!

http://www.abcam.com/protocols/antigens

http://www.abcam.com/protocols/tips-for-designing-a-good-peptide-immunogen

https://www.genscript.com/peptide\_design\_guideline.html

<blockquote class="wp-embedded-content" data-secret="ARRsI3a4hm">
  <p>
    <a href="https://mainebiotechnology.com/antigen-design-considering-target/">Antigen Design: Considering the Target</a>
  </p>
</blockquote>