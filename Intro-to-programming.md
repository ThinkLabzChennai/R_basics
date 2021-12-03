---
title: "Introduction to <br>Programming <br> with R"
author:    
    -  "RSN_Thinklabz_Chennai"
    -  Website https://www.thinklabz.ai/
    -  Mail Thinklabz.chennai@gmail.com
date: "July 3, 2021"
output:
  html_document:
    keep_md: true
    toc: yes
    df_print: kable
---
<style>

.main-container {
  max-width: 1800px;
  margin-left: auto;
  margin-right: auto;
}

#TOC {
  
  
  font-size: 16px;
  font-family: serif;
  color: #5C3317;
  background-color: #F9DB24;
  font-weight: bold;

}
.tocify .tocify-item {

background: floralwhite;

}
.tocify .tocify-header .active {
 color: green;
 background: khaki;
 }
p {
    text-align: justify;
    font-size: 18px;
    font-family: Bookman Old Style;
    line-height: 24px;
    margin: 0px 0px 12px 0px;
}

h1 {
    text-align: center;
    font-family: Bookman Old Style;
    font-size: 24px;
    font-weight: bold;
    color: darkblue;
}

h2, h3, h4, h5, h6, legend {
    text-align: justify;
    font-family: Bookman Old Style;
    font-size: 18px;
    font-weight: bold;
    color: red;
}
body {
background-color: aliceblue;
}
</style>





# Preamble
This notes is intended to give reader an introduction to basic programming concepts using R. We shall discuss the following topics 
   
   + Usage of brackets
   + Creating function
   + Controlling flow of a program
   

# Dataset 
   We shall use **iris** data for many of our examples. Let us look at structure of iris data
<table class="table table-striped" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> Variable.name </th>
   <th style="text-align:left;"> Description </th>
   <th style="text-align:left;"> Type </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Sepal.Length </td>
   <td style="text-align:left;"> Sepal Length of Iris </td>
   <td style="text-align:left;"> Numeric </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Sepal.Width </td>
   <td style="text-align:left;"> Sepal Width of Iris </td>
   <td style="text-align:left;"> Numeric </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Petal.Length </td>
   <td style="text-align:left;"> Petal Length of Iris </td>
   <td style="text-align:left;"> Numeric </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Petal.Width </td>
   <td style="text-align:left;"> Petal Width of Iris </td>
   <td style="text-align:left;"> Numeric </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Species </td>
   <td style="text-align:left;"> Species of Iris flower </td>
   <td style="text-align:left;"> Character </td>
  </tr>
</tbody>
</table>
   

# Programming 
We wish to perform various tasks using computers, for this we give recipie to the computer in understandable language. This process is called as programming. In this notes we shall look at some important tools in R programming.

## Brackets 
Brackets act as an important tool for performing tasks such as   
   
   + Executing function
   + Accessing elements in Dataframe, matrix etc
   + Defining a Function
   
### Using paranthesis
'( )' operator is used to specify input for a function in R. Every function must be called using the round brackets. Example

```r
# Creating vector
Example=c(1,2,34)

# Finding sum
sum(Example)
```

```
[1] 37
```

```r
# loading package 
library(dplyr)

# 
```

### Square brackets
Let us look at first few rowsw of our data 

```r
# Consider iris data
data("iris")
head(iris)
```

<div class="kable-table">

<table>
 <thead>
  <tr>
   <th style="text-align:right;"> Sepal.Length </th>
   <th style="text-align:right;"> Sepal.Width </th>
   <th style="text-align:right;"> Petal.Length </th>
   <th style="text-align:right;"> Petal.Width </th>
   <th style="text-align:left;"> Species </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 5.1 </td>
   <td style="text-align:right;"> 3.5 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:left;"> setosa </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;"> 3.0 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:left;"> setosa </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 4.7 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;"> 1.3 </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:left;"> setosa </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 4.6 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:left;"> setosa </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.0 </td>
   <td style="text-align:right;"> 3.6 </td>
   <td style="text-align:right;"> 1.4 </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:left;"> setosa </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5.4 </td>
   <td style="text-align:right;"> 3.9 </td>
   <td style="text-align:right;"> 1.7 </td>
   <td style="text-align:right;"> 0.4 </td>
   <td style="text-align:left;"> setosa </td>
  </tr>
</tbody>
</table>

</div>

Any data structure in R having more than one element requires use of '[]' for accessing one or more of its elements, it makes use of indexing. For example let us get 3rd element of the 'Example' vector 

```r
Example[3]
```

```
[1] 34
```



In a data frame and matrix we can use indexing in form '[m,n]' where 'm' represents row number and 'n' represents column number. 

```r
# Obtaining 5th row 3rd column value
iris[5,3]
```

```
[1] 1.4
```

### Curly braces
While defining functions, executing conditional statements we make use of '{}'. Example of this can be seen in next topic 'Functions'.


## Functions

A function can be regarded as a collection of statements. One of the strengths of R is the ability to extend R by writing new functions.

The general form of a function is given by:
```{}
Function_name = function (arg1, arg2, ...)
{
Body of function: a collection of valid statements
}
```

Where arg1, arg2 etc are arguments of the function, which are inputs for the functions. Body of function is where we give instructions for task we are interested. An example can be seen as

