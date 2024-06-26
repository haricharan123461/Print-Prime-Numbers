WITH RECURSIVE numbers AS (
    SELECT 2 AS num
    UNION
    SELECT num + 1
    FROM numbers
    WHERE num < 1000
),
primes AS (
    SELECT num
    FROM numbers n1
    WHERE NOT EXISTS (
        SELECT 1
        FROM numbers n2
        WHERE n2.num < n1.num AND n1.num % n2.num = 0
    )
)
SELECT GROUP_CONCAT(num SEPARATOR '&') AS prime_numbers
FROM primes;
