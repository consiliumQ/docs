# Features check list for the project

## Frontend

### Apollo client

- [ ] set up
  - [x] connect to backend and react
  - [ ] authentication
  
### Components (site map)

- [ ] Kanban Board
  - [x] Drag and drop
    - [x] DnD card on card
    - [x] DnD card on list (when drag card on an empty list / not on a card)
    - [x] DnD list on list
    - [x] Trigger graphql mutation when drop the card

- [ ] Kanban Columns
  - [x] Add column
    - [x] Add column form UI
    - [x] Trigger graphql mutation
  - [ ] Delete column
    - [ ] Delete column button
    - [ ] Trigger graphql mutation
  - [ ] Update column
    - [ ] Update column form UI
    - [ ] Trigger graphql mutation

- [ ] TaskCard
 - [x] Card UI
 - [x] Update Card form UI
 - [x] Delete Button alert
 - [x] Add Task Card form ui
 - [ ] Trigger graphql mutation
 
- [ ] SideBar 
  - [x] SideBar Dummy UI
  - [ ] render based on authentication
  - [ ] query graphql for data

- [ ] Header
  - [ ] Select projects drop down

### Pages

- [ ] KanbanBoard Page
  - see components

- [ ] Project Dashboard
  - [ ] Show column details (name, description, number of tasks...)
    - [ ] should be able to add column here as well
  - [ ] Show tasks details
    - [ ] Aggregate tasks by backlog category
    - [ ] Aggregate/sort tasks by story points / priority
    - [ ] should be able to add task here as well
  - [ ] Show burndown chart

- [ ] User Dashboard
  - [ ] Show user info
  - [ ] Show project details
  - [ ] Should be able to add project here

## Backend

### Databas CRUD

- [ ] Users
  - [x] getAll
  - [x] gretById
  - [x] createOne
  - [ ] update
  - [ ] delete
- [x] Projects
  - [x] getAll // probably not needed
  - [x] getById
  - [x] getByUserId
  - [x] getByColumnId
  - [x] createOne
  - [x] updateOne
  - [x] deleteOne
- [x] Columns
  - [x] gertById
  - [x] createOne
  - [x] updateOne
  - [x] deleteOne
- [x] Tasks
  - [x] getById
  - [x] createOne
  - [x] updateOne
  - [x] deleteOne
- [x] Other
  - [x] config
  - [x] seeding // extends to seed demo data

### Apollo Server

- [ ] resolvers
  - [x] User
  - [x] Project
  - [x] Column
  - [x] Task
  - [ ] Query // blocked by authentication
    - [x] projects (work around)
    - [x] project (work around)
    - [x] task
    - [x] user
    - [ ] burndown chart
  - [ ] Mutation // majorly blocked by authentication
    - [x] addProject
    - [x] udpateProject
    - [x] deleteProject
    - [x] addTask
    - [x] udpateTask
    - [x] deleteTask
    - [x] addColumn
    - [x] udpateColumn
    - [x] deleteColumn
- [x] schema
- [ ] authentication
  - [ ] username & password
  - [ ] social media / 3rd party account
  
### Redis

> As little as it look, I suspect some hidden complexity is waiting

- [ ] Set up (create server & connect to apollo server)
- [ ] Write cache data
  - [ ] Cache all projects of a user when user is logged in, by project id
  - [ ] Update cache when user fire the mutation and change the database
- [ ] Read cache data
  - [ ] Read data with desirable shape