```r
greet=function(Name){
  cat("Hello ",Name)
}
greet('Data Scientist') 
```

```
Hello  Data Scientist
```

## Conditional statements and Flow control
Programming requires controlling the flow from one part of the program to another. Flow control occurs through
the use of loops, conditional statements and branching, and stopping conditions that cause the program
to stop executing one thing and execute something else or quit entirely. Conditional statements helps in specifying which blocks of code to run on which elements under different contexts

### if
if statement helps us check for a condition and executes the given instruction if condition is met and does nothing if condition is not met.
```{}
if (test_expression) 
      {
	statement
			}	
```


```r
if(length(iris$Sepal.Length)>2){
  print("Sepal.Length is having more than two elements")
}
```

```
[1] "Sepal.Length is having more than two elements"
```

### if else
An if else statement is a programming conditional statement that , if test expression is satisfactory , performs a function or displays information .Otherwise it performs a statement of else. So it is used when an alternate option is available for a situation.
```{}
if (test_expression) 
      {
	statement 1
			}else{
			statement 2
			}	
```



```r
if(length(iris$Sepal.Width)>115){
  print("Sepal.Length is having more than 115 elements")
}else{
  print("false")
}
```

```
[1] "Sepal.Length is having more than 115 elements"
```

### if else if
An if-else-if ladder statement is the addition of one or more if else statements one after the other. It is used when multiple responses are possible and outcome for each response is different.
```{}
if(test_expression1)
  {
  statement1
  } else if(test_expression2)
    {
    statement2
    } else if(test_expression3)
      {
      statement3
      } else
      {
          statement4
        }

```
An Example is shown below

```r
if(length(iris$Sepal.Length)<10){
  print("small vector")
}else if(length(iris$Sepal.Length)>10 & length(iris$Sepal.Length)<30 )
      {
      print("moderate vector")
      } else
      {
          print("Sepal.Length of iris is a long vector")
        }
```

```
[1] "Sepal.Length of iris is a long vector"
```

### for 
A for loop is a repetition control structure that allows to efficiently write a loop that needs to execute a specific number of times. 
```{}
for (value in vector) {
   statements
}
```


```r
# Considering Species variable of iris and using index of elements
for(i in 1:5)
{
  print(iris$Species[i])
}
```

```
[1] setosa
Levels: setosa versicolor virginica
[1] setosa
Levels: setosa versicolor virginica
[1] setosa
Levels: setosa versicolor virginica
[1] setosa
Levels: setosa versicolor virginica
[1] setosa
Levels: setosa versicolor virginica
```

for loops are particularly flexible that they are not limited to integers, or even numbers in the input. We can pass character vectors, logical vectors, lists or expressions.

```r
# Considering Species variable of iris
for(species in iris$Species[c(47:53,108)])
  {
  print(species)
} 
```

```
[1] "setosa"
[1] "setosa"
[1] "setosa"
[1] "setosa"
[1] "versicolor"
[1] "versicolor"
[1] "versicolor"
[1] "virginica"
```

### repeat
The Repeat loop executes the same code again and again until a stop condition is met.
```{}
repeat { 
   commands 
   if(condition) {
      break
   }
}
```


```r
v <- "Repeating statement for "
cutoff <- 1

repeat {
   cat(v,cutoff," time /n")
   cutoff <- cutoff+1
   
   if(cutoff > 5) {
      break
   }
}
```

```
Repeating statement for  1  time /nRepeating statement for  2  time /nRepeating statement for  3  time /nRepeating statement for  4  time /nRepeating statement for  5  time /n
```

```r
print("Came out of loop to next statement")
```

```
[1] "Came out of loop to next statement"
```

### while
The While loop executes the code for all elements for which the condition is met.
```{}
while (test_expression) {
   statement
}
```


```r
x=20
while(x<50){
  print("Re do the exam")
  x= x+5
}
```

```
[1] "Re do the exam"
[1] "Re do the exam"
[1] "Re do the exam"
[1] "Re do the exam"
[1] "Re do the exam"
[1] "Re do the exam"
```

```r
print(x)
```

```
[1] 50
```

### break

When the break statement is encountered inside a loop, the loop is immediately terminated and program control resumes at the next statement following the loop. 
```{}
var=1
repeat {
  statement
   var <- var + 1
	
   if(var > 5) {
      break
   }
}
```
we have seen example for break statement before in repeat statement

### next

The next statement in R programming language is useful when we want to skip the current iteration of a loop without terminating it. On encountering next, the R parser skips further evaluation and starts next iteration of the loop.

```{}
for (value in vector) {
   
   if (test_expression) 
      {
	next
			}
	 statement
}
```


```r
v <- LETTERS[1:6]
for ( i in v) {
   
   if (i == "D") {
      next
   }
   print(i)
}
```

```
[1] "A"
[1] "B"
[1] "C"
[1] "E"
[1] "F"
```
We have used 'next' for element 'D' that's why it was skipped.
   
   
# Final Note
In this notes we have learn how to brackets and also how to control the flow of the program using conditional loops and control statements. We have discussed 
   
   + Creating function and usage of **{}**
   + Executing function using **()**
   + Accessing elements in Dataframe, matrix etc. using **[]**
   + if else if
   + for
   + while
   + break
   + next
   
