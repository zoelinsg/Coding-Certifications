# SQL Tutorial
## MySQL 解法

### SELECT basics
來源：[SQLZoo SELECT basics](https://www.sqlzoo.net/wiki/SELECT_basics)

```sql
-- 1. 查詢德國人口
SELECT population FROM world
WHERE name = 'Germany';

-- 2. 查詢北歐三國的人口
SELECT name, population FROM world
WHERE name IN ('Sweden', 'Norway', 'Denmark');

-- 3. 查詢面積在 200000 到 250000 的國家
SELECT name, area FROM world
WHERE area BETWEEN 200000 AND 250000;
```

### SELECT names
來源：[SQLZoo SELECT names](https://www.sqlzoo.net/wiki/SELECT_names)

```sql
-- 1. 名稱以 Y 開頭
SELECT name FROM world
WHERE name LIKE 'Y%';

-- 2. 名稱以 y 結尾
SELECT name FROM world
WHERE name LIKE '%y';

-- 3. 名稱中含有 x
SELECT name FROM world
WHERE name LIKE '%x%';

-- 4. 名稱以 land 結尾
SELECT name FROM world
WHERE name LIKE '%land';

-- 5. 名稱以 c 開頭且以 ia 結尾
SELECT name FROM world
WHERE name LIKE 'c%' AND name LIKE '%ia';

-- 6. 名稱中包含兩個 o（連續或不連續）
SELECT name FROM world
WHERE name LIKE '%oo%';

-- 7. 名稱中有三個 a（不一定連續）
SELECT name FROM world
WHERE name LIKE '%a%a%a%';

-- 8. 第二個字母為 t，並依照名稱排序
SELECT name FROM world
WHERE name LIKE '_t%'
ORDER BY name;

-- 9. 兩個 o 中間隔兩個字元
SELECT name FROM world
WHERE name LIKE '%o__o%';

-- 10. 名稱剛好 4 個字元
SELECT name FROM world
WHERE name LIKE '____';

-- 進階應用：首都與國家名稱的關係
-- 11. 名稱與首都相同的國家（如 Luxembourg）
SELECT name
FROM world
WHERE name = capital;

-- 12. 首都是國名 + " City" 的國家（如 Mexico City）
SELECT name
FROM world
WHERE capital = CONCAT(name, ' City');

-- 13. 首都中包含國名（如 Mexico 在 Mexico City 中）
SELECT capital, name
FROM world
WHERE capital LIKE CONCAT('%', name, '%');

-- 14. 首都是國名的延伸（開頭相同，但不完全相同）
SELECT capital, name
FROM world
WHERE capital LIKE CONCAT(name, '%')
  AND capital != name;

-- 15. 顯示首都為國名延伸，並顯示延伸部分（如 -Ville）
SELECT name, REPLACE(capital, name, '') AS extension
FROM world
WHERE capital LIKE CONCAT(name, '%')
  AND capital != name;
```