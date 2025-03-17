This TaskOrch consists of multiple components that collaborate to efficiently schedule and execute tasks. Below is a high-level summary of its key components:

Scheduler: Acts as the front-end server, receiving tasks from clients and scheduling them for execution.

Coordinator: Determines which tasks should be executed at any given time based on their schedules. It also manages worker registration, decommissioning, and distributes tasks to available workers.

Worker: Executes assigned tasks and reports the results back to the coordinator. Workers automatically register with the coordinator and send periodic heartbeats to indicate they are active.

Client: Submits tasks to the scheduler via an HTTP endpoint and can request task status updates.

Database: A PostgreSQL database stores task details, including task IDs, execution schedules, and completion status. Both the scheduler and coordinator interact with it to retrieve and update task information.
