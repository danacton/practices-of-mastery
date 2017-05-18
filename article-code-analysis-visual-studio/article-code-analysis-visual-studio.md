This article shows how to use static code analysis in Visual Studio so that you can adhere to acceptable style guides and coding standards for your Visual Studio-based projects.

# Understanding static code analysis in Visual Studio
Static Code Analysis can help developers identify potential issues in their code that could affect quality. Microsoft has a standard set of rules which are sufficient to highlight common pitfalls and issues. These rules can be applied to your code as you write it, without the need for compilation.

# Running Code Analysis manually
As you are writing code, you can analyze your code by selecting the _Analyze_ menu -> _Run Code Analysis_. You can then fix issues you find as you code.

# Running code analysis as part of the build
It's also a good idea to analyse your code each time you build your project. In a team project where there are multiple contributors, this ensures that the code stays in-line with your expected level of quality, regardless of who committed it.

To enable analysis on each build, select _Enable Code Analysis on Build_ in the project's Properties.

# Defining the rules to be applied during analysis
You can understand the rule sets that are applied when you analyze your code (and even customize your own rule sets) in the article [here on MSDN](http://msdn.microsoft.com/en-us/library/dd264974.aspx).

