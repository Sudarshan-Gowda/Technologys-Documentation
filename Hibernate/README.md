# Hinernate
Brief Introduction to Hibernate

## 	Introduction:
*	Hibernate is an open source ORM tool used to connect & interact with the database.
*	It is light weight & faster in performance.

### 	ORM tool:
*	ORM simplifies the data creation, data manipulation & data access.
*	It is a programming technique that maps the object to the data stored in the database.
*	It internally uses the JDBC API to interact with the database.

### 	JPA: 
JPA is a Java Persistence API which provides certain functionality & standard to ORM tools. javax.persistence packages contains the JPA classes & interfaces.

**Advantages of Hibernate Framework:**

*	Open source & lightweight
*	Fast performance
*	Database Independent Query.
*	Automatic table creation
*	Simplifies complex join

### 	Hibernate Mapping

*	One to One
*	One to Many
*	Many to One
*	Many to Many

#### 	One to One

Various supported techniques for one to one mapping
1. 	Using foreign key association
2. 	Using common join table
3. 	Using shared primary key


##### 	Using foreign key association:

In this kind of association, a foreign key column is created in owner entity. For example, if we make EmployeeEntity owner, then a extra column "ACCOUNT_ID" will be created in Employee table. This column will store the foreign key for Account table.

Table structure will be like this:

 


 

 

 


##### 	Using Join Table

In this technique, main annotation to be used is @JoinTable. This annotation is used to define the new table name (mandatory) and foreign keys from both of the tables. Lets see how it is used:

 

 

##### 	Shared Primary key

In this approach, @PrimaryKeyJoinColumn is the main annotation to be used. Let see how to use it.

 

 

 



#### 	One to Many

Hibernate one to many mapping solutions
1)	Hibernate one to many mapping with foreign key association
2)	Hibernate one to many mapping with join table


##### 	Foreign Key Association

In this approach, both entity will be responsible for making the relationship and maintaining it. EmployeeEntity should declare that relationship is one to many, and AccountEntity should declare that relationship from its end is many to one.

 


Parent Entity: EmployeeEntity

 


Child Entity: AccountEntity

 

Main Class:

 


##### 	Using Join Table

This approach uses a join table to store the associations between account and employee entities. @JoinTable annotation has been used to make this association.
 

Parent Entity: EmployeeEntity

 

Child Entity: AccountEntity

 

Main Class:

 

#### 	Many to Many

Hibernate many to many mapping is made between two entities where one can have relation with multiple other entity instances. 

For example, for a subscription service SubscriptionEntity and ReaderEntity can be two type of entities. Any subscription can have multiple readers, where a reader can subscribe to multiple subscriptions.

 

Parent Entity:

Owner entity is the entity which is responsible for making the association and maintaining it. In our case, I am making ReaderEntity the owner entity. @JoinTable annotation has been used to make this association.

 


Child Entity:

Our mapped entity is SubscriptionEntity which is mapped to ReaderEntity using “mappedBy” attribute.

 


### 	Important concepts

#### 	Difference between load () and get ()

Hibernate Session provide different methods to fetch data from the database. In that two of them are get and load functions.

If we call the get() methods, It returns the object by fetching it from the database or from the hibernate cache Whereas load() just returns the reference of an proxy object & it loads the data from the database or cache only when we access other properties other of the object.

Whenever the data is not there in the database & if we call get() & load() methods , get() method return null object if the data is not present but load method throws Object Not Found Exception.

As a part of performance load method is preferred to use since it will load the proxy object and it will reduce the database hit count since it will hit to database only whenever we load the data other than getId() & if it is not in database. But get method will always load the actual or real object from the cache or database hence number of database hit count will be more. & performance will be slight slower than load method.

When To Use Get and Load:
Whenever we don’t know whether the object is present or not then its good option to go with get method since it will return null if no object found in the cache or database but in case of load we should be known the data, and then only we should go for load method.

#### 	Difference between merge and refresh ()

refresh() is used to re-populate the entity with latest data available in database. This method will reload the properties of the object from the database, overwriting them.

merge() does exactly opposite to what refresh() does. It updates the database with values from the detached entity.

#### 	Second level Cache

Second-level cache is an optional Cache which Hibernate provides. It is accessible to all Sessions.

The Second Level cache is by default disabled. Hibernate also doesn't provide any caching implementation for that. Instead, it gives CacheProvider interface and any third party Cache which implements CacheProvider interface can be hooked as Second level cache, e.g. EHCache or NCache.

The second-level cache can improve the performance of your Java Web application even further than first level.

**First level Cache vs. Second-level Cache in Hibernate**

1.  The primary difference is that first level cache is maintained at the Session level while the second level cache is maintained at SessionFactory level.

2.  The data stored in the first level cache is accessible to the only Session who maintains it, while the second level cache is accessible to all.

3.	The first level cache is by default enabled while the second level cache is by default disabled.

**A couple of things to know about hibernate first level cache**

1.  You can use Session.evict() to remove the loaded entity from the first level cache, can use refresh() method to refresh the cache and can use clear() method to remove all entities in cache.

2.  You cannot disable the first level cache, it always enabled.

3.  Hibernate entities or database rows remain in cache only until Session is open, once Session is closed, all associated cached data is lost.

**Different strategies for caching an object:**
* 	Read Only: 
This caching strategy should be used for persistent objects that will always read but never updated. It’s good for reading and caching application configuration and other static data that are never updated. This is the simplest strategy with best performance because there is no overload to check if the object is updated in database or not.

* 	Read Write:
It’s good for persistent objects that can be updated by the hibernate application. However if the data is updated either through backend or other applications, then there is no way hibernate will know about it and data might be stale. So while using this strategy, make sure you are using Hibernate API for updating the data.

* 	Nonrestricted Read Write:
If the application only occasionally needs to update data and strict transaction isolation is not required, a nonstrict-read-write cache might be appropriate.

* 	Transactional:
The transactional cache strategy provides support for fully transactional cache providers such as JBoss TreeCache. Such a cache can only be used in a JTA environment and you must specify hibernate.transaction.manager_lookup_class.

#### 	Hibernate Cascade Types

Basically while updating (doing any operation) master entity, to make associated entity also to get reflected, we will use Cascade Type.
Detail Explanation: Let’s consider we have two entity, One is Employee (Parent) and other one is Account (Associated), If we do any operation to Parent entity, that should also to be reflected in associated entity means we should configure cascade type.
For Ex: While deleting Employee details and we not configured Cascade type with ALL or REMOVE, Container will not allow to remove the object since it hold relation with associated entity. By Configuring cascade type we can remove both the entity.
List of Cascade-Types available are:

* 	**CascadeType.PERSIST** : 
cascade type persist means that save() or persist() operations cascade to related entities. 
* 	**CascadeType.MERGE** : 
cascade type merge means that related entities are merged when the owning entity is merged. 
* 	**CascadeType.REFRESH** : 
cascade type refresh does the same thing for the refresh() operation. 
* 	**CascadeType.REMOVE** : 
cascade type remove removes all related entities association with this setting when the owning entity is deleted. 
* 	**CascadeType.DETACH** : 
cascade type detach detaches all related entities if a “manual detach” occurs. CascadeType.ALL : cascade type all is shorthand for all of the above cascade operations.

The orphan removal will do the same job as like CascadeType in JPA. We just need to configure enable or disable.


