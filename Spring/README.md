# Spring Framework:

## 8.1	Introduction:

Spring is a light weight framework provides support to other framework as well such as Structs, Hibernate, EJB etc. It is developed by Rod Johnson in 2003.


Advantages of Spring Framework:
*	Predefined Templates -- Spring framework provides templates for JDBC, Hibernate, JPA etc. technologies, Lets take the example of JDBC Template, we don’t need to write for Exception Handling, Create connection, statement, committing  transaction, closing connection <br/>
*	Loose coupling -- Spring applications are loosely coupled because of dependency injection <br/>
*	Easy to test <br/>
*	Lightweight<br/>
*	Fast development<br/>
*	Power Abstraction<br/>
*	Declarative support<br/>


## 8.2	IOC (Inversion of Control):
*	IOC makes the code loosely coupled. In such cases there is no need to modify the code if our logic is moved to new environment. <br/>
*	And also it makes the application easy to test & maintain.<br/>
*	In spring framework IOC container is responsible to inject the dependency. We provide Meta data to the IOC container either by XML file or annotation.<br/>

### 8.2.1	IOC container:
*	IOC container is responsible for instantiate, configure & assemble the objects.<br/>
*	It gets the information from the XML file and works accordingly. <br/>

Types of IOC container:
*	BeanFactory (org.springframework.bean.factory)
*	ApplicatonContext (org.springframework.context)

#### 8.2.1.1	Using BeanFactory:

Resource resource = new ClassPathResource("applicationContext.xml");  <br/>
BeanFactory factory = new XmlBeanFactory(resource);  <br/>

#### 8.2.1.2	Using ApplicatonContext:

ApplicationContext context =    new ClassPathXmlApplicationContext("applicationContext.xml"); <br/>

	
## 8.3	Dependency Injection:

DI is design pattern that removes the dependency from the programming code so that it can be easy to manage & test the application. It makes our program loosely coupled.<br/>

Two ways to perform dependency injection:<br/>
* By Constructor
*	By Setter method

### 8.3.1	Dependency Injection by Constructor:

*	<constructor-arg> which is sub element of bean is used for constructor injection.<br/>
*	primitive & sting based values<br/>
*	dependent objects<br/>
*	Collection values etc.<br/>

**Additional Info**
*	Simple bean initialization

	``` <bean id="" class=""><br/>
	<constructor-arg value="" type=""/>
	</bean>```

*	Object Initialization:
	``` <bean id="" class="">
    		<constructor-arg> 
     		   <ref bean=""/> <
     		 /constructor-arg>
  	    </bean>```

*	List Initialization:

	```  	<bean id="" class="">
			<c nstruct r-arg>
				<list>
					<value>Test1</value>
					<value>Test2</value>
				</list>
			</c nstruct r-arg>	
 		</bean>```


*	For List of Object Ref:

	```  
 	<bean id="" class="">
		<c nstruct r-arg>
			<list>
				<ref-bean>test1</ref-bean>
				<ref-bean>Test2</ref-bean>
			</list>
		</c nstruct r-arg>	
 	</bean>  ```

 
*	Map:

	``` <bean id="" class="">
	      <constructor-arg>
		<map>
		  <entry key="" value=""/>
		</map>
	      </constructor-arg>
	    </bean>
	```
 
### 8.3.2	Dependency Injection by Setter Method:

* The <property> which is subelement of <bean> is used for setter injection.
* We can inject the dependency for the 
  1	Primitive and String based values
  2.	Object based values
  3.	Collection
*	Simple property
   
   ```<bean id=""  class="">
        <property name="" value=""/>
    </bean> ```
    
* Object
	 ```<bean id="" class="">
	      <property name="" ref=""/>
	    </bean>```
 
*	List of String
 ```<bean id="" class="">
	    <property name="">
        <list>
          <value></value>
        </list>
      </property>
    </bean>
 ``` 
*	List of Objects:
```
 	<bean id="" class="">
		<property name="">
			<list>
			<ref bean=""/>
			</list>
		</property>
	</bean>	
```

*	Map:
```
	<bean id="">
		<property name="">
			<map>
				<entry key="" value=""/>
			</map>
		</property>
	</bean>
```

### 8.3.3	Difference between Constructor & Setter Injection:

