
- Management of data includes both defining structure for storing data & providing mechanisms for manipulation of that data. 

- `File-processing system`: System stores permanent records in various files & it needs different application programs to extract and add records from appropriate files.

- `Atomic operations`: Either occur all or none occur.

- `Database system`: A database system is a collection of interrelated data and a set of programs that allow users to access and modify these data. `data+programs/software+hardware+users` while `dbms=managingdata/programs/software`.

- A major purpose of D.S. is to provide abstract view of data to user to hide complex implementation details from user.It's called `data abstraction`.

---

- `The need for efficiency has led designers to use complex data structures/ algorithms  to represent data in the database. Since many database-system users are not computer trained, developers hide the complexity from users through several levels of abstraction, to simplify users’ interactions with the system:`
 
> ->`abstract` : simplified.
> ->`Abstraction` is process of simplifying complex entities like concepts , systems etc.
> ->Abstraction applys to both `defining and manipulating data`.
 
 1. `Physical level`: Lowest level , describe complex-data-structure in detail.

 2. `Logical level`: What data is stored in DB & what relationships exits among those data. Describes entire DB in  small number of `relatively` simple structures.

 >->`Physical data independence`: Concept of hiding complexities of how data is stored at lower levels when user interact with the logical level.
 > ex: . Database administrators, who must decide what information to keep in the database, use the logical level of abstraction.

3. `View level`: Describes only part of DB , as user only need it.The system may provide many views for the same DB. Also provide security mechanism to prevent user from accessing certain parts of detail.

---
> As database keep getting updated ->

- `Instances`: The collection of info/A state of DB at a particular moment.
- `Schema`: The overall design of DB. 

> EX: In  a program , the variable declaration is schema , and its value at a particular point 
> in time is schema.

> ->`DB structure`: physical storage , data types , way of storing data on disk .
> ->`DB schema`: structure of table views , relationships b/w tables , constraints , permisssions.

- DB has several schemas , partitioned according to levels of abstraction like physical schema , logical schema , subschema.

- Logical schema is most important since `developers constructs application using logical schema`.

---
- `data model` : A conceptual framework/ that describe design the database at physical , logical and view levels . Types of data -> `hierarchial model` -> `network model` 
	1. `realational model`:Uses `tables` to represent `data` as well as `realationships`. Tables are also know as relations.`Record based model`.
	2. `Entity-Relational model`
	3. `Object based model`
---
#### Databases Languages : 
1. `Data Defination Language`: specify database schema through set of definitions & specify additional properties of data.                                                                                         ex: domain constraints (dataTypes) , referential integrity , assertion{condition that DB must satisfy} , authorization.                                                                                                The output of DDL is stored in data dictionary which contains meta data.

2. `Data Manipulation Language`: database queries & update.
	2.1. `Procedual DMLs`: specify `what`  data is needed & `how`  to get those data.
	2.2.`Declarative DMLs`: only specify `what` data is needed.
>   DDL & DML are part of a single database lang. , ex: `SQL` /-sequel-/

3. `query language`:
>->A  `Query`  is a statement requesting retrieval of data.Takes input from several table and return only one.
[[SQL]]
---
### Relational Databases:
Uses table(s) to represent `data` and `relationships` among data. Hides low-level implementation from users and developers ex: special character for comma , new-line character used in file system model.
1. `tables`: Each table contains record of particular type.

> -> SQL don't support actions/computations like user input , show output , network calls etc , therefore such actions must be written in host language like c++,java etc with `embedded SQL queries` that access the data in database.

> -> `Application programs` are programs that are used to interact with database. Written in combination of programming lang. and query.
[[1. Relational Model]]
---
### Database Design
->Mainly include design of DB schema.

->In terms of relational model , it include `what attribute to capture in DB` , `how to group these attributes to form tables` etc.
- process : conceptual-design phase -> logical-design phase -> physical-design phase.

#### ER-model : entity-relationship data model  for relational DB

-> Collection of `objects` and `relationships` among these objects.

-> Object is a `real world entity`{singular or plural} like a person , bank accounts etc.

-> Entities are `set of attributes` ex: `dept_name`.

-> `relationship` is association among several entities. ex: `member` relationship associates instructor with department.


> Set of all entities of same type or relationships of same type is termed as `entity/relationship set`.

-> logical schema can be represented by `ER diagram` , made through `UML`.

-> can express some constraints also.

#### Normalization for relational DB 

-> design schemas in `normal form`.

-> normal forms are set of rules & guidelines to ensure DB schema is well structured and follow certain standards.

---
### Data storage & Querying
-> DB system is partitioned into modules that deal with its own responsibilities.

-> Data is moved between storage disk and main memory as needed , therefore DB system should structure the data so as to minimize the need to move data between disk and main memory.

-> `query processor`: simplify and facilitate access to data. DDL interpreter , DML compiler, query evolution engine , query optimization.

---
### Transaction Management
-> `Atomicity`: all or none requirement/condition.ex: amount transaction,telecommunication.

-> `consistency`: correctness requirement.

-> `durability`: persistence requirement.

-> A `transaction` is a collection of operations that perform a single logical function in DB application.

---
### Database Architecture 
-> DB system can be centralized , client-server:where one machine ,server executes tasks on behalf of multiple client machines , parallel processing.
![[Screenshot from 2023-12-06 16-28-10.png]]
![[Pasted image 20231206171115.png]]

---
