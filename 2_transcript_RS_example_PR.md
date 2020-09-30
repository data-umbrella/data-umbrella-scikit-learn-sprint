# Example of Contributing and Submitting a Pull Request to [scikit-learn](https://github.com/scikit-learn)

## Video Transcript
- Speaker:  [Reshama Shaikh](https://twitter.com/reshamas)   
- Video:  [Scikit-learn PR Contributing Example](https://youtu.be/PU1WyDPGePI) (30 minutes)
- Transcriber: [Reshama Shaikh](https://twitter.com/reshamas)

## Video
<a href="https://youtu.be/PU1WyDPGePI"><img src="images/sklearn_rs_video.png" width="80%" /></a>

---

### Intro

Hello, my name is Reshama, and I'm going to go through an example of submitting a pull request, or a PR.  I participated in my first scikit-learn sprint about a year and a half ago and I'm happy to share an example.  Once you learn this example - it's going to be for the sklearn repo - but once you've learned how to do it for this repository you can do it for any repository on GitHub.  

### Set Up Virtual Environment

So the first thing that I'm going to do is I'm just going to make sure that I have my, I have some things set up.  And the first thing is I'm working out of my home directory.  I just want to make sure and see which Python I am using with the system is it Anaconda (uses command: `which python`). I am using the Anaconda version which is good. I also want to just confirm what version of Python I'm using (uses command: `python --version`) and it's version 3 6 8.  And I just want to check one more thing, which is, do I have git installed (uses command: `git --version`), and I do.  That's great. 

So, the next thing that I'm going to do is I'm going to set up my work environment, my virtual environment. And to do that I'm going to use `conda create - n`, for name, and the name of my virtual environment is going to be sklearn dev.  And I'm going to install the following packages in this environment.  It's going to be numpy, scipy, matplotlib, pytest, sphinx, cython and ipykernel (uses command: `conda create -n sklearndev numpy scipy matplotlib pytest sphinx cython ipykernel`).  And so this is going to take just a little bit of time as it creates the environment.  It's going to ask me if I want to proceed. I can hit enter or type yes enter.  

So the environment has been created. It tells us right here to activate this environment, use this command, conda activate sklearn dev.  Or conda deactivate.  Also if you want to see a list of your virtual environments, I just type conda environment list (uses command: `conda env list`).  And for me I have two virtual environments. I have my dash environment for another project I'm doing.  And sklearn dev.  And I want to go into that one.  So I'm going to do `conda activate sklearndev`.  And I want to do additional installations within this virtual environment.  And to do that I'm going to do `conda install - c conda-forge sphinx-gallery`.  And it's going to be this sphinx dash gallery.  There we go. Yes, I'm sure.  Type yes enter.  

### Set Up Repository (3:46)

Okay so the next thing that I'm going to do is I'm going to set up my repository.  And so I'm going to go over to scikit-learn.  And this is the main repository. And so I'm going to fork it, so I get a copy within my own account, and I'm going to fork it under my GitHub there.  It just takes a little bit of time.  All right there we go.  So right, here, it has my forked repo and over here it has - okay over here is the main repo. The next thing I'm going to do is I'm going to clone it right here. I have my SSH keys set up so I'm going to use this. If you don't, you want to use this URL. So I'm going to click, use SSH.  I'm going to copy, and then I'm going to go back to my terminal.  I'm going to just clear it and go to the top and I'm going to type `git clone`. And I'm going to clone this. 

Okay so then I'm going to type `ls` and that just lists what I have in this folder.  And it shows scikit-learn right here. And I'm going to `cd` into it.  `cd scikit-learn`.  Okay and the next thing that I'm going to do is I'm going to build from source so I'm going to do pip install - e space dot (uses command: `pip install -e .`).  

Alright so that took a little bit of time but it looks like it's done.  The next thing that I'm going to do is I'm just going to check my remotes for git (uses command: `git remote -v`). So I have origin, I have mine. And I want to add my upstream. And so to do that, I'm going to go over here. I'm just going to open this in another window. I'm going to get the URL for it.  And the way to do it is that I do `git remote add upstream`.  And I add this URL to it.  Okay and then when I check my remotes, looks like I have the origin.  And I have the upstream, which is good.  That's where I want to be.  So I just cloned the repo and it's up-to-date.  But, say you're going back to your work.  If I want to get the latest changes to scikit-learn, I do `git pull upstream master`.  So I'm pulling from this remote upstream.  And it's the master branch.  Okay, and it tells me it's already up-to-date which I expect, because I just cloned the repo.  

### Work on an Issue (7:28)

The next thing that I'm going to do is I'm going to  go to an issue that I have already picked out that I'm going to work on.  And what it's going to be is this issue which is one five seven six one.  And it says that the documentation of default values and many classes are either not included or it's inconsistent and so I'm going to reference this issue in my work. It's going to be one five seven six one, and I'm going to go look at an example of one.  So for instance, here's one where the default values are consistent.  So it says default equals two, default equals Euclidian, it's the string.  Default equals none, so this is the way, the consistent way that it should be. In an example that I found, for instance, in under the decomposition folder under score dict underscore learning, I found one where it is not consistent.  In here, on line 75 it shows - you, can make this a little bit bigger - it shows that it's an integer that goes 1000 by default right. And I just want to I'm going to make a fix to this file alright. So what I'm going to do is I'm going to go back to my terminal here and what I can do is I can go to this issue that's opened, right.  And I can make a comment on it and I can say I am working on - sklearn/decomposition/_dict_learning.py, okay. Just so people know that I'm working on this at the sprint to make sure that somebody else also isn't working on the same thing at the same time.  


### Create a Feature Branch (9:35)

And the next thing that I'm going to do is I'm going to create a feature branch.  So I'm going to go over here and I'm going to call my branch git checkout minus b, and I'm going to call it doc because I'm working on a documentation change.  And I'm going to call it dict learning (uses command: `git checkout -b doc_dictlearning`).  And it looks like I'm already, because I created the branch this way, I'm in the branch right there.  And I'm going to open up visual studio code, my editor.  You can use any editor you wish, but I'm using Visual Studio code. Okay so I'm in the scikit-learn repository, my copy of it, on my computer and it is under decomposition, it's under decomposition, and it is dict underscore learning, okay.  

So here I am and it was on line 75. Okay.  And right, there notice how it says 1000 by default.  And if I want to be consistent, I want to say default equals 1000.  And I'm going to come here and I'm going to do that. Okay and so I am going to save this file and then I'm going to go back to ... I'm gonna bring this over here and the next thing that I do is I'm going to commit my changes so I'm gonna do `git status`.

Ah. It tells me right here that I have modified this file right here so I'm going to add it and do `git add sklearn/decomposition/_dict_learning.py`. Okay. So the next thing that I'm gonna do after git add is I'm going to commit the file and it's `git commit -m` then the description is I'm gonna say I'm gonna say,  "Updated formatting for default value or consistency". 

### Running Tests (12:15)

Okay all right so the next step that I'm gonna do before I push my changes is I'm going to run some tests so I am going to learn run the flake8 tests for formatting. So it's flake8 sklearn and here I'm going to put the path to my file so it's going to be decomposition (uses command: `flake8 sklearn/decomposition/_dict_learing.py`) and there we go now and it tells me that on line 75 I have this thought I have a trailing white space.  So I'm going to go back to my okay when I do control e for the end.  Yep I'm not. I had one extra space which I shouldn't. So I'm going to go back one. I'm going to save this file again, make sure my changes are saved.  Then I'm going to come back here okay. When I do `git status` it should show me that I've changed something and it does - it tells me right here.  So I'm going to go through the process again.  I'm going to do `git add`.  Okay decomposition and I'm going to do git commit so I'm going to type in the same thing. I'm going to say update my commit so I'm gonna say, "fixed flake8 error". There we go. 

Okay so great and I'm gonna run the flake8 test again just to make sure - I just arrowed up - to make sure now that I fixed that trailing space it didn't show me any more errors so that's a good thing. The next thing that I'm gonna do is I'm gonna run the `pytest sklearn` test. Now I made a documentation change and I don't expect there to be any errors but this is an example where it shows you I'm running the suite of pytests for sklearn just to see what the output looks like. 

So what this is doing is going through every test that's created and it's just making sure that none of the changes I made has an adverse impact on any of them. [PAUSE] Alright so it looks like one of the tests did not pass. I made a documentation change and occasionally some test doesn't pass but it doesn't impact - actually it says over here it gets skipped.


### Pushing to the Forked Repo (15:50)

So let's see what happens. I had done a git add, a git commit now I'm gonna do a git push. I'm gonna do git push origin is to my remote and to my branch name which is do see dict learning (uses command: `git push origin doc_dictlearning`). Let's see what happens. So it has pushed to my branch. I'm going to go over to my my forked repo. I just refresh this page and it tells me that I have a pull request that I can compare and submit. 


### Preparing the Pull Request (16:05)

So I'm gonna click on that. Okay and this is where I add a meaningful title. Okay and so I'm gonna call it DOC because it's a documentation fix and I'm gonna say cleaning parameter doc string in decomposition/_dict_learning.py and this is where I write some information. And so I'm gonna say here that I am this PR references it references 1 5 7 - notice it's automatically linking to - there you go - fix documentation. So I can hold that in. I can delete this. Remember I don't want to do closes here or anything like that. I'm gonna put a description here that says that I updated default value documentation for consistency. Okay and if I have - Do I have any other comments? What I'm gonna do is I'm gonna assume that I worked with of my pair programming partners - okay - so she also gets the notifications and I'm gonna, I'm gonna assume that it's Miriam. 

I am actually - alright. And I just want to read this it tells me it's a loose team of volunteers so let's be patient about it. I have read it. They thanked me for contributing - great! And I have the information here I can also preview over here and it tells me what it references which one. It tells me that and here I can - I click on allow edits by maintainers in case something needs to be changed. I can go through here that tells me that this is exactly what I changed - I changed one line - and the line I change was instead of a thousand by default it's default equals a thousand so it looks like everything is in order.  I am going to create the pull request. 

### Continuous Integration Tests (19:30)

Okay and now notice I'm at the scikit learn repo and it is running some checks right here. This is in gold so it means it's still processing right there. I'm going to go to the repo. I'm gonna click on pull requests and this is just a way to see what are the pull requests other people have submitted. Notice that it's in green. It has the DOC. It has the circle. I'm going to go back into it just to see what's happening. There's a bunch of checks here form progress to pending to neutral to one successful. Sometimes if you know, if the check fails, you can click on details here. This one has passed so I'm just going to open this up in another tab just to see what's going on. And it gives some information on - log into github -  I guess I could do that later. And this can also take a bit of time and sometimes when we're in a sprint a lot of people are submitting for requests it takes a little bit longer also. Let's see what happens if I log in here. I'll log into Circle CI. I'm going to authorize. 

Interesting.  Alright, let me click on these details again and see what happens.  This is what I wanted. Zero errors and zero warnings. Okay, I'm going to come back here and I'm gonna just look at this one here. And it tells me that there's one test one successful fail and so this is actually a good way as these tests are being run if they fail, you can click on these details and get more information about why they failed. So I am going to stop right here and then come back to it. [PAUSE]

So I am back. I am checking to see my pull request. It looks like all checks have passed which is great! Just so that you know the first time I did these PRs I did not get so lucky. But you know if one of your tests doesn't pass you can open up the details and look for more - click through - and look for more information about what's in there. Sometimes you'll have a comment back from a reviewer. I would say this took a good twenty or so minutes to run so keep that in mind when you are, when you are running, when you're submitting PRS.  And so that is an example of how to submit a PR with a simple, with a very simple fix.  

### Summarizing the PR Process (23:50)

And so I just want to go over the pull request. So what you want to do to get started you want to make sure that you have your right environment setup.  Anaconda is always good to use. Python and git are installed.  You want to setup your virtual environment.  You want to fork and clone and create a branch. You want to make an update to a file starting off with a small fix in documentation and then gradually moving on to editing some code. Running the test and submitting a pull request.  

### Mistakes I Have Made (24:20)

You know when you set up your virtual environment or somewhere along the way, you are most likely going to run into glitches.  I certainly did.  And so and it depends on your setup and what operating system you're using and what versions of libraries you have.  And a lot of, a lot of dependencies. And so there's various ways to resolve these glitches.  If you run into an error you can google it to see what information's out there.  Chances are other people have also run into that error.  If you're in a structured environment like this open source sprint now, you can troubleshoot with your pair programming partner. Everybody comes in with a different background and experience. And you know if you need assistance we have, I mean this is the reason we have this sprint.  We have our help queue on the discord and you can ask one of the mentors at the sprint and somebody will help you.  

So I just want to go over some common mistakes that I have made along the way.  You know what, chances are you're going to leave this the sprint and then the follow-up work is going to come later. And so as I would go back to do work, I just want to make sure, you know, like am I in my virtual environment?  Sometimes I actually don't go into my virtual environment and I run tests. And I run into all these errors and so that's always important.  

I always make sure that I'm in the appropriate branch that can be a cause of problems too.  I make sure that I sync my repo with sklearn.  If you go back and, you know, work on your PR three days, one week, two weeks later, there are going to be updates that have been made to sklearn and you just want to make sure that you have the latest updates on your local computer.  And you just want to make sure that you've run the test.  Make sure that you've run the flake8 tests and the pytests as well. 

### Thank You

And thank you for joining.  I look forward to looking at the PRs and answering any questions on discord or on Gitter or wherever.  Thanks for joining. Bye!
