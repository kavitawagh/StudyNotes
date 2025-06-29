Lets you define family of algorithms and put each of them into separate class and make their objects interchangeable.

Context class
\- strategy
\+ setStrategy()
\+ doSomething(): strategy.execute()

IStrategy
\+ execute()
  
StrategyA
StrategyB
StrategyC

//Client code

context.setStrategy(strA)
context.doSomething()

context.setStrategy(strB)
context.doSomething()
