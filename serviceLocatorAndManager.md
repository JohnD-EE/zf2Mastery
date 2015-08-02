#Service Locator and Manager
The Service Locator and Service Manager are confusing concepts in ZF2:
We can use `$this->getServiceLocator()` and `$this->getServiceManager()` which both seem to return a `Service Manager` object. 

The Service Locator is actually the `Interface` and the Service Manager is an implementation of this interface.

The Service Manager is an example of `Inversion of Control` - IoC - the aim is to remove dependencies. This is done by Dependency Injection - DI - which is a form of IOC
The Service Manager is an Inversion of Control Container which achieves Dependency Injection.
We want to move away from code like this in the controller: '$object = new MyClass();' we don't want to use new in the controller (apart from `throw new Exception('This went wrong');')
The Service Manager lets us specify dependencies through configuration.
```php
$sm = $this->getServiceLocator();
$object  = $sm->get('MyClass');
```
This should go in a factories array in Module.php, not in the controller or models!  
See article by Reese Wilson [Using the ServiceManager as an Inversion of Control Container (Part 1)](http://techblog.shinymayhem.com/2013/09/using-servicemanager-as-inversion-of.html)

In our Module.php we should add the factory closures for the services we need in the controller:
```php
public function getControllerConfig()
{
    return array('factories' => array(
        'Application\Controller\Customer' => function ($sm)
        {
            $customer = $sm->getServiceLocator()->get('Customer');
            $controller = new Controller\CustomerController(
                $customer, $viewFactory);
            return $controller;
        }
    ));
}
```
The service above isn't created until the controller's constructor is called, because it is a factory which is being passed in, not a service / model.
The factory is a closure (an un-named function) which can be saved as a variable. By default, services are shared (this can be changed through config).
The first time it is referenced, a shared services is instantiated by calling the closure creating the object, and the instantiated object is returned for subsequent references


ZF2 Uses Multiple Service Managers


[Wikipedia - Service Locator Pattern](https://en.wikipedia.org/wiki/Service_locator_pattern)


Rob Allen
[Zend\ServiceManager configuration keys](http://akrabat.com/zendservicemanager-configuration-keys/)

Jurian Sluiman
[Using Zend Framework service managers in your application](https://juriansluiman.nl/article/120/using-zend-framework-service-managers-in-your-application)
