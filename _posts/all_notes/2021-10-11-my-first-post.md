---
layout: post
title:  "Simplex Method - Linear Programming (LP)"
date:   2021-10-12 09:29:20 +0700
categories: post
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Pre-Req: Linear Programming, also called as linear optimization, is a method to achieve the best outcome in a mathematical model with constraints represented by linear relationships.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Simplex algorithm is a method used in mathematical optimization to solve linear programming problems. It can be done by hand or using computers (ex. using solver in Excel).
Furthermore, Simplex method is used to solve maximization problems (every minimization problem can be converted to a maximization problem).
We know that every linear programming (LP) problem has basic solutions. We could check all the solutions for optimality and feasibility
one by one and get our optimal solution. This is simple when our LP problem has a small number of variables. However, most of the real-world
LP problems have many variables and a huge number of constraints. Checking each possible solution would take a great amount of time. 
For example, if a problem has n = 30 decision variables and m = 35 problem constraints, thenumber of possible basic solution becomes 
approximately 3 × 10^18 . It will take about 15 years for an average modern personal computer to check all these solutions for feasibility and optimality. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The simplex method describes a ”smart” way to find much smaller subset of
basic solutions which would be sufficient to check in order to identify the optimal
solution. Staring from some basic feasible solution called initial basic feasible
solution, the simplex method moves along the edges of the polyhedron (vertices
of which are basic feasible solutions) in the direction of increase of the
objective function until it reaches the optimal solution. We can see the graphical representation of simplex method in the following image.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ![simplex representation](../../assets/posts_images/simplex_0.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In order to tackle the simplex method, we must know the standard form of a standard maximization problem. 
The form is as follows:

{% highlight ruby %}
#=>Objective function:
P = c1 * x1 + c2 * x2 + . . . + cn * xn
#=> Constraints:
a11 * x1 + a12 * x2 + . . . + a1n * xn ≤ b1
···
am1 * x1 + am2 * x2 + . . . + amn * xn ≤ bm
x1 , x2 , . . . , xn ≥ 0

{% endhighlight %}

where x1 , x2 , . . . , xn are decision variables, c1 , . . . , cn ,
a11 , . . . , amn are any real numbers, and b1 , . . . , bm ≥ 0 are
nonnegative real numbers.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
We will follow the list of steps to complete LP problem using Simplex method:

    • Standard form
    • Introducing slack variables
    • Creating the tableau
    • Pivot variables
    • Creating a new tableau
    • Checking for optimality
    • Identify optimal values

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
