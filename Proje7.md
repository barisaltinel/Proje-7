film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.
film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?
film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

1) film tablosunda replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız
SELECT DISTINCT replacement_cost
FROM film
ORDER BY replacement_cost;

2) film tablosunda replacement_cost sütununda birbirinden farklı kaç tane veri vardır?
SELECT COUNT(DISTINCT replacement_cost) AS distinct_replacement_cost_count
FROM film;

3) film isimlerinden (title) T ile başlayan ve rating = 'G' olan kaç tane film vardır?
SELECT COUNT(*) AS count_T_start_G_rating
FROM film
WHERE title LIKE 'T%'
  AND rating = 'G';

4) country tablosunda 5 karakterden oluşan ülke isimleri kaç tanedir?
SELECT COUNT(*) AS count_5char_countries
FROM country
WHERE LENGTH(country) = 5;

5) city tablosunda şehir isimlerinden 'R' veya 'r' ile bitenler kaç tanedir?
SELECT COUNT(*) AS count_cities_end_with_R
FROM city
WHERE city ILIKE '%r';


Burada ILIKE büyük/küçük harf duyarsız arama için kullanıldı.
