#  Mean and variance of a discrete  distribution


# Aim : 

To find mean and variance of arrival of objects from the feeder using probability distribution


# Software required :  

Python and Visual components tool

# Theory:

The expectation or the mean of a discrete random variable is a weighted average of all possible
values of the random variable. The weights are the probabilities associated with the corresponding values. 
It is calculated as,

![image](https://user-images.githubusercontent.com/103921593/192938463-e34177f4-f188-48a0-bda2-8f6d1d660ed2.png)

The variance of a random variable shows the variability or the scatterings of the random variables.
It shows the distance of a random variable from its mean. It is calcualted as

![image](https://user-images.githubusercontent.com/103921593/192938695-99fedc01-34d5-4d36-84df-5880e766ed0c.png)


# Procedure :

1. Construct frequency distribution for the data

2. Find the  probability distribution from frequency distribution.

3. Calculate mean using 
   
   ![image](https://user-images.githubusercontent.com/103921593/192940431-03b81777-c54d-4286-b4f4-82dfe7666b4c.png)

4. Find  
   
      ![image](https://user-images.githubusercontent.com/103921593/192940255-2d9dd746-6875-4a6d-877b-6da6cdb96ab1.png)

5.  Calculate variance using 
  
      ![image](https://user-images.githubusercontent.com/103921593/192942852-913550a9-fabe-4a55-b956-0487b18bbd97.png)


# Experiment :

![image](https://user-images.githubusercontent.com/103921593/229993174-5b67e57e-3e01-4ac4-9f83-410a932b22bf.png)

# Program :
```
import numpy as np

# Read arrival values from user
data = [int(x) for x in input("Enter values: ").split()]

size = len(data)
highest = max(data)

arrivals = []
freq = []

# Finding frequency of each value
for val in range(highest + 1):
    count = 0

    for k in range(size):
        if data[k] == val:
            count += 1

    freq.append(count)
    arrivals.append(val)

total = sum(freq)

# Probability calculation
prob = [x/total for x in freq]

# Mean calculation
avg = np.inner(arrivals, prob)

# E(x²)
second = np.inner(np.square(arrivals), prob)

# Variance and SD
variance = second - avg**2
std = np.sqrt(variance)

print("\nValue\tProbability")

for i in range(len(freq)):
    if freq[i] != 0:
        print(f"{arrivals[i]}\t{prob[i]:.3f}")

print("\nMean =", round(avg,3))
print("Variance =", round(variance,3))
print("Standard Deviation =", round(std,3))

```



# Output : 
<img width="1099" height="314" alt="image" src="https://github.com/user-attachments/assets/554d704f-450d-40f4-825c-3bf3dede112d" />


# Results :
The mean and variance of arrivals of objects from feeder using probability distribution are calculated.

