# Cardinalities

## Cardinality Types

| Type                          | Syntax                 |
|-------------------------------|------------------------|
| [Zero or One](#zero-or-one)   | <code>-o--</code>      |
| [Exactly One](#exactly-one)   | <code>-&#124;--</code> |
| [Zero or Many](#zero-or-many) | <code>}o--</code>      |
| [One or Many](#one-or-many)   | <code>}&#124;--</code> |

## Zero or One

A user can have zero or one task lists and a task list can have zero or one users.

### Code

<code-block src="ERModel/cardinality-zero-or-one.ermd"/>

### Output

![](cardinality-zero-or-one.png)

## Exactly One

A user always has one task lists and a task list always has one user.

### Code {id="code_1"}

<code-block src="ERModel/cardinality-exactly-one.ermd"/>

### Output {id="output_1"}

![](cardinality-exactly-one.png)

## Zero or Many

A user can have zero or more task lists and a task list can have zero or more users.

### Code {id="code_2"}

<code-block src="ERModel/cardinality-zero-or-many.ermd"/>

### Output {id="output_2"}

![](cardinality-zero-or-many.png)

## One or Many

A user always has one or more task lists and a task list always has one or more users.

### Code {id="code_3"}

<code-block src="ERModel/cardinality-one-or-many.ermd"/>

### Output {id="output_3"}

![](cardinality-one-or-many.png)

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

### Code {id="code_4"}

<code-block src="ERModel/mixed-cardinality.ermd"/>

### Output {id="output_4"}

<note>The result of this output is still a work in progress and may still change.</note>

![](mixed-cardinality.png)