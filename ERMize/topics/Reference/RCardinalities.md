# Cardinalities

## Zero or One

A task list has zero or one users.

### Code

<code-block src="rcardinality-zero-or-one.txt"/>

### Output

<note>This is a concept image and not the actual result of the application.</note>

![](rcardinality-zero-or-one.svg)

## Exactly One

A task list has one user.

### Code {id="code_1"}

<code-block src="rcardinality-exactly-one.txt"/>

### Output {id="output_1"}

<note>This is a concept image and not the actual result of the application.</note>

![](rcardinality-exactly-one.svg)

## Zero or Many

A task list has zero or more users.

### Code {id="code_2"}

<code-block src="rcardinality-zero-or-many.txt"/>

### Output {id="output_2"}

<note>This is a concept image and not the actual result of the application.</note>

![](rcardinality-zero-or-many.svg)

## One or Many

A task list has one or more users.

### Code {id="code_3"}

<code-block src="rcardinality-one-or-many.txt"/>

### Output {id="output_3"}

<note>This is a concept image and not the actual result of the application.</note>

![](rcardinality-one-or-many.svg)

## Mixing Cardinalities

The following applies in this diagram:

- A user always has one or more emails. (EmailOfUser)
- A user has zero or more task lists. (TaskListOfUser)
- A task list has zero or more users that it can be shared with. (SharedTaskList)
- A user has zero or more task lists that have been shared with them. (SharedTaskList)
- A task list has zero or more tasks. (TaskOfTaskList)
- A user has zero or more tasks assigned to them. (AssignedTo)

### Code {id="code_4"}

<code-block src="rmixed-cardinality.txt"/>

### Output {id="output_4"}

<note>This is a concept image and not the actual result of the application.</note>

![](rmixed-cardinality.svg)