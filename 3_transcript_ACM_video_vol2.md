<p float="left">
 <a href="https://www.dataumbrella.org"> <img src="images/full logo-transparent copy.png" height="40%" width="40%" /> </a>
  <img  width="150" />
   <a href="https://github.com/scikit-learn" target="_blank"> <img src="images/1280px-Scikit_learn_logo_small.svg.png" width="15%" height="15%" />  </a>
</p>


# [Data Umbrella](https://www.dataumbrella.org): Andreas's Video Sprint Instructions for scikit-learn Volume 2

## Video Transcript
- Speaker:  [Andreas Mueller](https://twitter.com/amuellerml)
- Video:  [Scikit-learn Sprint Instructions: Volume 2 FAQs](https://youtu.be/p_2Uw2BxdhA) (15 minutes)
- PDF slides: [ ] ()
- Transcriber: [ ] ( )

## Key Links

## Video
<a href="https://youtu.be/p_2Uw2BxdhA?t=1"><img src="images/sklearn_video1.png" width="90%" /></a>

---

hi everybody this is another video
providing information about how to
contribute to socket learn in particular
as part of an open source sprint
reshma is organizing another sprint
together with the data umbrella
this time with a geographical focus on
africa and the middle east
we've gotten a lot of feedback on past
spreads and
i'm trying to clarify some of the points
that people struggled with
in our past friends in this video here
if you haven't already please check out
the videos we posted before
i've given a short overview of
contributing to socket learn
and rashma did a whole walk through on
creating your first pull request
if you're new to contributing to open
source and or to socket learn
i highly recommend you check out both of
them
this video here will assume that you
understand the basics that we described
there
and we'll discuss some of the topics in
more detail
first word repair programming during a
sprint
we highly encourage people to work in
pairs
using a process from agile development
called pair programming
pair programming is great
pep programming is great because it
allows the participants to share
knowledge
it usually increases the fun of
programming a lot
in particular if you're new to your code
base it's common to struggle
and having more eyes on the code often
helps
in pair programming you have two
developers working together on the same
problem
with one person driving who actually
writes the code
the other person observes and discusses
the programming with the person driving
right now you're likely not in the same
space
as the person you're coding with but
online platforms like discord allow you
to easily share your screen and have a
private audio channel
being able to talk while typing the code
is quite important for pair programming
to be productive
good pair programming depends on both
people being
good communicators and be patient with
each other both of which take a lot of
practice
the two of you should be talking
together basically constantly
i could recommend that the person that's
less familiar with the code base
or feels less certain about the work
drives most of the time
this can be a little bit intimidating at
first but will provide a huge learning
opportunity to both of you
if the more experienced person is
driving it's
very easy for them to lose the other one
with the less experienced person driving
the person driving will likely learn
some programming tips
from the other one while the observer
will practice explaining their ideas in
detail
in other areas you might have
complementing strength
and will learn from each other you can
switch
who is driving but i wouldn't switch
very often and instead
talk through any stumbling blocks
together
alright so let's say you've found a
partner and you have found
an issue you want to work on if you're
both new to second learn it's a good
idea to get oriented a bit
and generally i think the conciseness of
python means it's pretty easy to
manually magnifigate
even complex code bases but having some
assistance from programming tool helps
i used to code in vim but these days i'm
using vs code
and i'll show you how to navigate the
code base with it
you can do the same with any other ide
or editor though
so here i open the second learn
repository in vs code
and you can see all the files and
folders on the left hand side
usually a python project has a setup.py
at the top level of the repository
which you can see here
and then there's the folder that
contains the actual module which is s
keller in this case
and only code that is part of the
library is going to be in this folder
then there can be several other folders
site and learn has become quite complex
over the years and so there are a lot of
folders
i don't want to go through all of them
many of the files and folders actually
set up various continuous integrations
infrastructure and automatic pipelines
for release of packages
that's for example circle ci and github
and many of the yaml files you'll see
down here
for travels and azure pipelines and so
on
you're relatively unlikely in a sprint
to touch any of these
you're more likely to work on twitter
folders that are related to the
documentation which is example and doc
the examples folder contains example
python scripts
that are also rendered to the website as
you can see each of these
folders here has several python files in
them
and the doc folder
contains the code for the website and
for all of the user guide
and i'll tell you a little bit more
about this in a bit
the tests in second learn are
interleaved with the code
in separate test folders so within the
sqln folder
you have a test folder
here and within each of the subfolders
you have a test folder that's specific
to this particular submodule
for example if you want to work on
logistic regression logistic regression
is at the sklearn
linear model folder and so there's a
file logistic here
that contains logistic regression and
the corresponding tests
will be in the linear model folder in
the subfolder tests
test logistic
alright so now let's say you want to
address a particular issue
for example this one here
in this issue there
there's a complaint about dog strain
and so this is a dog string of the
kalinski howrah score
let's say we want to find this
the easiest way to do this is to use the
search function in your editor
if your editor doesn't have a search
function you can also just give git grab
so
luckily this this name is actually quite
unique and so the research results are
pretty small
still it helps you to understand the
different folders these are
the results are in so here the dot
modules this is the
documentation escalante metrics this is
the code so it's the actual
implementation and
then here these are tests
we can also briefly uh quickly find the
definition by just by putting def in
front of it
and so now we go to the actual code
the issue was about the doc string in
the docs docstring
is part of the documentation that is
with the code so here you have the
function definition
and just after the function definition
you have
this string this is what's going to be
rendered in the api
documentation on the website which is
uh unlike the user guide the user guide
is in the doc folder
and so now if you want to make a change
you could make the change here
now let's get into the documentation and
website a little bit more
the documentation is generated using a
tool called sphinx
and mostly written in a market language
called restructure text
or ist it's not a very common language
outside of the python documentation and
it needs a little bit getting used to
all the files in the documentation
folder doc folder are written
in rst they are parsed by
the things tool which then generates the
website
things can also generate other outputs
like pdfs but usually we mostly use the
html output for our website
syncs also reads part of the
documentation that's inside the code
the docs strings that we saw are
embedded with the function class
definitions
and these are then also rendered on the
website i said before sphinx also reads
the examples
and puts them on the website so if you
want to modify
the uh part of the documentation it's
part of your docs string
as i showed you you have to do this in
the source code itself
so everything that will be rendered in
the api documentation
is written in the source code itself if
you want to modify the user guide
this will be written in rst inside the
doc folder
the docs string has a particular format
the numpy.format
and we have several other conventions
ourselves
you can find all of these in the
contributor guide
all right so finally i want to talk
through two issues with git
that people often struggle with in the
other videos we already walk through the
basic workflow
but there are two tasks that often come
up that i want to highlight
during a sprint there can be a lot of
activity on the repository
and the changes that the people make can
be relevant to whatever you're working
on
this might lead to conflicts or to you
working on an outdated version of the
code
before you start anything and whenever
github shows you your branch is out of
sync
you should update your feature branch to
synchronize with the main repository
for that make sure that you currently
have your feature branch checked out
with git checkout feature branch where
feature branch is
the name of your branch then assuming
you have the main repository added as
your remote called upstream
you can do git pull upstream master to
fetch and merge with the
upstream master branch
if there are any conflicts you need to
resolve them now
then once the merge is complete you can
push it
uh your feature branch
to your fork so the origin
remote with git push origin feature
branch
if you have a pull request based on your
feature branch the call request will be
updated automatically
the last thing i want to mention is a
con but easy to avoid mistake
when getting started with the github
workflow
so if you have followed the other videos
you know how to fork
and pull a repo create a branch and make
a first pull request
then it usually takes a while for a
contribution to be reviewed
and you might want to start on your next
issue
remember that right now your folder
reflects the content of your pull
request
if you want to start on something else
make sure your base is on the current
master branch
not on your pull request so
check out your the master branch and get
pull-ups remastered to have the current
version of the master branch
then create a new branch with uh check
git checkout dashb from the master
branch
not from your feature branch
and just to be sure whenever you create
a new portal request
look at the div that is shown on github
and check if it includes any changes
that
you didn't mean to include
if you find you have more changes than
expected before creating the pr
you can go back and see if you can fix
your branch
if you can if you um if you don't notice
at first
you can still undo any changes and
update your pro request by pushing to
the branch again
one relatively easy way to rewrite your
history is
to do git reset dash soft upstream
master
this will undo all of your commits but
will keep
the files as they are
so basically your history will roll back
to the state of upstream master
but all your files will be however you
change them
from there you can selectively commit
all the changes you want to commit
while leaving out anything that you
don't want to include
then pushing again to your feature
branch
potentially you need to force push you
can update your pull request that's all
i had for the upcoming sprint
there are many other libraries that
could use your help though and the data
umbrella has curated a video series
of how to contribute to several python
projects including numpy
pandas and core python
like scikit-learn these are fairly big
in established projects
if you're a seasoned developer
contributing to such a project can be
very gratifying
so please go and check out his videos
however getting a change accepted in a
mature project can sometimes
be challenging and you can also look for
smaller newer projects that are
less established new projects are often
easier to contribute to
and are usually very enthusiastic if
they get outside contributions
might also provide more of an
opportunity for you to collaborate in
shaping the vision of the project
so make sure to check out small project
that we are using or interested in
and see if they are looking for
contributors or ask if you are unsure
there's often lots of interesting work
to do and it's a great way to get
involved with open source
that's it and i hope i'll see you at the
sprint
