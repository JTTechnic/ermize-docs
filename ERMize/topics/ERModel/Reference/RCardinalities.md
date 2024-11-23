# Cardinalities

## Zero or One

A task list has zero or one users.

### Code

<code-block src="ERModel/rcardinality-zero-or-one.ermd"/>

### Output

![](rcardinality-zero-or-one.png)

## Exactly One

A task list has one user.

### Code {id="code_1"}

<code-block src="ERModel/rcardinality-exactly-one.ermd"/>

### Output {id="output_1"}

![](rcardinality-exactly-one.png)

## Zero or Many

A task list has zero or more users.

### Code {id="code_2"}

<code-block src="ERModel/rcardinality-zero-or-many.ermd"/>

### Output {id="output_2"}

![](rcardinality-zero-or-many.png)

## One or Many

A task list has one or more users.

### Code {id="code_3"}

<code-block src="ERModel/rcardinality-one-or-many.ermd"/>

### Output {id="output_3"}

![](rcardinality-one-or-many.png)

## Mixing Cardinalities

The following applies in this diagram:

- A user always has one or more emails. (EmailOfUser)
- A user has zero or more task lists. (TaskListOfUser)
- A task list has zero or more users that it can be shared with. (SharedTaskList)
- A user has zero or more task lists that have been shared with them. (SharedTaskList)
- A task list has zero or more tasks. (TaskOfTaskList)
- A user has zero or more tasks assigned to them. (AssignedTo)

### Code {id="code_4"}

<code-block src="ERModel/rmixed-cardinality.ermd"/>

### Output {id="output_4"}

![](rmixed-cardinality.png)