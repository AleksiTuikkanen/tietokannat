
```markdown
# Relaatiotietokannan peruskäsitteiden harjoitukset viikko 1

### Tehtävä 1
5

### Tehtävä 2
5

### Tehtävä 3
ident

### Tehtävä 4
varchar

### Tehtävä 5
iso_country

### Tehtävä 6
country

### Tehtävä 7
iso_country

### Tehtävä 8
varchar

### Tehtävä 9
70942

### Tehtävä 10
iso_country

### Tehtävä 11
varchar

### Tehtävä 12
248

### Tehtävä 13
goal

### Tehtävä 14
0DEG

### Tehtävä 15
id

### Tehtävä 16
Epätosi

### Tehtävä 17
game

### Tehtävä 18
game

### Tehtävä 19
game

### Tehtävä 20
game

### Tehtävä 21
id

### Tehtävä 22
location

### Tehtävä 23
goal_reached

### Tehtävä 24
goal_id, game_id

### Tehtävä 25
2
```

# Yhteen tauluun kohdistuvien kyselyiden harjoitukset viikko 2

### Tehtävä 1
```sql
SELECT *
FROM goal;
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys1.png)

### Tehtävä 2
```sql
SELECT name
FROM airport
WHERE iso_country = "FI";
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys2.png)

### Tehtävä 3
```sql
SELECT name
FROM airport
WHERE iso_country = "FI"
ORDER BY name;
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys3.png)

### Tehtävä 4
```sql
SELECT name, type
FROM airport
WHERE iso_country = "FI"
ORDER BY type, name;
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys4.png)

### Tehtävä 5
```sql
SELECT name
FROM country
WHERE name LIKE "F%";
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys5.png)

### Tehtävä 6
```sql
SELECT name
FROM country
WHERE name LIKE "%F%";
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys6.png)

### Tehtävä 7
```sql
SELECT location
FROM game
WHERE screen_name = "Vesa";
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys7.png)

### Tehtävä 8
```sql
SELECT co2_consumed
FROM game
WHERE screen_name = "Ilkka";
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys8.png)

### Tehtävä 9
```sql
SELECT DISTINCT co2_budget
FROM game;
```
![ruudunkaappaus](/Tehtävät/03%20Yhteen%20tauluun%20kohdistuvien%20kyselyiden%20harjoitukset/kys9.png)
```


# Where-osan liitosehto harjoitukset viikko 2

### Tehtävä 1
```sql
SELECT country.name AS "country name", airport.name AS "airport name"
FROM airport, country
WHERE airport.iso_country = country.iso_country 
  AND country.name = "Iceland";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys1.2.png)

### Tehtävä 2
```sql
SELECT airport.name AS "airport name"
FROM airport, country
WHERE airport.iso_country = country.iso_country 
  AND country.name = "France" 
  AND airport.type = "large_airport";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys2.2.png)

### Tehtävä 3
```sql
SELECT country.name AS country_name, airport.name AS airport_name
FROM airport, country
WHERE airport.iso_country = country.iso_country 
  AND country.continent = "AN";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys3.2.png)

### Tehtävä 4
```sql
SELECT airport.elevation_ft
FROM airport, game
WHERE location = ident 
  AND screen_name = "Heini";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys4.2.png)

### Tehtävä 5
```sql
SELECT airport.elevation_ft * 0.3048 AS elevation_m
FROM airport, game
WHERE location = ident 
  AND screen_name = "Heini";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys5.2.png)

### Tehtävä 6
```sql
SELECT airport.name
FROM airport, game
WHERE location = ident 
  AND screen_name = "Ilkka";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys6.2.png)

### Tehtävä 7
```sql
SELECT country.name
FROM airport, game, country
WHERE location = ident 
  AND screen_name = "Ilkka" 
  AND airport.iso_country = country.iso_country;
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys7.2.png)

### Tehtävä 8
```sql
SELECT name
FROM goal, goal_reached, game
WHERE game.id = game_id 
  AND goal.id = goal_id 
  AND screen_name = "Heini";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys8.2.png)

### Tehtävä 9
```sql
SELECT airport.name
FROM airport, game, goal, goal_reached
WHERE ident = location 
  AND game.id = game_id 
  AND screen_name = "Ilkka" 
  AND goal.name = "CLOUDS";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys9.2.png)

### Tehtävä 10
```sql
SELECT country.name
FROM country, airport, game, goal, goal_reached
WHERE airport.iso_country = country.iso_country 
  AND ident = location 
  AND game.id = game_id 
  AND screen_name = "Ilkka" 
  AND goal.name = "CLOUDS";
```
![ruudunkaappaus](/Tehtävät/04%20Where-osan%20liitosehto%20harjoitukset/kys10.2.png)

# Join harjoitukset viikko 3

### Tehtävä 1
```sql
SELECT country.name AS "country name", airport.name AS "airport name"
FROM country
INNER JOIN airport ON airport.iso_country = country.iso_country
WHERE country.name = "Finland" 
  AND scheduled_service = "yes";
```
![ruudunkaappaus](/Tehtävät/05%20Join%20harjoitukset/kys1.3.png)

### Tehtävä 2
```sql
SELECT screen_name, airport.name
FROM game
INNER JOIN airport ON location = ident;
```
![ruudunkaappaus](/Tehtävät/05%20Join%20harjoitukset/kys2.3.png)

### Tehtävä 3
```sql
SELECT screen_name, country.name
FROM game
INNER JOIN airport ON location = ident
INNER JOIN country ON airport.iso_country = country.iso_country;
```
![ruudunkaappaus](/Tehtävät/05%20Join%20harjoitukset/kys3.3.png)

