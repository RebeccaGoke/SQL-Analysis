# SQL-Analysis
Donation Data for a Charity Organisation
Select * from DONATION_DATA
SELECT * FROM DONOR_DATA

--1) How much is the total donation
SELECT SUM(donation) AS DONATIONS
FROM donation_data

--2) What is the total donation by gender?
select gender, sum(donation)
from donation_data
group by Gender

--3) Show the total donation and number of donations by gender
select * from donation_data
select * from donor_data
 select gender, sum(donation) as donation, count(id) as total_Donations
from donation_data
group by gender

--4) Total donation made by frequency
select * from donation_data
select * from donor_data
select sum(donation) as donation, donation_frequency
from donation_data
join donor_data
on donation_data.id = donor_data.id
group by donation_frequency
order by donation desc

--5) Total donation and number of donation by job field
select count(ID)as number_of_donations, job_field , sum(donation) as donations
from donation_data
group by job_field
order by job_field desc

--6) Total donations and number of donations above $200
select * from donation_data
select * from donor_data
select id, donation
from donation_data
where donation > 200
ORDER BY DONATION DESC

and or 
select count(ID) , SUM(DONATION)
FROM DONATION_DATA
WHERE DONATION > 200

--Total Donation and number of donations below $200
select id, donation
from donation_data
where donation < 200
ORDER BY DONATION DESC

and or 
select count(ID) , SUM(DONATION)
FROM DONATION_DATA
WHERE DONATION < 200

--8) Top 10 state which contributes the highest donation
select * from donation_data
Select state, sum(donation) as Donations
from donation_data
group by state
order by Donations desc
limit 10

--9) Which top 10 states contributes the least donation
select * from donation_data
Select state, sum(donation) as Donations
from donation_data
group by state
order by Donations Asc
limit 10

--10) What are the top 10 cars driven by the highest donor
select * from donor_data
select * from donation_data

select concat(first_name, ' ', last_name) as Name, donor_data.id, car, donation
from donation_data
join donor_data
on donation_data.id = donor_data.id
order by donation desc
limit 10
