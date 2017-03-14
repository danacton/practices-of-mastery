# Local Conventions and Code Complexity

The complexity of software limits the ability of teams to maintain
and change the software. This complexity is often described in terms
of accidental complexity and essential complexity 
([See “No Silver Bullet” by FP Brooks](https://en.wikipedia.org/wiki/No_Silver_Bullet)).
Accidental complexity relates to problems created by software engineering 
that can be fix in principle. Essential complexity is caused by the problem to
be solved.

One of the Practices of Mastery is local conventions. Local conventions
include style guides. A typical style guide covers two aspects, firstly, 
the code layout and language constructs, and secondly, complexity measures. 

The topic of interest here is complexity measures and the impact of applying
the requirement of adherence to a code base. Can these code complexity measures
be used to manage accidental complexity?

## Approach

For this exercise a working code base of about 2000 lines of Ruby code is used. 
The code was developed without the requirement to adhere to any style
guide. 

[Rubocop](http://rubocop.readthedocs.io/en/latest/) is Ruby static code analyzer. 
It can enforce many of the guidelines outlined in the 
[Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide).

In this exercise version 0.39.0 of Rubocop is used to the enforce  code 
complexity measures .

The code complexity measures of interest for this exercise are:
* Assignment Branch Condition size for a method is too high. (Limit 15)
* Method has too many lines. (Limit 10)
* Class has too many lines. (Limit 100)
* Cyclomatic complexity for a method is too high. (Limit 6)
* Perceived complexity for a method is too high. (Limit 7)

All the other default style settings in Rubocop are also enforced. The one that
impacts these measures most directly is the line length limit. The default 
limit of 80 characters is used.

## Objectives

The first objective is to determine if it is possible to change the code
base to adhere to these requirements while maintaining the functionality. 
An automated test suite is available for rapid feedback on functional adherence. 
The impact on performance is not considered as the performance of the 
application in question is dominated by external factors.

The changes made need to be reasonable in the context of software engineering
practices and the features of the target language (Ruby).

The second objective is to document the methods used to achieve adherence to 
the complexity measures. 

The third objective is to observe the changes to the structure of the code base.

## Techniques

The first step is to let software do the work, i.e. automation. In particular
to use the auto fix switch (-a) of Rubocop. It fixes many of the style and 
language usage related non compliance.

This feature is not perfect and it can introduce bugs into the code. In our case
a change to the String literal syntax introduced additional whitespace that
application is sensitive to. The automated test suite detected the bug and it
was fixed.

To further improve adherence manual change is required. The approach is to make
the smallest possible change that moves towards the goal (of full style guide
adherence) while ensuring the code still functions as before (using
reasoning and automated testing). This is repeated until the goal is 
accomplished.

At each step the changes are committed to version control (another Practice of 
Mastery). This provides a history of the changes and the thought processes. In
general a file by file process is followed.

### Break Apart

To achieve compliance with the metrics it is necessary to break apart methods
that include more than one concept. For example, consider a function that 
effectively produced two outputs based on it's input. It has different 
cases for different input values. If it had 5 different cases for how output 
1 is calculated and 2 different cases for how output 2 is calculated then 
we had 10 cases (2 x 5) in the combined function. Splitting it apart results in 
two functions one with 2 cases and one with 5 cases. This is more 
understandable and maintainable. To a reader of the code it easier to see how 
output 2 is calculated (looking at 2 versus 10 cases).

It is very difficult to write a function that deals with 10 cases in 10 lines 
of code. Writing a function that deals with 2 cases in 10 lines of code is
significantly easier.

The heart of incidental complexity is joining things together that don’t need 
to be joined together. The complexity metrics force you to look for ways 
to break things apart, otherwise you can't achieve adherence.

### Introducing New Concepts

Another strategy is to introduce new a concept that models a part of the
problem domain. The required functionality is then written in terms of this
new domain concept.

An interesting side effect of this strategy is a better understanding and
modelling of the problem domain.

The resulting code is then shorter and easier to follow. Depending on the usage
of the domain concept it could result in an nett gain or loss of line of code.

### Higher Level Language Concepts

Language concepts like 'map' and 'filter' can replace imperative loops. This
results in a decrease in code size and code complexity measures. It also
has the benefit of bringing the intent of the code to the surface.

The code is then written is terms of what, leaving more of the how to the
compiler and runtime.

The resulting code tends to shorter in terms of line of code.

### Extract Common Patterns

Examination of the code can reveal common patterns. Extracting these patterns
into new classes and/or methods will result in a reduction in code complexity.

An interesting side effect of this technique is that it can reveal patterns
in the problem domain. In this case a symmetry in the problem domain was
discovered by looking for patterns in the code. Asymmetries in the problem
domain are now reflected more directly.

The resulting code is easier to follow and maintain.

### Remove Unused Code

This is the simplest to execute. Removing code that does contribute to the
required functionality.

The resulting code is smaller and now the reader of the code does not need
to consider the purpose of the code.

## Change Statistics

The original code is 1748 lines (excluding comments and blank lines) in 
18 files with 981 Rubocop offences. The largest file is 940 lines and
the largest method is 398 lines.

The compliant the code is now 2004 lines (excluding comments and blank lines)
in 42 files with each containing a Ruby class or module. The largest file is
163 lines and no method had more than 10 lines of code (as measured by Rubocop).

The number of methods increased form 201 to 301.

The changes statistics are 42 files changed, 1789 insertions and 1378 
deletions. Excluding the automatic Rubocop auto changes the statistics are 42 
files changed, 1713 insertions and 1226 deletions.

The number of remaining Rubocop offences is 0.

The test suite is unchanged.

## Results

The first result is that it is possible to write reasonable Ruby code 
that meets the code complexity requirements measure by Rubocop at the default 
settings described above.

The techniques used included:
* Break apart - This tended to increase the number of components (modules, 
classes and/or methods), and tended to increase the code size in terms of lines. 
Almost by definition these components tended to be simpler and deal with fewer 
concepts.
* Introducing new concepts. Also be definition this increase the number of 
components in the system (modules or classes) and increased the total line 
code. The line count of consumer of the new concept decreased. The consumer of 
the concept could then be written in term of the new concept and not language 
level constructs.
* Use of higher level constructs. This tends to decrease 
the line count of the methods involved as well as reduce the complexity measures. 
It is my observation that it is easier to see the intent of the code when using
higher level language constructs.
* Extract common code and patterns. This will tend to increase the number 
classes and or methods, but depending on the case either increase or reduce the 
total line count. Future maintainability is increased due to the removal of 
this duplication.
* Removal of unused code. This by definition reduces the line count.

The overall code base in terms of line of code increased, the number of 
components either measured by classes or modules, and methods also increase 
significantly. The concerns of each of these components themselves, however,
decreased.

## Conclusion

The use of code complexity measures like those included with Rubocop can
reduce the complexity of code. The complexity measures included with 
Rubocop are limited in scope and do not address complexity due to coupling 
between components.

This exercise also illustrates that complexity is more easily achieved than 
simplicity. Additional work and focus is required to reduce accident 
complexity.

