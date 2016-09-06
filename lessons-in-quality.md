# Lessons in Automation (and Quality)

The following article is based on the talk Dan Acton and I gave at the Industry
Dev Ops Day in Johannesburg on the 22nd of June 2016.

## Background

We wanted to understand how automation will enable as to deliver high quality
products at high velocity by building a real working product.

We wanted to live the motto of automate everything, build a system to build
the product rather than just the product itself. This is sometimes called the
two product principle.

The product we built delivered services to internal customers. The technologies
deployed included application services, OS services and network services.

The system for building the product, constructed and tested the resulting
product based on a set of configuration parameters.

Along the journey of trying live this motto we learnt some lessons.

## Lesson 1: It is Hard Work

If you go done with road you will discover it is hard. There are a few reasons
for this.

First, you need to be precise. You need to know the rules and not just the
answer. The approach of trying different answers until it looks like it works,
doesn't work when you automate. You just can't build a repeatable process
without understanding the system in which you operate. You need to know the
rules.

Second, you need to understand the technical domain (be that the OS, the
middleware, the application or software defined networks). Then there is
the automation tooling (for example Chef for infrastructure automation, or
Cucumber for test automation) that you to master. Finally, you need
software engineering skills to think about the automation system as a
software solution and not just a set of scripts. You need to maintain
the system for building the product as you would the product itself.

Third, you need to remember that the automation is in service of product
you will deliver to your customers. That is why we did not achieve our goal
of automating absolutely everything. Technology constraints meant the automation
effort exceed the benefit in the context of the customer product we were
delivering. You need to pragmatic and remember the end goal is to deliver value
for your customers.

# Lesson 2: It is Never Only Once

Not everybody will believe that automation is worth the effort.

"Why are you automating, we will only build it once?" That is something
you might to asked when going down the path of automating everything.
But is it not true.

Name a system that never changes, name a system that does not need to be
verified and you have a system that will only be built once. However, you
will still encounter unexpected change. How about a data centre migration?

Once you gone down this journey, once you have factory in place, the cost
of building the next copy will fall to almost zero. That changes your ability
to respond to new demands in ways you never imagined.

A reduction in the cost of creating a capability due to automation results
in an increase in demand for that capability.

# Lesson 3: It Drives Velocity

Automation will drive your velocity, however, it won't help you win the
spirit race. Over a longer distance it will assist in building up velocity
and maintaining it.

Automation is hard, you need to overcome a hurdle before you can start
delivering value. You are forced to move some complexity left (earlier in the
project). Once you overcome the hurdle, tasks start to disappear and you start
to pick up speed. Take care to ensure you are still heading in the direction
of delivering a product of value to your customers. Remember velocity is a
vector (with speed and direction).

Knowledge and patterns are transferred into the automation code. You no longer
need to manually apply these patterns in each case. This frees up time to work
on other value adding tasks. For that you need software engineering skills.

The solution is also more internally consistent. It works the same way in
every case. This frees up time and mental energy.

Automation is enables agility, the ability to response to external changes
and/or unexpected events. For example, we had to integrate a product into
a solution at short notice. Automation and virtual infrastructure allowed
us to create a test platform to prove the proposed product would integrate
into the solution in a matter of days. Unfortunately, the proposed product
proved to be unsuitable due to conflicting requirements between it and
another component. After verifying with the vendors involved that the product
would not work, it only took a small code change before we had integrated
an alternative product into a test platform and within a day we had proven
the alternative product works. Automation enabled high velocity response
even in the face of failure.

# Lesson 4: It Drives Quality

The effort you put into building the system that builds the product shows
up in the quality of the finished product.

Quality is enabled by code being repeatedly verified. Automation enables
this. This goes beyond just automated testing. The behaviour of any system
is impacted by its environment. Only some of these interactions are explicitly
modelled, others are not. Repetition with a varying environment allows more
interactions to surface. Fixing those that impacts behaviour drives in
quality. When doing it once manually, you only need the stars to align once,
when repeating it automatically many times, you will find the stars
unaligned at least once.

Quality also comes from the freedom to refactor. The freedom to fix the small
things, safe in the knowledge that "free" verification is available to
verify continued correct function. This "free" verification is not
possible without automation.

Consistency also drives quality. Consistency can be enabled by including
high level concepts and patterns into the automation code as first class
citizens. Driving these concepts into the automation code in a just in time
basis requires the freedom to refactor.

With the system we built, the parts that cause the most trouble are those
components we could not automate due to time and/or technology constraints.

That is how automation assists in delivering quality products.

# Increased Quality and Velocity

Quality and velocity are traditionally seen as quantities you need to trade
off. To increase quality we need to go slower, to increase velocity we need
to sacrifice quality.

That need not be the case. Automation is one of the tools that allows us to
shift the quality versus velocity curve up. Driving up both the quality and
the velocity.

By investing in the system that builds the product you can shift the curve up.

That is what the automation journey demonstrated to us. Automation is a tool
that can be used to move the curve up, delivering improved quality at
higher velocity.
