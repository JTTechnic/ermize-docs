# Naming a Relationship

```
entity User {
    username <PI> USRNAME <M>
}

entity TaskList {
    title <PI> TITLE <M>
    description DESC
}

User -- TaskList : TaskListOfUser
```

![](relationship-with-name.svg)