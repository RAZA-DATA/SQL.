use cars;

-- 1) read data --
select * from car_dekho;

-- 2) Total Cars: to get a count of total records --
SELECT count(*) FROM car_dekho;


-- 3) How many cars will be available in 2023?--
SELECT count(*)
From car_dekho
where year = 2023;


-- 4) How many cars is available in 2020, 2021, 2022--
SELECT count(*) from car_dekho Where year = 2020; #74
SELECT count(*) from car_dekho Where year = 2021; #7
SELECT count(*) from car_dekho Where year = 2022; #7
-- total count --
Select count(*)
from car_dekho
where year in (2020,2021,2023)
GROUP BY year;


-- 5) Total of all cars by year--
SELECT year, count(*)
FROM car_dekho
GROUP BY year;


-- 6) How many diesel cars will be there in 2020? --
SELECT count(*)
from car_dekho
where fuel = "Diesel" and year = 2020;


-- 7) How many petrol cars is there in 2020? -- #51
SELECT COUNT(*)
FROM car_dekho
where fuel = "petrol" and year = 2020;


-- 8) Print all the fuel cars (petrol, diesel, CNG) come by all year --
SELECT year, count(*)
FROM car_dekho
WHERE fuel = "petrol"
Group by year;

SELECT year, count(*)
FROM car_dekho
WHERE fuel = "diesel"
Group by year;

SELECT year, count(*)
FROM car_dekho
WHERE fuel = "CNG"
Group by year;


-- 9) which year had more than 100 cars? 
Select year, count(*)
from car_dekho
group by year
having count(*)>100;


-- 10) all cars count details between 2015 and 2023? #4,124
select count(*)
from car_dekho
where year between 2015 and 2023;

-- 11) now pull all the details and sort them in acending order by year
select *
from car_dekho
where year between 2015 and 2023
order by year;
