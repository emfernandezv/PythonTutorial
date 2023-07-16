# Problem Solve
## Excercise 1: Printer Queue

You are tasked with implementing a printer queue that simulates a printer processing print jobs. Each print job has a priority, and higher priority jobs should be printed before lower priority jobs. Write a Python program to simulate the printer queue.

````python
class PrintJob:
    def __init__(self, name, priority):
        self.name = name
        self.priority = priority

class PrinterQueue:
    def __init__(self):
        self.queue = []

    def add_job(self, job):
        self.queue.append(job)

    def process_jobs(self):
        #Your code starts here

# Example usage
printer = PrinterQueue()

job1 = PrintJob("Document A", 3)
job2 = PrintJob("Document B", 1)
job3 = PrintJob("Document C", 2)
job4 = PrintJob("Document D", 4)

printer.add_job(job1)
printer.add_job(job2)
printer.add_job(job3)
printer.add_job(job4)

printer.process_jobs()
````
The output should be:
````python
Printing job: Document D
Printing job: Document A
Printing job: Document C
Printing job: Document B
````

Compare your code:

<details markdown="1">
<summary>Solution</summary>
<br>

````python
class PrintJob:
    def __init__(self, name, priority):
        self.name = name
        self.priority = priority

class PrinterQueue:
    def __init__(self):
        self.queue = []

    def add_job(self, job):
        self.queue.append(job)

    def process_jobs(self):
        while self.queue:
            # Sort the jobs based on priority (highest priority first)
            self.queue.sort(key=lambda job: job.priority, reverse=True)

            # Print the job with the highest priority
            job = self.queue.pop(0)
            print(f"Printing job: {job.name}")

# Example usage
printer = PrinterQueue()

job1 = PrintJob("Document A", 3)
job2 = PrintJob("Document B", 1)
job3 = PrintJob("Document C", 2)
job4 = PrintJob("Document D", 4)

printer.add_job(job1)
printer.add_job(job2)
printer.add_job(job3)
printer.add_job(job4)

printer.process_jobs()
````
</details>

[GO BACK - QUEUE Main](1-Queue.md)

[NEXT - QUEUE - Problem 2](1-Queue-Prob-2.md)