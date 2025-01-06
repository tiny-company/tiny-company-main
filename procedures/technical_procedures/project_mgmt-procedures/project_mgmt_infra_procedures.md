# Project Management

[&larr; Get back to the index](../readme.md)

## Description

Find here all the project management methods used in the infrastructure team.

We are using Agile method "[Scrum](https://scrumguides.org/)" to manage our project and using the tool : "[Open-project](https://www.openproject.org/fr/)".

See below in details what are the steps in a project and how we manage it.

- [Project phase](#project-phase) :
    - [Brainstorming](#brainstorming)
    - [Prepare](#prepare)
    - [Design](#design)
    - [Implement](#implement) :
        - [Sprint phase](#sprint) :
            - [Plan](#plan)
            - [Do](#do)
            - [Act](#act)
            - [Check](#check)
    - [Retrospective](#retrospective)

## Project phase

We define 5 phases for our projects :
- [Brainstorming](#brainstorming)
- [Prepare](#prepare)
- [Design](#design)
- [Implement](#implement)
- [Retrospective](#retrospective)

### Brainstorming

**Duration : 1 meeting (1 or 2 hour)**

During this step, the project members and roles are define (who do what ?):
- Define roles :
    - Project Manager : The person in charge for the project.
        - He manage the task priority and follow the progress.
        - He write the project documentation and all the documents about it.
        - He manage the ressources (time, human, material and budget)
        - He organize the meeting and write the report.
    - Product Owner : End client (usually not technical) that define the project goal
        - define the goals and user stories
        - validate the priorities
    - Technical member : developper, devops that create the product
        - define and validate the tasks
        - do the task time estimation


Then the stakeholder (member of the project) defines the boundary of the project :
- goals (user stories) : precise goal to reach.
- tasks : tasks needed to reached the goals / users stories. Define task dependencies, time estimation and priority. Task time estimation could be done in mob (group) with tools like [thunderdome battles](https://thunderdome.dev/battles).
- ideas : just an idea, could be a goal, task, milestone, anything that could be implemented under the project. 

The objective during this phase is to prepare the [Product goal](https://www.scrum.org/resources/what-product-goal), that could be seen as rendering first user stories description with according tasks ([backlog](https://www.scrum.org/resources/what-is-a-product-backlog)).

**Example :**
```
Project Name : Log
Project main goal : create an log centralized system
Project member :
- XXXX (Project Manager)
- XXXX

User stories :
- create a central log system using IAC (3 weeks, priority : 1)
- configure a server to send log to central server (1 weeks, priority : 1)
- automate the deployment and update process using CICD (2 weeks, priority : 5)


Idea list :
- enforce log value using an IDS service
- enforce log using iptables logs
- adding webdrones application log
- configure backup for the log centralized server
- configure log rotation
```

### Prepare

**Duration : 1 or 2 meeting (1 hour), 2 week after the brainstorming phase**

During this phase, all the team refine their ideas about the project or add new one, main goal is to  :
- Conduct research on the solution
- Create some technical POC for solutions (what is the best technical solution ?)
- Refine the goals and tasks (all the goals are valuable ? some user stories could been merged ? review the work time estimation)
- Refine the task duration (usually in work hour, create subtask if needed)
- Migrate some ideas from the Brainstorming phase into user stories or tasks
- Refine the task priority and size according to the [eisenhower matrix](https://asana.com/fr/resources/eisenhower-matrix) with the product owner.


**Example :**
```
What are the existing free, open source solution to create a centralized log system that matches projects need ?
If multiple exist, test them (one is better than another, have more features ...)
Refine the tasks list :

User stories :
- create a central log system using IAC (2 weeks, priority : 1) :
    - [task] create a new server using terraform (5 days)
    - [task] configure the server using ansible (7 days)
- configure a server to send log to central server (1 weeks, priority : 1) :
    - [task] configure syslog system (3 days)
    - [task] configure the grok for the specific logs (2 days)
- automate the deployment and update process using CICD (2 weeks, priority : 5) :
    - [task] automate the deployment using githubaction (5 days)
    - [task] deploy on multiple environnement using terraform (5 days)
```

### Design

**Duration : 1 meeting (1 or 2 hour), 1 week after the Prepare phase**

During this phase every part of the project is validated by the stakeholder :
- user stories and tasks : all the user stories and tasks should be validated.
- Any ideas not migrated into task or user stories is deleted (will not be implemented in the project).
- Budget is validated according to the needs (material, people)
- Project milestone are define

As the user stories and tasks are validated, we can define how long the project will last and how much time it will take to reach each user stories. The project team with the product owner will start creating a macro planning : Define user stories planning (What will be done in which order, like a roadmap or gant diagramm).

### Implement

This is where the sprint cycle occured, where the tasks are planned and done each week. See below in the [sprint part](#sprint) how this process is organized.

#### Sprint

We usually define and plan our work on [sprint(https://www.scrum.org/resources/what-is-a-sprint-in-scrum)] with one week duration. A sprint is the minimum time period to reach product goals (User story).

For each Sprint, we use the PDCA (Plan, Do, Act, Check) method to achieve goals.

##### Plan

Each Monday, we are doing the [Plan part](https://www.scrum.org/resources/what-is-sprint-planning) for the current sprint (week) :
- Define the sprint goal (according to the user stories) : What need to be achieved at the end of the sprint.
- Choose the tasks from the backlog according to the time available, priority and work load.
- For each tasks choosen :
    - Define the main person in charge (who does the task ?) : don't forget to distribute the work load on all the team members.
    - make sure to define the work and status that meets the definition of Done (by what action does the task status will be moved to "Done" ?)
- Review the all task priority with the Project Manager (tasks for all projects) : did task from previous sprint should be done this sprint ? Or did tasks from another project have higher priority ?

**Example :**
```
- task 1 :
    - Time estimated : 2 days
    - Responsible : XXXX
    - Priority : 1
    - Description : create ansible playbook that configure log server to send log to centralized.
```

##### Do

During this phase the work planned previously is done, multiple method could be used to achieve work :
- [pomodoro](https://asana.com/fr/resources/pomodoro-technique)
- [GTD](https://asana.com/fr/resources/getting-things-done-gtd)
- 1-3-5 rule : define 1 big task, 3 medium, 5 little to achieve for the day
- Time blocking : bloc time on task
- Time boxing: bloc time on group of task
- Eat the frog : doing the least pleasant task first

Usually a good practice for each days is to :
- Take time in the morning to define and organize the tasks / goals for the day (daily planning), on 7 hour work :
    - reserve 15 minutes on daily planning
    - reserve 2 work session of 2 hours for big task that need focus.
    - reserve 1 hours on unexpected or small task.
    - reserve 1 hour on recurent task (check monitoring, check mail, inventory, ...)
    - reserve half hour on pause, rest, technological watch ...
    - reserve 15 minutes on daily review ([act phase](#act))

Learn more on [daily planning](https://asana.com/fr/resources/daily-schedule-template)

##### Act

At the end of each day, reponsible (team member on which tasks are assigned) should write a quick recap on their tasks on the project management tools.

##### Check

Each Friday (or last day of the week), we are doing a meeting on the tasks and projects progress of the current week :

- [Sprint retrospective](https://www.scrum.org/resources/what-is-a-sprint-retrospective)

- Write the Progress report :
    - short description : what has recently been done, what is still to do
    - note important event
    - Gather the KPI :
        - [TIME] late time and reason
        - [BUDGET] budget status (over, in, below)
        - [WORK] task status (achieved, not done, for this sprint)
        - [HUMAN-RESSOURCES] people workload, mental health
    - Communicate about the project status : blocked for reason, action needed by smbdy

> Note that the progress report should be concise, quick and easy to read.

**Example :**
```
Progress report n°4 [28/07/2023]
- Progress status : Late on schedule
- Comment : project xxx had task with higher priority and need ressource XXXX.
- Event :
    - [24/07/2023] : test server went down after misconfiguration
- Budget :
    - adding one new server (-180 € per month)
- Tasks status :
    - 5 done / 7
    - 2 delayed / 7
- Workload :
    - XXXX : 13h /week
    - XXXX : 07h /week
    - XXXX : 23h /week
```

### Retrospective

Also called AAR (After Action Review), during this phase the project team review how the project was carried out :
- overall feedack on project :
    - what was positive and negative point
    - What worked well ?
    - What could be improved ?
- The project manager show to the stakeholder the overwall data of the project (report) :
    - task and user stories progress (time, delay and task progress)
    - major event of the project
    - budget status
    - high workload moment

learn more on [AAR guide](https://asana.com/fr/resources/after-action-review-template)

Tools like [thunderDome](https://thunderdome.dev/retros) can help to do this retrospective.


## Sources :

- [RACI charts](https://asana.com/resources/raci-chart)