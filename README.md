# DBMSNotes 

//A Database Management System (DBMS) is software that enables users to efficiently define, create, maintain, and control access to a database. It acts as an interface between the end-users and the database, ensuring data integrity, security, and consistency.

//Advantages of DBMS over File Systems
1. Data conssitancy and redundncy
2. INTEGRITY - avoide duplicecy in the databse
3. security - for e commerce one to user can see each other order history
4. cunnxurency - multiple use can access the same product together
5. scalability

//Database Users 
1. end user - like customer browesing on the amazon websute is the enduser
2. Data Administrators (DBAs) - Responsible for maintaining the database, ensuring security, backups, and optimization.

//Data model - collection of conceptual tool for data describing , data relationships and consistancy constrain
1. herarcial model - like sile systenm folder have sunfolder and files
2. Network model - like inkedin single peron has lots of conncton
3. Relational model - tebular form

//DBMS application attribute - 
clint server
T1 - clint , server and db in the same pc . 
T2 - clint sent -> query to server in the different pc by direct calling to the db . interfacing concept is also use
T3 - divided into 3 part ,clint call to -> server which again call to -> db and get the result , this enhance the scalability(www) , security and data integrety.

//SCHEMAS
1.physical - lower level data abstraction describe how the data stored
2.logical abstraction - describe the design of database (like tabular etc) , no need to aware about physical levle 
3.view level - show the user the db in which they are intrested and hide the rest of the data

//Data Independence - the sbility to modify the schema at one level without affevting the other one 
1. physical Data Independence - affecting this without affecting logical level
2. logical Data Independence - vose versa

ENTITY - 
attributes - how u gonna discribe them .
consistency constrane - no coloum = null , no bad or wrong data .
relationships - bw coloum

//ER model - entity relations --- student is an entity with their attribute like  name , courses , id etc 
use to discribe the entity , entity is unique .
entities - attribute - relations - er diagram(work ae a ablue print)
strong entity(recoconized by primary key , it's independent)
week entity (not reconized by pk , depend on other strong entity )
// type of attribute -
simple (not divide) 
composite (eg fisrt and last name )
single valued - (student id )
multi valued - (g -different [hone nu.)
derived (eg - age from dom)
null value (eg no middle value NA )

//Genrelization - it is the process of combining two or more lower-level entities into a higher-level entity.This is use to reduce redundecy . Example car and bus entity become vecheal .
//Specilization - It is the process of creating sub-entities . example vechile to car and bus .
//Aggrigation - Aggregation is a higher-level abstraction where a relationship itself is treated as an entity and is linked to another entity. "Department" monitors the relationship between "Professor" and "Course."





//degree of relations 
unery (one entity participate) eg - employ manges employ
binary (2 entity participate ) eg - coustomer bororw loan
terchery (3 entities participate) employee works on job

//relationa; constrane 
*mapping cardinality - ek entity ke kitne no. of enrirty dusre no. of entity set se connected h
1. one to one (entity set a ka ek entity entity set B ke ek entity se connected hoga )
   eg citizen has adhar cade.
2. one to many - a ki entity b ke many entity se connected . eg citizen has car
3. many to one - cpurse taken by prof.
4. many to many eg coustomer and product

*participation constrane(minimum cardinelity)

//aggrigation - to show relationship among relationship and it avoid redundency 

//How to make ER diagram
identift entity set - attribute of entity set - data type - relationship and constrain (mapping and participation) among entities 

//RELATIONAL MODELA representation in tabular form with unique table nmae ,attribute , tople(row)
each entity become one table and all the attribute represent each coloum 
*degree of relation = no. of coloums 
*cardinality = no.of tuples(row)

//steps to design -----
make er diagram - relation model while implemented by the software called RDBMS(eg MYSQL , ORECAL )

//keys in realtional model 
1.SUPER KEY sk - aaisa permutation and combination of attribute that uniquely identify the touples.
2.condidate key - minimum attribute of the sk subset that identify the tuple without any redundency(duplicacy) ,can't null
3. primary key - identify the min set of ck that uniquely identify . only one in table , not null
4. alletnate key -> ck -pk 
5.foregin key - creat a relation b/w tables , by establishing pk from one relational model as a foregin key for someother model 
6.composite key - pk form by atleast two attribute 
7.compound key - pk fromed by using two or maore fk

//integrity 
after crud operation their may be inconsistance check it by integraty constrance like roll no has to be integer 
1.domain constrain - define domain prev (like roll no. is int )
2.entity constrain - every relation has a pk and it won't be null
3.referencial constrain - 
*inset constrain - u won't add value(taple) in child table if it won't be in the parant table .
*delete constrain - value won't be del from parant table if it's lying in the child table . but you resolve this by putting FK NULL at that tuple which got del from the parant .

//KEY CONSTRAIN (define when you are adding that atribute) '
NOT NULL -(eg - that the nmae attribute won't be null degined initially )
UNIQUE - that attribute is unique but their is more than one unique attribute entries in th
DEFAULT 
CHCEK - limit the domain (like age not > 18  then allowed else error)
PK CONSTRAIN - it is unique and not null
FK CONSTRAIIN - to develop relation b/w 2 entity by making common attribute 

//convert er to relational model 
*strong entity - become individual coloum 
*week entity - having a fk from the parant or strong entitty
*single valued attribute - 
*composite attribute - divide them in their respective attributes 
*multi valued attribute - new table is created with pk of parent key act as the fk of this table 
