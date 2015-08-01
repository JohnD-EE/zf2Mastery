#Doctrine Association Mapping

[Making more sense of the Doctrine Association Mapping docs](http://doctrine-orm.readthedocs.org/en/latest/reference/association-mapping.html)
Association mapping is a way of defining relationships between entities. Doctrine uses these associations to create foreign key relationships  
and join tables database.

##Pre-requisites:
Foreign Keys:
* A foreign key is a way of associating one database table with another. 
* A foreign key is a column in database table1 which refers to the primary key in table2.
* Table 2 doesn't need to be altered in any way.
* The foreign key creates a unique relationship between the tables 
* Suppose that a row of data in table1 has an id of 25 and column called table2_id with the value of 7.  This means that that the id 25 in table1 is now related to the id 7 in table2
* This relationship forms a forms a `foreign key constraint` so that the related rows in each table cannot be deleted independently of one another ()e.g. they have `referential integrity`

John Tables (aka junction tables, mapping tables, bridge tables, intersection tables, many to many resolver, link table etc...):
* The standard device for creating many to many mapping between database tables
* Suppose a school in which many students can attend many classes - students can join many classes and classes can have many students
* Two tables: Student & Class
* the join table contains student_id and class_id to map which students are mapped to which classes

##All Possible Association Mappings
**Many to One, Uni-directional**
* In this example there is a User entity and an Address entity.
* So here we have the potential for MANY users all be related to just ONE address (Many to One)
* The relationship is uni-directional so the foreign key is on the User table and not on the Address table
* So this will create an additional column `address_id` in the User table with a foreign key to the `id` column of the Address table 
* The `@JoinColumn` is optional because `address_id` and `id` would be defaults anyway.

```php
/** @Entity **/
class User
{
    /**
     * @ManyToOne(targetEntity="Address")
     * @JoinColumn(name="address_id", referencedColumnName="id") 
     **/
     private $address
}

/** @Entity **/
class Address
{
    // Here there is an address entity with an id column which is referenced by address_id foreign key in the user table
}
```
 
**One to One, Uni-directional**

**One to One, Bi-directional**

**One to One, Self Referencing**

**One to Many, Bi-directional**

**One to Many, Uni-directional with Join Table**

**One to Many, Uni-directional Self Referencing**

**Many to Many, Uni-directional**

**Many to Many, Bi-directional**

**Owning and Inverse side on a Many to Many association**

**Many to Many, Self Referencing**

##Mappiong Defaults
**Mapping Defaults**

##Collections
**Collections**
**Initialising Collections**