### Tehtävä 4
```sql
SELECT airport.name, screen_name
FROM airport
LEFT JOIN game ON ident = location
WHERE name LIKE "%Hels%";
```
![ruudunkaappaus](/Tehtävät/05%20Join%20harjoitukset/kys4.3.png)

### Tehtävä 5
```sql
SELECT name, screen_name
FROM goal
LEFT JOIN goal_reached ON goal.id = goal_id
LEFT JOIN game ON game.id = game_id;
```
![ruudunkaappaus](/Tehtävät/05%20Join%20harjoitukset/kys5.3.png)
```

# Sisäkysely harjoitukset viikko 3

### Tehtävä 1
```sql
SELECT name
FROM country
WHERE iso_country IN (
    SELECT iso_country
    FROM airport
    WHERE name LIKE "Satsuma%");
```
![ruudunkaappaus](/Tehtävät/06%20Sisäkysely%20harjoitukset/kys1.6.png)

### Tehtävä 2
```sql
SELECT name
FROM airport
WHERE iso_country IN (
    SELECT iso_country
    FROM country
    WHERE name = "Monaco");
```
![ruudunkaappaus](/Tehtävät/06%20Sisäkysely%20harjoitukset/kys2.6.png)

### Tehtävä 3
```sql
SELECT screen_name
FROM game
WHERE id IN (
    SELECT game_id
    FROM goal_reached
    WHERE goal_id IN (
        SELECT id
        FROM goal
        WHERE name = "CLOUDS"));
```
![ruudunkaappaus](/Tehtävät/06%20Sisäkysely%20harjoitukset/kys3.6.png)

### Tehtävä 4
```sql
SELECT country.name
FROM country
WHERE iso_country NOT IN (
    SELECT airport.iso_country
    FROM airport);
```
![ruudunkaappaus](/Tehtävät/06%20Sisäkysely%20harjoitukset/kys4.6.png)

### Tehtävä 5
```sql
SELECT name
FROM goal
WHERE id NOT IN (
    SELECT goal.id
    FROM goal, goal_reached, game
    WHERE game.id = game_id 
      AND goal.id = goal_id 
      AND screen_name = "Heini");
```
![ruudunkaappaus](/Tehtävät/06%20Sisäkysely%20harjoitukset/kys5.6.png)
```

# Koostetieto kyselyt harjoitukset viikko 4

### Tehtävä 1
```sql
SELECT MAX(elevation_ft)
FROM airport;
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys1.5.png)

### Tehtävä 2
```sql
SELECT continent, COUNT(*)
FROM country
GROUP BY continent;
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys2.5.png)

### Tehtävä 3
```sql
SELECT screen_name, COUNT(*)
FROM game, goal_reached
WHERE id = game_id
GROUP BY screen_name;
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys3.5.png)

### Tehtävä 4
```sql
SELECT screen_name
FROM game
WHERE co2_consumed IN (SELECT MIN(co2_consumed) FROM game);
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys4.5.png)

### Tehtävä 5
```sql
SELECT country.name, COUNT(*)
FROM airport, country
WHERE airport.iso_country = country.iso_country
GROUP BY country.iso_country
ORDER BY COUNT(*) DESC
LIMIT 50;
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys5.5.png)

### Tehtävä 6
```sql
SELECT country.name
FROM airport, country
WHERE airport.iso_country = country.iso_country
GROUP BY country.iso_country
HAVING COUNT(*) > 1000;
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys6.5.png)

### Tehtävä 7
```sql
SELECT name
FROM airport
WHERE elevation_ft IN (
    SELECT MAX(elevation_ft)
    FROM airport);
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys7.5.png)

### Tehtävä 8
```sql
SELECT name
FROM country
WHERE iso_country IN (
    SELECT iso_country
    FROM airport
    WHERE elevation_ft IN (SELECT MAX(elevation_ft) FROM airport));
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys8.5.png)

### Tehtävä 9
```sql
SELECT COUNT(*)
FROM game, goal_reached
WHERE id = game_id AND screen_name = "Vesa"
GROUP BY screen_name;
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys9.5.png)

### Tehtävä 10
```sql
SELECT name
FROM airport
WHERE latitude_deg IN (
    SELECT MIN(latitude_deg)
    FROM airport);
```
![ruudunkaappaus](/Tehtävät/07%20Koostetieto%20kyselyt%20harjoitukset/kys10.5.png)
```

# Päivityskyselyt harjoitukset viikko 4

### Tehtävä 1
```sql
UPDATE game
SET location = (SELECT ident FROM airport WHERE name = "Nottingham Airport"),
    co2_consumed = co2_consumed + 500
WHERE screen_name = "Vesa";

SELECT * FROM game;
```
![ruudunkaappaus](/Tehtävät/08%20Päivityskyselyt%20harjoitukset/kys1.6.png)

### Tehtävä 2
```sql
-- Tehtävä 2: goal_reached
```
*Ei kuvaa*

### Tehtävä 3
```sql
DELETE FROM goal_reached;
SELECT * FROM goal_reached;
```
![ruudunkaappaus](/Tehtävät/08%20Päivityskyselyt%20harjoitukset/kys3.6.png)

### Tehtävä 4
```sql
DELETE FROM game;
SELECT * FROM game;
```
![ruudunkaappaus](/Tehtävät/08%20Päivityskyselyt%20harjoitukset/kys4.6.png)
```
# Tietokannan suunnittelu harjoitukset

### Tehtävä 1
ident

### Tehtävä 2
airport

### Tehtävä 3
a.

### Tehtävä 4
tosi

### Tehtävä 5
epätosi

### Tehtävä 6
a.

### Tehtävä 7
c.

### Tehtävä 8
tosi

### Tehtävä 9
c.

### Tehtävä 10
*Ei vastausta*
