## Users

- All users
  - Owners
  - Contributors

## User Stories

- CRUD a project
  - Owner only
- Create tasks for a project
  - Owner only
  - Start Point & Priority
    - Number attribute and sort them
- CRUD status of a task
  - Planning
  - In Progress
  - Done
- Project Progress
  - Maintain a project backlog -- All the tasks
    - Owner only
  - Maintain release backlog -- All the tasks in Next release
    - Owner
  - Maintain a sprint backlog -- All the tasks in Next development cycle
- Burndown Chart

## Database Scheme

```json
Table User as U {
  id string
  username string
  email string
}

Table Project as P {
  id string
  name string
  owner user_id
  contributors Array(user_id)
  description string
  taskIds Set(task_ids)
  columns Array(column_ids)
}

Table Task as T {
  id string
  title string
  discription string
  backlogType Oneof(project, release, sprint)
  priority int
  storyPoint int
  statusId string
  assignee user_id
}

Table Column as C {
  id string
  name string
  description string
  taskList LinkedList(task_id)
  // We should re-think about this part
  // How we will keep track of the position of the task in column
}

Ref: P.taskIds > T.id
Ref: T.statusId > C.id
Ref: P.columns > C.id
Ref: U.id > P.contributors
Ref: P.taskIds > T.id
Ref: C.taskList > T.id
```
