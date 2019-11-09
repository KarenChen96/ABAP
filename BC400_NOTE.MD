# ABAP 

## Chapter 1
Some concepts regarding to ABAP workbench. E.g., (selection) screen,  

### Lesson 1:

- Each Apllication Component (eg. FI, HR, ...) contains serveral packages.
- Each Repository Object must be assigned to a package.
- Example of Repository Obbject: Function Modules, Programs, Tables, etc.
- A Repository Object can be made up of subobjects which are Repositoy Objects themselves.
- Common tools in ABAP workbench to process repository objects"
    - ABAP Editor: edit source code
    - ABAP Dictionary: edit databse table definitions, central data types, and so on
    - Function Builder: process function modules
    - Class Builder: process global classes
    - Screen Painter: ...
    - Menu Painter: ...

-----------------------
### Lesson 2: Developing Programs and Organizing Developments
Learn about: 
- how to create package & program
- how to assign repository objects to a package
- how to create a transaction code fot a program 

> Organizing Developments
    
dev system to prod system vis change request. We can perform the scheduling of the common transport for the repository object using a changing request.

> Creating Packages

> Introduction to the Programming Language ABAP Objects

> Creating an ABAP program

> Creating Transaction Codes


## Chapter 2
TBD

## Chapter 3 Introduction to the ABAP Dictionary
### Lesson 1: Transparent Tables and Views
Target:
- Description & Structure of transparent tables
- Difference between structures and transparent tables
- How to use data types from the ABAP Dictionary

> The ABAP Dictionary as a Central Tool iof the ABAP Workbench

**Transparent Table**
- Define transparent tables in the ABAP Dictionary
- key-related concepts are similar to SQL, like key fields, foreign key fields, primary key fields.
- Normally use a data element to type a table filed. Semantic properties, such as field lables, are stored in the data element.
    - A data element represents a field type. A data element normally uss a domain. :thinking: 
- The transparent table in the ABAP Dictionary contains the platform-independent description of the relevant database table, and they two have the same table name and field names. 
    
    :point_right: The table content is in the database; The transparent table is only technical description/logical view.

**Structure**
- A Structure doesn't represent a database table int he ABAP Dictonary but a **pure type definition**.
- Use **Component & Component type** to replace Field & Field type, and we can store a (sub)structure component under a component name.
- TABELS meaning & usage? :thinking:


## Chapter 4

### Lesson 1: Workig with Elementary Data Objects
Whitepoint: didn't find the icon on GUI; don't understand its functionality

### Lesson2: Working with Structures
keyword 'TYPES' is used to define structure types lcoally. What if we want to define our own non-structure type?


Q: CAN'T CLASSFIY structure and (transparent) table

w/o Header line haven't read yet.


## Chapter 5
### Lesson 1: Reading Database Tables
Reading several rows
Two ways: 1. using a loop, SELECT-ENDSELECT; 2. using an Array Fetch, SELECT. (what will happen if with ENDSELECT?)

Q: What's the function of ENDSELECT? 


## unit 7: event blocks
Q: Meaning of "the system sends the selectoin screen with this new value to the presentation server."


## Unit 10: Cross-Program Modularization
### Lesson 1: Working with Function Modules
**Function modules** are actively integrated modularization units（主动集成模块化单元）with an interface. 

A **Function group** represents the main program for function modules. Several function modules operating on the same data content are combined to form a function group. 

- The interface of a function module can contain the following elements: import/export/changing parameters, exceptions.
- A function group can contain the same components as an executable program, including Data objects, Subroutines, Screens.
- About Exception: Within *CALL FUNCTION* block, we can assign number values to the exceptions. When a specific exception is raised, the nunber value will be placed in SY-SUBRC.

### Lesson 2: Working with Methods
- classes are very similar to function groups but a class can have mulitple instances. I can understand that a class contains the technical description of objects/instances, but then what a function group contains??? :thinking:

- Example: SAP Grid Control ... :thinking:

### Lesson 3: Working with BAPIs
> BAPI: Business Application Programming Interface

A BAPI is a well-defined interface to processes and data of a business application system, implemented as a method od a business object in the Business Object Repository(BOR).

- Some of the most important standard BAPIs: GetList, GetDetail, Create/Change/Delete/Cancel, AddItem/RemoveItem.

- Function module for BAPIs naming convention: BAPI_<business_object_name>_<method_name>
- No Changing parameters and Exception Parameters. Errors are reported to the caller using special export parameters.
- Function module is a method/funciton?

## Unit 11: Software Logistics and Software Adjustment
> keyword: 
- orderly development
- terms related to object: original/copy/correction/repair/modification

### Lesson 1: Outlook: Organization of Development and Transport
When we create a Repository object, it has the original system. Other systems only contain copies of this object.



### Lesson 2: Outlook: Enhancing the Standard Software
To Be Continued...