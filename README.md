# Abl Schools - Student Assessment Analysis Assignment

Hi there! We're ecstatic that you're interested in working with us at Abl. To get a better idea of your current data science skills, we'd like for you to complete a challenge - perform an analysis on a set of data to answer a set of client questions.

The expected deliverables from this assignment are:

  1) Your answers to the 3 questions in the challenge below
  2) All code necessary to take the three provided .csvs (see below) as input, and output the same answers

For some loose requirements on how to write your code, imagine yourself as a member of our team. This means that:

* Other members of the team will need to read your code.
* They will expect to be able to reproduce your results.
* They may want to reuse some of your analyses.
* They (or you) might need to do something similar in the near future.
* They will certainly want to make use of the same data.
* They don't have a license for paid statistical software like SAS, SPSS or Stata. Please use something free like Python, R or SQL.

Once you have completed your solution, please email your answers and code attachments to codechallenge@ablschools.com.  If you have any questions about the challenge or submission process, feel free to email us.

## The Challenge

One of our partner schools has provided us with a set of data consisting of teachers, students, and assessments.  A detailed description of the dataset is given below, but basically, an assessment is an end-of-year standardized test in a specific subject, associated with a given student and a given teacher.  Each assessment is scored, and that score is recorded in the data.  For the sake of this challenge, consider the assessment score to be the only measure of performance that we care about.

Given this data, our partner school would like some guidance on how best to allocate resources.

1) Are there individual students that are performing significantly below average? What about groups of students, based on common attributes?

2) Are there individual teachers whose performance deficit (measured by how well their students are doing on the assessments) is statistically significant and should be addressed? What about groups of teachers, based on common attributes?

3) If we wanted to target gaps in performance strategically, but we have limited resources, which general populations (of students and/or teachers) should we target first?

## The Data

We've provided you with CSVs in the [the data directory](data/) representing three tables - `teachers`, `students`, and `assessments`.  Basically, an assessment is an end-of-year standardized test in a specific subject, associated with a given student and a given teacher.

The data carries several pieces of metadata on each table.  Here are the tables and their column descriptions (not including the `id` columns, which are just unique identifiers):

### Teachers

<table>
  <thead>
    <tr>
      <th>column</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>last_name</td>
      <td>The teacher's last name</td>
    </tr>
    <tr>
      <td>years_teaching</td>
      <td>How many years of experience the teacher has</td>
    </tr>
    <tr>
      <td>student_evaluation</td>
      <td>From 0.0 (worst) to 100.0 (best), a score given by this teacher's students at the end of the year, evaluating their performance</td>
    </tr>
  </tbody>
</table>

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
      <td>last_name</td>
      <td>The student's last name</td>
    </tr>
    <tr>
      <td>birth_date</td>
      <td>In date format (YYYY-MM-DD), the student's birth date</td>
    </tr>
    <tr>
      <td>gender</td>
      <td>A string representing the student's gender - currently categorized as "M", "F", or "NB" (Male, Female, Non-Binary)</td>
    </tr>
    <tr>
      <td>ell</td>
      <td>A boolean flag for whether or not the student is an English Language Learner</td>
    </tr>
    <tr>
      <td>current_grade_level</td>
      <td>An integer representing the student's current grade level</td>
    </tr>
  </tbody>
</table>

### Assessments

<table>
  <thead>
    <tr>
      <th>column</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>subject</td>
      <td>A string with the subject that was assessed in this test, either "math" or "language"</td>
    </tr>
    <tr>
      <td>student_id</td>
      <td>Which student this assessment was for</td>
    </tr>
    <tr>
      <td>grade_level</td>
      <td>What the student's grade level was at the time of the assessment</td>
    </tr>
    <tr>
      <td>teacher_id</td>
      <td>Which teacher taught this subject to this student for the year being assessed</td>
    </tr>
    <tr>
      <td>instructional_minutes</td>
      <td>How many instructional minutes per week this student had in this subject, on average, for the year being assessed</td>
    </tr>
    <tr>
      <td>assessment_year</td>
      <td>What year this assessment is for (this represents the calendar year in which the academic year began, not ended; so for the 2016-2017 academic year, this column will show '2016')</td>
    </tr>
    <tr>
      <td>assessment_score</td>
      <td>From 0.0 (worst) to 100.0 (best), the student's score on a standardized test measuring their aptitude in the given subject.  This test is taken at the end of the academic year, so it reflects the impact of the other values in this table.</td>
    </tr>
  </tbody>
</table>
