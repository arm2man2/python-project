# python-project
####################################################################################################################################################################################


Problem 1: Almond Cashew


hist = {}

def Function_(Number, b):
    if Number in hist.keys():
        return hist[Number]
    for j in b:
        if Number % j == 0:
            if j % 2 == 0:
                hist[Number] = True
                return True
            nn = Number // j
            if not Function_(nn, b):
                hist[Number] = True
                return True
    hist[Number] = False
    return False

Number, s = (int(j) for j in input().split())
b = [int(j) for j in input().split()]

if Function_(Number,b):
    print("almond")
else:
    print("chashew")

====================================================================================================================================================================================



Examples:

Input 1: 
10 3
5 1000000000000000000 2

Output 1:
Almond

Input 2:
718791247583033625 6
3 5 17 19 23 37

Output 2:
Almond

Input 3:
328360141446962625 7
5 9 11 35 57 165 345

Output 3:
Cashew

####################################################################################################################################################################################
problem 2:=

import math
numDiameter,velocity=input().split()
numDiameter=int(numDiameter)
velocity=int(velocity)
diameter=list(map(int,input().split()))
maxE=max(diameter)
gx=[]
gx.append(0)
gx.append(1)
gx.append(2)

def isPrime(p):
    for i in range(2,math.floor(math.sqrt(p)+2)):
     if(p%i==0):
        return False
    
    return True
for i in range(3,maxE+3):
    gx.append(gx[i-1]+gx[i-2])
ans=0
for i in diameter :
    if isPrime(i):
        ans+=gx[i]%velocity
print(ans%velocity)
====================================================================================================================================================================================================================
Examples:

Input 1: 
3 1000000007
3 5 7

Output 1:
32

Input 2:
4 1000000007
31 59 77 4

Output 2:
10923393

Input 3:
5 1000000007
13 15486833 23 17 8731

Output 3:
467275880

 
    

####################################################################################################################################################################################

Problem 3: Same Old Array

def Function_contin(l_a,n1):
    S_set=set()
    for i in range(0,n1):
        for j in range(i,n1+1):
            sum=0
            for k in range(i,j):
                sum=sum+l_a[k]
            S_set.add(sum)
    return len(S_set)-1




Number=int(input())
List_a=[]
for i in range(0,Number):
    List_a.append(int(input()))
print(Function_contin(List_a,Number))
====================================================================================================================================================================================================================
Example 1:

Input:
5
1 2 3 5 7

Output:
13

Example 2:

Input:
15
1 2 3 5 7 11 13 17 19 23 29 31 37 41 43

Output:
98

 
 


####################################################################################################################################################################################


Problem 6 - File Reduce

arman-lenovo-520:Problem6 arman$ ls
Problem6.R	sample.csv
arman-lenovo-520:Problem6 arman$ RScript Problem6.R sample.csv 3
arman-lenovo-520:Problem6 arman$ ls
Output_0	Problem6.R	sample.csv
arman-lenovo-520:Problem6 arman$ cat Output_0 	
"type"	"symbol"		"price"	"quantity"		"expirydate"		"strikeprice"	"amendtime"			  "id"		"parentid"
"P"		  "ICICIBANK"	1100		100			      20121210			   120			    "20121209103030		1237		1234
"P"	  	"ICICIBANK"	1100		100			      20121210			   120			    "20121209103030		1241		1234
"T"	  	"ICICIBANK"	1000		100			      20121210		     120		    	"20121209103030		1234		0
arman-lenovo-520:Problem6 arman$ 
```
**In Output0.txt file**<br />
*Tab separated variables*<br />
"type"	"symbol"		"price"	"quantity"		"expirydate"		"strikeprice"	"amendtime"			  "id"		"parentid"<br />
"P"		  "ICICIBANK"	1100		100			      20121210			   120			    "20121209103030		1237		1234<br />
"P"	  	"ICICIBANK"	1100		100			      20121210			   120			    "20121209103030		1241		1234<br />
"T"	  	"ICICIBANK"	1000		100			      20121210		     120		    	"20121209103030		1234		0<br />
====================================================================================================================================================================================

Sample file:

	T,ICICIBANK,1000,100,20121210,120,20121209103030,1234,0

	T,AXISBANK,1000,100,20121210,120,20121209103031,1235,0

	T,SBIBANK,1000,100,20121210,120,20121209103032,1236,0

	P,ICICIBANK,1100,100,20121210,120,20121209103030,1237,1234

	P,AXISBANK,1000,100,20121210,120,20121209103031,1238,1235

	T,ICICIBANK,1000,100,20121210,120,20121209103035,1239,0

	T,.CITIBANK,1000,101,20121210,120,20121209103036,1240,0

	P,ICICIBANK,1100,100,20121210,120,20121209103030,1241,1234

	P,ICICIBANK,1100,100,20121210,120,20121209103035,1242,1239

Write an optimal program that takes a file and an integer X as command
line arguments and splits the input file into maximum number of smaller
files such that each smaller file contains a minimum of X number of records
with the condition that all the children of a parent record should be in
the same file as the parent record. Each smaller file should be named as
output_<n>.txt where value n is  1, 2, 3 ... N (maximum number of files
possibles)

For e.g. if the sample file above is split into files containing minimum
two rows each, then records -

	T,ICICIBANK,1000,100,20121210,120,20121209103030,1234,0

	P,ICICIBANK,1100,100,20121210,120,20121209103030,1237,1234

	P,ICICIBANK,1100,100,20121210,120,20121209103030,1241,1234
	
should be in one file.

##############################################################################################################################