1. Partial Dependency: If the class has 3 property and we if want to initialize only 2 of them means we need  to go for Setter Injection, through constructor is not possible.
2. Overriding - If we define both constructor as well as setter, container will use setter injection
3. Changes - constructor will initiate bean every time so better to go for setter injection always.  


## 8.4	Autowiring in Spring:

* Autowiring enables us to inject the object dependency implicitly. 
*	It internally uses setter or constructor injection.
*	Autowiring can't be used to inject the primitive & string values. It works for reference only.

### 8.4.1	Advantages of Autowiring:

It requires less code because we don’t need to write code for inject the dependency explicitly.

### 8.4.2	Disadvantages:

* No control of programmer
*	It can’t be used for primitive & string values.

### 8.4.3	Autowiring modes:

*	no   --> It is the default autowiring mode.
*	byName --> container injects the bean according to the name of the bane. It internally calls the setter dependency injection. Here property name and bean name should be same.
*	byType --> It injects the dependency according to the type. It internally calls setter injection
             Here property name and bean name can be different.    
*	constructor ---> It injects the dependency by calling the constructor of the class.
                   It calls constructor having large number of parameters.
*	autodetect --> It is deprecated since spring 3.

## 8.5	AOP: Aspect Oriented Programming Language:

*	AOP breaks the program logic into distinct parts (called concerns).
*	It is used to increase the modularity by cross-cutting concerns.
*	Cross cutting concerns that can affect the whole application & should be centralized in one location in code as possible, Such as transaction management, authentication, logging, security etc.
  
## 8.6	Spring with ORM Framework:
*	Spring provides an API to easily integrate with ORM framework such as Hibernate, JPA, iBATIS etc

### 8.6.1	Advantages of ORM Frameworks with Spring:

*	Less coding is required.
*	Easy to test.
*	Better exception Handling.
*	Integrated Transaction Management.

## 8.7	Hibernate with Spring Integration:
*	Spring framework provides Hibernate Template class, So we don’t need to follow many steps like create Configuration, BuildSessionFactory, Session, Beginning & committing transaction.
*	So it saves lot of code.

### 8.7.1	Methods of Hibernate Template;
*	persist
*	save
*	saveOrUpdate
*	update
*	delete
*	get
*	load
*	loadAll

### 8.7.2	Spring Data JPA:

*	JPA API provides JPA class to integrate Spring application with JPA framework.
*	JPA is the sun specification for persisting objects in the enterprise application.
*	It saves lots of code.
*	We don’t need to write before or after code persisting, updating, deleting or searching  object such as creating persistence instance, creating EntityManageFactory instance, Create EntityTransaction instance, create EntityManager instance, commiting EntityTransaction instance & closing EntityManager.  

## 8.8	SPEL: Spring Expression Language:

*	It supports the feature of querying & manipulating an object at runtime.
*	Some of the expression languages are JSP EL, MVEL, JBOSS EL, OGNL etc.

## 8.9	Spring MVC:

### 8.9.1	Introduction to Spring MVC:

*	Spring MVC is a Java framework used to build web applications.
*	It follows the Model-View-Controller design pattern.
*	It implements all the basic feature of core spring framework like Inversion of Control, Dependency Injection.
*	Here DispatcherServlet is a class that receives the incoming request and maps it to the right resource Such as controllers, models and view.
  
<b>Model:</b> A model contains the data of the application. A data can be a single object or collection of objects.

<b>Controller:</b> A Controller contains the business logic of an application. Here the @Controller annotation is used to represent the controller class.

<b>Views:</b> A view is used to represents the provided information in a particular format. Generally JSP+JSTL is used to create a view page. Although spring support other view technologies such as Thymeleaf & FreeMarker.


### 8.9.2	Flow of Spring MVC:

*	All the incoming request is intercepted by Dispatcher server which acts as front controller.
*	DispatcherServlet gets an entry of handler mapping from the XML file & forwards the request to the Controller.
*	The controller returns an object of ModelAndView.
*	The DispatcherServlet checks the entry of view resolver in the XML file & invokes the specified view component.

### 8.9.3	Advantages of Spring framework:
*	Separate roles - Spring MVC separates each role, where the model object, controller, command object, view resolver, Validator etc can be fulfilled by a specialized object.
*	Light weight - It uses light weight servlet container to develop & deploy your application.
*	Powerful configuration
*	Rapid development
*	Reusable business code
*	Easy to Test
*	Flexible mapping

