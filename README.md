# Data_Science_R_Basics
# HarvardX: PH125.1x | Data Science: R Basics

## Abstract

This is the first course in the HarvardX Professional Certificate in Data Science, a series of courses that prepare you to do data analysis in R, from simple computations to machine learning.

The textbook for the Data Science course series is [freely available online](https://rafalab.github.io/dsbook/).

## Learning Objectives
- Learn to read, extract, and create datasets in R
- Learn to perform a variety of operations on datasets using R
- Learn to write your own functions/sub-routines in R

## Course Overview

### Section 1: R Basics, Functions, Data types
You will get started with R, learn about its functions and data types.

### Section 2: Vectors, Sorting
You will learn to operate on vectors and advanced functions such as sorting.

### Section 3: Indexing, Data Manipulation, Plots
You will learn to wrangle and visualize data.

### Section 4: Programming Basics
You will learn to use general programming features like ‘if-else’, and ‘for loop’ commands, and write your own functions to perform various operations on datasets.

## Section 1 Overview

Section 1 introduces you to R Basics, Functions and Datatypes.
In Section 1, you will learn to:
- Appreciate the rationale for data analysis using R
- Define objects and perform basic arithmetic and logical operations
- Use pre-defined functions to perform operations on objects
- Distinguish between various data types

The textbook for this section is available [here](https://rafalab.github.io/dsbook/r-basics.html)

## Assessment 1
1. What is the sum of the first n positive integers? The formula for the sum of integers 1 through n is n(n+1)/2. Define n = 100 and then use R to compute the sum of 1 through 100 using the formula. What is the sum?
```
# Here is how you compute the sum for the first 20 integers
20*(20+1)/2 
```
```
## [1] 210
```
```
# However, we can define a variable to use the formula for other values of n
n <- 20
n*(n+1)/2
```
```
## [1] 210
```
```
n <- 25
n*(n+1)/2
```
```
## [1] 325
```
```
# Below, write code to calculate the sum of the first 100 integers
n <-100
n*(n+1)/2
```
```
## [1] 5050
```
2. Now use the same formula to compute the sum of the integers from 1 through 1,000.
```
# Below, write code to calculate the sum of the first 1000 integers 
n <- 1000
r <- n*(n+1)/2
r
```
```
## [1] 500500
```
3. Look at the result of typing the following code into R:
```
n <- 1000
x <- seq(1, n)
sum(x)
```
Based on the result, what do you think the functions seq and sum do?
- [ ] A. sum creates a list of numbers and seq adds them up.
- [x] B. seq creates a list of numbers and sum adds them up.
- [ ] C. seq computes the difference between two arguments and sum computes the sum of 1 through 1000.
- [ ] D. sum always returns the same number.

4. In math and programming, we say that we evaluate a function when we replace the argument with a given number. So if we type sqrt(4), we evaluate the sqrt function. In R, you can evaluate a function inside another function. The evaluations happen from the inside out. Use one line of code to compute the log, in base 10, of the square root of 100.
```
# log to the base 2 
log2(16)
```
```
## [1] 4
```
```
# sqrt of the log to the base 2 of 16:
sqrt(log2(16))
```
```
## [1] 2
```
```
# Compute log to the base 10 (log10) of the sqrt of 100. Do not use variables.
log10(sqrt(100))
```
```
## [1] 1
```
5. Which of the following will always return the numeric value stored in x? You can try out examples and use the help system if you want.
- [ ] A. log(10^x)
- [ ] B. log10(x^10)
- [x] C. log(exp(x))
- [ ] D. exp(log(x, base = 2))

## Assessment 2

1. Load the US murders dataset.
```
library(dslabs)  
data(murders)
```
Use the function str to examine the structure of the murders object. We can see that this object is a data frame with 51 rows and five columns. Which of the following best describes the variables represented in this data frame?
- [ ] A. The 51 states.
- [ ] B. The murder rates for all 50 states and DC.
- [x] C. The state name, the abbreviation of the state name, the state's region, and the state's population and total number of murders for 2010.
- [ ] D. str shows no relevant information.

2. What are the column names used by the data frame for these five variables?
```
# Load package and data
library(dslabs)
data(murders)

# Use the function names to extract the variable names 
names(murders)
```
```
## [1] "state"      "abb"        "region"     "population" "total"
```
3. Use the accessor $ to extract the state abbreviations and assign them to the object a. What is the class of this object?
```
# To access the population variable from the murders dataset use this code:
p <- murders$population 

# To determine the class of object `p` we use this code:
class(p)
```
```
## [1] "numeric"
```
```
# Use the accessor to extract state abbreviations and assign it to a
a <- murders$abb

# Determine the class of a
class(a)
```
```
## [1] "character"
```
4. Now use the square brackets to extract the state abbreviations and assign them to the object b. Use the identical function to determine if a and b are the same.
```
# We extract the population like this:
p <- murders$population

# This is how we do the same with the square brackets:
o <- murders[["population"]] 

# We can confirm these two are the same
identical(o, p)
```
```
## [1] TRUE
```
```
# Use square brackets to extract `abb` from `murders` and assign it to b
b<-murders[["abb"]]

# Check if `a` and `b` are identical 
identical(a, b)
```
```
## [1] TRUE
```
5. We saw that the region column stores a factor. You can corroborate this by typing:
```
class(murders$region)
```
With one line of code, use the function levels and length to determine the number of regions defined by this dataset.
```
# We can see the class of the region variable using class
class(murders$region)
```
```
## [1] "factor"
```
```
# Determine the number of regions included in this variable 
length(levels(murders$region))
```
```
## [1] 4
```
6. The function table takes a vector and returns the frequency of each element. You can quickly see how many states are in each region by applying this function. Use this function in one line of code to create a table of states per region.
```
# Here is an example of what the table function does
x <- c("a", "a", "b", "b", "b", "c")
table(x)
```
```
## x
## a b c 
## 2 3 1
```
```
# Write one line of code to show the number of states per region
table(murders$region)
```
```
## 
##     Northeast         South North Central          West 
##             9            17            12            13
```
## Section 2 Overview

In Section 2.1, you will:
- Create numeric and character vectors.
- Name the columns of a vector.
- Generate numeric sequences.
- Access specific elements or parts of a vector.
- Coerce data into different data types as needed.

In Section 2.2, you will:
- Sort vectors in ascending and descending order.
- Extract the indices of the sorted elements from the original vector.
- Find the maximum and minimum elements, as well as their indices, in a vector.
- Rank the elements of a vector in increasing order.

In Section 2.3, you will:
- Perform arithmetic between a vector and a single number.
- Perform arithmetic between two vectors of same length.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/r-basics.html#vectors)

## Assessment 3

1. Use the function c to create a vector with the average high temperatures in January for Beijing, Lagos, Paris, Rio de Janeiro, San Juan and Toronto, which are 35, 88, 42, 84, 81, and 30 degrees Fahrenheit. Call the object temp.
```
# Here is an example creating a numeric vector named cost
cost <- c(50, 75, 90, 100, 150)

# Create a numeric vector to store the temperatures listed in the instructions into a vector named temp
# Make sure to follow the same order in the instructions
temp <- c(35, 88, 42, 84, 81,30)
```
2. Now create a vector with the city names and call the object city.
```
# here is an example of how to create a character vector
food <- c("pizza", "burgers", "salads", "cheese", "pasta")

# Create a character vector called city to store the city names
# Make sure to follow the same order as in the instructions
city <- c("Beijing", "Lagos", "Paris", "Rio de Janeiro", "San Juan", "Toronto")
```
3. Use the names function and the objects defined in the previous exercises to associate the temperature data with its corresponding city.
```
# Associate the cost values with its corresponding food item
cost <- c(50, 75, 90, 100, 150)
food <- c("pizza", "burgers", "salads", "cheese", "pasta")
names(cost) <- food

# You already wrote this code
temp <- c(35, 88, 42, 84, 81, 30)
city <- c("Beijing", "Lagos", "Paris", "Rio de Janeiro", "San Juan", "Toronto")

# Associate the temperature values with its corresponding city
names(temp) <- city
```
4. Use the [ and : operators to access the temperature of the first three cities on the list.
```
# cost of the last 3 items in our food list:
cost[3:5]
```
```
## salads cheese  pasta 
##     90    100    150
```
```
# temperatures of the first three cities in the list:
temp[1:3]
```
```
## Beijing   Lagos   Paris 
##      35      88      42
```
5. Use the [ operator to access the temperature of Paris and San Juan.
```
# Access the cost of pizza and pasta from our food list 
cost[c(1,5)]
```
```
## pizza pasta 
##    50   150
```
```
# Define temp
temp <- c(35, 88, 42, 84, 81, 30)
city <- c("Beijing", "Lagos", "Paris", "Rio de Janeiro", "San Juan", "Toronto")
names(temp) <- city

# Access the temperatures of Paris and San Juan
temp[c(3,5)]
```
```
##    Paris San Juan 
##       42       81
```
6. Use the : operator to create a sequence of numbers 12, 13, 14,..,73.
```
# Create a vector m of integers that starts at 32 and ends at 99.
m <- 32:99

# Determine the length of object m.
length(m)
```
```
## [1] 68
```
```
# Create a vector x of integers that starts 12 and ends at 73.
x <- 12:73

# Determine the length of object x.
length(x)
```
```
## [1] 62
```
7. Create a vector containing all the positive odd numbers smaller than 100.
```
# Create a vector with the multiples of 7, smaller than 50.
seq(7, 49, 7) 
```
```
## [1]  7 14 21 28 35 42 49
```
```
# Create a vector containing all the positive odd numbers smaller than 100.
# The numbers should be in ascending order
seq(1,100,2)
```
```
##  [1]  1  3  5  7  9 11 13 15 17 19 21 23 25 27 29 31 33 35 37 39 41 43 45
## [24] 47 49 51 53 55 57 59 61 63 65 67 69 71 73 75 77 79 81 83 85 87 89 91
## [47] 93 95 97 99
```
8. Create a vector of numbers that starts at 6, does not pass 55, and adds numbers in increments of 4/7: 6, 6+4/7, 6+8/7, etc.. How many numbers does the list have? Hint: use seq and length.
```
# We can a vector with the multiples of 7, smaller than 50 like this 
seq(7, 49, 7) 
```
```
## [1]  7 14 21 28 35 42 49
```
```
# But note that the second argument does not need to be last number.
# It simply determines the maximum value permitted.
# so the following line of code produces the same vector as seq(7, 49, 7)
seq(7, 50, 7)
```
```
## [1]  7 14 21 28 35 42 49
```
```
# Create a sequence of numbers from 6 to 55, with 4/7 increments and determine its length
length(seq(6,55,4/7))
```
```
## [1] 86
```
9. What is the class of the following object a <- seq(1, 10, length.out = 100)?
```
# Store the sequence in the object a
a <- seq(1, 10, length.out = 100)

# Determine the class of a
class(a)
```
```
## [1] "numeric"
```
10. What is the class of the following object a <- seq(1, 10)?
```
# Store the sequence in the object a
a <- seq(1, 10)

# Determine the class of a
class(a)
```
```
## [1] "integer"
```
11. The class of class(a<-1) is numeric, not integer. R defaults to numeric and to force an integer, you need to add the letter L. Confirm that the class of 1L is integer.
```
# Check the class of 1, assigned to the object a
a <- class(1)

# Confirm the class of 1L is integer
class(1L)
```
```
## [1] "integer"
```
12. Define the following vector:
```
x <- c(“1”, “3”, “5”, “a”)
```
and coerce it to get integers.
```
# Define the vector x
x <- c(1, 3, 5,"a")

# Note that the x is character vector
x
```
```
## [1] "1" "3" "5" "a"
```
```
# Typecast the vector to get an integer vector
x <- as.numeric(x)

# You will get a warning but that is ok
```
## Assessment 4

For these exercises we will use the US murders dataset. Make sure you load it prior to starting.
```
library(dslabs)
data("murders")
```
1. Use the $ operator to access the population size data and store it as the object pop. Then use the sort function to redefine pop so that it is sorted. Finally, use the [ operator to report the smallest population size.
```
# Access the `state` variable and store it in an object 
states <- murders$state 

# Sort the object alphabetically and redefine the object 
states <- sort(states) 

# Report the first alphabetical value  
states[1]
```
```
## [1] "Alabama"
```
```
# Access population values from the dataset and store it in pop
pop <- murders$population

# Sort the object and save it in the same object 
pop<-sort(pop)

# Report the smallest population size 
pop[1]
```
```
## [1] 563626
```
2. Now instead of the smallest population size, find the index of the entry with the smallest population size. Hint: use order instead of sort.
```
# Access population from the dataset and store it in pop
pop <- murders$population

# Use the command order, to order pop and store in object o
o <- order(pop)

# Find the index number of the entry with the smallest population size
which.min(murders$population)
```
```
## [1] 51
```
3. We can actually perform the same operation as in the previous exercise using the function which.min. Write one line of code that does this.
```
# Find the smallest value for variable total 
which.min(murders$total)
```
```
## [1] 46
```
```
# Find the smallest value for population
which.min(murders$population)
```
```
## [1] 51
```
4. Now we know how small the smallest state is and we know which row represents it. Which state is it? Define a variable states to be the state names from the murders data frame. Report the name of the state with the smallest population.
```
# Define the variable i to be the index of the smallest state
i <- which.min(murders$population)

# Define variable states to hold the states
states <- murders$state

# Use the index you just defined to find the state with the smallest population
states[i]
```
```
## [1] "Wyoming"
```
5. You can create a data frame using the data.frame function. Here is a quick example:
```
temp <- c(35, 88, 42, 84, 81, 30)
city <- c(“Beijing”, “Lagos”, “Paris”, “Rio de Janeiro”, “San Juan”, “Toronto”)
city_temps <- data.frame(name = city, temperature = temp)
```
Use the rank function to determine the population rank of each state from smallest population size to biggest. Save these ranks in an object called ranks, then create a data frame with the state name and its rank. Call the data frame my_df.
```
# Store temperatures in an object 
temp <- c(35, 88, 42, 84, 81, 30)

# Store city names in an object 
city <- c("Beijing", "Lagos", "Paris", "Rio de Janeiro", "San Juan", "Toronto")

# Create data frame with city names and temperature 
city_temps <- data.frame(name = city, temperature = temp)

# Define a variable states to be the state names 
states <- murders$state

# Define a variable ranks to determine the population size ranks 
ranks <- rank(murders$population)

# Create a data frame my_df with the state name and its rank
my_df <- data.frame(name=states, ranks)
```
6. Repeat the previous exercise, but this time order my_df so that the states are ordered from least populous to most populous. Hint: create an object ind that stores the indexes needed to order the population values. Then use the bracket operator [ to re-order each column in the data frame.
```
# Define a variable states to be the state names from the murders data frame
states <- murders$state

# Define a variable ranks to determine the population size ranks 
ranks <- rank(murders$population)

# Define a variable ind to store the indexes needed to order the population values
ind <- order(murders$population)

# Create a data frame my_df with the state name and its rank and ordered from least populous to most 
my_df<-data.frame(states = states[ind], ranks = ranks[ind])
```
7. The na_example vector represents a series of counts. You can quickly examine the object using:
```
data(“na_example”)
str(na_example)
nt [1:1000] 2 1 3 2 1 3 1 4 3 2 …
```
However, when we compute the average with the function mean, we obtain an NA:
```
mean(na_example)
[1] NA
```
The is.na function returns a logical vector that tells us which entries are NA. Assign this logical vector to an object called ind and determine how many NAs does na_example have.
```
# Using new dataset 
library(dslabs)
data(na_example)

# Checking the structure 
str(na_example)
```
```
##  int [1:1000] 2 1 3 2 1 3 1 4 3 2 ...
```
```
# Find out the mean of the entire dataset 
mean(na_example)
```
```
## [1] NA
```
```
# Use is.na to create a logical index ind that tells which entries are NA
ind <- is.na(na_example)

# Determine how many NA ind has using the sum function
sum(ind)
```
```
## [1] 145
```
8. Now compute the average again, but only for the entries that are not NA. Hint: remember the ! operator.
```
# Note what we can do with the ! operator
x <- c(1, 2, 3)
ind <- c(FALSE, TRUE, FALSE)
x[!ind]
```
```
## [1] 1 3
```
```
# Create the ind vector
library(dslabs)

data(na_example)
ind <- is.na(na_example)

# We saw that this gives an NA
mean(na_example)
```
```
## [1] NA
```
```
# Compute the average, for entries of na_example that are not NA 
mean(na_example[!ind])
```
```
## [1] 2.301754
```
## Assessment 5

1. Previously we created this data frame:
```
temp <- c(35, 88, 42, 84, 81, 30)
city <- c("Beijing", "Lagos", "Paris", "Rio de Janeiro", "San Juan", "Toronto")
city_temps <- data.frame(name = city, temperature = temp)
```
Remake the data frame using the code above, but add a line that converts the temperature from Fahrenheit to Celsius. The conversion is C =5/9 ? (F ??? 32).
```
# Assign city names to `city` 
city <- c("Beijing", "Lagos", "Paris", "Rio de Janeiro", "San Juan", "Toronto")

# Store temperature values in `temp`
temp <- c(35, 88, 42, 84, 81, 30)

# Convert temperature into Celsius and overwrite the original values of 'temp' with these Celsius values
temp <- 5/9*(temp-32)

# Create a data frame `city_temps` 
city_temps <- data.frame(name=city,temperature=temp)
```
2. What is the following sum 1 + 1/2^2 + 1/3^2 + .1/100^2 ? Hint: thanks to Euler, we know it should be close to ??^2/6.
```
# Define an object `x` with the numbers 1 through 100
x <- c(1:100)

# Compute the sum 
sum(1/x^2)
```
```
## [1] 1.634984
```
3. Compute the per 100,000 murder rate for each state and store it in the object murder_rate. Then compute the average murder rate for the US using the function mean. What is the average?
```
# Load the data
library(dslabs)
data(murders)

# Store the per 100,000 murder rate for each state in murder_rate
murder_rate <- murders$total/murders$population *100000

# Calculate the average murder rate in the US 
mean(murder_rate)
```
```
## [1] 2.779125
```
## Section 3 Overview

Section 3 introduces to the R commands and techniques that help you wrangle, analyze, and visualize data.

In Section 3.1, you will:
- Subset a vector based on properties of another vector.
- Use multiple logical operators to index vectors.
- Extract the indices of vector elements satisfying one or more logical conditions.
- Extract the indices of vector elements matching with another vector.
- Determine which elements in one vector are present in another vector.

In Section 3.2, you will:
- Wrangle data tables using the functions in ‘dplyr’ package.
- Modify a data table by adding or changing columns.
- Subset rows in a data table.
- Subset columns in a data table.
- Perform a series of operations using the pipe operator.
- Create data frames.

In Section 3.3, you will:
- Plot data in scatter plots, box plots and histograms.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/r-basics.html#indexing)

## Assessment 6

Start by loading the library and data.
```
library(dslabs)
data(murders)
```
1. Compute the per 100,000 murder rate for each state and store it in an object called murder_rate. Then use logical operators to create a logical vector named low that tells us which entries of murder_rate are lower than 1.
```
# Store the murder rate per 100,000 for each state, in `murder_rate`
murder_rate <- murders$total / murders$population * 100000

# Store the `murder_rate < 1` in `low` 
low <- murder_rate < 1
```
2. Now use the results from the previous exercise and the function which to determine the indices of murder_rate associated with values lower than 1.
```
# Store the murder rate per 100,000 for each state, in murder_rate
murder_rate <- murders$total/murders$population*100000

# Store the murder_rate < 1 in low 
low <- murder_rate < 1

# Get the indices of entries that are below 1
which(low)
```
```
##  [1] 12 13 16 20 24 30 35 38 42 45 46 51
```
3. Use the results from the previous exercise to report the names of the states with murder rates lower than 1.
```
# Store the murder rate per 100,000 for each state, in murder_rate
murder_rate <- murders$total/murders$population*100000

# Store the murder_rate < 1 in low 
low <- murder_rate < 1

# Names of states with murder rates lower than 1
murders$state[low]
```
```
##  [1] "Hawaii"        "Idaho"         "Iowa"          "Maine"        
##  [5] "Minnesota"     "New Hampshire" "North Dakota"  "Oregon"       
##  [9] "South Dakota"  "Utah"          "Vermont"       "Wyoming"
```
4. Now extend the code from exercise 2 and 3 to report the states in the Northeast with murder rates lower than 1. Hint: use the previously defined logical vector low and the logical operator &.
```
# Store the murder rate per 100,000 for each state, in `murder_rate`
murder_rate <- murders$total/murders$population*100000

# Store the `murder_rate < 1` in `low` 
low <- murder_rate < 1

# Create a vector ind for states in the Northeast and with murder rates lower than
ind <- low & murders$region=='Northeast'

# Names of states in `ind` 
murders$state[ind] 
```
```
## [1] "Maine"         "New Hampshire" "Vermont"
```
5. In a previous exercise we computed the murder rate for each state and the average of these numbers. How many states are below the average?
```
# Store the murder rate per 100,000 for each state, in murder_rate
murder_rate <- murders$total/murders$population*100000

# Compute average murder rate and store in avg using `mean` 
avg <- mean(murder_rate)

# How many states have murder rates below avg ? Check using sum 
sum(murder_rate<avg)
```
```
## [1] 27
```
6. Use the match function to identify the states with abbreviations AK, MI, and IA. Hint: start by defining an index of the entries of murders$abb that match the three abbreviations, then use the [ operator to extract the states.
```
# Store the 3 abbreviations in abbs in a vector (remember that they are character vectors and need quotes)
abbs <- c('AK','MI','IA')

# Match the abbs to the murders$abb and store in ind
ind <- match(abbs , murders$abb)

# Print state names from ind
murders$state[ind]
```
```
## [1] "Alaska"   "Michigan" "Iowa"
```
7. Use the %in% operator to create a logical vector that answers the question: which of the following are actual abbreviations: MA, ME, MI, MO, MU ?
```
# Store the 5 abbreviations in `abbs`. (remember that they are character vectors)
abbs <- c('MA', 'ME', 'MI', 'MO', 'MU')

# Use the %in% command to check if the entries of abbs are abbreviations in the the murders data frame
abbs%in%murders$abb
```
```
## [1]  TRUE  TRUE  TRUE  TRUE FALSE
```
8. Extend the code you used in exercise 7 to report the one entry that is not an actual abbreviation. Hint: use the ! operator, which turns FALSE into TRUE and vice versa, then which to obtain an index.
```
# Store the 5 abbreviations in abbs. (remember that they are character vectors)
abbs <- c("MA", "ME", "MI", "MO", "MU") 

# Use the `which` command and `!` operator to find out which abbreviation are not actually part of the dataset and store in ind
ind <- which(!abbs%in%murders$abb)

# What are the entries of abbs that are not actual abbreviations
abbs[ind]
```
```
## [1] "MU"
```
## Assessment 7

Load the dplyr package and the murders dataset.
```
library(dplyr)
library(dslabs)
data(murders)
```
1. You can add columns using the dplyr function mutate. This function is aware of the column names and inside the function you can call them unquoted. Like this:
```
murders <- mutate(murders, population_in_millions = population / 10^6)
```
Note that we can write population rather than murders$population. The function mutate knows we are grabing columns from murders.\
Use the function mutate to add a murders column named rate with the per 100,000 murder rate. Make sure you redefine murders as done in the example code above. Remember the murder rate is defined the total divided by the population size times 100,000.
```
# Redefine murders so that it includes column named rate with the per 100,000 murder rates
murders <- mutate(murders, rate=total/murders$population*100000)
```
2. mutate

Note that if rank(x) gives you the ranks of x from lowest to highest, rank(-x) gives you the ranks from highest to lowest. Use the function mutate to add a column rank containing the rank, from highest to lowest murder rate. Make sure you redeinfe murders.
```
# Note that if you want ranks from highest to lowest you can take the negative and then compute the ranks 
x <- c(88, 100, 83, 92, 94)
rank(-x)
```
```
## [1] 4 1 5 3 2
```
```
# Defining rate
rate <-  murders$total/ murders$population * 100000

# Redefine murders to include a column named rank
# with the ranks of rate from highest to lowest
murders <- mutate(murders,rank=rank(-rate))
```
3. select

With dplyr we can use select to show only certain columns. For example with this code we would only show the states and population sizes:
```
select(murders, state, population)
```
Use select to show the state names and abbreviations in murders. Just show it, do not define a new object.
```
# Load dplyr
library(dplyr)

# Use select to only show state names and abbreviations from murders
select(murders,state,abb)

state                   abb
<chr>                   <chr>
Alabama                 AL
Alaska                  AK
Arizona                 AZ
Arkansas                AR
California              CA
Colorado                CO
Connecticut             CT
Delaware                DE
District of Columbia    DC
Florida                 FL
1-10 of 51 rows
```
4. filter
    
The dplyr function filter is used to choose specific rows of the data frame to keep. Unlke select which is for columns, filter is for rows. For example you can show just New York row like this:
```
filter(murders, state == “New York”)
```
You can use other logical vector to filter rows.
Use filter to show the top 5 states with the highest murder rates. After we add murder rate and rank, do not change the murders dataset, just show the result. Note that you can filter based on the rank column.
```
# Add the necessary columns
murders <- mutate(murders, rate = total/population * 100000, rank = rank(-rate))

# Filter to show the top 5 states with the highest murder rates
filter(murders,rate,rank<=5)

state                   abb   region        population total  rate       rank
<chr>                   <chr> <fctr>        <dbl>      <dbl>  <dbl>      <dbl>
District of Columbia    DC    South         601723     99     16.452753	 1
Louisiana               LA    South         4533372    351    7.742581	 2
Maryland                MD    South         5773552    293    5.074866	 4
Missouri                MO    North Central 5988927    321    5.359892	 3
South Carolina          SC    South         4625364    207    4.475323	 5
5 rows
```
5. filter with !=

We can remove rows using the != operator. For example to remove Florida we would do this:
```
no_florida <- filter(murders, state != “Florida”)
```
Create a new data frame called no_south that removes states from the South region. How many states are in this category? You can use the function nrow for this.
```
# Use filter to create a new data frame no_south
no_south <- filter(murders, region != 'South')

# Use nrow() to calculate the number of rows
nrow(no_south)
```
```
## [1] 34
```
6. filter with %in%
    
We can also use the %in% to filter with dplyr. For example you can see the data from New York and Texas like this:
```
filter(murders, state %in% c(“New York”, “Texas”))
```
Create a new data frame called murders_nw with only the states from the Northeast and the West. How many states are in this category?
```
# Create a new data frame called murders_nw with only the states from the northeast and the west
murders_nw <- filter(murders, region %in% c('Northeast','West'))

# Number of states (rows) in this category 
nrow(murders_nw)
```
```
## [1] 22
```
7. filtering by two conditions

Suppose you want to live in the Northeast or West and want the murder rate to be less than 1. We want to see the data for the states satisfying these options. Note that you can use logical operators with filter:
```
filter(murders, population < 5000000 & region == “Northeast”)
```
Add a murder rate column and a rank column as done before. Create a table, call it my_states, that satisfies both the conditions: it is in the Northeast or West and the murder rate is less than 1. Use select to show only the state name, the rate and the rank.
```
# add the rate column
murders <- mutate(murders, rate =  total / population * 100000, rank = rank(-rate))

# Create a table, call it my_states, that satisfies both the conditions 
my_states <- filter(murders, region %in% c('Northeast','West') & rate < 1)

# Use select to show only the state name, the murder rate and the rank
select(my_states,state,rate,rank)

state           rate            rank
<chr>           <dbl>           <dbl>
Hawaii          0.5145920	49
Idaho	        0.7655102	46
Maine	        0.8280881	44
New Hampshire   0.3798036	50
Oregon	        0.9396843	42
Utah	        0.7959810	45
Vermont	        0.3196211	51
Wyoming	        0.8871131	43
8 rows
```
8. Using the pipe %>%

The pipe %>% can be used to perform operations sequentially without having to define intermediate objects. After redefining murder to include rate and rank.
```
library(dplyr)
murders <- mutate(murders, rate = total / population * 100000, rank = (-rate))
```
in the solution to the previous exercise we did the following:

Created a table
```
my_states <- filter(murders, region %in% c(“Northeast”, “West”) & rate < 1)
```
Used select to show only the state name, the murder rate and the rank
```
select(my_states, state, rate, rank)
```
The pipe %>% permits us to perform both operation sequentially and without having to define an intermediate variable my_states

For example we could have mutated and selected in the same line like this:
```
mutate(murders, rate = total / population * 100000, rank = (-rate)) %>% select(state, rate, rank)
```
Note that select no longer has a data frame as the first argument. The first argument is assumed to be the result of the operation conducted right before the %>%

Repeat the previous exercise, but now instead of creating a new object, show the result and only include the state, rate, and rank columns. Use a pipe %>% to do this in just one line.
```
# Load library
library(dplyr)
```
```
## Define the rate column
murders <- mutate(murders, rate =  total / population * 100000, rank = rank(-rate))
```
```
# show the result and only include the state, rate, and rank columns, all in one line
filter(murders, region %in% c("Northeast", "West") & rate < 1 ) %>% 
select(state, rate, rank)

state           rate            rank
<chr>           <dbl>           <dbl>
Hawaii	        0.5145920	49
Idaho	        0.7655102	46
Maine	        0.8280881	44
New Hampshire	0.3798036	50
Oregon	        0.9396843	42
Utah	        0.7959810	45
Vermont	        0.3196211	51
Wyoming	        0.8871131	43
8 rows
```
9. mutate, filter and select

Now we will make murders the original table one gets when loading using data(murders). Use just one line to create a new data frame, called, my_states that has murder rate and rank column, consider only states in the Northeast or West, which have a murder rate lower than 1 and contain only the state, rate, and rank columns. The line should have four components separated by three %>%.
- The original dataset murders
- A call to mutate to add the murder rate and the rank.
- A call to filter to keep only the states from the Northeast or West and that have a murder rate below 1
- A call to select that keeps only the columns with the stata name, the murder rate and the rank.

The line should look something like this my_states <- murders %>% mutate something %>% filter something %>% select something. Please, make sure the columns in the final data frame must be in the order: state, rate, rank.
```
# Loading the libraries
library(dplyr)
data(murders)

# Create new data frame called my_states (with specifications in the instructions)
my_states <- murders %>% mutate(rate=total/murders$population*100000, rank=rank(-rate)) %>% filter(region %in% c('Northeast','West') & rate <1) %>% select(state,rate,rank)
```
## Assessment 8

1. We made a plot of total murders versus population and noted a strong relationship. Not surprisingly, states with larger populations had more murders.
```
library(dslabs)
data(murders)
population_in_millions <- murders$population/10^6
total_gun_murders <− murders$total
plot(population_in_millions, total_gun_murders)
```
Keep in mind that many states have populations below 5 million and are bunched up. We may gain further insights from making this plot in the log scale. Transform the variables using the log10 transformation and then plot them.
```
# Load the datasets and define some variables
library(dslabs)
data(murders)

population_in_millions <- murders$population/10^6
total_gun_murders <- murders$total

plot(population_in_millions, total_gun_murders)
```
![index](https://user-images.githubusercontent.com/17474099/75668573-cdb1c800-5c79-11ea-98c3-222b70b1eb88.png)
```
# Transform population using the log10 transformation and save to object log10_population
log10_population <-log10(murders$population)

# Transform total gun murders using log10 transformation and save to object log10_total_gun_murders
log10_total_gun_murders <- log10(total_gun_murders)

# Create a scatterplot with the log scale transformed population and murders 
plot(log10_population,log10_total_gun_murders)
```
2. Create a histogram of the state populations.
```
# Store the population in millions and save to population_in_millions 
population_in_millions <- murders$population/10^6

# Create a histogram of this variable
hist(population_in_millions)
```
![index](https://user-images.githubusercontent.com/17474099/75668993-7bbd7200-5c7a-11ea-98d7-bc5e28e69d07.png)

3. Generate boxplots of the state populations by region.
```
# Create a boxplot of state populations by region for the murders dataset
boxplot(population~region, data=murders)
```
![index](https://user-images.githubusercontent.com/17474099/75669696-bc69bb00-5c7b-11ea-9cd1-bc5218b21b40.png)
## Section 4 Overview

Section 4 introduces you to general programming features like ‘if-else’, and ‘for loop’ commands so that you can write your own functions to perform various operations on datasets.

In Section 4.1, you will:
- Understand some of the programming capabilities of R.

In Section 4.2, you will:
- Use basic conditional expressions to perform different operations.
- Check if any or all elements of a logical vector are TRUE.

In Section 4.3, you will:
- Define and call functions to perform various operations.
- Pass arguments to functions, and return variables/objects from functions.

In Section 4.4, you will:
- Use ‘for’ loop to perform repeated operations.
- Articulate in-built functions of R that you could try for yourself.

The textbook for this section is available [here](https://rafalab.github.io/dsbook/programming-basics.html)

## Assessment 9

1. What will this conditional expression return?
```
x <- c(1,2,-3,4)

if(all(x>0)){
print(“All Postives”)
} else{
print(“Not all positives”)
}
```
- [ ] A. All Positives
- [X] B. Not All Positives
- [ ] C. N/A
- [ ] D. None of the above

2. Which of the following expressions is always FALSE when at least one entry of a logical vector x is TRUE?

- [ ] A. all(x)
- [ ] B. any(x)
- [ ] C. any(!x)
- [X] D. all(!x)

3. The function nchar tells you how many characters long a character vector is.

Write a line of code that assigns to the object new_names the state abbreviation when the state name is longer than 8 characters.
```
# Assign the state abbreviation when the state name is longer than 8 characters 
new_names <- ifelse(nchar(murders$state)>8, murders$abb, murders$state)
```
4. Create a function sum_n that for any given value, say n, computes the sum of the integers from 1 to n (inclusive). Use the function to determine the sum of integers from 1 to 5,000.
```
# Create function called `sum_n`
sum_n <- function(n){
  sum(1:n)
}
# Use the function to determine the sum of integers from 1 to 5000
sum_n(5000)
```
```
## [1] 12502500
```
5. Create a function altman_plot that takes two arguments, x and y, and plots the difference against the sum.
```
# Create `altman_plot` 
altman_plot <- function(x,y) {
  plot(x+y,y-x)
}
```
6. After running the code below, what is the value of x?
```
x <- 3
my_func <- function(y){
x <- 5
y+5
}
```
```
# Run this code 
x <- 3
    my_func <- function(y){
    x <- 5
    y+5
}

# Print value of x 
print(x)
```
```
## [1] 3
```
7. Write a function compute_s_n that for any given n computes the sum S_n = 1^2 + 2^2 + 3^2 + . n^2. Report the value of the sum when n = 10.
```
# Here is an example of function that adds numbers from 1 to n
example_func <- function(n){
    x <- 1:n
    sum(x)
}

# Here is the sum of the first 100 numbers
example_func(100)
```
```
## [1] 5050
```
```
# Write a function compute_s_n that with argument n and returns of 1 + 2^2 + ...+ n^2
compute_s_n <- function(n){
  x <- 1:n
  sum(x^2)
}
# Report the value of the sum when n=10
compute_s_n(10)
```
```
## [1] 385
```
8. Define an empty numerical vector s_n of size 25 using s_n <- vector(“numeric”, 25) and store in the results of S_1, S_2, . S_25 using a for-loop.
```
# Define a function and store it in `compute_s_n`
compute_s_n <- function(n){
  x <- 1:n
  sum(x^2)
}

# Create a vector for storing results
s_n <- vector("numeric", 25)

# write a for-loop to store the results in s_n
for(i in 1:25){
  s_n[i] <- compute_s_n(i)
}
```
9. If we do the math, we can show that S_n=12+22+32+???+n2=n(n+1)(2n+1)/6. We have already computed the values of Sn from 1 to 25 using a for loop. If the formula is correct then a plot of Sn versus n should look cubic.
```
# Define the function
compute_s_n <- function(n){
  x <- 1:n
  sum(x^2)
}

# Define the vector of n
n <- 1:25

# Define the vector to store data
s_n <- vector("numeric", 25)
for(i in n){
  s_n[i] <- compute_s_n(i)
}

#  Create the plot 
plot(n,s_n)
```

    Confirm that s_n and n(n+1)(2n+1)/6 are the same using the identical command.

# Define the function
compute_s_n <- function(n){
  x <- 1:n
  sum(x^2)
}

# Define the vector of n
n <- 1:25

# Define the vector to store data
s_n <- vector("numeric", 25)
for(i in n){
  s_n[i] <- compute_s_n(i)
}

# Check that s_n is identical to the formula given in the instructions.
identical(s_n,n*(n+1)*(2*n+1)/6)

## [1] TRUE

