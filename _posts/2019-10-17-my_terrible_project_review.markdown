---
layout: post
title:      "My Terrible Project Review 😲"
date:       2019-10-17 20:13:13 -0400
permalink:  my_terrible_project_review
---


I’d finished up my CLI project and was, frankly, pretty proud of myself! I’d found a relevant topical domain, learned how to work with the API, and utilized a ton of new gems and tools that resulted in something prettier and more functional than I could’ve imagined. I ticked off all the requirements boxes for passing the assessment, but also added a bunch more stuff just because I started having fun! See: [Greenfield is Exhilarating](https://wifelette.github.io/greenfield_is_exhilarating)!

[![My simple Project Walkthrough](https://i.ytimg.com/vi/C1D2AfdVoSo/hqdefault.jpg?)](https://youtu.be/C1D2AfdVoSo)

*My Project Walkthrough: so much CLI! It doesn't look like it (limited formatting here) but that image is a link to my Project Walkthrough video, if you feel so inclined.*


I came to my review slightly nervous, but excited to show off what I’d been working on. Previously, I’d submitted a blog post on my work, the GitHub repo URL, and a video of me walking through the gem. I had a solid big picture of what my gem did, as well as of *how* it did, and a ton of inline docs to help me over the parts I was worried I’d forget.

When my reviewer popped on the line, I was thrown off right out the gate by her confusion over what we were doing there. She first asked me excitedly how I was feeling about my final project, and when I looked confused, corrected to “Oh, this must be a Sinatra project!” —nope. Not a *fatal* start, but I felt kind’v deflated.

In the next few minutes it became clear that the reviewer had no idea who I was or what my project was about. I’m not sure if this is an oversight, or an intentional part of the way the reviews are structured. I had assumed that I was writing a blog post and recording my tool walkthrough so that my assessor would come prepared with questions and thoughts, but perhaps that was a faulty assumption.

That *too* shouldn’t have been a fatal step, but in a lot of ways it was. Remember earlier, when I said I’d used fun tools and gems to make things look nice and work well? My reviewer complemented the way things *looked*, but very rapidly started expressing frustration with those tools. Specifically, the general messaging was “this is bad because I don’t know how it works.”

The primary tool she took issue with was `thor`:

> Thor is a toolkit for building powerful command-line interfaces. It is used in Bundler, Vagrant, Rails and others.

[Thor](https://github.com/erikhuda/thor) has nearly *three* *hundred million* downloads on RubyGems. It’s a dependency of Rails, bundler, fog, faker, rack, google-api-client, bourbon, solargraph, jenkins, and I could go on but let’s just round it up to a rough *1.3 million repos and 6400 packages*.

The point is to say, the “complicated tool” that was a real thor-n (get it, thor? heh!) in my reviewer’s side wasn’t some new, untested, dinky gem I’d pulled off an arcane StackOverflow question or some such thing (not that even *that* should’ve been a problem, but still). It was a nearly decade-old tool that’s intrinsic to the ecosystem, well known, and quite frankly, not all that complicated.

Though we spent barely any time on my actual program code (we’ll get to that a bit later), each time we did she paused to remind us out loud that it was extra complicated and/or hard to parse because of “this Thor thing you used”.

She also took issue with the fact that I didn’t understand how Thor itself worked on the inside. This line in particular: `Candidates::Cli.start`*.* She seemed incredibly disappointed that I couldn’t explain how Thor’s `start` method itself worked.

This part I have mixed feelings about. Sure, I could’ve spent time learning about how each of the gems I used worked, but first, a lot of it would *surely* be over my head at this stage, and second, isn’t not knowing how they work *precisely the point*? If I could do everything Thor did, I wouldn’t have needed it—I could’ve just written it all myself. From my perspective most of the *value* of using open source tools like Ruby and Rails is that you *can* accomplish more than you understand. You can save time, effort, and *lots* of make-work, by benefiting from those who came before you.

And sure, when I have much more experience programming, I *will* likely understand more about the innards of the tools I use. But at this stage, it seems like a useless critique. What am I to take from it? That I should stay away from anything I can’t 100% build on my own? That the entire robust ecosystem of tools is up in an ivory tower I’m to stay away from until I become a mythical “real programmer”? I don’t know how *Ruby* implements most of the things we’ve been learning in the class *either*. Uhoh.

Back to our review. So Thor was definitely a thing hanging over my head the whole session. She absolutely made me feel bad for using it, and frankly I’m pretty upset about that. See my earlier point about preparation. Had she taken a look at *anything* about my project before our session, then she could’ve compensated for the fact that she’d never heard of Thor before, by doing maybe five minutes of research.

But also, isn’t coming across code and tools you haven’t seen before the *job*? Has she never approached a code base she didn’t write entirely on her own? That can’t be true. Why was she so thrown by seeing something she didn’t know about, and more importantly, why did she, in the position of power in this interaction, make me feel incompetent for using an ambitious toolset? I’m not the instructor here, but when someone I’m assessing professionally has come up with a clever way to accomplish their assigned task, I’m *impressed* by their find, not defensively dismissive because there’s something I hadn’t seen before. To the contrary: by all means, teach *me* something!

Thor led to some of the things she said that were the most upsetting:

> “It’s totally fine that you’re using Thor and everything, but you had to then explain all that to me, and that took too much time.”

> “I can tell you put in a lot of work but your code is a mess because of all this Thor stuff.”

> “This CLI class is majorly confusing because it’s so heavily dependent on Thor”

I was chastised for having used a tool that resulted in what my assessor herself called “probably the most complex CLI project I’ve seen in a long time” (in a good way), and that “looked way better than the other projects I’ve seen” and “does so much more than any of the other projects”… because she herself couldn’t grasp how one of my *dependencies* was implemented.

I want to stop here and focus on one seemingly throwaway thing she said: that my code was “a mess”.

First, a plea. Please literally ***never*** say this to any new student. Maybe it’s not that big a deal, but to me it effectively undermined just about all my work—even though the work itself *worked*! And it worked well! We’re talking custom error classes, multiple forks to take, a handy wizard, the whole shebang! (I’ll come back to the shebang later too…)

Second, no, it was *not* a mess. Was it the most beautiful code ever written? Almost certainly not! It was standard, and possibly even better-than-run-of-the-mill, *new developer code*. I’d written, refactored, gotten help from mentors and engineers, extracted parts out when they got complicated, and done literally everything I’ve been taught at this point to keep it tidy. Line spacing and indents that all followed convention, breaking out bits of methods so they don’t do a ton at once, had fairly descriptive method names, and even used an overly-aggressive linter to fix things I hadn’t previously even known were things.

Unlike a lot of the other students she’s talked to, I’m also an industry veteran, and I myself have seen almost certainly more beginner and advanced code than she has. Unfortunately, knowing what I know didn’t make it any less of a gut punch when the person tasked with evaluating me casually undermined it all.

But I’ll move on. So the shebang.

This might be another case of mismatched expectations, but I went into the assessment eager and prepared to explain all the code I’d written. Instead, right out the gate we focused on the code I *hadn’t* written. I’m not talking about Thor here, I’m talking about all the stuff Bundler and RubyGems give you right out the gate to make writing gems quick and easy (`bundle gem` ftw!) . The things they provide since they’re always nearly identical, and so you can get to the business of learning and writing your actual code.

So instead of being asked how my code worked, the focus was on why Bundler set up the file directory the way it did. And what the bits of *that*, were *called.* And on where I `required` my files. In one particularly frustrating case, she asked about this line:`#!/usr/bin/env ruby`

We ran into multiple problems here. First, it seemed there was a sheet she was using to tick off boxes, that required me to literally say certain words (she referred to it as a rubric, which is typically much more about skills than a vocabulary list, but regardless).

The challenging part was that she was pretty bad at letting me know what she was trying to get me to say. Several times in the review I said “I don’t understand your question. Are you trying to get me to say the word X?”. When I got it right, I got a laugh and an affirmative nod. When I got it wrong, I got a blank “you don’t know what you’re doing, do you, silly student” stare back.

Even while criticizing my own choice of words as “too vague” she kept asking questions like “what is this” and “I need you to say something different” while fishing for a very specific answer that I had very little chance of sorting out without additional prompts.

In theory, this might not be bad. We have lectures and office hours each week, and it’s pretty routine for our cohort lead to respond to a student’s confusion with “well what is that called” and “how does that work”, in an effort to help lead them to an answer they already know. But this didn’t feel at all like that, and it wasn’t because I didn’t know the answers (because I did probably 86% of the time).

It felt like playing Taboo, where the cards prohibited her from saying pretty much *anything* useful, and I was left there just reciting a dictionary in an effort to figure out what plane we were even on. As with all the other things, I can’t know if this was my particular reviewer’s *way*, or a prescribed Flatiron plan. In either case, it wasn’t helpful, and it constrained the conversation enough that I ended up appearing to not know things I knew *cold* because I couldn’t interpret the word salad (*lite!)* and understand what was being asked .

So back to the shebang. I didn’t remember that it was *called* a shebang. This resulted in numerous expressions of disappointment, the hard statement that “I clearly haven’t been talking about code at all” and the assessment that I didn’t know “where any of my code went.”

A little more detail on that: my CLI tool ended up being nicely complex. So in an effort to make it easier to read, I split my primary code into two files: a `topic.rb` file, and a `cli.rb` file, and added the various require statements to make it all work (plus most of it was inside the same Module). The main distinction I drew was that my actual API calls and data fetching happened in the `topic.rb` file, as well as the Class definition and instantiation, whereas the actual business of the CLI’s interactions, happened in `cli.rb`. It was a choice based on intuitive sense, rather than “instructions told me to do it this precise way”, and that didn’t seem okay to my reviewer.

I explained this thrice. I got blank stares in return each time, and continued assertions that I had no idea where anything was supposed to be. My technique went from what I had thought was a good idea to make it easier for someone to read the code, to “this is bad because I have to look at two different files instead of one.” Now again, beginner programmer here, but isn’t splitting code up so it’s easier to grok a *good* thing? Aren’t we supposed to avoid super duper long files with thousands of lines of code?

PS: She also told me twice “but none of this is Object Oriented Programming” — which I kind’v just stuttered at. Ruby *is* OO. I made a Class, and then instantiated instances of it. What part of OO did she think I’d missed?? How was my entire project *not* OO? She didn’t provide any precise explanation, just a hand-wavey “you didn’t do the main thing you were supposed to do.”

I’m not perfect by any stretch. I didn’t expect to need to walk through the things bundler had done *for* *me*, and so indeed I found her questions on that confusing and demoralizing (in addition to the previously mentioned problematic lack of clarity).

It’s not that I’m right for not knowing them, it’s just that they really didn’t seem like the high order bit. What about all the code I’d written, that I was supposed to be demonstrating? How was that less than 20% of the time we spent? How was that the afterthought?

Imagine you spend significant time working on an ambitious solo project, and you build a beautiful house. Buyers are coming through, and you’re ready to explain to them how it all works, why you chose the fixtures you chose, what choices you made in the foundation, all of it. Everything from the paint color choices to the soil sample reports you looked up before you started. But then the buyers arrive, and they don’t ask about *any* of those things.

Instead they want to know the precise title of the city inspector who provided your permits when you broke ground, and where he went to college. They want to know what *brand* of gaskets the plumber used when installing the hot water heater, and by the way, gaskets made it really unattractive to look at the pipes anyway. They want to know a whole bunch of things that you could *easily* look up, and indeed looked up when they were relevant as you made the choices, but which you absolutely didn’t commit to memory, couldn’t spit out on demand, and which you trusted vetted professionals along the way to handle for you.

Oh yeah. And then, on the way out, after telling you that you clearly had no idea what was going on, they mentioned that it was the most beautiful and well built house they’d seen in years, and congratulated you on the offer headed your way later.

At the end of the day, I made the sale. I passed the evaluation. And studying up on my gaskets and inspector’s titles is a thing I can do anyway, so that’s great—I will.

But how was I walking away from my meeting feeling like crap? How did it not seem strange that in the same evaluation, she told me it was the best app she’d seen, and also that I had no idea what was going on, and that my code was a mess?

Some of the other reasons I felt bad, full disclosure, were perhaps things I should learn to ignore. For example, my assessor clearly had something else going on while doing my assessment. Unsure if it was a pet, or a child, or a plumber, whoever—but she kept drifting out while I was explaining things to motion to or interact with someone off the screen. And when she’d come back, she’d missed much of what I’d said, sowing extreme doubt on my end. Was I right? Should I repeat what I just said? Was I wrong? Was she just not listening?

All in all it was the closest to a grade school experience that I’ve had in decades. Where someone, just by virtue of them being in the position of power, criticized things I was pretty confident weren’t broken, focused on the “the curriculum list says this so you have to do exactly this” rather than what I’d accomplished, and where I was so thoroughly unimportant that despite this being a critical step for me, the person in power literally had no idea who I was. It felt like an exercise in following the rules, rather than a programming exercise, and it was completely absent any empathy.

I'm in a frankly pretty privileged position right now. I'm learning more coding because I *want* to, not because my current livelihood depends on it; when I'm done I likely won't go out and job hunt, I'll just be able to do more different things at my *current* job. That makes it lower pressure. But if I’d had that review experience, coupled with my financial future being dependent on it, the pressure would’ve likely just made me quit. It would’ve made me “realize” that I “just wasn’t cut out for programming” and that would’ve been that.

Last up, lest you all think I thought I was perfect, my list from my review of things I do indeed need to get a better understanding of:

- `require` vs `require_relative`. There were a few of the former in my codebase that the reviewer said ought be the *latter*, and I definitely need to better understand why I choose which—even though I can make it *work* with them being effectively interchangeable.
- The file structure bundler provides by default. I’d been able to put everything where it needed to be to work, and I learned it all once upon a time, but indeed I can’t quite articulate some of the choices I made. For the most part in that case the answer is “I googled it and figured it out”—but remembering more of the *why* is of course useful.
- I had various gems `require`d in different places. Specifically, when I reasoned about where to put each gem, I tried to put the `require` statements in the files that would actually be *using* them, thinking that that way, if another file was the one being used, it wouldn’t need to load every single gem in my program. My reviewer thought they ought all be in one single place (“Ruby only loads things once, so they should all be in the same place; they should all be in the environment file”). I need to dig into this to better understand what she means, so I make better decisions next time around.
- Testing! Testing is not *not* one of the things we talked about in my review, even though I did some, and it’s something I really don’t know enough about building out. We’ve only barely covered them in the curriculum, but I could already see from just the CLI project how they’d be useful and found myself missing them. So requirements agnostic, I hope I can devote more of my side-energy to learning more to write tests.
- Custom Error Handling. Again, not critical to my gem, and not a project requirement. We touched on it briefly in the curriculum, and I implemented it in my project—but barely. I lacked confidence while working with it, and had everything not worked precisely so, likely would’ve given up and stripped it out, even though it was a valuable enhancement. So this too is on the list of things I want to go back and get better at.

---

I talked over my review experience with some folks in my cohort at the next office hours, and thankfully it seems like my experience wasn’t the norm. My classmates who had already had theirs seemed to have been able to focus mostly on the code they *wrote*, weren’t quizzed much on terminology in the precise way I’d been, and walked away feeling encouraged and optimistic. So hopefully my experience was isolated. It helped me feel less like “maybe I was just being so sensitive,” and more like “this was peculiar, and I shouldn’t hold on to it much.” I’m still just as good at this as I thought I could be going *into* the review.

Maybe my reviewer was having a bad day. Maybe their life is really stressful right now. I guess the best thought I can offer to hopefully help this not happen in the future, are these words of advice to reviewers:

- Recognize that you’re in a position of power. Recognize that casual insults you may not even commit to memory, are *extremely* meaningful to a beginner, and extremely high stakes. Recognize that they have little value, and there’s surely a more positive way to constructively criticism.
- Prepare! Your student has a lot riding on this. It’s another task for you, but an extremely important milestone for them. You should be excited, receptive, and appear to care. Fake it if you must!
- Try not to be distracted. Yes, life happens, but for important assessments, the person you’re evaluating should be the primary and solitary thing you’re focusing on. Being distracted sows doubt, and instead of reinforcing your student so they do better, you’re panicking them about why they can’t keep you focused.
- Your student is an adult. This isn’t grade school. Yes, in this case you’re in a position of power, but that’s incidental. When the eval is over, most of us are parents, bosses, nurses, whatever, and we’re just trying to claw our way to a better spot in the world! It’s not important to establish the power dynamic with you as the person “in charge”. You *are* in charge, that’s enough. There’s zero value in interacting with a newbie in a way that *reminds* them they’re a newbie at every step of the way. They may know more than *you*, in certain areas, and that’s a possibility you ought embrace, not a challenge you ought stymie. Best to ask *why* they did something the way they did it, rather than chastise them for taking some path other than the precise one you’d have chosen.
- And lastly, be empathetic. If your interaction *comes* from an empathetic place, you’ll likely get all the *previous* things on the list right. Put yourself in our shoes, remember the anxieties you felt when you were in our spot: making someone feel at ease is the least you can do, and will result in better outcomes for the students, and more enjoyable interactions for you.

---

For reference, as a final thought, this is the feedback / review I received after my session:
```
TTY gem create table, color + nice user interface

deesn't know sheebang, or really know where her code goes
doesn't really understand the diff btw require & require relative

confusion on ID'n self when involking fn

very bright

live code showing the user list of name of the users they've searched for & added into the app

blog about diff btw require & require relative, w/snippet about shebang line
```

Well. At least I'm bright 🙄
