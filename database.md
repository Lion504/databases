##Announcement: 
1. The countries.csv data have some problems, originally the fields they have are id , code , name, continent, wikipedia_link, keywords. But in some of the countries there are 1-3 more fields after the keywords column. The traditional way will not be able to load this .csv file.
2. To load dumpfile.sql which is flight_game.sql, we should copy this file from Moodle to local file, then use Windows shell command: mysql -u root -p game < "/path/name.sql"

##Week 1 upload by Moodle

##Week 2 has no Exercise 

##Week 3 Exercise 2
Q: 1, 2, 8, 9, 10 submit from Moodle

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

My Professor, you should provide game data for us, without it how can I complete this quiz

select location from game where screen_name = "Vesa";

##Week 3 Exercise 3

###Q1
select country.name as "country name", airport.name as "airport name"
from airport, country
where airport.iso_country = country.code = "IS" and country.name = "Iceland" limit 20;
<img width="865" alt="Exercise 3 Q1" src="https://github.com/user-attachments/assets/84467c2c-b27a-4652-9607-abcd107ba798">

###Q2
select airport.name as 'airport name'
from airport, country
where country.name = 'France' and airport.type = 'large_airport' limit 30;
<img width="865" alt="Exercise 3 Q2" src="https://github.com/user-attachments/assets/74e274d7-f2c8-4fd6-bbd5-39dfd61fe445">

###Q3
select country.name as 'country_name', airport.name as 'airport_name'
from country, airport
where country.name = 'Antarctica' limit 30;
<img width="865" alt="Exercise 3 Q3" src="https://github.com/user-attachments/assets/75dbbfce-57b9-4077-8f74-aed20ced9852">

###Q4 & Q5 & Q6 & Q7 & Q9 & Q10 can pass via Moodle,  Q8* not possible
My Professor, you should provide game data for us, without that how can I know their information?


