# Common Queue Applications
##  Job Scheduling
Job scheduling using a queue is a process where jobs or tasks are managed and executed based on their priority or order of arrival. The queue data structure is used to maintain the order in which the jobs are scheduled. Each job is added to the queue, and the scheduler processes them one by one, typically following a FIFO (First-In-First-Out) approach.

In a job scheduling system, each job has certain attributes such as priority, arrival time, and execution time. Jobs with higher priority or earlier arrival time are usually scheduled before jobs with lower priority or later arrival time.

Here an example:
````python
from queue import Queue

class Job:
    def __init__(self, name, priority):
        self.name = name
        self.priority = priority

# Create a queue to hold the jobs
job_queue = Queue()

# Add jobs to the queue
job_queue.put(Job("Job 1", 3))
job_queue.put(Job("Job 2", 1))
job_queue.put(Job("Job 3", 2))

# Process jobs in the queue
while not job_queue.empty():
    current_job = job_queue.get()
    print("Processing job:", current_job.name)
    # Perform the necessary operations for the job

    # Example: Simulate job execution time
    for i in range(1, 4):
        print("Executing task", i, "of", current_job.name)

    print("Job", current_job.name, "completed\n")

# Output:
# Processing job: Job 1
# Executing task 1 of Job 1
# Executing task 2 of Job 1
# Executing task 3 of Job 1
# Job Job 1 completed
#
# Processing job: Job 2
# Executing task 1 of Job 2
# Executing task 2 of Job 2
# Executing task 3 of Job 2
# Job Job 2 completed
#
# Processing job: Job 3
# Executing task 1 of Job 3
# Executing task 2 of Job 3
# Executing task 3 of Job 3
# Job Job 3 completed
````
In the above example, we create a queue (job_queue) and add three jobs with different priorities to the queue. We then process the jobs in the order they were added to the queue. Each job is printed as it is being processed, and a simulated execution time is shown.

The output demonstrates the FIFO nature of the queue, where the jobs are processed in the same order they were added. This allows for fair scheduling based on arrival time or priority, depending on how the jobs are enqueued.

Job scheduling using a queue ensures that jobs are executed in a predictable order, maintaining fairness and adherence to priority or arrival time criteria.

[GO BACK - QUEUE Main](1-Queue.md)

[NEXT - QUEUE - Problem 1](1-Queue-Prob-1.md)