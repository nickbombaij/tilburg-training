Github and R Markdown for Research Productivity and Transparency
========================================================
author: Jeff Dotson - Brigham Young University
date: February 6, 2020
autosize: true

Tutorial Set-up
========================================================
Hopefully you are already done the following things:

- Create a free github account
- Install R and Rstudio
- Install Git
- Connect R to Github

If not, work on that now.  It may take a little while.  I can help during our first break. 

Motivation
========================================================

- Work needs to be reproducible 
- Work needs to be generalizable
- Work needs to be collaborative

Concerns you might have
========================================================

- Someone might steal my work!
- What if someone finds and error?!
- I don't want people to see that I'm not a good programmer!

Workflow
========================================================
What does your workflow look like?


Getting Started with Github 
========================================================

GitHub is a powerful collaboration and version control tool. 

We will be using it for: 
- **project management** 
- **writing** 
- **coding**

Project Management
========================================================
By project management I primarily mean keeping track of assigned tasks using the **Issues** tab on GitHub. 

We can have an ongoing conversation here about each specific issue and close it out when its completed or resolved. 

Be sure to tag collaborators you want to see the conversation (e.g., `@jeff-dotson`). 

Think of this as an email thread or Slack channel where all of the conversations are in one place, easily searchable, and automatically archived.

Project Management - Illustration
========================================================


Writing
========================================================
Think of using GitHub to collaborate on writing like using something like Google Docs. 

It is essential that we document what we're doing in each project as we do it. This is true for a number of reasons:

1. Writing forces you to think clearly about what you're doing.
2. If you're coding, think of the associated writing as long-form comments.
3. The final product of any project is going to be a paper, so start writing it now.

Writing
========================================================
GitHub supports **markdown** syntax, which you're probably more familiar with than you might expect from time spent with **R Markdown**. 

We will be writing using *parameterized* R Markdown so we can easily reference model output instead of including it manually. The output in the **YAML**, the header at the top, should always be set to `output: github_document`. When you knit changes to your R Markdown document, it will create a markdown document that is easy for GitHub to read.

Writing Illustration
========================================================

Coding
========================================================

GitHub was created for software developers. While we aren't developing software, we will be importing, wrangling, visualizing, and modeling data.

Even if you were just working solo, you will be collaborating with your past self and you should do yourself a favor and impose good version controls on your code.

R Markdown allows us to integrate executable code directly into a document. 

Coding - Illustration
========================================================



Git Basics - Clone a Repo
========================================================
First **clone** the repo for this tutorial. 

This creates a local copy of the repo. 

You do this inside RStudio by creating a new project and selecting `Version Control > Git`.


Git Basics - Clone a Repo
========================================================
![](clone.png)

Daily Work: Pull, Commit, Push
========================================================
![](daily-work.png)

Daily Work: Pull, Commit, Push
========================================================

When you start a new work session, you'll want to click on the blue down arrow to **pull** the latest changes from the repo, possibly the work other collaborators have pushed, so you're synced.


Daily Work: Pull, Commit, Push
========================================================

Open up the RStudio Project in the clone and work on the project. 

You have a new Git pane in RStudio that notifies you that changes you've made means you are out-of-sync with the **remote** repo (i.e., the one on GitHub). 

Once you've made a number of changes, you click on the files you want to **commit** and click commit. 

Think of a **commit** as saving a snapshot of all of the changes you've made across these files all at once. 

Include a clear commit message. You'll do this fairly frequently for your local repo, possibly just **amending** the same commit each time.

Daily Work: Pull, Commit, Push
========================================================

Eventually you'll be ready for other people to have access to your changes on the remote repo. 

To do this, you'll click on the green up arrow to **push** your changes to the remote repo. 

You push far less often than you commit, maybe once a work session, since this means you think it's ready for others to have access to. 

Each time you push, all of your commits are archived on the remote repo, including the **diff** or the side-by-side comparison of what changes you made to the previous version.

Collaborating: Branches and Pull Requests
========================================================

Because GitHub is very systematic in the way it manages commits, we will run into commit errors when multiple people have changed the same thing at the same time. 

We can avoid this problem by using **branches**. 

Each branch is a separate version of the repo that exists in parallel, one where you can make changes or experiment without it affecting the **master** branch. 

In fact, the master branch is protected so that you can't accidentally push changes to it.

Collaborating: Branches and Pull Requests
========================================================

To do your work as a collaborator, create a new branch on GitHub with a short, descriptive name specific to the issue you're working on (e.g., `jeff-paper-revision`). 

When you start a work session, make sure you select the branch you want to work on from the dropdown in the Git pane in RStudio. 

You can commit, push, and pull as usual to the branch you're working on. 

When you've completed work on the issue associated with the branch, create a **pull request** on GitHub and tag the repo owner (i.e., `@jeff-dotson`). 

Project Organization
========================================================

Each project has a similar organization. 

There are certain limitations on the size and type of files that can be pushed to GitHub. 

There are also certain things that shouldn't be accessible by the public (e.g., data we have a licence to access). 

For these reasons, we have folders and files that are pushed to GitHub and those that are not.

Example Project Organization (Pushed to Github)
========================================================
* **/Code** Each script should do something specific, have a descriptive name, and include number prefixes if they are meant to be run in a certain order (e.g., `01_import_data.R`, `02_clean_data.R`).
* **/Data** While all data live here, only data that are small and can be shared publically will be pushed.
* **/Figures** Figures live here, including images (saved as PNG files) and data referenced or used for tables, for use in the `README`, paper, and presentation.
* **/Paper** The manuscript of the paper, without any PDF knits, including a specified Creative Commons license.
* **/Presentation** Slides for presentations, again without any PDF knits.
* **README** The abstract and any project-specific details and deviations from this outline.

Example Project Organization (Pushed to Github)
========================================================
* **/Output** Output from model runs. These files tend to be too large. They are also something each user can create on their own.
* **/Readings** Loose papers that you want to keep track of reading locally. GitHub is not a paper management system.
* **/Temporary** A catch-all folder for *temporary* files specific to a project that might not have anywhere else to live.

Note that you can create **Output**,  **Readings**, and **Temporary** folders in your local clone without worrying about them being pushed. We can further modify the `.gitignore` file to add other folders and files that aren't pushed to GitHub.


Exercise - Create File Structure for your Repo
========================================================

1. Navigate to the location local repo and create the following folders:
Code, Data, Figures, Paper, Presentation, Output, Readings, and Temporary
2. Modify the **.gitignore** file to prevent Output, Readings and Temporary from being pushed to github
3. Pull, Committ and Push
4. Check github to make sure your file strucure has been correctly updated

Github Troubleshooting
========================================================

Problems will arise, merge conflicts will happen.  

Use Google to sort out any issues you encounter.  

This may involve the need to invoke commands through the terminal 


Introduction to R Markdown
========================================================

What can I do in R Markdown?
========================================================
- Compile a single document into multiple formats (PDF, HTML, Word)
- Create notebooks to run code chunks interactively
- Make slides for presentations (HTML5, Beamer, PowerPoint)
- Produce dashboards with interactive layouts
- Build web-based applications using Shiny
- Write journal articles
- Author books of multiple chapters
- Generate websites and blogs 

See the [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/) for details


R Markdown Basics
========================================================

Putting It All Together
========================================================

