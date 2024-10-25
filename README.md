# Emerging Technologies

Emerging Technologies runs from September to December 2024 at [ATU](https://www.atu.ie).

![A futuristic lecture.](img/lecture.jpeg)


## Assessment

**The deadline for all assessment elements is Friday, 20 December 2024**.

Submission instructions [are given below](#repository-20).

This assessment brief is available from the beginning of the semester. 
If anything is unclear, make sure to ask questions well before the deadline.


### Purpose

The purpose of the assessment is for you to demonstrate ability in the following.

1. Detect new and emerging technologies in computing through reputable sources.

1. Contextualize an emerging technology by identifying its origins and proponents.

1. Research an emerging technology in order to use it.

1. Implement a solution to a computing problem using an emerging technology.

The assessment consists of three overlapping parts: a GitHub repository containing all your work (20%), a series of tasks (40%), and a small project (40%).


### Feedback

Guidance on your expected progress will be provided during lectures.
At certain points during the semester, submitted repositories will be reviewed.
Feedback may be given individually, to the whole class, or both, depending on need.
To get the most benefit from the feedback, ensure you regularly commit and push your work to GitHub.

If you have any questions, ask them well in advance of the deadline.
Pay close attention to the marking scheme and the advice below.
They are based on feedback given to previous students in this and other modules.
You should treat it as a form of [feed-forward](https://www.qaa.ac.uk/docs/qaas/focus-on/a-student-guide-to-feedback-feedforward.pdf) to help you improve.



### Repository (20%)

Start by creating a new repository on [GitHub](https://github.com).
Include in it only work that is part of your submission.
Make sure your final submission is in the `main` branch, though you can use other branches for development.
Your grade will be based on the last commit made on or before the deadline.


#### Submit Your Repository Info

**Immediately** submit your GitHub username and repository name using [this form](https://forms.office.com/e/9cunX4pd3Q). 
The form is only accessible through your ATU student account.  
You can find your username and repository name in the browser's address bar when viewing your repository on GitHub.
In the browser's location bar your will see something like `github.com/<username>/<repository_name>/`

#### Use GitHub Issues
Use [GitHub Issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues) to plan and track your progress.
Begin by making a clear plan for your tasks and project.
Your submission must include this plan and explain any design decisions made.
Document and track your plan using the [Issues tab](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue#creating-an-issue-from-a-repository) for your repository.
   
You may structure your issues as you see fit.
However, I suggest having at least one issue per task and several for the project.
You should also include issues related just to your repository, such as writing the `README.md`.

#### Organize Your Repository

Your work should be easy to showcase during a technical interview.
An interviewer should be able to understand and interact with your work without any assistance.
This will have a significant impact on your mark for this and other components.

To this end, make sure your repository is well-structured and includes:
  - A clear [README.md](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes).
  - A relevant [`.gitignore` file](https://github.com/github/gitignore).
  - [No unnecessary files or folders](https://realpython.com/python-git-github-intro/#what-not-to-add-to-a-git-repo).
  - Lowercase file and folder names, except for files like `README.md`.
  - No spaces or special characters in filenames. Underscores, hyphens, and full stops are okay.

#### Private Repositories  

You can make your repository private.
If you do, add `ianmcloughlin` [as a collaborator](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository#inviting-a-collaborator-to-a-personal-repository).


#### Choosing a GitHub Username  

Your GitHub username will be visible to potential employers.
Choose wisely.
You can use your real name, but a pseudonym is also fine if it’s reasonable.
Avoid using your student number.
You can [change your username by following the instructions on GitHub](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-user-account-settings/changing-your-github-username).



### Tasks (40%)

Complete all tasks in a notebook called `trigrams.ipynb` in your repository.
The tasks should be completed without the use of external libraries or APIs.
However, you can use [anything in a standard library](https://en.wikipedia.org/wiki/Standard_library).

For each task, you should write your code in code cells while using MarkDown cells to give explanations and insights into your code.
Break up your code into smaller, manageable cells whenever possible.
Each code cell should focus on a single step in your overall solution.

Include comments in all code cells to tell the reader what each statement does.
Write clean, readable, and efficient code, using meaningful variable names and consistent formatting.
You should follow Python coding standards and guidelines such as [PEP8](https://peps.python.org/pep-0008/).

Make regular commits to your repository while completing the tasks.
Your commit history should demonstrate how each solution to each task evolved.
There should be several commits for each task demonstrating incremental improvements, clarifications, and revisions.

#### Task 1: Third-order letter approximation model
 
Select five free English works in `Plain Text UTF8` format from [Project Gutenberg](https://www.gutenberg.org/).
Use them to create a model of the English language as follows.
Remove any preamble and postamble.
Remove all characters except for (ASCII) letters (uppercase and lowercase), full stops, and spaces.
Make all letters uppercase.

Next create a trigram model by counting the number of times each sequence of three characters (that is, each trigram) appears.
You can design your own data structure for storing the results but explain your design and its rationale in your answer.

For example, the sentence: `It is what it is.` would become `IT IS WHAT IT IS.`
This will give a model like `{'IT ': 2, 'T I': 3, ' IS': 2, 'IS ': 1, ...}`.


#### Task 2: Third-order letter approximation generation

Use your model from Task 1 to generate a string of 10,000 characters.
Start with the string `TH`.
Generate each next character by looking at the previous two characters.
Find the trigrams in your model that start with those two characters.
Randomly select one of the third letters of those trigrams, using the counts as weights.

For example, suppose your model has five trigrams starting with `TH`: `THE` appeared 150 times, `THA` appeared 70 times, `THI` 60 times, `TH ` 50 times, and `TH.` appeared 10 times.
The total of the counts is 340.
Select the next character as `E` with probability `150/340`, `A` with probability `70/340`, and so on.

#### Task 3. Analyze your model

Copy the list of English words available in `words.txt` in this repository to your own repository.
Use it to determine the percentage of words in your 10,000 characters that are actual words in the English language.


#### Task 4: Export your model as JSON

Export your model as JavaScript Object Notation (JSON), saving it in your repository as `trigrams.json`.


### Project (40%)

Create your own version of the [ELIZA chatbot](https://en.wikipedia.org/wiki/ELIZA) and deploy it to [GitHub Pages](https://pages.github.com/) using [GitHub Actions](https://docs.github.com/en/actions).
In your `README.md` file, include a direct link to your GitHub Pages site.

The chatbot must run entirely on the client-side, without using any external libraries or APIs.
Use **HTML** and **CSS** for the interface and plain **JavaScript** and/or [WebAssembly](https://webassembly.org/) for the chatbot logic.
Name the main page `index.html` and place it in a folder called `eliza` in the root of your repository. 
Store your CSS in a file called `style.css`, also in the `eliza` directory.

Place your main chatbot logic in a file named `eliza.js` in the same location.
The chatbot interface should include a text box for user input and an area to display the conversation history.

Ensure your code is well-commented and that your interface introduces and explains how your chatbot works.


## Marking Scheme

Each component will be graded based on the following four categories.
Each category carries equal weight.

Remember, your repository is what will be evaluated.
It should demonstrate evidence of the criteria outlined for each category.
That said, the examiners' overall impression of the submission may affect marks in each category.

You are expected to make steady progress on the assessment throughout the semester.
This should be reflected in your commit history.
Huge commits, especially late in the semester, will not be accepted.
At any stage you may be asked to discuss the work to date in your repository.

If you encounter issues with your repository, seek help well before the deadline.
Do not delete any files or commits without first consulting the lecturer.


### Research
 - Evidence of research on relevant topics.
 - Appropriate referencing.
 - Building upon the literature and documentation.
 - Comparisons to similar work.
  
### Development
 - Clear, concise, and correct code.
 - Appropriate tests.
 - Knowledge of different approaches and algorithms.
 - Clean architecture.
  
### Documentation
 - Clear explanations of concepts.
 - Concise comments in code and elsewhere.
 - Appropriate `README.md` for repository.
  
### Consistency
 - Tens of commits, each representing a reasonable amount of work.
 - Literature, documentation, and code evidencing work on the assessment.
 - Evidence of reviewing and refactoring.


## Advice

The freedom provided in open-style assessments such as this one can feel challenging.
You need to decide how to start, what content to include, how much to cover, and how to make the work your own. 

The assessment is designed to provide you with opportunities for independent thinking and decision-making.
Employers value graduates who can take initiative, work independently, and make design decisions with minimal guidance.
We expect you to have basic programming knowledge and be able to find information on your own.

Make sure to follow ATU's policies and regulations which are on the [Student Hub](https://studenthub.atu.ie).
Pay particular attention to any policies on plagiarism and the Student Code.
If you're unsure about anything, ask the lecturer.