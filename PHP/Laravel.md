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

#### List / Remove Duplicated object collection / Databse entry through model

```PHP
use Illuminate\Database\Eloquent\Collection;

function removeDuplicates(Collection $models, array $attributes): Collection {
    $seen = [];
    return $models->filter(function($model) use (&$seen, $attributes) {
        $compositeKey = [];
        foreach ($attributes as $attribute) {
            $compositeKey[] = $model->{$attribute};
        }
        $compositeKey = implode('-', $compositeKey);

        if (in_array($compositeKey, $seen)) {
            // TODO: Perform specific action if required
            // $model->delete();
            return false;
        } else {
            $seen[] = $compositeKey;
            return true;
        }
    });
}

// Usage
$movies = Movie::all();
$uniqueMovies = removeDuplicates($prices, ['name', 'publication_date', '...']);

```

keywords: laravel, delete, remove, duplicates, models, entry, database
