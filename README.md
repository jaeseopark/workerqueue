# workerqueue

A thread-based worker queue

## Installation

```bash
pip install workerqueue
```

## Usage

```python
from workerqueue import WorkerQueue
from time import sleep

def myfunc(arg1, arg2):
    print(f"{arg1}*2={arg2}")
    sleep(0.5)

myqueue = WorkerQueue(myfunc, thread_count=2)

for i in range(10):
    myargs = i, i*2
    myqueue.put(myargs)

sleep(1)

print("Calling join()...")
myqueue.join()

print("Finished processing")
```
