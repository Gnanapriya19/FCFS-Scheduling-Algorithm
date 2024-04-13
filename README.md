IMPLEMENTATION OF FCFS SCHEDULING ALGORITHM
 AIM
To write a C program to implement First Come First Serve scheduling algorithm.
DESRIPTION:
For FCFS scheduling algorithm, read the number of processes/jobs in the system, their CPU burst times. The scheduling is performed on the basis of arrival time of the processes irrespective of their other parameters. Each process will be executed according to its arrival time. Calculate the waiting time and turnaround time of each of the processes accordingly.
.ALGORITHM:
Step 1: Start the program.
Step 2: Get the input process and their burst time.
Step 3: Sort the processes based on order in which it requests CPU.
Step 4: Compute the waiting time and turnaround time for each process. Step 5: Calculate the average waiting time and average turnaround time. Step 6: Print the details about all the processes.
Step 7: Stop the program.
PROGRAM
PROGRAM:
#include<stdio.h> Void main()
{
int bt[50],wt[80],at[80],wat[30],ft[80],tat[80]; int i,n;
float awt,att,sum=0,sum1=0; char p[10][5];
printf("\nenter the number of process	"); scanf("%d",&n);
printf("\nEnter the process name and burst-time:"); for(i=0;i<n;i++)
scanf("%s%d",p[i],&bt[i]); printf("\nEnter the arrival-time:"); for(i=0;i<n;i++)
scanf("%d",&at[i]); wt[0]=0;
for(i=1;i<=n;i++)
wt[i]=wt[i-1]+bt[i-1]; ft[0]=bt[0]; for(i=1;i<=n;i++)
ft[i]=ft[i-1]+bt[i]; printf("\n\n\t\t\tGANTT CHART\n"); printf("\n	\n");
for(i=0;i<n;i++)
printf("|\t%s\t",p[i]); printf("|\t\n");
printf("\n	\n");
printf("\n"); for(i=0;i<n;i++)
printf("%d\t\t",wt[i]);
printf("%d",wt[n]+bt[n]); printf("\n	\n");
printf("\n"); for(i=0;i<n;i++)
wat[i]=wt[i]-at[i]; for(i=0;i<n;i++)
tat[i]=wat[i]-at[i];
printf("\n FIRST COME FIRST SERVE\n");
printf("\n Process Burst-time Arrival-time Waiting-time Finish-time Turnaround- time\n");
for(i=0;i<n;i++)
printf("\n\n	%d%s	\t	%d\t\t	%d	\t\t	%d\t\t	%d	\t\t
%d",i+1,p[i],bt[i],at[i],wat[i],ft[i],tat[i]); for(i=0;i<n;i++)
sum=sum+wat[i]; awt=sum/n;
for(i=0;i<n;i++)
sum1=sum1+bt[i]+wt[i]; att=sum1/n;
printf("\n\nAverage waiting time:%f",awt); printf("\n\nAverage turnaround time:%f",att);
}
OUTPUT:
enter the number of process 3
Enter the process name and burst-time: p1 2
p2 3
p3 4
Enter the arrival-time:0 1 2 GANTT CHART

|	p1	|	p2	|	p3	|	

0		
2		
5		
9	

FIRST COME FIRST SERVE	
Process	Burst-time	Arrival-time	Waiting-time	Finish-time	Turnaround-time
p1	2	0	0	2	2
p2	3	1	1	5	4
p3	4	2	3	9	7
Average waiting time:1.333333 Average turnaround time:5.333333 
