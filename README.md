This Distributed task master is composed of several key components that work together to schedule and execute tasks. Here's a brief overview of each component:

Scheduler: The scheduler is the front-end server of the system. It receives tasks from the clients and schedules them for execution.

Coordinator: The coordinator is responsible for selecting the tasks that need to be executed at a given instant based on their schedules. The coordinator is also responsible for handling worker registration and decommissioning. It selects the tasks to be executed and distributeds them across the available workers to execute.

Worker: Workers are responsible for executing the tasks assigned to them by the coordinator. Once a task is completed, the worker reports the status back to the coordinator. Workers automatically register with the coordinator and communicate their "liveness" via heartbeats.

Client: Clients submit tasks to the scheduler for execution using an HTTP endpoint. They can also query the scheduler for the status of their tasks.

Database: A PostgreSQL database is used to store information about tasks such as their ID, task information, scheduling information, completion information. The coordinator and scheduler interact with the database to retrieve and update task information.

Each of these components is implemented as a separate service, and they communicate with each other using gRPC. This architecture allows for high scalability and fault tolerance.
