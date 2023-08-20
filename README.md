# DBMSNotes 

//major purpose of dbms is to provide abstract view of dat to the users
DB SCHEMEA


attributes - how u gonna discribe them .
consistency constrane - no coloum = null , no bad or wrong data .
relationships - bw coloum

//view of data - system store certain details like how the data stored(enable user to access the same data with personalised view) it simplify user interction
it give the same data to different users with an personalized view 
it is 3 scheme archetucture having 
physical abstraction - lower level data abstraction describe how the data stored
, logical abstraction - describe the design of database at aconceptual level , no need to aware about physical levle 
 view level - show the user the db in which they are intrested and hide the rest of the data

//im dbms 
define schema (overall designing of db is called db scheme)

//interfacing - use to convert like c++ into dbms by Odbc

//DBAdiministrater - it has the central control of all the data . 
handle in scheme and physical level .

//DBMS application attribute - 
clint server
T1 - clint , server and ddb in the same pc . 
T2 - clint sent query to server in the different pc by direct calling to the db . interfacing concept is also use
T3 - clint call to application server which again call to the db and get the result , this enhance the scalability.

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

//degree of relations 
unery (one entity)
binary (2 entity participate ) coustomer bororw loan
terchery 

//relationa; constrane 
*mapping cardinality - ek entity ke kitne no. of enrirty dusre no. of entity set se connected h
1. one to one (entity set a ka ek entity entity set B ke ek entity se connected hoga )
   eg citizen has adhar cade.
2. one to many - a ki entity b ke many entity se connected . eg citizen has car
3. many to one
4. many to many eg coustomer and product

*participation constrane(minimum cardinelity)

//aggrigation - to show relationship among relationship and it avoid redundency 

//ho wto make ER diagram
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

//KY CONSTRAIN (define when you are adding that atribute) '
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
