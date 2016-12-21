# Happy Fun Ball

## Scenario
You have been hired by Wacky Products Incorporated. They are just weeks away from starting a global marketing campaign for their new hot product Happy Fun Ball and they want a top-notch web page to be launched as soon as possible.

Mysteriously, the entire dev team has lapsed into comas and it is up to you to save the project.

As a professional developer, you will do whatever it takes to finish this project! Everything, BUT work directly on the master branch!


### Setup
#### Part 1 - Get the files
Browser - github:
- Fork Happy-Fun-Ball (make a copy of this remote repository to your github account):
  - [Go here]( https://github.com/Krafalski/hfb) and click fork (upper right) to fork it to your personal repo (Don't worry! You can totally delete it after the lesson!) ![Upper right on github](https://i.imgur.com/TjcbBOB.png)
- Navigate to YOUR version on your repo
- Click the 'clone or download' button (on the right, below fork). ![Copy or Clone button](https://i.imgur.com/hsHdQTA.png)

This will give you the option to copy the link to your clipboard and make it ready to paste in the command line. REMEMBER: This should be from YOUR repo (the link to be copied should be `git@github.com:your-github-handle/hfb.git`)

Command line:
- Navigate to a directory OUTSIDE of wdi-remote-matrix
`mkdir` (if you need to)
- ```$git clone `git@github.com:your-github-handle/hfb.git` ``` (use `command v` to paste the url from github)
- The above command should create a copy of Happy Fun Ball locally (on your computer) and initialize git. Let's check:
  - `cd` into the directory and then `ls` and check that `index.html` and `main.css` are in your folder
  - `git status`
=> ![on branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean](https://i.imgur.com/SMyXeGV.png)
- `git remote -v` (should be YOUR github url) => ![this should show you the url where you are fetching and pushing from (with an alias of origin). It should be your github.](https://i.imgur.com/QVG9UPS.png)

#### Part 2 - Configure Git to Have Autocorrect
To help with today's lesson we can configure git to have autocorrect. We are going to install it locally (just to this repository). If you end up liking the configuration, you can always install it globally later

Command line:
- `git config --local help.autocorrect`
- example output:

   ![an autocorrect message](https://i.imgur.com/Jsi5Jwx.png)


#### Part 3 - Make a Dev Branch
Command line:
- To make a new branch AND checkout the new branch(we will call our new branch 'dev'): `git checkout -b dev` => ![new branch](https://i.imgur.com/AnAkrWr.png)
- Do `ls` and `git status` to confirm everything looks like it should
=> ![on branch dev
nothing to commit working tree clean](https://i.imgur.com/ulpNaf2.png)

- Get this branch on your github repo!: `git push origin dev`

Browser - github:
- See your new branch on github (it should be there, refresh if you don't see it. If you still don't see it, let me know and we'll trouble shoot)
=> new message along the top of github OR from clicking the Branch: master button ![pull-down menu](https://i.imgur.com/Q6N93aM.png)

Command line:
- open the files in atom `atom .`
- open index.html in the broswer `open index.html`

Final Steps:
Organize your browser, command line and Atom so that you can easily switch between them (don't forget to use spectacle). Here is how I worked on this project:
![window organization](https://i.imgur.com/gmXjBhh.png)

Take a couple minutes to get familiar with the code you'll be working on.

### New Feature - Link the HTML and CSS




### New Feature - Update the colors
- Work on a new feature - working in the main.css file, you will update the colors of the Happy Fun Ball web page

Command line:
- Before we begin, let's make a new branch specifically for our new feature:
  - Check that you are on the dev branch `git branch` will list all your branches and have a `*` next to the branch you are on. Then:
  -  `git checkout -b color-updates`

Atom - index.html :
- You probably noticed that index.html had a typo! On line 19 `class="pr"` should actually be `class="price"`. Let's update that! Now, it's not really our task, or our file to work on, but we're just being proactive and  helpful! What could possibly be wrong with that?

Command line:
- Let's go ahead and `git add index.html` and `git commit -m 'fixed typo in index.html'`, there! We added our changes and put in a descriptive commit message. We are undoubtebly awesome.

Atom - main.css:
- Now let's update the colors in the `body`, let's change `color` (font color), and `background-color` to whatever our heart desires. [Go ahead and use hexadecimal colors, rgb, hsl or some of the standard web colors.]( http://htmlcolorcodes.com/color-names/)

Make changes here in main.css ![main.css](https://i.imgur.com/1WY4xj8.png)
- When we've found the colors we like, we can go ahead and `git add main.css` and `git commit -m 'updated colors'`

### See Branching in Action
Command line:
- `git checkout dev` (Notice: no `-b`)

Atom - main.css:
- See that our changes are gone

Broswer - index.html:
- Refresh the page and see that the page has reverted to the original version

Let's get back to our changes!
- `git checkout color-updates`

Go through atom and the browser to see that your changes have come back

Atom - main.css:
- Let's make one more color change, now that we are on our color-updates branch. `.price` change the color from orange, to whatever color you want
- Don't forget to save your file

### Working on a New Feature
- There was an error! The price of Happy Fun Ball is supposed to be $24.95, not $14.95!
- Let's make a new branch off of the dev branch to hotfix this major problem!
Command line:
- `git checkout dev`
- ERROR!: ![error](https://i.imgur.com/h5Cu1Vh.png)

- We will commit our changes (we will not cover `stash` today):

 `git add .` then `git commit -m 'changed price color'`
- Now `git checkout dev`
- `git checkout -b 'price-fix` to make a new branch off of dev (and automatically be switched to the new branch) **

Atom - index.hmtl:
- update the price of happy fun ball from `$14.95` to `$24.95` (~ line 19 of index.html)

Command line:
- `git add index.html`
- `git commit -m 'fixed price of happy fun ball on index.html'`
- `git pull origin dev` (this should come back clean, but it is good practice to pull before pushing)
- `git push origin price-fix` to create a new branch on github

** GOTCHA:  Branches can be created off any other branch. Be sure you are on the branch that you want to branch off of before creating a new branch!

### Merging Our New Feature into the Dev branch
Browser - github:
- See our new branch (either a message will pop up or use the left side pull down to see) ![github screenshot](https://i.imgur.com/mgEzi40.png)
- Select the pull request tab
- Select `base: dev` and `compare: price-fix`
- Wait a moment to let github tell you if there are any merge conflicts ![github all clear](https://i.imgur.com/L72S16y.png)
- All clear! Go ahead and press the merge button, go ahead and confirm the merge! (Note: when you work on a team, it is unlikely that you would merge your own pull requests) ![Merge Pull Request message and button](https://i.imgur.com/2yUuGmq.png)

Command line:
- `git checkout dev`
- `git pull origin dev` - to pull down your changes from the remote to your local copy

### Going Back to Our Updated Colors Feature
- Whew! That was exciting! It's nice to be back to working on this feature. We know there were changes to dev, so let's get them

Command line:
- `git pull origin dev`

...

...

...

ERROR! Merge conflict! ![error message](https://i.imgur.com/KtbGDup.png)

### Merge Conflict (and resolution)!

Atom - index.html :

- View the conflict in Atom
![index.html file](https://i.imgur.com/itPVnM1.png)

- Delete  everything between `<<<<<<< HEAD` and `========`:

Which is the line:

 `<h3 class="price>Only $14.95</h3>`
  - this conflict is our doing, let's get rid of our mistake from working in index.html when we were only supposed to be working in main.css and keep the change made from the price-fix branch

- Now that we've removed the conflict let's finish cleaning up the conflict and remove the line
`>>>>>>> 3b73c340f2c158a80ce20828fd94ad83ea60b444`

- `git add index.html`
- `git commit -m 'fixed merge conflict'`

- `git push origin dev`

Browser- github:
- Since we were on dev and fixed dev, the changes should have automatically been sent to github
- Check the index.html file on github to see that our fix went through


### Finishing and Merging Your Color Updates

Command line:
- `git checkout color-updates`

Atom main.csss:
- Make your final updates to `main.css`

Command line:
- `git add main.css`
- `git commit -m 'updated colors'`
- `git push origin color-updates`

Browser - github :
- Pull Request
- compare `base: dev` to `compare: color-updates`
- Wait to be sure there are no conflicts
- Merge Pull Request
- Confirm Pull Request

Command line:
- `git checkout dev`
- `git pull origin dev`

Atom index.html/main.css :
- Take the time to review that the changes to the dev branch that you wanted are there and there are no errors or bugs
- **Only working code should ever be pushed to master!**

- If everything is ok, go ahead and push the changes to master
- If you made changes, don't forget to `git add` and `git commit -m ''`

Command line:
- `git pull orgin dev` (yes, we _just_ did this, but it is a good habit to do a pull before doing a push )
- `git push origin dev` (it is ok if git tells you that your working directory is clean)

Browser - github:
- Pull request
- Compare `base: master` to `compare: dev`
- Wait to be sure tehrea re no conflicts
- Merge Pull Request
- Confirm Pull Request
- Check to see that your changes have been successfully made to the master branch

### Hungry for More?
- Make a new branch, continue to update the Happy Fun Ball web page, and merge back your changes (New Feature Ideas: change color of Happy Fun Ball. Add a google font. Add some js/jQuery to show/hide Happy Fun Ball's Warning.)

### Sudden and Permanent Shut Down of Wacky Products Incorporated
- Well, it was fun while it lasted?