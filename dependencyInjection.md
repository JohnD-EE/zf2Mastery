#Dependency Injection - DI
DI is integral to ZF2, separating the creation of objects and their dependencies - Inversion of Control (Martin Fowler)
Dependency Inversion Principle - code should depend upon abstractions - decoupling from lower level implementatins
Inject your dependencies into your classes instead of instantiating an object within a class

3 types of injection:
* Constructor Injection
* Setter Injection 
* Interface Injection

*Dependency Injection enables loose coupling and loose coupling makes code more maintainable* - Mark Seemann
Maintainability, Extensibility, Testability

Rob Allen
[Injecting dependencies into ZF2 Controllers](http://akrabat.com/injecting-dependencies-into-your-zf2-controllers/)
[What problem does dependency injection solve?](http://akrabat.com/what-problem-does-dependency-injection-solve/) - An intro to Dependency Injection Containers DIC
[YouTube - Introducing Dependency Injection](https://www.youtube.com/watch?v=ElnqUIjLWVk) - see also [supporting slides](http://akrabat.com/wp-content/uploads/2014-10-28-zc-di-in-zf2.pdf)

Anthony Ferrara
[YouTube - Dependency Injection](https://www.youtube.com/watch?v=IKD2-MAkXyQ)

Matthew Setter
[Zend Framework 2 Core Concepts – Dependency Injection](http://www.masterzendframework.com/articles-2/zend-framework-2-core-concepts-understanding-dependency-injection)

Padraic Brady
[http://blog.astrumfutura.com/2011/10/zend-framework-2-0-dependency-injection-part-1/](Zend Framework 2.0: Dependency Injection (Part 1))

Matthew Weier O’Phinney
[Dependency Injection: An analogy](https://mwop.net/blog/260-Dependency-Injection-An-analogy.html)

Ralph Schindler 
[Learning About Dependency Injection and PHP](http://ralphschindler.com/2011/05/18/learning-about-dependency-injection-and-php)

Fabien Potencier
[What is Dependency Injection?](http://fabien.potencier.org/what-is-dependency-injection.html)
[Twittee - a DIC which fits into a tweet](https://github.com/fabpot/twittee)

Laracasts:
[IOC Containers](https://laracasts.com/lessons/the-ioc-container)
[DI Containers](https://laracasts.com/lessons/dependency-injection-containers)

Pimple:
[A small PHP 5.3 dependency injection container](https://github.com/silexphp/Pimple)

[YouTube - Dependency Injection vs Service Locator](https://www.youtube.com/watch?v=PniFqdDJfCg)
In ZF2 the Service Locator is sometimes described as a Dependency Injection Container
Both help clients create objects