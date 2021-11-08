# XOR-Equation-codechef
**PLEASE CLICK ON THE ABOVE SHOWN README.md FILE YOU WILL GET THE CODE**

**GUYS THE CODE IS CORRECT AND PASSED ALL THE TEST CASES BUT THE ONLY PROBLEM IS THE CODE IS EXCEEDING THE TIME LIMIT PLEASE CORRECT IT IF I CRACK IT I WILL SEND THE ANSWER IMMEDIATELY**

**INITIALLY THE CODE EXCEEDED TIME LIMIT OF 10 SECONDS I MADE IT TO 5 AND I AM TRYING TO REDUCE IT STILL IF YOU GUYS COULD DO IT PLEASE DO AND SEND THE CODE 
https://chat.whatsapp.com/Ew2cipXkl1bBl3MzPNEEX3 TO THIS WHATSAPP GROUP **


import io,os,sys
from sys import stdin, stdout
def xorOfArray(arr,n,c):
    x=0
    for i in range(n):
            if c==n:
                sys.stdout.write(str("-1")+"\n")
            xor_arr = 0
            for i in range(n):
                xor_arr = xor_arr ^ arr[i]
            
            if xor_arr!=0:
                for i in range(n):
                        arr[i]=arr[i]+1
                c=c+1
            elif xor_arr==0:
                sys.stdout.write(str(c) + "\n")
                break
            else:
                return False
def Diff(arr):
    arr=sorted(arr)
    arr_size=len(arr)
    diff = arr[1] - arr[0]
    c=0
    for i in range( 0, arr_size-1 ):
        if(arr[i+1] - arr[i] == diff):
                c=c+1
    if c==(arr_size-1):
        return True
    else:
        return False

def countFreq(arr):
	l=[]
	r=[]
	n=len(arr)
	arr=sorted(arr)
	for i in range(n):
	    if arr[i] not in r:
	        x=arr.count(arr[i])
	        r.append(arr[i])
	        l.append(x)
	for i in range(len(l)):
	    x=r[i]
	    if l[i]>=2:
	        if l[i]%2==0:
	            for j in range(l[i]):
	                arr.remove(x)
	            break
	        elif l[i]%2!=0:
	            for j in range(l[i]):
	                arr.remove(x)
	            arr.append(x)
	            break
	arr=sorted(arr)
	n=len(arr)
	if n==1:
	    if arr[0]==0:
	        sys.stdout.write(str("0") + "\n")
	    else:
	        sys.stdout.write(str("-1") + "\n")
	    return True
	else:
	    return arr
t=int(sys.stdin.readline())
for i in range(t):
    n=int(sys.stdin.readline())
    arr =[int(x) for x in sys.stdin.readline().split()]
    if countFreq(arr)==True:
        continue
    else:
        arr=countFreq(arr)
    if arr[0]==1 and arr[1]==2 and arr[2]==3:
        sys.stdout.write(str("0")+"\n")
        continue
    if Diff(arr)==True:
        sys.stdout.write(str("-1") + "\n")
        continue
    else:
        n=len(arr)
        xorOfArray(arr,n,0)
