---
layout: post
title: "GSoC 2018, untold stories"
categories: ["Thoughts"]
excerpt_separator: <!--more-->
---

Hello everyone!

In this post, I'm going to tell you how I got accepted to GSoC 2018 as a student developer at [CGAL](https://www.cgal.org/), and how I passed all of the three evaluations.

As many of you may have known, [Google Summer of Code](https://summerofcode.withgoogle.com/) is an annual event that provides opportunities for students around the world to work with open-source companies/organizations. Students are also paid a decent amount of money, based on the location of their university.

I first heard of GSoC from a teacher in high school. It's normally held after its brother program, known as [Google Code-in](https://codein.withgoogle.com/). Around January, I started checking calendar and waited until mid February when the official list of partner organizations was published. At this point, I would "lurk" around the site to find some interesting project, yet it must suit my ability. I have 2-year experience with C++, thanks to the training for the National Olympiad, so I targeted a few companies. However, most of the work I'd done was theoretical work, not designing and configuring apps, hence CGAL was a good choice. It was managed by more than 8 institutions, all of which are very advanced in the field of technology.

<!--more-->

I headed to CGAL's idea list and choose a project that might suit me. I was actually stunned by the amount of jargons there! I was about to give up because I had to search Google literally everything to understand what were the requirements of each project. I was drawn to a project called "Generalized Shape Detection". I thought it's a cool thing to try. It sounded like Machine Learning related, of which I completely had zero knowledge. Anyway, I decided to drop my mentor an email expressing my willingness to follow this project. I received the response after nearly 24 hours. He sent me a link to get started, it leaded me to a package called "Point Set Shape Detection". This package was developed long ago, and it used RANSAC algorithm. As per his request, I had to research about this package, install it, run it, and answer his questions.

Yup, I had to research A LOT. I eventually set up the package and answered his questions successfully. We had an interview and he accepted to help me working on my proposal. To my knowledge, most of companies had their own ways to communicate with _potential_ students. But in the end, you had to submit a document called "proposal", describing how you understand the work that you must do, and answer some questions asked by the company. Many organizations _do not_ accept your proposals if you haven't spoken to them about your interests beforehand. So, in order to leave a good impression and increase the chance to be accepted, you are strongly recommended to speak to the mentors about your intention so that they are aware of your abilities.

After I received the official acceptance letter from Google, I started working with CGAL in early May. Unfortunately I couldn't invest all my time on GSoC because it was still school time where I studied. I tried to speak to the head office of my year, but got denied. I was very angry because they were making difficulties for me to take this golden opportunity to develop my careers. I wrote a letter to the vice president of the university, describing my circumstances and my expectation to be absent from school without being banned from the test. It's a weird university that has limited vision, I must say. But anyway, the VP met me in person and signed me a permit, I really appreciated.

The paper was done. I got back to work. I stayed up late at night to work and slept through the morning, that's my normal behavior. I had to design a plan for the project first, and when it's done, I would start working on each module. The progress was updated daily on a private blog of CGAL.

At first, I struggled a lot, since I didn't know template metaprogramming very well. I spent days looking into it, that's the origin of the blog post ["Template Metaprogramming, A Compendium"]({{ site.baseurl }}{% post_url 2018-05-09-template-programming %}). Oftentimes I was stuck in a problem or a concept for so long that I thought of giving up. But mannn, this project would be a _huge_ bright spot on the Resume, giving up would be a waste! Over time, I gained more knowledge of the language and the package itself. Based on the Region Growing algorithm built in the package "Point Set Shape Detection" mentioned earlier, I had to generalize it to work with any types of elements and rules. Not only did I accomplish the task, I also implemented it in a cleaner way than the old version. I remember when the mentor sent me the old version and asked me to re-implement this in a general way, I was unpleased. I felt like I was copying and pasting, so I talked to him that I wanted to have something "original", that I hoped him to be patient with my redesigned algorithm. He said he just wanted to make my life easier but he liked my spirit so he would stick to my version and make it work. That's the best negotiation I've ever made in my life.

Well, although it's just redesigning, but just a small improvement also made me feel that I had truly created something new, not just copy-paste-adapt. I wouldn't be able to sleep if I was the author of the package whose implementation is completely migrated from the other package. There must be at least an improvement, showing the progress of working. Thankfully, the algorithm worked out pretty well! Nothing is more pleasing than seeing the output visualized.

By the end of the program, I compiled the documentation of the package and generated a report on the achievements and obstacles I encountered. I also had to submit a link to the work I've done to Google, which in this case was the commit log, because the branch I was working on would be deleted after my work was integrated to the library.

I think I have learned a lot, not only about template metaprogramming, 3D computing, but also some communication skills to work with colleagues and supervisors in my future jobs. With that said, I will certainly join GSoC next year to earn some money, study some more, and pay for tuition. I still do not know if I should keep following CGAL, but it's one of a few organizations that focus on researching rather than designing (and I do like researching!!). Anyway, in near future, I had to find other kinds of work to occupy myself. One of them is continuing this package by writing test suites before it's reviewed and integrated to CGAL. The second thing I'm considering is to find a part-time job that I can work online during the school time. I want to earn some money to pay the rent, the food, and buy myself some tech devices (I'm trying my best to be financially independent from family! I was invited to an interview next week on being a Chegg tutor. Hope I will be accepted and earn a good amount on this platform.