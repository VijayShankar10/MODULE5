# Ex.No:3  
# Ex.Name: FCFS CPU Scheduling – Waiting Time, Turnaround Time & Averages  

## Date:  

## Aim:  
To implement the FCFS (First-Come, First-Served) scheduling algorithm for a set of processes given only their burst times, and to compute waiting times, turnaround times, and averages.  

## Algorithm:  
1. Start the program.  
2. Read burst times for processes.  
3. Calculate waiting times (WT):  
   - `wt[0] = 0`  
   - `wt[i] = wt[i-1] + bt[i-1]`  
4. Calculate turnaround times (TAT):  
   - `tat[i] = wt[i] + bt[i]`  
5. Compute average waiting time and average turnaround time.  
6. Display the process table and averages.  
7. Stop the program.  

## Program:
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> bt;
    int x;
    while (cin >> x) bt.push_back(x);

    int n = bt.size();
    vector<int> wt(n,0), tat(n,0);

    for (int i = 1; i < n; i++) wt[i] = wt[i-1] + bt[i-1];
    for (int i = 0; i < n; i++) tat[i] = wt[i] + bt[i];

    cout << "Processes   BT time   WT time   TA time\n";
    for (int i = 0; i < n; i++)
        cout << setw(8) << i+1 << setw(8) << bt[i] 
             << setw(8) << wt[i] << setw(8) << tat[i] << "\n";

    double avg_wt = accumulate(wt.begin(), wt.end(), 0.0) / n;
    double avg_tat = accumulate(tat.begin(), tat.end(), 0.0) / n;

    cout << "Average waiting time = " << avg_wt << "\n";
    cout << "Average turn around time = " << avg_tat << "\n";
}
```

## Output:
<img width="861" height="798" alt="image" src="https://github.com/user-attachments/assets/cb196cd3-2dee-476f-9ccb-9adf5024f0be" />

## Result:
```
Input:
6 7 8 9

Output:
Processes   BT time   WT time   TA time
       1       6       0       6
       2       7       6       13
       3       8       13       21
       4       9       21       30
Average waiting time = 10
Average turn around time = 17.5
```
