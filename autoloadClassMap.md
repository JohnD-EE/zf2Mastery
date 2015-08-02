#Autoload Classmap

An autoload_classmap.php file can sit within your module and is read when ZF2 runs.  
This speeds up the class autoloading 
The file is also needed when running Doctrine commands so doctrine can find the entities.

I got this to work by 
going into my VM in my module directory and running 
```
php ../../vendor/zendframework/zendframework/bin/classmap_generator.php
```


