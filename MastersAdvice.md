# Description, Objectives, Ethics & Resources (DOER)

- You will need to fill out a DOER, some documents on a DOER and projects can found here (in the slides lined on that page): [https://studres.cs.st-andrews.ac.uk/CS5099/0-General/](https://studres.cs.st-andrews.ac.uk/CS5099/0-General/) (including the ethics one). These are CS focussed so if you’re on GD5999 (the Digital Health MSc programme) then the requirements are slightly different so you don’t strictly need to do a DOER but I’d like you to fill out one anyway.
- More information on the DOER can be found here :- [https://info.cs.st-andrews.ac.uk/student-handbook/course-specific/sh-project.html](https://info.cs.st-andrews.ac.uk/student-handbook/course-specific/sh-project.html)

## Breakdown of DOER

**Description:**

A title and a short description of the project aims, context and background. It should provide broad overview of your goals, justification for their significance, and your intended approach. You can use what has been discussed about your project for this as a first draft.

**Objectives:**

You should all have a literature review on your topic as your first objective. Then have a fairly easily achievable objective (such as replicating something done before to get a result), then a more difficult objective (such as implementing a more complicated system to get a more interesting, perhaps novel result), then a harder objective which will stretch you to achieve. All of these objectives have to be completable within the given time frame while still having time to write the dissertation (this is the most difficult part).

**Ethics:**

All of you will need to fill in a proper ethics form as you’re using data from humans. Although, as you are using published open data, it means that you can skip about half of the questions in the form. This is the most important document to be sorted first.

**Resources:**

Your resources are:

(A) the data you will use (you should provide a link to this as it’s already available)

(B) the compute resource you need

- you will be provided access to the lab GPUs (see below) as you’ll all be running ML algorithms which can make use of the GPUs. If you run out of memory on the lab machines, then you can be provided shared access to my machine (CASE) which has 256GB RAM (and 2x1080Ti GPUs), if even that is not enough then you can have access to my (DHB) DGX1 machine (8xV100 GPU) although hopefully no one should need this. Some of you are using very large datasets and so part of your project will be using the data appropriately on limited hardware (e.g. experimenting on small subsets before running on all/larger chunks of data, possibly taking 2D slices instead of using al 3D etc). You will need to mention both the data and that you have access to GPU machines to do your work as the resources.

**Remote connection:**

If you have any home working issues and /or working in a different time zone, please let your supervisor know as soon as possible. Stuart Norcross (Director of Infrastructure) has been informed that you will need remote access to GPU machines. You will need to email the School's Systems Group (by emailing cs-support@st-andrews.ac.uk using your St Andrews University email account) your SSH public key (please do this asap). Hopefully he will then send instructions to you about how to access these machines soon. Please let your supervisor know if you have not received these instructions from Stuart about how to access the GPU machines.

# Expectations

What you can expect from the supervisor :-

- Guidance on how to shape your project, explaining what they think makes a good dissertation, and trying to keep you on track for a good dissertation (this would be their main role).
- Sensible discussion on your methodological approaches.
- They will not tell you what to do or demand different approaches, however they will make suggestions (which is then up to you to decide if you follow them or not).
- Please note that they do not help with code debugging however, they may occasionally point you towards resources which may help.
- Everything will be discussed during the meetings however, if you have anything really urgent then you can contact them either via email or via MS teams.
- Also note that I do not check my emails/MS teams out of hours (outside 9am-5pm Mon-Friday) and you should give me 2 working days to reply before chasing me, although after that please do chase me (I won’t get offended).
- I (DHB) will take some holiday and the dates are to be confirmed. The exact times of my annual leave is not yet defined, in your DOER you can put that your supervisor will be taking annual leave in the summer but the dates are yet to be confirmed.

What is expected from you :-

- Make progress each week and present that progress at the weekly meetings.
- For you to be self-starters, come up with solutions to problems yourself and also figure out what the best problems are to solve (this is probably the biggest difference from undergrad to masters).
- You are expected to deviate from the plan but when you do so you should have :-

  (a) a good reason for doing so

  (b) evidence of that reasoning.

- You should manage the project yourselves effectively. The supervisor will help oversee this and step in where necessary, however at this (masters) level they should be there as reminder guidance rather than as a boss.
- When you have questions you should try to solve them yourselves, the meeting provides an opportunity to have a discussion about the possible different solutions and if it's still not solved then at least the possible approaches could be discussed. Do come to meetings with discussion points but do not come to meetings and ask questions you haven’t even tried to answer yourself (these days if you haven’t even asked google then it’s almost rude).

# Suggested Dissertation Timeline

**Suggested timeline for your dissertation :**

You have approximately 11 weeks from start to finish (starting 1<sup>st </sup>June, finishing Mid Aug)

The following is roughly suggested (which can move approx. 1 week either way depending on your preference):

- Literature review : 3 weeks
  - This informs and justifies what the approach/methods you want to implement/test.
  - (see below info action points on literature review for more info)
- Minimal viable analysis : 3 weeks (get your data in, then process in a basic way to get the right kind of output metrics).
- Advanced analysis : 2 weeks.
- Write up dissertation : 3 weeks
  - Although really you should try to write up as you go along.
- Submit (with enough time before the deadline to upload, download, check that all files are present and correct, fix if there is a problem and then re-upload and re-check).
