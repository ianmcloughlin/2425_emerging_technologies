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

To begin, create a new repository on [GitHub](https://github.com).
Include only work you are submitting for this assessment in the repository.
Ensure your work is in the `main` branch of the repository, although you may use other branches in developing this main body of work.
Your overall submission will be graded based on the last commit in GitHub on or before the deadline day.

**Immediately submit your GitHub username and repository name using [this form](https://forms.office.com/e/Bninfm2LeU)**.
The form is only accessible when you are logged into your ATU student account.
You will need your GitHub username and repository name.
These can easily be found in your browser's location bar when visiting your repository on [github.com](https://github.com).
In the location bar will be something like: `github.com/username/reponame`
Your username is between the first two forward slashes after `github.com`.
Your repository name is between the second and third forward slashes after `github.com`.
The forward slashes are not part of the username or repository name.

Your repository should be well-organized with [a clear `README.md`](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes), a [relevant `.gitignore` file](https://github.com/github/gitignore/blob/main/Python.gitignore), and any requirements below.
Avoid committing [unnecessary files or folders](https://realpython.com/python-git-github-intro/#what-not-to-add-to-a-git-repo).
Use [lowercase](https://developers.google.com/style/filenames) for file and folder names, except for the usual uppercase files such as `README.md`, and avoid using spaces and unusual characters.
It is okay to use underscores, hyphens, and full stops.

Your completed repository should be easy to present during technical job interviews.
An interviewer should understand your work and how to interact with it without any assistance.
This will significantly influence your grade for this component and all other components.

#### Note: Private Repositories

You can set your repository to `private` if you wish.
Make sure to add `ianmcloughlin` as a collaborator if you do.
To add a collaborator, [follow the instructions here.](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository#inviting-a-collaborator-to-a-personal-repository)

#### Note: Usernames

Interviewers often ask to see GitHub profiles. Choose your GitHub username carefully.
I use my full name, but do not necessarily recommend you do. Neither do I recommend using your student number. You can use a pseudonym, so long as it does not sound too silly.
You can change your GitHub username by [following the instructions on docs.github.com.](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-user-account-settings/changing-your-github-username)


### Tasks (40%)

Complete all tasks in a notebook called `trigrams.ipynb` in your repository.
The tasks should be completed without the use of external libraries or APIs.
However, you can use of anything in a standard library.

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

Select five free English-language works from [Project Guternberg](https://www.gutenberg.org/) and use them to create a model of the English language as follows.
Remove all characters except for (ASCII) letters (uppercase and lowercase), full stops, and spaces.
Make all letters uppercase.

Next create a trigram model by counting the number of times each sequence of three characters (each trigram) appears.
You can design your own data structure for storing the results but explain your design and its rationale in your answer.

For example, the sentence: `It is what it is.` would become `IT IS WHAT IT IS.`
This will give a model like `{'IT ': 2, 'T I': 3, ' IS': 2, ' IS': 2, 'IS ': 1, ...}`.


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
Use **HTML** and **CSS** for the interface and plain **JavaScript** for the chatbot logic.
Name the main page `index.html` and place it in the root of your repository. 
Store your CSS in a file called `style.css`, also in the root directory.

Place your chatbot logic in a file named `eliza.js` in the same location.
The chatbot interface should include a text box for user input and an area to display ELIZA's responses.

Ensure your code is well-commented and that your interface introduces and explains how your chatbot works.


## Marking Scheme

Each component will be graded based on the following four categories, each of equal weight. 
Remember, your repository is what will be evaluated.
It should demonstrate evidence of the criteria outlined for each category.
The examiners' overall impression of the submission may affect marks in each category.

You are expected to make steady progress on the assessment throughout the semester, and this should be reflected in your commit history.
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
 - Appropriate README for repository.
  
### Consistency
 - Tens of commits, each representing a reasonable amount of work.
 - Literature, documentation, and code evidencing work on the assessment.
 - Evidence of reviewing and refactoring.


## Advice

In open-style assessments like this one, students may find it challenging to navigate the freedom provided.
Guided by the module's materials, you will need to determine where and how to begin, what content is relevant for your submission, how much is appropriate, and how to personalize your work.
This level of autonomy is intentional and meant to foster independent thinking and decision-making skills.

Companies value graduates who can take initiative, work autonomously, and make design decisions with minimal guidance.
We assume you have a reasonable knowledge of programming and an ability to source your own information.
You need a plan; you cannot just start coding straight away.

Remember you must adhere to ATU policies and regulations.
You can view these on the [Student Hub](https://studenthub.atu.ie).
Pay special attention to the Policy on Plagiarism and the Student Code.
If you have any questions about what is permitted, email the lecturer.