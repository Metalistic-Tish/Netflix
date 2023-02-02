# Netflix
Down below, I have answered a few questions about my netflix database in SQL

Q1. How many movie titles are there in the database? (movies only, not tv shows) 

select count(*) 
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info"
WHERE type='Movie';

Q2. When was the most recent batch of tv shows and/or movies added to the database? 

select max(date(date_added))
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info";

Q3. List all the movies and tv shows in alphabetical order. 

select title
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info"
ORDER BY title asc;

Q4. Who was the Director for the movie Bright Star? 

select 
director
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info" titles
LEFT JOIN  "CharlotteChaze/BreakIntoTech"."netflix_people" people
ON titles.show_id=people.show_id
where titles.title='Bright Star'

Q5. What is the oldest movie in the database and what year was it made? 

select title, release_year
FROM "CharlotteChaze/BreakIntoTech"."netflix_titles_info"
WHERE type='Movie'
ORDER BY release_year asc
LIMIT 1;
