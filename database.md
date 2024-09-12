##Announcement: 
1. The countries.csv data have some problems, originally the fields they have are id , code , name, continent, wikipedia_link, keywords. But in some of the countries there are 1-3 more fields after the keywords column. The traditional way will not be able to load this .csv file.
2. To load dumpfile.sql which is flight_game.sql, we should copy this file from Moodle to local file, then use Windows shell command: mysql -u root -p game < "/path/name.sql" after that we have already get airport, country, game, goal, goal_reached those 5 tables.

##Week 1 upload by Moodle

##Week 2 has no Exercise 

##Week 3 Exercise 2
Q: 1, 2, 8, 9, 10 submit from Moodle. 

###Q1
select * from goal;

<img width="799" alt="Exercise2-Q1" src="https://github.com/user-attachments/assets/1546d258-6580-4a35-a063-ff7a25b2d134">

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

###Q9
select distinct co2_budget from game;

<img width="454" alt="Exercise2-Q9" src="https://github.com/user-attachments/assets/883f3b60-951b-48a5-874e-194b4d4ee046">

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

###Q4
select elevation_ft
    -> from airport, game
    -> where location = ident and screen_name = "Heini";

<img width="450" alt="Exercise3-Q4" src="https://github.com/user-attachments/assets/fb12c9b1-4c73-4cc6-b256-bc7f4d4fa370">

###Q5
select elevation_ft * 0.3048 as elevation_m
    -> from airport, game
    -> where location = ident and screen_name = "Heini";

<img width="469" alt="Exercise3-Q5" src="https://github.com/user-attachments/assets/46ecd892-b36c-487d-b445-cc9ca449dea4">

###Q6
select name
    -> from airport, game
    -> where location = ident and screen_name = "Ilkka";

<img width="454" alt="Exercise-Q6" src="https://github.com/user-attachments/assets/6d534c9c-bbe6-4a2d-baed-6977fb70f650">

###Q7
 select country.name
    -> from airport, game, country
    -> where location = ident and airport.iso_country = country.iso_country  and screen_name = "Ilkka";

<img width="721" alt="Exercise3-Q7" src="https://github.com/user-attachments/assets/0638ef5e-6027-4a84-832c-522cd5959989">

###Q8
 select name
    -> from goal, goal_reached, game
    -> where game.id = game_id and goal.id = goal_id and screen_name = "Heini";
    
<img width="637" alt="WindowsTerminal_BZ0yA8j1pc" src="https://github.com/user-attachments/assets/cf36e4be-4a5e-4cab-acbc-36d16d0023a2">

###Q9
 select airport.name
    -> from airport, game, goal, goal_reached
    -> where ident = location and game.id = game_id and goal.id = goal_id and screen_name = "Ilkka" and goal.name = "CLOUDS";

<img width="844" alt="Exercise3-Q9" src="https://github.com/user-attachments/assets/0c594d68-8533-4a5e-b08b-35c712c7c132">

###Q10
select country.name
    -> from country, airport, game, goal, goal_reached
    -> where airport.iso_country = country.iso_country and ident = location and game.id = game_id and goal.id = goal_id and screen_name = "Ilkka" and goal.name = "CLOUDS";

<img width="834" alt="Exercise3-Q10" src="https://github.com/user-attachments/assets/870f7376-e53b-4a99-b224-79c935dc414b">

##Week 4 Exercise 4

###Q1
SELECT country.name AS "country name", airport.name AS "airport name"
    -> FROM country
    -> INNER JOIN airport ON airport.iso_country = country.iso_country
    -> WHERE country.name = 'Finland' AND airport.scheduled_service = 'yes';
<img width="650" alt="Week4-Q1" src="https://github.com/user-attachments/assets/6db06cf3-98ac-4f2b-9e00-ecb25beef5fe">

###Q2
select screen_name, airport.name
    -> from game inner join airport on location = ident;

<img width="417" alt="Exercise4-Q2" src="https://github.com/user-attachments/assets/ddb35dc9-30fc-4389-aec2-caed27685146">

###Q3
select screen_name, country.name
    -> from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;

<img width="850" alt="Week4-Q3" src="https://github.com/user-attachments/assets/23d57c02-942b-4d63-90c4-dacd249aa14b">

###Q4
select airport.name, screen_name
    -> from airport left join game on ident = location where name like "%Hels%";

<img width="599" alt="Exercise4-Q4" src="https://github.com/user-attachments/assets/96dd5ade-09c8-43ef-9487-b085746319da">

###Q5
select name, screen_name
    -> from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;

<img width="694" alt="Exercise4-Q5" src="https://github.com/user-attachments/assets/81044f8b-3732-4c78-8b0c-3d37c41ceaff">

##Week 4 Exercise 5
###Q1
 select name
    -> from country
    -> where iso_country in(
    -> select iso_country
    -> from airport
    -> where name like "Satsuma%"
    -> );

<img width="306" alt="Exercise5-Q1" src="https://github.com/user-attachments/assets/57123c57-171a-4c41-a4a6-ec7d93ae274d">
###Q2
 select name
    -> from airport where
    -> iso_country in(
    -> select iso_country
    -> from country
    -> where name = "Monaco"
    -> );

