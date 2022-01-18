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
### 3.2 Create a program that display your name ###
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
## ##
## (Thursday 13/1) ##
### Search for real word applications of Javascript ###
1. Web Development

JavaScript is a client scripting language which is used for creating web pages. It is a standalone language developed in Netscape. It is used when a webpage is to be made dynamic and add special effects on pages like rollover, roll out and many types of graphics. It is mostly used by all websites for the purpose of validation. In addition to validations, it supports external applications like PDF documents, running widgets, supporting for flash applications etc. It can also load content into a document whenever the user requires it without even reloading the entire page.

2. Web Applications

With technology browsers and personal computers have improved to the extent that a language was required to create robust web applications. When a user explores a map in Google Maps then the user just needs to click and drag the mouse. All detailed view is visible by just a click. This is possible due to JavaScript. It interacts with the browser without sending messages to and fro to the servers. JavaScript uses Application Programming Interfaces(APIs) that provide extra powers to the code.

3. Presentations

JavaScript also provides the facility of creating presentations as a website. JavaScript provides RevealJS and BespokeJS libraries to build a web-based slide deck. Reveal.js creates some of the most beautiful and interactive decks using HTML. A user can easily insert nested slides. Even if the user is not aware of programming language then they can easily build a site with so much help online. These presentations are touch optimized and work great with mobile devices, phones, and tablets. With all this JavaScript also provides different transition styles, themes, and slide backgrounds. It supports all CSS color formats. JavaScript also provides Bespoke.js plugin with a wide variety of features. These include responsive scaling, animated bullet lists, and syntax highlighting for code examples. It provides themes which are polished and not too flashy. The quickest way to start Bespoke.js is using a generator. It allows the user to set titles to your presentation and go through a set of questions to get the plugins required.

4. Server Applications

Node JS is built on Chrome’s Javascript runtime for building fast and scalable network applications. It uses event-driven, lightweight and efficient applications which are to be distributed over the systems with the help of a server. Javascript is used to handle HTTP requests and generate contents. When a user is writing thick applications in JavaScript on the client then a user may even write the logic in JavaScript on the server so that cognitive leaps can be done from one language to the other.

5. Web Servers

Using Node JS a web server can be created. The advantages of Node JS are that it is event-driven and would not wait for the response of the previous call. It moves to the next call and takes advantage of events to get notifications when a response is received for a previous call. The servers built on Node JS are very fast and do not use buffering and transfers chunks of data. In addition to this, it is single threaded with event looping which is used in a non-blocking way. The HTTP module can help in creating a server by using the createServer() method. This method is executed whenever someone tries to access port 8080. In response to this, the HTTP server should display HTML and should be included in HTTP header. It can be installed easily by typing ‘npm install -g http-server’ and it can be started by typing http-server command.

6. Games

Not only websites but uses of JavaScript also helps in creating games for leisure. The combination of JavaScript and HTML5 makes JavaScript popular in games development as well. It provides the Ease JS library which provides simple solutions for working with rich graphics. It also has an API that is familiar to all flash developers with a hierarchical display list. A user can create a Stage and it will render the display list to its target canvas. Ease JS also has 2D bitmaps called Sprites which are drawn directly to render the target for transformations.

7. Art

Using the HTML5 in JavaScript drawing graphics on a web page has become easier. All two and three-dimensional shapes can be easily drawn on a canvas and this has opened the browser as a new medium for all different digital art projects. A canvas has no border and no content and hence lets the user create his own art.

8. Smartwatch Applications

Javascript being the most used language is because it is being used in all possible devices and applications. Uses of JavaScript provides a library Pebble JS which is used in smartwatch applications. This framework works for applications that require the internet for its functioning. Using Pebbles allows a developer to create an application for a number of watches using JavaScript.

9. Mobile Applications

The most important thing that can be done by the uses of JavaScript is building applications without web contexts. Mobiles being mostly available in Apple and Android two different languages are used to build these. It should be possible to write once and use it on both platforms of these devices. PhoneGap is the framework which enables this. Also recently we have React Native that serves this purpose. It is the major player in cross-platform changes and deployments. Hence uses of Javascript can be used to deploy and download the respective applications across cross environments.

10. Flying Robots

Yes, even this is the field that is not left untouched by JavaScript.Using Node Js a user can program a flying robot.
