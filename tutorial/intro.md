---
layout: default
title: Docs
next.url: /dreammaker_fx/tutorial/install
---

### Introduction

#### So how does this thing work?
Okay, here it is: you write simple code (or copy and paste it from the web) into a simple, free programming tool (Arduino).  And then a bunch of magic happens and suddenly you're playing through the coolest effect you've ever heard.  

In this case, the magic is a super powerful SHARC DSP chip that is a friendly companion of the little chip that runs our programs.  Unlike other Arduino based effects platforms, this one uses a DSP complete with FFT accelerators and other hardware that gives you at least an order (maybe two) of magnitude in processing performance over other Arduino-based effects platforms.  The DSP is where all of the audio processing is done.  But you don't need to know anything about that.  Just believe in magic.

#### Programming? Is this going to hurt?
It's going to be great.  Don't be a baby.  Do you know how to type?  Do you know how to follow basic examples?  Have you ever copied and pasted on a computer before?  You're going to be amazing.  

#### Programming? It's 2019, isn't there an easier way?
Programming allows us to do some cooler stuff that gets a bit tricky with some of the more graphical approaches out there.  And we're programming Arduino-style.  Yes, that's a thing.  Are you ready?  Yes you are.  Do not be afraid.  You are going to be great.

#### What is that word, Arduino?
Have you heard about **Arduino**?  If not, Arduino is this little circuit board created about 10 years ago which was designed to make programming hardware easy.  I won't bore you with the details but that shit got huge.  Now lots of people make Arduino-compatible boards (that use their simple programming software) and accessory boards with sensors and other batshit crazy stuff.

So rather than learning some arcane programming language and software tools, you're using one of the easiest programming tools ever created.  And there are plenty of resources for learning and getting help out there.  Here's a great set of tutorials to get started if you're new to Arduino in general: https://www.arduino.cc/en/Tutorial/HomePage?from=Main.Tutorials.

Okay, so buckle in and get ready to blow some minds.

{% if page.next.url %}
    [{{page.next.title}}]({{page.next.url}}) 
{% endif %}