# 5. Multiple server with infinite capacity - (M/M/c):(oo/FIFO)
## Name : PRIYANKA.R
## Reg : 212223220081
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](https://user-images.githubusercontent.com/103921593/203238035-1c8109bc-cbf2-4c77-baea-c5b682a752ef.png)

## Procedure :

![image](https://user-images.githubusercontent.com/103921593/203238265-176740b0-eae2-4772-90be-5449869ac9b0.png)




## Experiment:
![image](https://github.com/user-attachments/assets/c72f345d-5a7c-4564-b6cf-7d5419a87e40)


## Program
```
import math
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ser_time=float(input("\nEnter the mean  inter service time of Lathe Machine (in secs) :  "))
Robot_time=float(input("\nEnter the Additional time taken for the Robot (in secs) :  "))
c=int(input("\nNumber of service centre :  "))
lam=1/arr_time
mu=1/(ser_time+Robot_time)
print("\n--------------------------------------------------------------")
print("Multiple Server with Infinite Capacity - (M/M/c):(oo/FIFO)")
print("--------------------------------------------------------------")
print(f"The mean arrival rate per second : {lam:.2f}")
print(f"The mean service rate per second : {mu:.2f}")
rho=lam/(c*mu)
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)
for i in range(0,c):
    sum=sum+(lam/mu)**i/math.factorial(i)
P0=1/sum
if (rho<1):
    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    Ls=Lq+lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print(f"Average number of objects in the system : {Ls:.2f}")
    print(f"Average number of objects in the conveyor : {Lq:.2f}")
    print(f"Average waiting time of an object in the system : {Ws:.2f} secs")
    print(f"Average waiting time of an object in the conveyor : {Wq:.2f} secs")
    print(f"Probability that the system is busy : {rho:.2f}")
    print(f"Probability that the system is empty : {(1-rho):.2f}")
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("--------------------------------------------------------------")
```

## Output :
![image](https://github.com/user-attachments/assets/d0c83bf0-e570-42a2-81cc-15f4afb08399)

## Result : 
Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
