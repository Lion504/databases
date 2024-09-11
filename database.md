##Announcement: 
1. The countries.csv data have some problems, originally the fields they have are id , code , name, continent, wikipedia_link, keywords. But in some of the countries there are 1-3 more fields after the keywords column. The traditional way will not be able to load this .csv file.
2. To load dumpfile.sql which is flight_game.sql, we should copy this file from Moodle to local file, then use Windows shell command: mysql -u root -p game < "/path/name.sql" after that we have already get airport, country, game, goal, goal_reached those 5 tables.

##Week 1 upload by Moodle

##Week 2 has no Exercise 

##Week 3 Exercise 2
Q: 1, 2, 8, 9, 10 submit from Moodle. 
###Q2
select name, type from airport where iso_country = 'FI';

<img width="524" alt="Exercise2-Q2" src="https://github.com/user-attachments/assets/b34fcebb-5237-4827-aa95-91369cc7a2cb">

###Q3 
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name;
<img width="597" alt="Exercise2 - Q3" src="https://github.com/user-attachments/assets/7963d4fe-e798-4dd0-ab0b-a75c02fd48d1">

###Q4
SELECT name,type FROM airport WHERE iso_country = 'FI' ORDER BY type,name;
<img width="865" alt="Exercise2 - Q4" src="https://github.com/user-attachments/assets/fa65fafe-f18a-44ec-8836-eb739964c5dc">

###Q5
SELECT name FROM countries WHERE name like "F%";
<img width="578" alt="Exercise2 - Q5" src="https://github.com/user-attachments/assets/8f6e122c-974d-4f8b-895d-ac81d0949e55">

###Q6
SELECT name FROM countries WHERE name like "%F%";

<img width="496" alt="Exercise2 - Q6" src="https://github.com/user-attachments/assets/542423ac-558a-4005-af0c-ff3b9bddbf97">

###Q7 
select location from game where screen_name = 'Vesa';
<img width="629" alt="Exercise2-Q7" src="https://github.com/user-attachments/assets/c384560e-cc13-4e17-b394-fd5d01b57110">

###Q8
select co2_consumed from game where screen_name = 'Ilkka';
<img width="582" alt="Exercise2-Q8" src="https://github.com/user-attachments/assets/794337c2-31d0-4359-895e-3bce4ef2a7d1">

###Q10
select screen_name, co2_budget,co2_consumed, (co2_budget - co2_consumed) AS co2_left
    -> from game
    -> where screen_name = 'Ilkka';
    
<img width="751" alt="Exercise2-Q10" src="https://github.com/user-attachments/assets/261786c5-ca84-4690-8854-70d773f7b846">

##Week 3 Exercise 3
###Q4 & Q5 & Q6 & Q7 & Q9 & Q10 can pass via Moodle

###Q1
select country.name as "country name", airport.name as "airport name"
from airport, country
where airport.iso_country = country.code = "IS" and country.name = "Iceland" limit 20;
<img width="865" alt="Exercise 3 Q1" src="https://github.com/user-attachments/assets/84467c2c-b27a-4652-9607-abcd107ba798">

###Q2 Moodle has wrong answer

select airport.name as 'airport name'
from airport, country
where country.name = 'France' and airport.type = 'large_airport' limit 30;
<img width="865" alt="Exercise 3 Q2" src="https://github.com/user-attachments/assets/74e274d7-f2c8-4fd6-bbd5-39dfd61fe445">

###Q3
select country.name as 'country_name', airport.name as 'airport_name'
from country, airport
where country.name = 'Antarctica' limit 30;
<img width="865" alt="Exercise 3 Q3" src="https://github.com/user-attachments/assets/75dbbfce-57b9-4077-8f74-aed20ced9852">

###Q8
 select name
    -> from goal, goal_reached, game
    -> where game.id = game_id and goal.id = goal_id and screen_name = "Heini";
    
<img width="637" alt="WindowsTerminal_BZ0yA8j1pc" src="https://github.com/user-attachments/assets/cf36e4be-4a5e-4cab-acbc-36d16d0023a2">

##Week 4 Exercise 4

###Q1
SELECT country.name AS "country name", airport.name AS "airport name"
    -> FROM country
    -> INNER JOIN airport ON airport.iso_country = country.iso_country
    -> WHERE country.name = 'Finland' AND airport.scheduled_service = 'yes';
<img width="650" alt="Week4-Q1" src="https://github.com/user-attachments/assets/6db06cf3-98ac-4f2b-9e00-ecb25beef5fe">

###Q3
select screen_name, country.name
    -> from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;

<img width="850" alt="Week4-Q3" src="https://github.com/user-attachments/assets/23d57c02-942b-4d63-90c4-dacd249aa14b">

###Q4
select airport.name, screen_name
    -> from airport left join game on ident = location where name like "%Hels%";

<img width="591" alt="Week4-Q4" src="https://github.com/user-attachments/assets/f94f8394-342d-43e8-bd37-a247e5351c19">


