# Abl Schools - Student Grouping Analysis Assignment

Hi there! We're ecstatic that you're interested in working with us at Abl. To get a better idea of your current data science skills, we'd like for you to complete a challenge - perform an analysis on a set of data to answer a set of client questions.

The expected deliverables from this assignment are:

  1. Your answers to the 2 questions in the challenge below
  2. All code necessary to take the three provided .csv files (see below) as input, and output the same answers

For some loose requirements on how to prepare your submission, imagine yourself as a member of our team. This means that:

* You'll need to explain your approach and findings to some people without backgrounds in data science.
* Other members of the team will need to read your code.
* They will expect to be able to reproduce your results.
* They (or you) might need to do something similar in the near future.
* They don't have a license for paid statistical software like SAS, SPSS or Stata. Please use something free like Python or R.

The goal is for you to spend about 90 minutes on this assignment, so we do not expect perfection. That said, it can be helpful if you note when and where you took shortcuts or might want to do more if you had more time.

Once you have completed your solution, please email your answers and code attachments to codechallenge@ablschools.com.  If you have any questions about the challenge or submission process, feel free to email us.

## Evaluation
We'll be evaluating this homework on the following criteria:
- Problem focus and clarity of results
- Responsible and rigorous use of data and statistics
- Reproducible and maintainable code, given the time allowed


## The Challenge

One of our partner schools, Solar System Middle School, has provided us with a set of data consisting of teachers, students, student groupings, and quiz scores. The teachers are trying a new strategy for having peer support structures in their classroom. After each quiz the students are re-grouped by their teacher (either manually or with a special tool we have provided) into one of four types of groups:   

* SimGroup - Teams of students with similar performance levels
* DivGroup - Teams of students with a diverse range of performance levels (each team is comprised of roughly 1/3 high, 1/3 mid, 1/3 low performing students)
* Random - Random teams
* Manual - Manually assigned teams

For the sake of this challenge all of the quizzes are scored on a percentage basis and the most recent quiz score is how we decide on a performance level. The levels are simply defined as:
* High - top ⅓ of students on the last quiz
* Mid - middle ⅓ of students on the last quiz
* Low - bottom ⅓ of students on the last quiz

If a student does not have a score for any reason they will be put in the “Mid” tier. If a teacher were to group the students into a “SimGroup” that would indicate that the students with a “high” score on the previous test would be in a group together, the “mid” score students would be together in a group, and the “low” score students would work together in a group until the next quiz.
Given this data, our partner school would like some guidance on how to evaluate the success of different groupings and if there is feedback that they can give to their teachers. The feedback could be structured as general advice for all teachers or specific feedback to an individual teacher.

Here are the two questions that our partner school indicated they are interested in knowing more about:
1. What groups of students, based on common attributes, are consistently underperforming on their quizzes?
2. Are there any types of groups, e.g., manual groups vs calculated (SimGroup, DivGroup, Random), that you would recommend teachers use or avoid using?


## The Data

We've provided you with CSVs in the [the data directory](data/) representing three tables - `students`, `groups`, and `scores`.  

The data carries several pieces of metadata on each table.  Here are the tables and their column descriptions:

### Students

<table>
  <thead>
    <tr>
      <th>column</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>StudentId</td>
      <td>A unique id for each student</td>
    </tr>
    <tr>
      <td>Race</td>
      <td>A string representing the Race of the student (recall that our partner school is "Solar System Middle School", so some of these races may be unfamiliar to you)</td>
    </tr>
    <tr>
      <td>Gender</td>
      <td>A string representing the student's gender - currently categorized as "M", "F", or "NB" (Male, Female, Non-Binary)</td>
    </tr>
    <tr>
      <td>ClassId</td>
      <td>A unique id for the class the student attends. A class is simply a grouping of students and teacher who meet together for instruction</td>
    </tr>
    <tr>
      <td>Teacher</td>
      <td>A string representing the teacher who leads the class (each Teacher in our school instructs two classes of students)</td>
    </tr>
  </tbody>
</table>

### Groups

<table>
  <thead>
    <tr>
      <th>column</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>GroupType</td>
      <td>The type of grouping (SimGroup, DivGroup, Random, Manual) that the teacher used prior to the quiz indicated in the QuizNumber column</td>
    </tr>
    <tr>
      <td>QuizNumber</td>
      <td>An integer from 1 to 10 indicating which quiz the grouping was used for (these quizzes were given weekly in order from 1 to 10 over the course of the semester)</td>
    </tr>
    <tr>
      <td>ClassId</td>
      <td>A unique id (integer) relating to which class the grouping relates to (can join to the Student ClassId column)</td>
    </tr>
  </tbody>
</table>

### Scores

<table>
  <thead>
    <tr>
      <th>column</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>StudentId</td>
      <td>Which student this score was for</td>
    </tr>
    <tr>
      <td>QuizNumber</td>
      <td>Which quiz this score was for</td>
    </tr>
    <tr>
      <td>Score</td>
      <td>From 0.0 (worst) to 100.0 (best), the student's score on a quiz measuring their aptitude in the given subject.  This test is taken after a week of using the grouping strategy indicated in the groups table for this quiz number and student</td>
    </tr>
  </tbody>
</table>
