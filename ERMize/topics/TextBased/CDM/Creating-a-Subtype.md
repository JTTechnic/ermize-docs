# Creating a Subtype

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
    description DESC
    start_date SDATE <M>
    end_date EDATE <M>
    start_time STIME
    end_time ETIME
}

User -|--|<|{ UserEmail : EmailOfUser
User -|--o<|{ TaskList : TaskListOfUser
TaskList }o--o{ User : SharedTaskList
TaskList -|--o<|{ Task : TaskOfTaskList
Task }o--o- User : AssignedTo
```