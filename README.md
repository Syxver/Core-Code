# Core-Code
### Core Code Bootcamp


# Weak 1
## (Tuesday 11/1)
### 1- Java language is compiled or interpreted? (El lenguaje Java es compilado o interpretado?) ###
Java can be considered both a compiled and an interpreted language because its source code is first compiled into a binary byte-code. This byte-code runs on the Java Virtual Machine (JVM), which is usually a software-based interpreter. (Java se puede considerar tanto un lenguaje compilado como interpretado porque su código fuente se compila primero en un código de bytes binario. Este código de bytes se ejecuta en la máquina virtual de Java (JVM), que suele ser un intérprete basado en software.)
### 2- Create an algorithm to calculate the equivalent of your local currencty to USD ##
1. find out how much my currency is worth in USD
2. In my case my local currency is USD but as an example lempiras will be used and 1 Lempira is equivalent to 0.041 USD
3. Now if I want to know how many USD I have in HNL, the following will be done:
   1. Have my exact number in HNL
   2. Multiply this figure by 0.041
   3. The result of said multiplication would be my amount of Lempiras in Dollars
Example
I have 350 HNL and I want to know how much it is in USD I do the following:
350 * 0.041 = 14.35

### 3- Create a pseudocode to calculate the aproximated age of a user base on the year they born, (you can define a variable with the actual year if you need it, like for example i could define Y <-- 2022) ##
1. Start
2. Variable X = Year of birth
3. Variable Y = Current year
4. Variable Z = Y - X
5. Show Z and say Age "Z"
6. End
### 4- Why are flowcharts important to us as developers? ##
It is important because it is a diagram that describes a computer process, system, or algorithm. They are widely used in many fields to document, study, plan, improve, and communicate often complex processes in clear, easy-to-understand diagrams.
## ##
## (Wednesday 12/1)
### 1- Translate the year you where born to binary, decimal and hexadecimal ###
I born in 1998.
1. 11111001110
2. 1998
3. 7CE
### 2- Translate 51966 into hexadecimal and binary ###
1. 1100101011111110
2. CAFE
### 3- Base on the examples and the guide of the low-level language: ###

### 3.1 Create a program to add two numbers given by the user ###
```
.data
#Declares variables for program
   num1: .asciiz "\nNumero 1: " 
   num2: .asciiz "\nNumero 2: "
   message: .asciiz "\nEl resultado es: "
   
.text #Declares methods for program
	main:
	#Print num1
		li $v0, 4
		la $a0, num1
		syscall
		
		li $v0, 5
		syscall
		
	#Stores the number put in num1
		move $t0, $v0
		
	#Print num2	
		li $v0, 4
		la $a0, num2
		syscall
		
		li $v0, 5
		syscall
		
	#Stores the number put in num1		
		move $t1, $v0

	#Sum both numbers in $t2	
		add $t2, $t0, $t1

	#Print message
		li $v0, 4
		la $a0 message
		syscall

		li $v0, 1
		move $a0, $t2
		syscall
		
		# Exit
		li $v0, 10
		syscall
```
### 3.1 Create a program that display your name ###
```
.data

Ask: .asciiz "What is your name? " 
hi: .asciiz "Hi "
nice: .asciiz  "Nice to meet you!!"
name: .space 61 # including 

.text

# Print Ask
la $a0, Ask # address of string to print
li $v0, 4
syscall

# Input name
la $a0, name # address to store string at
li $a1, 61 # maximum number of chars 
li $v0, 8
syscall

# Print hi
la $a0, hi # address of string to print
li $v0, 4
syscall

# Print name
la $a0, name # address of string to print
li $v0, 4
syscall

# Print nice
la $a0, nice # address of string to print
li $v0, 4
syscall

# Exit
li $v0, 10
syscall
```
