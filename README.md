# faster-php

Different approaches to improve PHP script performance

## Get started

```bash
git clone https://github.com/devmount/faster-php
cd faster-php
php composer.phar install
```

Now you are ready to call the one of the test scripts presented below.

## List of methods

### 1. Removing duplicates

Method:

```php
// using
array_keys(array_flip($array));
// instead of
array_unique($array);
```

Test:

```bash
php test_array_unique.php
```

Result:

| method | time | memory |
|--------|-----:|-------:|
| `array_unique` | 787.31 ms | 230.00 MB |
| `array_keys` `array_flip` | 434.03 ms | 0.00 KB |

The alternative approach is **44.87 %** faster in this measurement. On average, it was 30 % faster.

### 2. Get random array element

Method:

```php
// using
$array[mt_rand(0, count($array) - 1)];
// instead of
array_rand($array);
```

Test:

```bash
php test_array_rand.php
```

Result:

| method | time | memory |
|--------|-----:|-------:|
| `array_rand` | 25.99 μs | 0.00 KB |
| `mt_rand` | 0.95 μs | 0.00 KB |

The alternative approach is **96.33 %** faster in this measurement. On average, it was 85 % faster.
