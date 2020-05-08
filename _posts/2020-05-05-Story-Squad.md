---
layout: post
title: Story Squad
subtitle: My contributions to this awesome project.
tags: [projects]
comments: true
---

## Story Squad is an engaging competitive storytelling platform to get children off Fortnight and back into their imagination.

Story squad is an app designed to reduce a user's screen time. Strange? Maybe. Effective? I'd like to think so. The core gameplay loop for Story Squad is as follows: 

>1) Read a story prompt.
>
>2) Use your imagination along with the classic pen and paper combination to come up with a short story AND an illustration.
>
>3) Submit your creations to be paired with another person.
>
>4) Divvy points amongst your team's submissions as a wager.
>
>5) Have your submissions judged by a third party.
>
>6) Win the combined points for each submission judged in your favor.
>
>7) Wait for next week to do it again!

There are some areas in this loop in which Data Science could prove useful, some more obvious than others. If the user is submitting a handwritten story, but we ultimately want the user to see typed text, we'll need some sort of OCR model. If we are pairing these kids up across multiple age groups, how should we do that? We could have a human read everyone and pair them up manually, or maybe we could find a model to that for us too...

## However obvious these applications may be, the real question is what should we do to launch?
### And this is probably the most impactful bit of knowledge I extracted during my time on the StorySquad project.

What did we absolutely need to have to get the product out the door? What do we build and what do we borrow? How do we convey this to the stake holder? The stakeholder absolutely had his ideals for how this app would function and how DS/ML would get him there. What he did not have was (much) data. So, I, with my team, set out to explore the little bit of data we had and what we could do to get a working version of this to launch, such that we could iterate on continuously. 

The pipeline we came up with was simple while setting ourselves (or any team) up for success in future iterations of this product. The first thing we did was to utilize Google Vision's OCR API to get the text lifted from the user submissions. This model proved to be the most accurate in our tests, and an accurate transcription is what we determined would be the thing we most needed to establish a solid foundation. After that, the transcriptions are analyzed to establish a multitude of metrics so we can better pair them. These metrics include the FLesch-Kincaid and coleman-liau reading scores (and others) along with some metrics our stakeholder was interested in tracking. The final step in our pipe is the actual pairing. For this, we chose to use hierarchical clustering. Unsupervised by design and forming from the bottom up to form a dendrogram, this model was perfect for our use case and went through several iterations to find the tight fit. Unfortunately, these pairings had to be done by hand, but our stakeholder was more than happy to pitch in for this part.

Ultimately this project presented some interesting problems that were fun to sort out and taught me a valuable lesson about how to make decisions that are in the best interest of the business, even if it means adjusting expectations on the role data science has to play. As well as how to lay a framework that can be easily and rapidly expand and iterate over. 


>Samanatha, Bhavani and Clay absolutely crushed [it]. The work they did on handwriting recognition allowed us to weaponize the time kids spend scribbling and drawing — this is the killer feature that makes Story Squad so impactful for kids: unlike YouTube, Fortnite, Snapchat et al, we don’t maximize for passive Time-on-Device, but for Time-in-Creative-Mode. Their work allows us to deliver this fundamental value prop to kids and parents. It’s a game changer in terms of product differentiation! Additionally, the team’s work on clustering matchups drives unprecedented value to users in terms of retention. The importance of their work in Labs 20 cannot be overstated! Story Squad would be a watered-down derivative idea without their contributions, and they have brought this cutting edge technological 'ooomph' that will makes an enormous difference in kids’ lives. Brava, bravo and thank you!!

-Story Squad Founder Graig Peterson

