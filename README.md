# Assignment-9

# Install simpy
# pip install simpy

import simpy


print("SimPy installed successfully!")

def process(env):
    print("Process starts at", env.now)
    yield env.timeout(5)
    print("Process ends at", env.now)

env = simpy.Environment()
env.process(process(env))
env.run()

print("-" * 30)

def customer(env):
    print("Customer arrives at", env.now)
    yield env.timeout(3)
    print("Customer served at", env.now)

env = simpy.Environment()
env.process(customer(env))
env.run()

print("-" * 30)


def process1(env):
    yield env.timeout(2)
    print("Process 1 completed at", env.now)

def process2(env):
    yield env.timeout(4)
    print("Process 2 completed at", env.now)

env = simpy.Environment()
env.process(process1(env))
env.process(process2(env))
env.run()

print("-" * 30)

 Average Waiting Time
wait_times = [2, 4, 3, 1]

average = sum(wait_times) / len(wait_times)

print("Average waiting time:", average)

