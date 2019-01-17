# <img src="http://www.rice.edu/_images/rice-logo.jpg" width=180> Comp427, Spring 2018, Homework 1
## Rational Paranoia
The homework specifications, as well as the corresponding course slide decks,
can be found on the [Comp427 Piazza](https://piazza.com/class/jqifhp864b37ju).
This assignment is due **Thursday, January 17 at 6 p.m.**

You will do this homework by editing the _README.md_ file. It's in
[MarkDown format](https://guides.github.com/features/mastering-markdown/)
and will be rendered to beautiful HTML when you visit your GitHub repo.

## Student Information
Please also edit _README.md_ and replace your instructor's name and NetID with your own:

_Student name_: Rishu Harpavat

_Student NetID_: rh34

Your NetID is typically your initials and a numeric digit. That's
what we need here.

_If you contacted us in advance and we approved a late submission,
please cut-and-paste the text from that email here._

## Problem 1
- Scenario: Stadium
- Assumptions:
  - Since we're the overseer(s) of the stadium, we have full control over all aspects of said stadium, including:
    * Access to restricted areas (locker rooms, VIP boxes, etc.)
    * Electronic hardware and data storing information about the team
  - We need to protect the stadium from physical damage as well as the team and/or any university officials from harm (while they are inside the stadium)
- Assets:
  - Restricted areas (locker rooms, VIP boxes, etc.): We need to protect the team as well as any visiting university officials from harm.
  - Confidential data: The stadium's systems might contain confidential data about things such as:
    * Player information (health, contact, etc.)
    * Team information (itineraries, play analysis, playbooks, etc.)
  - Stadium property: The stadium might be storing expensive training equipment, players' belongings, and other valuables; we'd want to protect these from theft.
  - The people involved - players, coaches, and university officials
- Threats:
  - Spies from competing schools: Rival schools may send spies in to infiltrate the stadium in order to:
    * obtain valuable team/player information that would allow them to anticipate their play strategy
    * sabotage the team in some manner (physically harm a player and render them unable to play subsequent games)
  - Overzealous fans: They might try and find players in locker rooms to get autographs and _accidentally_ walk away with personal belongings
- Countermeasures:
  - Biometric scanners controlling access to restricted areas 
    * Given that this is one of the top football teams in the nation, they probably generate enough revenue that we can afford this investment
    * Restricting access to certain areas is a solid first line of defense against an unauthorized accessor
  - Strong encryption on any confidential data, as well as strong login credentials for accessing the machine the data is stored on to begin with
    * Should not be super costly
    * Benefits of good encryption are very clear - without the key, it's _very_ hard to break, so even if someone manages to obtain the data, it's useless

## Problem 2
- Scenario: Grading
- Assumptions:
  - We have complete control of the grading system.
  - Grading system is online (submissions are done through an online portal) and are routed to and stored on a secure server.
  - Access to student submissions and the scoring portal is online as well, done through some web app.
- Assets:
  - Student submissions: Each student submission is their own intellectual property. We don't want either:
    * a student getting a hold of someone else's submission so they can cheat off of it, or
    * some external third party getting a hold of student submissions for a project that could potentially have real-world applications
  - Student grades: Each student has some online gradebook, which we only want instructors and that particular student to have access to.
    * Instructors need to have both read + write access.
    * Student only should have read access.
- Threats:
  - A student trying to alter their grades to be better.
  - A student trying to intercept/access other students' submissions in order to improve their own submission.
  - Some external third party trying to gain access to confidential student data without authorization.
- Countermeasures:
  - Ensure the secure server storing all the data is physically located somewhere that students (and external third parties) cannot access it - this prevents them from copying all the data onto a drive and brute-forcing it elsewhere.
    * Might be somewhat expensive
    * But is an excellent start towards securing data - network access can be restricted to a much greater degree than hardware access can
  - Strong permissions on the server/mechanism used to access this data - a student's login should only allow them to access their own file storage.
  - Strong read/write permissions on the gradebook - students should only have read access, while instructors need both read and write access.
  - Strong authentication - a central authentication service that requires a strong password on the user end
  - A system that monitors login attempts
    * If more than a certain number of attempts are made within a certain time limit, lock the account
    * Prevents anyone from attempting to brute-force a password

## Problem 3
- Scenario: As head TA for a class, you create a grading assignment spreadsheet for a class and send it to all the TAs involved in the class.
- Assumptions:
  - The spreadsheet is being shared via a link, so potentially anyone with the link might have access.
  - TAs only have access to grade students they were assigned to.
- Assets:
  - The contents of the spreadsheet - each TA is assigned to grade a few students.
- Threats:
  - TAs who might want to reassign some of their students to other TAs to lessen their workload.
  - Students who might want to reassign themselves to TAs known for being 'easy' graders.
- Countermeasures:
  - Restrict edit access on the sheet to just yourself
    * Easy to do
    * Makes it a little more inconvenient for TAs to mark when they're done grading, but they can live with that
  - Create an online form where a TA can submit their name + the name of the student they've finished grading
    * Fairly easy to do
    * Bogus submissions are easy to check - the only thing an attacker could potentially do is put the wrong information in the form. However, this information is easy to verify - if a form submission marks a student as graded but the student doesn't actually have a grade, it can be discarded. Similarly, if a TA's name is submitted along with the name of a student they were not assigned, that submission can be discarded since they only have access to grade the students they were assigned.