<img width="275" alt="Exercise5-Q2" src="https://github.com/user-attachments/assets/8dc46217-b58a-435d-9427-8837e2a8f051">

###Q3
 select screen_name
    -> from game
    -> where id in (
    -> select game_id
    -> from goal_reached
    -> where goal_id in(
    -> select id
    -> from goal
    -> where name = "CLOUDS"
    -> )
    -> );

<img width="253" alt="Exercise5-Q3" src="https://github.com/user-attachments/assets/f2bef08d-23ee-41f5-ab12-b97598fa135a">

###Q4
select country.name
    -> from country
    -> where iso_country not in
    -> (select airport.iso_country
    -> from airport);
    
<img width="259" alt="Exercise5-Q4" src="https://github.com/user-attachments/assets/cb670d19-d0a2-4aa2-975a-a49596848d63">

###Q5
 select name
    -> from goal
    -> where id not in(
    -> select goal.id
    -> from goal, goal_reached, game
    -> where game.id = game_id and goal.id = goal_id and screen_name = "Heini"
    -> );

<img width="559" alt="Exercise5-Q5" src="https://github.com/user-attachments/assets/7afbb0e4-09fd-4952-822d-c03233ab2687">

##Week5 Exercise6
###Q1
 select max(elevation_ft)
    -> from airport;

<img width="308" alt="Exercise6-Q1" src="https://github.com/user-attachments/assets/3a572637-f724-4e7c-81b9-3ce1fac121fa">

###Q2
select continent, count(*)
    -> from country
    -> group by continent;

<img width="538" alt="Exercise6-Q1" src="https://github.com/user-attachments/assets/ed839f4f-26fd-483b-882a-60bb1217aace">

###Q3
 select screen_name, count(*)
    -> from game, goal_reached
    -> where id = game_id
    -> group by screen_name;

<img width="336" alt="Exercise6-Q3" src="https://github.com/user-attachments/assets/c1e0e249-b790-450d-97a8-2a5397acdd6c">

###Q4
select screen_name
    -> from game
    -> where co2_consumed in(
    -> select min(co2_consumed)
    -> from game
    -> );

<img width="292" alt="Exercise6-Q4" src="https://github.com/user-attachments/assets/808fc208-763f-4ebf-a2b0-6e54f4e6fe94">

###Q5
 select country.name, count(*)
    -> from airport, country
    -> where airport.iso_country = country.iso_country
    -> group by country.iso_country
    -> order by count(*) desc
    -> limit 50;

<img width="388" alt="Exercise6-Q5" src="https://github.com/user-attachments/assets/4ab39774-c01e-4b65-9448-ca7edccb44dc">

###Q6
 select country.name
    -> from airport, country
    -> where airport.iso_country = country.iso_country
    -> group by country.iso_country
    -> having count(*) > 1000;

<img width="389" alt="Exercise6-Q6" src="https://github.com/user-attachments/assets/b3e83779-f825-4cd7-bd1d-4788c2e8b73f">

###Q7
select name
    -> from airport
    -> where elevation_ft in (
    -> select max(elevation_ft)
    -> from airport
    -> );

<img width="265" alt="Exercise6-Q7" src="https://github.com/user-attachments/assets/ef6c328a-fd22-4108-b985-06e6c3c5ff13">

###Q8
select name
    -> from country
    -> where iso_country in (
    -> select iso_country
    -> from airport
    -> where elevation_ft in(
    -> select max(elevation_ft)
    -> from airport
    -> )
    -> );

<img width="226" alt="Exercise6-Q8" src="https://github.com/user-attachments/assets/daf5e250-ebe9-4b35-8120-00ef46cb819c">

###Q9
select count(*)
    -> from game, goal_reached
    -> where id = game_id and screen_name = "Vesa"
    -> group by screen_name;

<img width="363" alt="Exercise6-Q9" src="https://github.com/user-attachments/assets/e21aa731-cf08-43b2-93b8-b42f5e195e53">

###Q10
 select name
    -> from airport
    -> where latitude_deg in(
    -> select min(latitude_deg)
    -> from airport
    -> );

<img width="247" alt="Exercise6-Q10" src="https://github.com/user-attachments/assets/cabb2267-8ecc-4983-ab52-0e5a62992138">

##Week5 Exercise7
###1
 update game
    -> set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
    -> where screen_name = "Vesa";
<img width="825" alt="7-Q1" src="https://github.com/user-attachments/assets/4f20acc8-688d-49ff-9ee0-d2faa2d3e92c">

###2
goal_reached

###3
DELETE FROM goal_reached WHERE game_id = 'some_game_id';
<img width="533" alt="7-Q3" src="https://github.com/user-attachments/assets/93d3ab39-9c18-4ae4-bd5c-4cb7b3fcd18a">

###4  DELETE FROM game WHERE id = 'some_game_id'
<img width="433" alt="7-Q4" src="https://github.com/user-attachments/assets/dc7bd6c1-8fd9-4e24-a7c1-06e54bc28171">

