#### Count database query

Put it before the query is being executed

```PHP
$counter = 0;
\DB::listen(function($sql) use (&$counter) {
    $counter++;
    file_put_contents('db_count.txt', $counter);
    file_put_contents('db_queries.txt', $sql->sql . "\n", FILE_APPEND);
});
```

keywords: laravel, query, queries, count, counter
