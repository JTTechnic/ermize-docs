# Cardinalities

- [Cardinality Types](#cardinality-types)
  - [Zero or One](#zero-or-one)
  - [Exactly One](#exactly-one)
  - [Zero or Many](#zero-or-many)
  - [One or Many](#one-or-many)
- [Mixing Cardinality Types](#mixing-cardinality-types)

## Cardinality Types

| Type                          | Syntax                 |
|-------------------------------|------------------------|
| [Zero or One](#zero-or-one)   | <code>-o--</code>      |
| [Exactly One](#exactly-one)   | <code>-&#124;--</code> |
| [Zero or Many](#zero-or-many) | <code>}o--</code>      |
| [One or Many](#one-or-many)   | <code>}&#124;--</code> |

### Zero or One

A user can have zero or one task lists and a task list can have zero or one users.

```
entity User {
    username <PI> USRNAME <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

User -o--o- TaskList : TaskListOfUser
```

![](cardinality-zero-or-one.svg)

### Exactly One

A user always has one task lists and a task list always has one user.

```
entity User {
    username <PI> USRNAME <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

User -|--|- TaskList : TaskListOfUser
```

![](cardinality-exactly-one.svg)

### Zero or Many

A user can have zero or more task lists and a task list can have zero or more users.

```
entity User {
    username <PI> USRNAME <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

User }o--o{ TaskList : TaskListOfUser
```

![](cardinality-zero-or-many.svg)

### One or Many

A user always has one or more task lists and a task list always has one or more users.

```
entity User {
    username <PI> USRNAME <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

User }|--|{ TaskList : TaskListOfUser
```

![](cardinality-one-or-many.svg)

## Mixing Cardinality Types

The following applies in this diagram:

- A user always has one or more emails. (EmailOfUser)
- An email always has one user. (EmailOfUser)
- A user has zero or more task lists. (TaskListOfUser)
- A task list always has one user. (TaskListOfUser)
- A task list has zero or more users that it can be shared with. (SharedTaskList)
- A user has zero or more task lists that have been shared with them. (SharedTaskList)
- A task list has zero or more tasks. (TaskOfTaskList)
- A task always has one task list. (TaskOfTaskList)
- A task has zero or one users assigned to it. (AssignedTo)
- A user has zero or more tasks assigned to them. (AssignedTo)

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

User -|--|{ UserEmail : EmailOfUser
User -|--o{ TaskList : TaskListOfUser
TaskList }o--o{ User : SharedTaskList
TaskList -|--o{ Task : TaskOfTaskList
Task }o--o- User : AssignedTo
```

![](mixed-cardinality.svg)