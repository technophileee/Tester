#greedy algo for job sequencing with deadline
def jobSequencing(jobs):
    jobs.sort(key = lambda x:x[2], reverse=True)
    maxDeadline = max(job[1] for job in jobs)
    slots = [-1] * maxDeadline
    profit = 0

    for job in jobs:
        for i in range(job[1]-1, -1, -1):
            if slots[i] == -1:
                slots[i] = job[0]   #jobs[0] ni job[0]
                profit += job[2]    #jobs[0] ni job[2]
                break
    return slots, profit

jobs = [
    ('J1',2,100),
    ('J2',1,19),
    ('J3',2,27),
    ('J4',1,25),
    ('J5',3,15),
]
result, maxProfit = jobSequencing(jobs)
print("Scheduled jobs : ", result)
print("Max Profit : ",maxProfit)

#mene edit kiya haiiiiiiiiiiii