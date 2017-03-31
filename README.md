![alt tag](https://raw.githubusercontent.com/thiagodnf/jacof/master/logo.png)


Java Ant Colony Optimization Framework
=========
**jacof** is an object-oriented Java-based framework for ant colony optimization (ACO). It implements the most used ACO's implementations.

What is the ACO?
-----

Dorigo [1] introduces an ant-based algorithm called Ant Colony Optimization (ACO). The algorithm tries to reproduce the behavior of the ants in the search process of solutions from the choice of the path to be followed until the process of updating the pheromone trail.

The main concepts used in ACO are based on real ants such as an artificial pheromone trail used to communication among the ants, a sequence of local moves to find the shortest path and a stochastic decision policy

The ACOs Developed
-------

This framework implements the following ACO's variations:

| Algorithm                  | Authors | Year | How to use | Reference
|---------------------------|----------------------|----------------------|----|----|
Ant System | Dorigo, Maniezzo and Colomi | 1992 | [Click here](#ant-system) | [1] |
Elitist Ant System | Dorigo | 1992 | [Click here](#elitist-ant-system) | [1,3] |
Ant Colony System | Dorigo and Gambardella | 1997 | [Click here](#ant-colony-system) | [2] |
Rank-based Ant System | Bullnheimer, Hartl and Strauss | 1997 | [Click here](#rank-based-ant-system ) | [4] |
Max-Min Ant System | Stützle and Hoos | 2000 | [Click here](#max-min-ant-system) | [5] |

The Problems Developed
-------

This framework addresses the following problems:

* Next Release Problem (NRP)
* Traveling Salesperson Problem (TSP)

How To Use
-------
At the following, it is pointed out how to use each ACO's variations

### Ant System

```java
Problem problem = new NextReleaseProblem("in/delsagrado20.nrp");

AntSystem aco = new AntSystem(problem);

aco.setNumberOfAnts(10);
aco.setNumberOfIterations(50);
aco.setAlpha(1.0);
aco.setBeta(2.0);
aco.setRho(0.1);

int[] bestSolution = aco.solve();

double value = problem.evaluate(bestSolution);

System.out.println(Arrays.toString(bestSolution) + " : " + value)
```

### Ant Colony System

```java
Problem problem = new NextReleaseProblem("in/delsagrado20.nrp");

AntColonySystem aco = new AntColonySystem(problem);

aco.setNumberOfAnts(10);
aco.setNumberOfIterations(50);
aco.setAlpha(1.0);
aco.setBeta(2.0);
aco.setRho(0.1);
aco.setOmega(0.1);
aco.setQ0(0.9);
	
int[] bestSolution = aco.solve();

double value = problem.evaluate(bestSolution);

System.out.println(Arrays.toString(bestSolution) + " : " + value);
```

### Elitist Ant System


```java
Problem problem = new NextReleaseProblem("in/delsagrado20.nrp");

ElitistAntSystem aco = new ElitistAntSystem(problem);

aco.setNumberOfAnts(10);
aco.setNumberOfIterations(50);
aco.setAlpha(1.0);
aco.setBeta(2.0);
aco.setRho(0.1);
aco.setWeight(6);

int[] bestSolution = aco.solve();

double value = problem.evaluate(bestSolution);

System.out.println(Arrays.toString(bestSolution) + " : " + value);

```

### Rank-based Ant System

```java
Problem problem = new NextReleaseProblem("in/delsagrado20.nrp");

RankBasedAntSystem aco = new RankBasedAntSystem(problem);

aco.setNumberOfAnts(10);
aco.setNumberOfIterations(50);
aco.setAlpha(1.0);
aco.setBeta(2.0);
aco.setRho(0.1);
aco.setWeight(6);

int[] bestSolution = aco.solve();

double value = problem.evaluate(bestSolution);

System.out.println(Arrays.toString(bestSolution) + " : " + value);

```

### Max-Min Ant System

```java
Problem problem = new NextReleaseProblem("in/delsagrado20.nrp");

MaxMinAntSystem aco = new MaxMinAntSystem(problem);

aco.setNumberOfAnts(10);
aco.setNumberOfIterations(50);
aco.setAlpha(1.0);
aco.setBeta(2.0);
aco.setRho(0.1);
aco.setStagnation(10);

int[] bestSolution = aco.solve();

double value = problem.evaluate(bestSolution);

System.out.println(Arrays.toString(bestSolution) + " : " + value);

```

Version
----
1.0


References
-------
[1] M. Dorigo. *Optimization, Learning and Natural Algorithms*. PhD thesis, Politecnico di
Milano, Italy, 1992. [in Italian].

[2] M. Dorigo and L. M. Gambardella. Ant colony system: A cooperative learning approach
to the traveling salesman problem. *IEEE Transactions on Evolutionary Computation*,
1(1):53–66, April 1997.

[3] M. Dorigo, V. Maniezzo, and A. Colorni. Ant system: Optimization by a colony of
cooperating agents. *IEEE Transactions on Systems, Man, and Cybernetics, Part B:
Cybernetics*, 26(1):29–41, February 1996.

[4] B. Bullnheimer, R. F. Hartl, and C. Strauss. A new rank based version of the ant system - a
computational study. *Central European Journal for Operations Research and Economics*,
7:25–38, 1997.

[5] T. Stützle and H. H. Hoos. MAX-MIN ant system. *Future Generation Computer Systems*,
16(9):889–914, June 2000.
