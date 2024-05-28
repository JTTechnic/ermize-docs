# Subtype Options

- [Exclusive](#exclusive)
- [Complete](#complete)
- [Combining Options](#combining-options)

## Exclusive

### Code

```
entity User {
    username <PI> USRNAME <M>
}

entity UserEmail {
    email <PI> EMAIL <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

entity Task {
    title <PI> TITLE <M>
    task_type TTYPE <M>
    description DESC
    start_date SDATE <M>
    end_date EDATE <M>
    start_time STIME
    end_time ETIME
}

entity SubTask {}

User -|--|<|{ UserEmail : EmailOfUser
User -|--o<|{ TaskList : TaskListOfUser
TaskList }o--o{ User : SharedTaskList
TaskList -|--o<|{ Task : TaskOfTaskList
Task }o--o- User : AssignedTo
Task -|--o<|{ SubTask : SubTaskOfTask

Task <--(X)-- SubTask : TypeOfTask
```

### Output

![](subtypes-exclusive.svg)

## Complete

### Code {id="code_1"}

```
entity User {
    username <PI> USRNAME <M>
}

entity UserEmail {
    email <PI> EMAIL <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

entity Task {
    title <PI> TITLE <M>
    task_type TTYPE <M>
    description DESC
    start_date SDATE <M>
    end_date EDATE <M>
    start_time STIME
    end_time ETIME
}

entity SubTask {}

User -|--|<|{ UserEmail : EmailOfUser
User -|--o<|{ TaskList : TaskListOfUser
TaskList }o--o{ User : SharedTaskList
TaskList -|--o<|{ Task : TaskOfTaskList
Task }o--o- User : AssignedTo
Task -|--o<|{ SubTask : SubTaskOfTask

Task <--(__)-- SubTask : TypeOfTask
```

### Output {id="output_1"}

![](subtypes-complete.svg)

## Combining Options

### Code {id="code_2"}

```
entity User {
    username <PI> USRNAME <M>
}

entity UserEmail {
    email <PI> EMAIL <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

entity Task {
    title <PI> TITLE <M>
    task_type TTYPE <M>
    description DESC
    start_date SDATE <M>
    end_date EDATE <M>
    start_time STIME
    end_time ETIME
}

entity SubTask {}

User -|--|<|{ UserEmail : EmailOfUser
User -|--o<|{ TaskList : TaskListOfUser
TaskList }o--o{ User : SharedTaskList
TaskList -|--o<|{ Task : TaskOfTaskList
Task }o--o- User : AssignedTo
Task -|--o<|{ SubTask : SubTaskOfTask

Task <--(_X_)-- SubTask : TypeOfTask
```

### Output {id="output_2"}

![](subtypes-excl-and-comp.svg)