# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 23/03/2024                                                                       
### REGISTER NUMBER : 212221040048
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
```
/*
likes(john, X) :- 
food(X).
 food(apple).
 food(vegetable).
 eats(sue,X):-eats(bill,X).
 eats(bill,peanuts).
 alive(bill).
*/
```
### Output:
<img width="544" alt="Screenshot 2024-03-23 230829" src="https://github.com/gsuryanavya/AI_Lab_2023-24/assets/133086963/7b87ce40-412f-4aa4-b706-d7dc5099f03d">

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
```
/*
 % Facts
 likes(steve, easy_courses).
 hard(science_courses).
 in_department(bk301, have_fun).
 % Discontiguous directive
 :- discontiguous likes/2.
 % Rules
 in_department_course(Department, Course) :- in_department(Course, Department).
 easy_course(X) :- in_department_course(have_fun, X).
 % Resolution rules
 likes(steve, Course) :- in_department_course(have_fun, Course), not(hard(Course)).
 % Negation of the statement to be proved
 :- likes(steve, bk301).
*/
```
### Output:
<img width="540" alt="Screenshot 2024-03-23 230939" src="https://github.com/gsuryanavya/AI_Lab_2023-24/assets/133086963/25e5f95b-8ab3-441d-8309-7fa72434096d">


### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
```
/*
 criminal(X):
american(X),
 weapon(Y),
 hostile(Z,X),
 sells(X,Y,Z).
 weapon(Y):
missile(Y).
 hostile(Z,X):
enemy(Z,X).
 sells(west,Y,nano):
missile(Y),
 owns(nano,Y).
 missile(m).
 owns(nano,m).
 enemy(nano,america).
 american(west).
*/
```
### Output:
<img width="548" alt="Screenshot 2024-03-23 231035" src="https://github.com/gsuryanavya/AI_Lab_2023-24/assets/133086963/6e37809a-c190-425b-b3c9-253eb014e044">

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
