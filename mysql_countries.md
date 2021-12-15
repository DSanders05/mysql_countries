<!-- Query 1 -->
SELECT name, language, percentage FROM countries
JOIN languages ON countries.id = languages.country_id
WHERE languages.language = 'slovene'
ORDER BY languages.percentage DESC
<!-- Query 2 -->
SELECT name, COUNT(cities.id) as number_cities FROM countries
JOIN cities ON countries.id = cities.country_id
GROUP BY countries.name
ORDER BY number_cities DESC
<!-- Query 3 -->
SELECT cities.name, cities.population, cities.country_id 
FROM cities
JOIN countries ON countries.id = cities.country_id
WHERE countries.name = 'Mexico' AND
cities.population > 500000
ORDER BY cities.population DESC
<!-- Query 4 -->
SELECT countries.name, language, percentage 
FROM languages
JOIN countries ON countries.id = languages.country_id
WHERE percentage > 89
ORDER BY percentage DESC
<!-- Query 5 -->
SELECT name, surface_area, population
FROM countries
WHERE surface_area < 501 AND
population > 100000
<!-- Query 6 -->
SELECT name, government_form, capital, life_expectancy
FROM countries
WHERE government_form = 'constitutional monarchy' AND
capital > 200 AND life_expectancy > 75
<!-- Query 7 -->
SELECT countries.name as country_name , cities.name as city_name, district, cities.population
FROM cities
JOIN countries ON countries.id = cities.country_id
WHERE countries.name = 'argentina' AND district = 'buenos aires' and
cities.population > 500000
<!-- Query 8 -->
SELECT countries.region, COUNT(countries.id) as num_countries
FROM countries
GROUP BY countries.region
ORDER BY num_countries DESC