---
tags:
  - Array
---

عالیه که یادگیری PHP را شروع کرده‌اید! در اینجا چند تمرین برای کار با آرایه‌ها در PHP آورده‌ام:

### تمرین 1: ایجاد و نمایش آرایه

یک آرایه جدید ایجاد کنید که شامل نام 5 میوه باشد و سپس همه میوه‌ها را با استفاده از یک حلقه `foreach` چاپ کنید.

```php
<?php
$fruits = ['Apple', 'Banana', 'Orange', 'Mango', 'Grapes'];

foreach ($fruits as $fruit) {
    echo $fruit . "\n";
}
?>
```

### تمرین 2: آرایه انجمنی (Associative Array)

یک آرایه انجمنی ایجاد کنید که شامل نام و سن 5 نفر باشد و سپس همه آنها را نمایش دهید.

```php
<?php
$people = [
    'Alice' => 25,
    'Bob' => 30,
    'Charlie' => 35,
    'David' => 40,
    'Eve' => 45
];

foreach ($people as $name => $age) {
    echo "$name is $age years old\n";
}
?>
```

### تمرین 3: آرایه چند بعدی (Multidimensional Array)

یک آرایه چند بعدی ایجاد کنید که شامل اطلاعات چند کتاب (عنوان، نویسنده، و قیمت) باشد و سپس اطلاعات هر کتاب را نمایش دهید.

```php
<?php
$books = [
    ['title' => 'Book One', 'author' => 'Author One', 'price' => 10],
    ['title' => 'Book Two', 'author' => 'Author Two', 'price' => 15],
    ['title' => 'Book Three', 'author' => 'Author Three', 'price' => 20]
];

foreach ($books as $book) {
    echo "Title: " . $book['title'] . "\n";
    echo "Author: " . $book['author'] . "\n";
    echo "Price: $" . $book['price'] . "\n\n";
}
?>
```

### تمرین 4: مرتب‌سازی آرایه

یک آرایه از اعداد ایجاد کنید و سپس آن را به ترتیب صعودی و نزولی مرتب کنید.

```php
<?php
$numbers = [3, 5, 1, 4, 2];

// مرتب‌سازی صعودی
sort($numbers);
echo "Ascending Order:\n";
print_r($numbers);

// مرتب‌سازی نزولی
rsort($numbers);
echo "Descending Order:\n";
print_r($numbers);
?>
```
#sort #rsort 
### تمرین 5: جستجو در آرایه

یک آرایه از اسامی ایجاد کنید و بررسی کنید که آیا یک نام خاص در آرایه وجود دارد یا خیر.

```php
<?php
$names = ['Alice', 'Bob', 'Charlie', 'David', 'Eve'];
$searchName = 'Charlie';

if (in_array($searchName, $names)) {
    echo "$searchName is in the array.\n";
} else {
    echo "$searchName is not in the array.\n";
}
?>
```
#in_array 
### تمرین 6: افزودن و حذف عناصر آرایه

یک آرایه از اسامی ایجاد کنید، یک نام جدید به آرایه اضافه کنید و سپس یکی از اسامی را حذف کنید.

```php
<?php
$names = ['Alice', 'Bob', 'Charlie', 'David', 'Eve'];

// افزودن عنصر
$names[] = 'Frank';
echo "After adding Frank:\n";
print_r($names);

// حذف عنصر
unset($names[1]); // حذف Bob
echo "After removing Bob:\n";
print_r($names);
?>
```
#unset 
### تمرین 7: ترکیب آرایه‌ها

دو آرایه را با هم ترکیب کنید و نتیجه را نمایش دهید.

```php
<?php
$array1 = ['a', 'b', 'c'];
$array2 = ['d', 'e', 'f'];

$combinedArray = array_merge($array1, $array2);
print_r($combinedArray);
?>
```

#array_merge 
### تمرین 8: شمارش عناصر آرایه

یک آرایه از اعداد ایجاد کنید و تعداد عناصر آن را شمارش کنید.

```php
<?php
$numbers = [10, 20, 30, 40, 50];
$count = count($numbers);
echo "The array has $count elements.\n";
?>
```
#count
### تمرین 9: فیلتر کردن آرایه

یک آرایه از اعداد ایجاد کنید و فقط اعداد زوج را فیلتر کرده و نمایش دهید.

```php
<?php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
$evenNumbers = array_filter($numbers, function($num) {
    return $num % 2 == 0;
});

print_r($evenNumbers);
?>
```
#array_filter 
### تمرین 10: تبدیل آرایه به رشته

یک آرایه از کلمات ایجاد کنید و آنها را با استفاده از یک جداکننده به یک رشته تبدیل کنید.

```php
<?php
$words = ['Hello', 'world', 'this', 'is', 'PHP'];
$sentence = implode(' ', $words);
echo $sentence . "\n";
?>
```
#implode 
### تمرین 11: تبدیل رشته به آرایه

یک رشته از کلمات ایجاد کنید و آن را با استفاده از یک جداکننده به یک آرایه تبدیل کنید.

```php
<?php
$sentence = 'Hello world this is PHP';
$words = explode(' ', $sentence);
print_r($words);
?>
```
#explode 
### تمرین 12: آرایه انجمنی با توابع

یک آرایه انجمنی ایجاد کنید که شامل نام و نمره چند دانش‌آموز باشد و سپس با استفاده از توابع `array_keys` و `array_values` فقط اسامی یا نمرات را استخراج کنید.

```php
<?php
$students = [
    'Alice' => 85,
    'Bob' => 78,
    'Charlie' => 92,
    'David' => 88,
    'Eve' => 90
];

$names = array_keys($students);
$scores = array_values($students);

echo "Names:\n";
print_r($names);

echo "Scores:\n";
print_r($scores);
?>
```
#array_keys #array_values 
### تمرین 13: تغییر عناصر آرایه

یک آرایه از اعداد ایجاد کنید و با استفاده از یک حلقه `foreach` همه عناصر آن را دو برابر کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];

foreach ($numbers as &$num) {
    $num *= 2;
}

unset($num); // برای جلوگیری از مشکلات احتمالی

print_r($numbers);
?>
```

### تمرین 14: پیدا کردن بزرگترین و کوچکترین عدد در آرایه

یک آرایه از اعداد ایجاد کنید و بزرگترین و کوچکترین عدد آن را پیدا کنید.

```php
<?php
$numbers = [3, 5, 1, 4, 2];

$maxValue = max($numbers);
$minValue = min($numbers);

echo "The maximum value is $maxValue\n";
echo "The minimum value is $minValue\n";
?>
```
#max #min 
### تمرین 15: مقایسه دو آرایه

دو آرایه از اعداد ایجاد کنید و عناصری که در هر دو آرایه مشترک هستند را پیدا کنید.

```php
<?php
$array1 = [1, 2, 3, 4, 5];
$array2 = [4, 5, 6, 7, 8];

$commonElements = array_intersect($array1, $array2);
print_r($commonElements);
?>
```
#array_intersect 
### تمرین 16: حذف عناصر تکراری از آرایه

یک آرایه ایجاد کنید و عناصر تکراری آن را حذف کنید.

```php
<?php
$numbers = [1, 2, 2, 3, 4, 4, 5];

$uniqueNumbers = array_unique($numbers);
print_r($uniqueNumbers);
?>
```
#array_unique 


### تمرین 17: جمع و میانگین عناصر آرایه

یک آرایه از اعداد ایجاد کنید و مجموع و میانگین آنها را محاسبه کنید.

```php
<?php
$numbers = [10, 20, 30, 40, 50];

$sum = array_sum($numbers);
$average = $sum / count($numbers);

echo "Sum: $sum\n";
echo "Average: $average\n";
?>
```
#count #array_sum 
### تمرین 18: ترکیب آرایه‌های انجمنی

دو آرایه انجمنی ایجاد کنید و آنها را ترکیب کنید. اگر کلیدهای مشترک وجود داشته باشند، آرایه دوم جایگزین اولی شود.

```php
<?php
$array1 = ['a' => 1, 'b' => 2, 'c' => 3];
$array2 = ['b' => 4, 'c' => 5, 'd' => 6];

$combinedArray = array_merge($array1, $array2);
print_r($combinedArray);
?>
```
#array_merge 
### تمرین 19: استخراج بخشی از آرایه

یک آرایه ایجاد کنید و یک بخش از آن را استخراج کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

$slice = array_slice($numbers, 3, 4); // از عنصر چهارم به بعد، 4 عنصر استخراج شود
print_r($slice);
?>
```
#array_slice 
### تمرین 20: تبدیل آرایه انجمنی به آرایه معمولی

یک آرایه انجمنی ایجاد کنید و آن را به آرایه معمولی تبدیل کنید.

```php
<?php
$associativeArray = ['a' => 1, 'b' => 2, 'c' => 3];

$regularArray = array_values($associativeArray);
print_r($regularArray);
?>
```
#array_values 
### تمرین 21: مرتب‌سازی آرایه انجمنی بر اساس مقادیر

یک آرایه انجمنی ایجاد کنید و آن را بر اساس مقادیر به صورت صعودی مرتب کنید.

```php
<?php
$ages = ['Alice' => 25, 'Bob' => 30, 'Charlie' => 20, 'David' => 35];

asort($ages); // مرتب‌سازی بر اساس مقادیر به صورت صعودی
print_r($ages);
?>
```
#asort
### تمرین 22: مرتب‌سازی آرایه انجمنی بر اساس کلیدها

یک آرایه انجمنی ایجاد کنید و آن را بر اساس کلیدها به صورت صعودی مرتب کنید.

```php
<?php
$ages = ['Alice' => 25, 'Bob' => 30, 'Charlie' => 20, 'David' => 35];

ksort($ages); // مرتب‌سازی بر اساس کلیدها به صورت صعودی
print_r($ages);
?>
```
#ksort 
### تمرین 23: استفاده از تابع array_map

یک آرایه از اعداد ایجاد کنید و از تابع `array_map` برای دو برابر کردن همه عناصر آن استفاده کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];

$doubled = array_map(function($num) {
    return $num * 2;
}, $numbers);

print_r($doubled);
?>
```
#array_map 
### تمرین 24: استفاده از تابع array_reduce

یک آرایه از اعداد ایجاد کنید و از تابع `array_reduce` برای محاسبه حاصل‌ضرب همه عناصر آن استفاده کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];

$product = array_reduce($numbers, function($carry, $item) {
    return $carry * $item;
}, 1);

echo "Product: $product\n";
?>
```
#array_reduce 
### تمرین 25: پیدا کردن کلید یک مقدار در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلید یک مقدار خاص را پیدا کنید.

```php
<?php
$ages = ['Alice' => 25, 'Bob' => 30, 'Charlie' => 20, 'David' => 35];
$searchValue = 30;

$key = array_search($searchValue, $ages);

if ($key !== false) {
    echo "The key for the value $searchValue is $key.\n";
} else {
    echo "The value $searchValue is not found in the array.\n";
}
?>
```
#array_search 
### تمرین 26: پر کردن آرایه با مقادیر مشخص

یک آرایه با طول مشخص ایجاد کنید و همه عناصر آن را با یک مقدار مشخص پر کنید.

```php
<?php
$length = 5;
$value = 'PHP';

$array = array_fill(0, $length, $value);
print_r($array);
?>
```
#array_fill
### تمرین 27: مقایسه آرایه‌ها و پیدا کردن تفاوت‌ها

دو آرایه از اعداد ایجاد کنید و تفاوت‌های آنها را پیدا کنید.

```php
<?php
$array1 = [1, 2, 3, 4, 5];
$array2 = [4, 5, 6, 7, 8];

$difference = array_diff($array1, $array2);
print_r($difference);
?>
```
#array_diff
### تمرین 28: ترکیب دو آرایه به عنوان کلید و مقدار

دو آرایه ایجاد کنید و آنها را به صورت کلید و مقدار ترکیب کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$combinedArray = array_combine($keys, $values);
print_r($combinedArray);
?>
```
#array_combine


### تمرین 29: اضافه کردن عناصر به ابتدای آرایه

یک آرایه از اعداد ایجاد کنید و یک یا چند عدد به ابتدای آن اضافه کنید.

```php
<?php
$numbers = [3, 4, 5];

array_unshift($numbers, 1, 2); // افزودن 1 و 2 به ابتدای آرایه
print_r($numbers);
?>
```
#array_unshift
### تمرین 30: حذف کردن عناصر از ابتدای آرایه

یک آرایه از اعداد ایجاد کنید و یک عنصر از ابتدای آن حذف کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];

array_shift($numbers); // حذف عنصر اول
print_r($numbers);
?>
```
#array_shift 
### تمرین 31: ایجاد آرایه انجمنی از رشته

یک رشته به فرمت JSON ایجاد کنید و آن را به یک آرایه انجمنی تبدیل کنید.

```php
<?php
$jsonString = '{"name": "Alice", "age": 25, "city": "New York"}';

$array = json_decode($jsonString, true);
print_r($array);
?>
```
#json_decode
### تمرین 32: پیدا کردن تکرار عناصر در آرایه

یک آرایه از اعداد ایجاد کنید و تعداد تکرار هر عدد را پیدا کنید.

```php
<?php
$numbers = [1, 2, 2, 3, 4, 4, 4, 5];

$counts = array_count_values($numbers);
print_r($counts);
?>
```
#array_count_values 
### تمرین 33: فیلتراسیون آرایه بر اساس کلیدها

یک آرایه انجمنی ایجاد کنید و فقط عناصر با کلیدهای مشخص را استخراج کنید.

```php
<?php
$array = ['name' => 'Alice', 'age' => 25, 'city' => 'New York', 'country' => 'USA'];

$keys = ['name', 'city'];
$filteredArray = array_intersect_key($array, array_flip($keys));
print_r($filteredArray);
?>
```
#array_intersect_key #array_flip 
### تمرین 34: ادغام آرایه‌ها با حفظ کلیدها

دو آرایه انجمنی را با هم ادغام کنید و کلیدهای مشابه را با هم ترکیب کنید.

```php
<?php
$array1 = ['a' => 1, 'b' => 2, 'c' => 3];
$array2 = ['b' => 4, 'c' => 5, 'd' => 6];

$mergedArray = array_replace($array1, $array2);
print_r($mergedArray);
?>
```
#array_replace 
### تمرین 35: تقسیم آرایه به بخش‌های کوچکتر

یک آرایه بزرگ ایجاد کنید و آن را به آرایه‌های کوچکتر تقسیم کنید.

```php
<?php
$numbers = range(1, 10); // آرایه‌ای از 1 تا 10

$chunkedArray = array_chunk($numbers, 3); // تقسیم به بخش‌های 3 تایی
print_r($chunkedArray);
?>
```
#count #array_chunk
### تمرین 36: پیدا کردن تفاوت کلیدها بین دو آرایه انجمنی

دو آرایه انجمنی ایجاد کنید و تفاوت کلیدهای آنها را پیدا کنید.

```php
<?php
$array1 = ['a' => 1, 'b' => 2, 'c' => 3];
$array2 = ['b' => 4, 'c' => 5, 'd' => 6];

$keyDifference = array_diff_key($array1, $array2);
print_r($keyDifference);
?>
```
#array_diff_key 
### تمرین 37: مرتب‌سازی چند بعدی آرایه

یک آرایه چند بعدی ایجاد کنید و آن را بر اساس یکی از مقادیر داخلی مرتب کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'age' => 25, 'grade' => 88],
    ['name' => 'Bob', 'age' => 22, 'grade' => 95],
    ['name' => 'Charlie', 'age' => 23, 'grade' => 82]
];

usort($students, function($a, $b) {
    return $a['grade'] <=> $b['grade'];
});

print_r($students);
?>
```
#usort 
### تمرین 38: مرتب‌سازی آرایه بر اساس توابع دلخواه

یک آرایه از رشته‌ها ایجاد کنید و آن را بر اساس طول رشته‌ها مرتب کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry', 'date'];

usort($strings, function($a, $b) {
    return strlen($a) - strlen($b);
});

print_r($strings);
?>
```
#usort #strlen 
### تمرین 39: ادغام دو آرایه و حذف تکراری‌ها

دو آرایه ایجاد کنید، آنها را ادغام کنید و سپس عناصر تکراری را حذف کنید.

```php
<?php
$array1 = [1, 2, 3, 4, 5];
$array2 = [4, 5, 6, 7, 8];

$mergedArray = array_unique(array_merge($array1, $array2));
print_r($mergedArray);
?>
```
#array_unique #array_merge 
### تمرین 40: جمع کردن مقادیر با کلید مشابه

دو آرایه انجمنی ایجاد کنید و مقادیر کلیدهای مشابه را با هم جمع کنید.

```php
<?php
$array1 = ['a' => 1, 'b' => 2, 'c' => 3];
$array2 = ['b' => 3, 'c' => 4, 'd' => 5];

$sumArray = $array1;
foreach ($array2 as $key => $value) {
    if (isset($sumArray[$key])) {
        $sumArray[$key] += $value;
    } else {
        $sumArray[$key] = $value;
    }
}

print_r($sumArray);
?>
```



### تمرین 41: پیدا کردن کلید بزرگترین مقدار در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلید بزرگترین مقدار را پیدا کنید.

```php
<?php
$ages = ['Alice' => 25, 'Bob' => 30, 'Charlie' => 35, 'David' => 20];

$maxValue = max($ages);
$key = array_search($maxValue, $ages);

echo "The key for the maximum value ($maxValue) is $key.\n";
?>
```
#max #array_search
### تمرین 42: استفاده از تابع array_walk برای تغییر مقادیر

یک آرایه از اعداد ایجاد کنید و با استفاده از تابع `array_walk` همه عناصر آن را دو برابر کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];

array_walk($numbers, function(&$num) {
    $num *= 2;
});

print_r($numbers);
?>
```
#array_walk 
### تمرین 43: مرتب‌سازی آرایه چند بعدی بر اساس چندین کلید

یک آرایه چند بعدی ایجاد کنید و آن را بر اساس دو کلید مختلف مرتب کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'age' => 25, 'grade' => 88],
    ['name' => 'Bob', 'age' => 22, 'grade' => 95],
    ['name' => 'Charlie', 'age' => 23, 'grade' => 82],
    ['name' => 'David', 'age' => 22, 'grade' => 90]
];

usort($students, function($a, $b) {
    if ($a['age'] == $b['age']) {
        return $a['grade'] <=> $b['grade'];
    }
    return $a['age'] <=> $b['age'];
});

print_r($students);
?>
```
#usort 
### تمرین 44: پیدا کردن اولین کلید در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و اولین کلید آن را پیدا کنید.

```php
<?php
$array = ['first' => 1, 'second' => 2, 'third' => 3];

$firstKey = array_key_first($array);
echo "The first key is $firstKey.\n";
?>
```
#array_key_first 
### تمرین 45: پیدا کردن آخرین کلید در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و آخرین کلید آن را پیدا کنید.

```php
<?php
$array = ['first' => 1, 'second' => 2, 'third' => 3];

$lastKey = array_key_last($array);
echo "The last key is $lastKey.\n";
?>
```
#array_key_last
### تمرین 46: جایگزینی بخشی از آرایه

یک آرایه از اعداد ایجاد کنید و بخشی از آن را با مقادیر جدید جایگزین کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
$replacement = [100, 200, 300];

array_splice($numbers, 3, 3, $replacement); // جایگزینی سه عنصر از اندیس 3 به بعد

print_r($numbers);
?>
```
#array_splice 
### تمرین 47: اجرای تابع بر روی کلیدها و مقادیر آرایه

یک آرایه انجمنی ایجاد کنید و با استفاده از تابع `array_map` یک تابع بر روی کلیدها و مقادیر آن اجرا کنید.

```php
<?php
$array = ['first' => 1, 'second' => 2, 'third' => 3];

$mappedArray = array_map(function($key, $value) {
    return $key . '_' . ($value * 2);
}, array_keys($array), $array);

print_r($mappedArray);
?>
```
#array_map #array_keys
### تمرین 48: ادغام آرایه‌های چند بعدی

دو آرایه چند بعدی ایجاد کنید و آنها را با هم ادغام کنید.

```php
<?php
$array1 = [
    ['id' => 1, 'name' => 'Alice'],
    ['id' => 2, 'name' => 'Bob']
];

$array2 = [
    ['id' => 3, 'name' => 'Charlie'],
    ['id' => 4, 'name' => 'David']
];

$mergedArray = array_merge($array1, $array2);
print_r($mergedArray);
?>
```
#array_merge
### تمرین 49: تغییر کلیدهای آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلیدهای آن را با استفاده از یک تابع تغییر دهید.

```php
<?php
$array = ['first' => 1, 'second' => 2, 'third' => 3];

$changedKeys = array_combine(
    array_map(function($key) {
        return strtoupper($key);
    }, array_keys($array)),
    $array
);

print_r($changedKeys);
?>
```
#array_combine #array_map #strtoupper #array_keys 
### تمرین 50: جایگزینی مقدار در آرایه چند بعدی

یک آرایه چند بعدی ایجاد کنید و مقدار مشخصی را در آن جایگزین کنید.

```php
<?php
$matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

array_walk_recursive($matrix, function(&$value, $key) {
    if ($value == 5) {
        $value = 50;
    }
});

print_r($matrix);
?>
```
#array_walk_recursive
### تمرین 51: فیلتر کردن آرایه انجمنی بر اساس طول مقادیر

یک آرایه انجمنی ایجاد کنید و فقط عناصری که طول مقادیر آنها بیش از 4 کاراکتر است را فیلتر کنید.

```php
<?php
$array = ['name' => 'Alice', 'age' => '25', 'city' => 'New York'];

$filteredArray = array_filter($array, function($value) {
    return strlen($value) > 4;
});

print_r($filteredArray);
?>
```
#array_filter #strlen
### تمرین 52: اضافه کردن پیشوند به کلیدهای آرایه

یک آرایه انجمنی ایجاد کنید و به همه کلیدهای آن یک پیشوند اضافه کنید.

```php
<?php
$array = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];

$prefixedArray = array_combine(
    array_map(function($key) {
        return 'prefix_' . $key;
    }, array_keys($array)),
    $array
);

print_r($prefixedArray);
?>
```
#array_combine #array_map #array_keys 
### تمرین 53: تبدیل آرایه انجمنی به آرایه دو بعدی

یک آرایه انجمنی ایجاد کنید و آن را به یک آرایه دو بعدی تبدیل کنید.

```php
<?php
$array = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];

$twoDimensionalArray = [];
foreach ($array as $key => $value) {
    $twoDimensionalArray[] = [$key, $value];
}

print_r($twoDimensionalArray);
?>
```

### تمرین 54: استخراج مقادیر منحصر به فرد از آرایه چند بعدی

یک آرایه چند بعدی ایجاد کنید و مقادیر منحصر به فرد آن را استخراج کنید.

```php
<?php
$array = [
    ['id' => 1, 'name' => 'Alice'],
    ['id' => 2, 'name' => 'Bob'],
    ['id' => 1, 'name' => 'Alice'],
    ['id' => 3, 'name' => 'Charlie']
];

$uniqueArray = array_map('unserialize', array_unique(array_map('serialize', $array)));

print_r($uniqueArray);
?>
```
#array_map #array_unique #array_map 
### تمرین 55: تبدیل آرایه چند بعدی به آرایه تک بعدی

یک آرایه چند بعدی ایجاد کنید و آن را به یک آرایه تک بعدی تبدیل کنید.

```php
<?php
$array = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$flattenedArray = [];
array_walk_recursive($array, function($value) use (&$flattenedArray) {
    $flattenedArray[] = $value;
});

print_r($flattenedArray);
?>
```
#array_walk_recursive
### تمرین 56: محاسبه میانگین مقادیر در آرایه چند بعدی

یک آرایه چند بعدی ایجاد کنید و میانگین مقادیر داخلی آن را محاسبه کنید.

```php
<?php
$array = [
    ['score' => 85],
    ['score' => 90],
    ['score' => 78],
    ['score' => 88]
];

$total = array_sum(array_column($array, 'score'));
$count = count($array);
$average = $total / $count;

echo "Average score: $average\n";
?>
```
#array_sum #count #array_column




### تمرین 57: استخراج زیردرخت از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و یک زیردرخت خاص از آن استخراج کنید.

```php
<?php
$tree = [
    'root' => [
        'branch1' => [
            'leaf1' => 'A',
            'leaf2' => 'B'
        ],
        'branch2' => [
            'leaf3' => 'C',
            'leaf4' => 'D'
        ]
    ]
];

$subTree = $tree['root']['branch1'];
print_r($subTree);
?>
```

### تمرین 58: پیدا کردن مسیر یک کلید در آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و مسیر یک کلید خاص را پیدا کنید.

```php
<?php
$tree = [
    'root' => [
        'branch1' => [
            'leaf1' => 'A',
            'leaf2' => 'B'
        ],
        'branch2' => [
            'leaf3' => 'C',
            'leaf4' => 'D'
        ]
    ]
];

function findKeyPath($array, $key) {
    $path = [];
    $iterator = new RecursiveIteratorIterator(new RecursiveArrayIterator($array), RecursiveIteratorIterator::SELF_FIRST);
    foreach ($iterator as $currentKey => $value) {
        if ($currentKey === $key) {
            foreach (range(0, $iterator->getDepth()) as $depth) {
                $path[] = $iterator->getSubIterator($depth)->key();
            }
            return $path;
        }
    }
    return null;
}

$path = findKeyPath($tree, 'leaf3');
print_r($path);
?>
```
#getDepth #getSubIterator #RecursiveIteratorIterator #RecursiveArrayIterator
### تمرین 59: یافتن عمق بیشترین عمق آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و بیشترین عمق آن را پیدا کنید.

```php
<?php
$array = [
    'level1' => [
        'level2' => [
            'level3' => [
                'level4' => 'end'
            ]
        ]
    ]
];

function findMaxDepth($array, $depth = 0) {
    if (!is_array($array)) {
        return $depth;
    }
    $maxDepth = $depth;
    foreach ($array as $value) {
        $maxDepth = max($maxDepth, findMaxDepth($value, $depth + 1));
    }
    return $maxDepth;
}

$maxDepth = findMaxDepth($array);
echo "Max Depth: $maxDepth\n";
?>
```
#is_array #max #findMaxDepth
### تمرین 60: مرتب‌سازی آرایه چند بعدی بر اساس مقادیر داخلی

یک آرایه چندبعدی از اطلاعات دانشجویان ایجاد کنید و آن را بر اساس نمرات به ترتیب نزولی مرتب کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'grade' => 88],
    ['name' => 'Bob', 'grade' => 95],
    ['name' => 'Charlie', 'grade' => 82],
    ['name' => 'David', 'grade' => 90]
];

usort($students, function($a, $b) {
    return $b['grade'] <=> $a['grade'];
});

print_r($students);
?>
```
#usort
### تمرین 61: حذف عناصر تکراری از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و عناصر تکراری آن را حذف کنید.

```php
<?php
$array = [
    ['id' => 1, 'name' => 'Alice'],
    ['id' => 2, 'name' => 'Bob'],
    ['id' => 1, 'name' => 'Alice'],
    ['id' => 3, 'name' => 'Charlie']
];

$uniqueArray = array_map('unserialize', array_unique(array_map('serialize', $array)));

print_r($uniqueArray);
?>
```
#array_map
### تمرین 62: ادغام آرایه‌های چند بعدی با حفظ کلیدها

دو آرایه چندبعدی ایجاد کنید و آنها را با حفظ کلیدها ادغام کنید.

```php
<?php
$array1 = [
    'group1' => ['id' => 1, 'name' => 'Alice'],
    'group2' => ['id' => 2, 'name' => 'Bob']
];

$array2 = [
    'group1' => ['age' => 25],
    'group3' => ['id' => 3, 'name' => 'Charlie']
];

$mergedArray = array_replace_recursive($array1, $array2);
print_r($mergedArray);
?>
```
#array_replace_recursive
### تمرین 63: تبدیل آرایه چندبعدی به آرایه انجمنی

یک آرایه چندبعدی ایجاد کنید و آن را به آرایه انجمنی تبدیل کنید.

```php
<?php
$array = [
    ['key' => 'name', 'value' => 'Alice'],
    ['key' => 'age', 'value' => 25],
    ['key' => 'city', 'value' => 'New York']
];

$associativeArray = array_column($array, 'value', 'key');
print_r($associativeArray);
?>
```
#array_column 
### تمرین 64: اعمال تابعی بر روی هر عنصر از آرایه چندبعدی

یک آرایه چندبعدی از اعداد ایجاد کنید و تابعی را بر روی هر عنصر آن اعمال کنید.

```php
<?php
$array = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

array_walk_recursive($array, function(&$value) {
    $value *= 2;
});

print_r($array);
?>
```
#array_walk_recursive
### تمرین 65: جستجوی یک مقدار در آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و یک مقدار خاص را در آن جستجو کنید.

```php
<?php
$array = [
    'level1' => [
        'level2' => [
            'level3' => [
                'target' => 'find me'
            ]
        ]
    ]
];

function searchArray($array, $target) {
    $iterator = new RecursiveIteratorIterator(new RecursiveArrayIterator($array), RecursiveIteratorIterator::SELF_FIRST);
    foreach ($iterator as $key => $value) {
        if ($value === $target) {
            return true;
        }
    }
    return false;
}

$found = searchArray($array, 'find me');
echo $found ? 'Found' : 'Not Found';
?>
```
#searchArray #new #RecursiveIteratorIterator #SELF_FIRST
### تمرین 66: ایجاد یک آرایه درختی از یک لیست

یک لیست مسطح از عناصر با والدین‌شان ایجاد کنید و آن را به یک آرایه درختی تبدیل کنید.

```php
<?php
$list = [
    ['id' => 1, 'parent_id' => 0, 'name' => 'root'],
    ['id' => 2, 'parent_id' => 1, 'name' => 'child 1'],
    ['id' => 3, 'parent_id' => 1, 'name' => 'child 2'],
    ['id' => 4, 'parent_id' => 2, 'name' => 'child 1.1'],
    ['id' => 5, 'parent_id' => 2, 'name' => 'child 1.2']
];

function buildTree(array &$elements, $parentId = 0) {
    $branch = [];
    foreach ($elements as &$element) {
        if ($element['parent_id'] == $parentId) {
            $children = buildTree($elements, $element['id']);
            if ($children) {
                $element['children'] = $children;
            }
            $branch[] = $element;
            unset($element);
        }
    }
    return $branch;
}

$tree = buildTree($list);
print_r($tree);
?>
```

### تمرین 67: پیدا کردن کلیدهای یکتا در آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و کلیدهای یکتای آن را پیدا کنید.

```php
<?php
$array = [
    ['id' => 1, 'name' => 'Alice'],
    ['id' => 2, 'name' => 'Bob'],
    ['id' => 3, 'name' => 'Charlie'],
    ['id' => 1, 'name' => 'Alice']
];

$uniqueKeys = array_keys(array_flip(array_column($array, 'id')));
print_r($uniqueKeys);
?>
```
#array_keys #array_flip #array_column
### تمرین 68: مرتب‌سازی آرایه چندبعدی بر اساس طول رشته‌ها

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و آن را بر اساس طول رشته‌ها مرتب کنید.

```php
<?php
$strings = [
    ['string' => 'apple'],
    ['string' => 'banana'],
    ['string' => 'cherry'],
    ['string' => 'date']
];

usort($strings, function($a, $b) {
    return strlen($a['string']) - strlen($b['string']);
});

print_r($strings);
?>
```
#usort #strlen
### تمرین 69: تجزیه یک رشته و تبدیل آن به آرایه چندبعدی

یک رشته به فرمت JSON ایجاد کنید و آن را به یک آرایه چندبعدی تبدیل کنید.

```php
<?php

$jsonString = '{"name": "Alice", "details": {"age": 25, "city": "New York"}}';


$array = json_decode($jsonString, true); 

print_r($array); 

?>
```

#json_decode

### تمرین 70: استفاده از تابع array_reduce برای جمع‌آوری مقادیر
یک آرایه از اعداد ایجاد کنید و مجموع مقادیر آن را با استفاده از تابع `array_reduce` محاسبه کنید.



```php
<?php
$numbers = [1, 2, 3, 4, 5];

$sum = array_reduce($numbers, function($carry, $item) {
    return $carry + $item;
}, 0);

echo "Sum: $sum\n";
?>
````
#array_reduce
### تمرین 71: ایجاد یک دیکشنری از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و آن را به یک دیکشنری (آرایه انجمنی) تبدیل کنید.

```php
<?php
$array = [
    ['key' => 'name', 'value' => 'Alice'],
    ['key' => 'age', 'value' => 25],
    ['key' => 'city', 'value' => 'New York']
];

$dictionary = [];
foreach ($array as $item) {
    $dictionary[$item['key']] = $item['value'];
}

print_r($dictionary);
?>
```

### تمرین 72: فیلتر کردن آرایه چندبعدی بر اساس شرط

یک آرایه چندبعدی ایجاد کنید و فقط عناصر که شرط خاصی را برآورده می‌کنند فیلتر کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'grade' => 88],
    ['name' => 'Bob', 'grade' => 95],
    ['name' => 'Charlie', 'grade' => 82],
    ['name' => 'David', 'grade' => 90]
];

$filteredStudents = array_filter($students, function($student) {
    return $student['grade'] > 85;
});

print_r($filteredStudents);
?>
```
#array_filter
### تمرین 73: ایجاد ماتریس‌های مختلف از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و ماتریس‌های مختلفی از آن استخراج کنید.

```php
<?php
$matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

// ماتریس قطر اصلی
$diagonal = [];
for ($i = 0; $i < count($matrix); $i++) {
    $diagonal[] = $matrix[$i][$i];
}

print_r($diagonal);
?>
```
#count
### تمرین 74: جستجوی کلید در آرایه چندبعدی و برگرداندن مقدار آن

یک آرایه چندبعدی ایجاد کنید و کلیدی را جستجو کنید و مقدار آن را برگردانید.

```php
<?php
$tree = [
    'root' => [
        'branch1' => [
            'leaf1' => 'A',
            'leaf2' => 'B'
        ],
        'branch2' => [
            'leaf3' => 'C',
            'leaf4' => 'D'
        ]
    ]
];

function findValueByKey($array, $searchKey) {
    $iterator = new RecursiveIteratorIterator(new RecursiveArrayIterator($array));
    foreach ($iterator as $key => $value) {
        if ($key === $searchKey) {
            return $value;
        }
    }
    return null;
}

$value = findValueByKey($tree, 'leaf3');
echo "Value: $value\n";
?>
```
#new #RecursiveIteratorIterator
### تمرین 75: تبدیل آرایه چندبعدی به آرایه تخت

یک آرایه چندبعدی ایجاد کنید و آن را به آرایه تخت تبدیل کنید.

```php
<?php
$array = [
    'level1' => [
        'level2' => [
            'level3' => 'value'
        ]
    ]
];

function flattenArray($array, $prefix = '') {
    $result = [];
    foreach ($array as $key => $value) {
        $newKey = $prefix === '' ? $key : $prefix . '.' . $key;
        if (is_array($value)) {
            $result = array_merge($result, flattenArray($value, $newKey));
        } else {
            $result[$newKey] = $value;
        }
    }
    return $result;
}

$flattenedArray = flattenArray($array);
print_r($flattenedArray);
?>
```
#is_array #array_merge 
این تمرین‌ها می‌توانند شما را در درک عمیق‌تر و کاربردهای پیچیده‌تر آرایه‌ها در PHP یاری کنند. هر سوالی داشتید، خوشحال می‌شوم کمک کنم!

حتما! در ادامه تمرین‌های بیشتری برای کار با آرایه‌ها در PHP آورده‌ام:

### تمرین 76: ایجاد یک آرایه انجمنی از رشته‌های جدا شده

یک رشته را به قسمت‌های جداگانه تقسیم کنید و یک آرایه انجمنی ایجاد کنید که کلیدها، کلمات و مقادیر، طول کلمات باشند.

```php
<?php
$string = "PHP is a popular general-purpose scripting language";
$words = explode(' ', $string);

$assocArray = [];
foreach ($words as $word) {
    $assocArray[$word] = strlen($word);
}

print_r($assocArray);
?>
```
#explode #strlen
### تمرین 77: مرتب‌سازی آرایه چند بعدی بر اساس چندین کلید

یک آرایه چندبعدی از اطلاعات محصولات ایجاد کنید و آن را بر اساس قیمت و سپس موجودی مرتب کنید.

```php
<?php
$products = [
    ['name' => 'Product 1', 'price' => 100, 'stock' => 20],
    ['name' => 'Product 2', 'price' => 200, 'stock' => 10],
    ['name' => 'Product 3', 'price' => 100, 'stock' => 30],
    ['name' => 'Product 4', 'price' => 300, 'stock' => 40]
];

usort($products, function($a, $b) {
    if ($a['price'] == $b['price']) {
        return $b['stock'] <=> $a['stock'];
    }
    return $a['price'] <=> $b['price'];
});

print_r($products);
?>
```
#usort
### تمرین 78: مقایسه دو آرایه چندبعدی و پیدا کردن تفاوت‌ها

دو آرایه چندبعدی ایجاد کنید و تفاوت‌های بین آنها را پیدا کنید.

```php
<?php
$array1 = [
    ['id' => 1, 'name' => 'Alice', 'grade' => 85],
    ['id' => 2, 'name' => 'Bob', 'grade' => 90],
    ['id' => 3, 'name' => 'Charlie', 'grade' => 80]
];

$array2 = [
    ['id' => 1, 'name' => 'Alice', 'grade' => 85],
    ['id' => 2, 'name' => 'Bob', 'grade' => 92],
    ['id' => 4, 'name' => 'David', 'grade' => 88]
];

$diff = array_udiff($array1, $array2, function($a, $b) {
    return $a['id'] <=> $b['id'];
});

print_r($diff);
?>
```
#array_udiff
### تمرین 79: جمع‌آوری مقادیر یکتا از آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات کاربران ایجاد کنید و مقادیر یکتای رشته‌ها را جمع‌آوری کنید.

```php
<?php
$users = [
    ['id' => 1, 'name' => 'Alice', 'city' => 'New York'],
    ['id' => 2, 'name' => 'Bob', 'city' => 'Los Angeles'],
    ['id' => 3, 'name' => 'Charlie', 'city' => 'New York'],
    ['id' => 4, 'name' => 'David', 'city' => 'Chicago']
];

$cities = array_unique(array_column($users, 'city'));
print_r($cities);
?>
```
#array_unique #array_column 
### تمرین 80: تبدیل آرایه چندبعدی به آرایه انجمنی با کلیدهای ترکیبی

یک آرایه چندبعدی از اطلاعات سفارشات ایجاد کنید و آن را به یک آرایه انجمنی با کلیدهای ترکیبی تبدیل کنید.

```php
<?php
$orders = [
    ['order_id' => 1, 'product' => 'Book', 'quantity' => 2],
    ['order_id' => 2, 'product' => 'Pen', 'quantity' => 10],
    ['order_id' => 3, 'product' => 'Notebook', 'quantity' => 5]
];

$assocArray = [];
foreach ($orders as $order) {
    $key = $order['order_id'] . '_' . $order['product'];
    $assocArray[$key] = $order['quantity'];
}

print_r($assocArray);
?>
```

### تمرین 81: فیلتر کردن آرایه چندبعدی با استفاده از کلیدهای خاص

یک آرایه چندبعدی از اطلاعات کتاب‌ها ایجاد کنید و فقط کتاب‌هایی که نویسنده آنها خاص است را فیلتر کنید.

```php
<?php
$books = [
    ['title' => 'Book 1', 'author' => 'Author A', 'year' => 2020],
    ['title' => 'Book 2', 'author' => 'Author B', 'year' => 2019],
    ['title' => 'Book 3', 'author' => 'Author A', 'year' => 2021]
];

$filteredBooks = array_filter($books, function($book) {
    return $book['author'] === 'Author A';
});

print_r($filteredBooks);
?>
```
#array_filter 
### تمرین 82: تبدیل آرایه چندبعدی به رشته JSON

یک آرایه چندبعدی از اطلاعات دانشجویان ایجاد کنید و آن را به یک رشته JSON تبدیل کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'grade' => 85],
    ['name' => 'Bob', 'grade' => 90],
    ['name' => 'Charlie', 'grade' => 80]
];

$jsonString = json_encode($students);
echo $jsonString;
?>
```
#json_encode 
### تمرین 83: پیدا کردن مقادیر حداقلی و حداکثری در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات فروش ایجاد کنید و مقدار حداقلی و حداکثری فروش را پیدا کنید.

```php
<?php
$sales = [
    ['product' => 'Book', 'amount' => 150],
    ['product' => 'Pen', 'amount' => 200],
    ['product' => 'Notebook', 'amount' => 50]
];

$amounts = array_column($sales, 'amount');
$minAmount = min($amounts);
$maxAmount = max($amounts);

echo "Min Amount: $minAmount\n";
echo "Max Amount: $maxAmount\n";
?>
```
#array_column #min #max 
### تمرین 84: تغییر فرمت تاریخ در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات کارمندان ایجاد کنید و فرمت تاریخ تولد آنها را تغییر دهید.

```php
<?php
$employees = [
    ['name' => 'Alice', 'birth_date' => '1990-01-15'],
    ['name' => 'Bob', 'birth_date' => '1985-07-23'],
    ['name' => 'Charlie', 'birth_date' => '1992-05-30']
];

foreach ($employees as &$employee) {
    $date = DateTime::createFromFormat('Y-m-d', $employee['birth_date']);
    $employee['birth_date'] = $date->format('d/m/Y');
}

print_r($employees);
?>
```
#DateTime #createFromFormat #format
### تمرین 85: محاسبه میانگین یک مقدار خاص در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات دانشجویان ایجاد کنید و میانگین نمرات آنها را محاسبه کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'grade' => 85],
    ['name' => 'Bob', 'grade' => 90],
    ['name' => 'Charlie', 'grade' => 80]
];

$total = array_sum(array_column($students, 'grade'));
$count = count($students);
$average = $total / $count;

echo "Average Grade: $average\n";
?>
```
#array_sum #array_column #count
### تمرین 86: ایجاد یک آرایه چندبعدی از مقادیر یک کلید خاص

یک آرایه چندبعدی از اطلاعات محصولات ایجاد کنید و فقط مقادیر یک کلید خاص را به آرایه‌ای دیگر انتقال دهید.

```php
<?php
$products = [
    ['name' => 'Product 1', 'price' => 100, 'category' => 'Books'],
    ['name' => 'Product 2', 'price' => 200, 'category' => 'Electronics'],
    ['name' => 'Product 3', 'price' => 150, 'category' => 'Books']
];

$bookProducts = array_filter($products, function($product) {
    return $product['category'] === 'Books';
});

print_r($bookProducts);
?>
```
#array_filter
### تمرین 87: گروه‌بندی مقادیر در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات دانشجویان ایجاد کنید و آنها را بر اساس نمرات گروه‌بندی کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'grade' => 'A'],
    ['name' => 'Bob', 'grade' => 'B'],
    ['name' => 'Charlie', 'grade' => 'A'],
    ['name' => 'David', 'grade' => 'C']
];

$groupedStudents = [];
foreach ($students as $student) {
    $groupedStudents[$student['grade']][] = $student;
}

print_r($groupedStudents);
?>
```

### تمرین 88: پیدا کردن مسیر

کامل یک کلید در آرایه چندبعدی یک آرایه چندبعدی ایجاد کنید و مسیر کامل یک کلید خاص را پیدا کنید.

```php
<?php
$tree = [
    'root' => [
        'branch1' => [
            'leaf1' => 'A',
            'leaf2' => 'B'
        ],
        'branch2' => [
            'leaf3' => 'C',
            'leaf4' => 'D'
        ]
    ]
];

function findKeyPath($array, $searchKey, $path = '') {
    foreach ($array as $key => $value) {
        $currentPath = $path ? "$path.$key" : $key;
        if ($key === $searchKey) {
            return $currentPath;
        }
        if (is_array($value)) {
            $result = findKeyPath($value, $searchKey, $currentPath);
            if ($result) {
                return $result;
            }
        }
    }
    return null;
}

$path = findKeyPath($tree, 'leaf3');
echo "Path: $path\n";
?>
```

### تمرین 89: تغییر ساختار آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات دانشجویان ایجاد کنید و ساختار آن را تغییر دهید.

```php
<?php
$students = [
    ['name' => 'Alice', 'subjects' => ['Math' => 85, 'Science' => 90]],
    ['name' => 'Bob', 'subjects' => ['Math' => 78, 'Science' => 88]],
    ['name' => 'Charlie', 'subjects' => ['Math' => 92, 'Science' => 81]]
];

$restructuredArray = [];
foreach ($students as $student) {
    foreach ($student['subjects'] as $subject => $grade) {
        $restructuredArray[$subject][] = ['name' => $student['name'], 'grade' => $grade];
    }
}

print_r($restructuredArray);
?>
```

### تمرین 90: پیدا کردن بیشترین مقدار در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات فروش ایجاد کنید و بیشترین مقدار فروش را پیدا کنید.

```php
<?php
$sales = [
    ['product' => 'Book', 'amount' => 150],
    ['product' => 'Pen', 'amount' => 200],
    ['product' => 'Notebook', 'amount' => 50]
];

$maxSale = max(array_column($sales, 'amount'));
echo "Max Sale Amount: $maxSale\n";
?>
```
#max #array_column
### تمرین 91: مقایسه و ادغام دو آرایه چندبعدی

دو آرایه چندبعدی از اطلاعات کاربران ایجاد کنید و آنها را با هم مقایسه و ادغام کنید.

```php
<?php
$users1 = [
    ['id' => 1, 'name' => 'Alice', 'email' => 'alice@example.com'],
    ['id' => 2, 'name' => 'Bob', 'email' => 'bob@example.com']
];

$users2 = [
    ['id' => 2, 'name' => 'Bob', 'email' => 'bob_new@example.com'],
    ['id' => 3, 'name' => 'Charlie', 'email' => 'charlie@example.com']
];

$mergedUsers = array_replace_recursive($users1, $users2);
print_r($mergedUsers);
?>
```
#array_replace_recursive
### تمرین 92: ایجاد آرایه‌های متقارن و نامتقارن از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و آرایه‌های متقارن و نامتقارن را از آن استخراج کنید.

```php
<?php
$array = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

// ماتریس متقارن
$symmetric = true;
for ($i = 0; $i < count($array); $i++) {
    for ($j = 0; $j < count($array); $j++) {
        if ($array[$i][$j] != $array[$j][$i]) {
            $symmetric = false;
            break 2;
        }
    }
}

echo $symmetric ? "Symmetric" : "Not Symmetric";
?>
```
#count
### تمرین 93: استخراج زیرآرایه‌های متناوب از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و زیرآرایه‌های متناوب را از آن استخراج کنید.

```php
<?php
$array = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
    [10, 11, 12]
];

$alternatingSubArray = [];
for ($i = 0; $i < count($array); $i += 2) {
    $alternatingSubArray[] = $array[$i];
}

print_r($alternatingSubArray);
?>
```

### تمرین 94: ایجاد ترکیب‌های مختلف از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و ترکیب‌های مختلفی از آن استخراج کنید.

```php
<?php
$array = [
    [1, 2],
    [3, 4],
    [5, 6]
];

$combinations = [[]];
foreach ($array as $set) {
    $newCombinations = [];
    foreach ($combinations as $combination) {
        foreach ($set as $value) {
            $newCombinations[] = array_merge($combination, [$value]);
        }
    }
    $combinations = $newCombinations;
}

print_r($combinations);
?>
```

### تمرین 95: تغییر کلیدهای یک آرایه چندبعدی به مقادیر خاص

یک آرایه چندبعدی از اطلاعات کتاب‌ها ایجاد کنید و کلیدهای آن را به مقادیر خاصی تغییر دهید.

```php
<?php
$books = [
    ['title' => 'Book 1', 'author' => 'Author A'],
    ['title' => 'Book 2', 'author' => 'Author B'],
    ['title' => 'Book 3', 'author' => 'Author C']
];

$renamedKeysArray = [];
foreach ($books as $book) {
    $renamedKeysArray[] = [
        'book_title' => $book['title'],
        'book_author' => $book['author']
    ];
}

print_r($renamedKeysArray);
?>
```

### تمرین 96: ادغام آرایه‌های چندبعدی با مقادیر مشترک

دو آرایه چندبعدی از اطلاعات دانشجویان ایجاد کنید و آنها را بر اساس مقادیر مشترک ادغام کنید.

```php
<?php
$students1 = [
    ['id' => 1, 'name' => 'Alice', 'grade' => 85],
    ['id' => 2, 'name' => 'Bob', 'grade' => 90]
];

$students2 = [
    ['id' => 2, 'name' => 'Bob', 'email' => 'bob@example.com'],
    ['id' => 3, 'name' => 'Charlie', 'email' => 'charlie@example.com']
];

$mergedStudents = [];
foreach ($students1 as $student1) {
    foreach ($students2 as $student2) {
        if ($student1['id'] === $student2['id']) {
            $mergedStudents[] = array_merge($student1, $student2);
        }
    }
}

print_r($mergedStudents);
?>
```

### تمرین 97: استفاده از ترکیب توابع برای پردازش آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات فروش ایجاد کنید و از ترکیب توابع برای پردازش آن استفاده کنید.

```php
<?php
$sales = [
    ['product' => 'Book', 'amount' => 150, 'date' => '2023-01-15'],
    ['product' => 'Pen', 'amount' => 200, 'date' => '2023-02-20'],
    ['product' => 'Notebook', 'amount' => 50, 'date' => '2023-03-10']
];

$salesInMarch = array_filter($sales, function($sale) {
    return strpos($sale['date'], '2023-03') === 0;
});

$totalSalesInMarch = array_sum(array_column($salesInMarch, 'amount'));

echo "Total Sales in March: $totalSalesInMarch\n";
?>
```

### تمرین 98: شبیه‌سازی عملیات پایگاه داده با آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات کاربران ایجاد کنید و عملیات‌های مشابه پایگاه داده را شبیه‌سازی کنید.

```php
<?php
$users = [
    ['id' => 1, 'name' => 'Alice', 'email' => 'alice@example.com'],
    ['id' => 2, 'name' => 'Bob', 'email' => 'bob@example.com'],
    ['id' => 3, 'name' => 'Charlie', 'email' => 'charlie@example.com']
];

// انتخاب کاربران با آدرس ایمیل خاص
$filteredUsers = array_filter($users, function($user) {
    return strpos($user['email'], 'example.com') !== false;
});

// بروزرسانی نام کاربری
foreach ($users as &$user) {
    if ($user['id'] == 1) {
        $user['name'] = 'Alice Updated';
    }
}

//حذف کاربری با شناسه خاص
$users = array_filter($users, function($user) { return $user['id'] !== 2; });

print_r($filteredUsers); print_r($users); ?>

```
#array_filter #strpos 



### تمرین 99: پیدا کردن تکراری‌ها در آرایه چندبعدی
یک آرایه چندبعدی از اطلاعات محصولات ایجاد کنید و محصولات تکراری را پیدا کنید.

```php
<?php
$products = [
    ['name' => 'Product 1', 'price' => 100],
    ['name' => 'Product 2', 'price' => 150],
    ['name' => 'Product 1', 'price' => 100],
    ['name' => 'Product 3', 'price' => 200]
];

$uniqueProducts = [];
$duplicateProducts = [];

foreach ($products as $product) {
    $hash = md5(json_encode($product));
    if (in_array($hash, $uniqueProducts)) {
        $duplicateProducts[] = $product;
    } else {
        $uniqueProducts[] = $hash;
    }
}

print_r($duplicateProducts);
?>
````
#json_encode #in_array 

### تمرین 100: مرتب‌سازی آرایه چندبعدی بر اساس چندین کلید

یک آرایه چندبعدی از اطلاعات دانشجویان ایجاد کنید و آن را بر اساس چندین کلید مرتب کنید.

```php
<?php
$students = [
    ['name' => 'Alice', 'age' => 25, 'grade' => 88],
    ['name' => 'Bob', 'age' => 22, 'grade' => 95],
    ['name' => 'Charlie', 'age' => 25, 'grade' => 90],
    ['name' => 'David', 'age' => 22, 'grade' => 85]
];

usort($students, function($a, $b) {
    if ($a['age'] == $b['age']) {
        return $b['grade'] <=> $a['grade'];
    }
    return $a['age'] <=> $b['age'];
});

print_r($students);
?>
```

این تمرین‌ها می‌توانند مهارت‌های شما را در کار با آرایه‌ها در PHP بهبود بخشند و شما را در یادگیری مفاهیم پیچیده‌تر یاری کنند. هر سوالی داشتید، خوشحال می‌شوم کمک کنم!

حتما! در اینجا 100 مثال دیگر برای کار با آرایه‌ها در PHP آورده‌ام:

### تمرین 101: تبدیل آرایه به مجموعه‌ای از کلیدها و مقادیر

یک آرایه انجمنی ایجاد کنید و آن را به مجموعه‌ای از کلیدها و مقادیر تبدیل کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$keys = array_keys($assocArray);
$values = array_values($assocArray);

print_r($keys);
print_r($values);
?>
```

### تمرین 102: یافتن میانگین یک آرایه عددی

یک آرایه عددی ایجاد کنید و میانگین مقادیر آن را محاسبه کنید.

```php
<?php
$numbers = [10, 20, 30, 40, 50];
$average = array_sum($numbers) / count($numbers);

echo "Average: $average\n";
?>
```

### تمرین 103: فیلتر کردن آرایه بر اساس یک شرط

یک آرایه از اعداد ایجاد کنید و فقط اعداد زوج را فیلتر کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
$evenNumbers = array_filter($numbers, function($number) {
    return $number % 2 === 0;
});

print_r($evenNumbers);
?>
```

### تمرین 104: ترکیب چندین آرایه

چندین آرایه را با هم ترکیب کنید.

```php
<?php
$array1 = [1, 2, 3];
$array2 = [4, 5, 6];
$array3 = [7, 8, 9];

$combinedArray = array_merge($array1, $array2, $array3);
print_r($combinedArray);
?>
```

### تمرین 105: پیدا کردن مقادیر تکراری در یک آرایه

یک آرایه از اعداد ایجاد کنید و مقادیر تکراری آن را پیدا کنید.

```php
<?php
$numbers = [1, 2, 3, 2, 4, 5, 5, 6, 7, 8, 8];
$duplicates = array_unique(array_diff_assoc($numbers, array_unique($numbers)));

print_r($duplicates);
?>
```

### تمرین 106: تغییر ترتیب آرایه

یک آرایه از اعداد ایجاد کنید و ترتیب آن را تغییر دهید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];
$reversedArray = array_reverse($numbers);

print_r($reversedArray);
?>
```

### تمرین 107: تبدیل آرایه به رشته

یک آرایه از رشته‌ها ایجاد کنید و آن را به یک رشته تبدیل کنید.

```php
<?php
$words = ['Hello', 'world', 'PHP', 'is', 'fun'];
$sentence = implode(' ', $words);

echo $sentence;
?>
```

### تمرین 108: پیدا کردن موقعیت یک عنصر در آرایه

یک آرایه از اعداد ایجاد کنید و موقعیت یک عنصر خاص را پیدا کنید.

```php
<?php
$numbers = [10, 20, 30, 40, 50];
$position = array_search(30, $numbers);

echo "Position: $position\n";
?>
```

### تمرین 109: ایجاد زیرآرایه از آرایه اصلی

یک آرایه از اعداد ایجاد کنید و یک زیرآرایه از آن استخراج کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
$subArray = array_slice($numbers, 2, 5);

print_r($subArray);
?>
```

### تمرین 110: مقایسه دو آرایه

دو آرایه ایجاد کنید و تفاوت‌های بین آنها را پیدا کنید.

```php
<?php
$array1 = [1, 2, 3, 4, 5];
$array2 = [4, 5, 6, 7, 8];

$differences = array_diff($array1, $array2);
print_r($differences);
?>
```

### تمرین 111: ادغام دو آرایه انجمنی

دو آرایه انجمنی ایجاد کنید و آنها را با هم ادغام کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['city' => 'New York', 'country' => 'USA'];

$mergedArray = array_merge($array1, $array2);
print_r($mergedArray);
?>
```

### تمرین 112: مرتب‌سازی آرایه انجمنی بر اساس مقدار

یک آرایه انجمنی ایجاد کنید و آن را بر اساس مقادیر مرتب کنید.

```php
<?php
$assocArray = ['Alice' => 25, 'Bob' => 20, 'Charlie' => 30];
asort($assocArray);

print_r($assocArray);
?>
```

### تمرین 113: حذف عناصر خالی از آرایه

یک آرایه ایجاد کنید و عناصر خالی آن را حذف کنید.

```php
<?php
$array = ['Apple', '', 'Banana', null, 'Cherry', false, 'Date'];
$filteredArray = array_filter($array);

print_r($filteredArray);
?>
```

### تمرین 114: تقسیم آرایه به بخش‌های کوچکتر

یک آرایه از اعداد ایجاد کنید و آن را به بخش‌های کوچکتر تقسیم کنید.

```php
<?php
$numbers = range(1, 20);
$chunkedArray = array_chunk($numbers, 5);

print_r($chunkedArray);
?>
```

### تمرین 115: پیدا کردن اشتراک دو آرایه

دو آرایه از اعداد ایجاد کنید و اشتراک آنها را پیدا کنید.

```php
<?php
$array1 = [1, 2, 3, 4, 5];
$array2 = [4, 5, 6, 7, 8];

$intersection = array_intersect($array1, $array2);
print_r($intersection);
?>
```

### تمرین 116: تغییر کلیدهای یک آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلیدهای آن را به مقادیر دیگر تغییر دهید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25];
$keys = ['full_name', 'years'];

$modifiedArray = array_combine($keys, array_values($assocArray));
print_r($modifiedArray);
?>
```

### تمرین 117: محاسبه مجموع یک آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات محصولات ایجاد کنید و مجموع مقادیر یک کلید خاص را محاسبه کنید.

```php
<?php
$products = [
    ['name' => 'Product 1', 'price' => 100],
    ['name' => 'Product 2', 'price' => 200],
    ['name' => 'Product 3', 'price' => 150]
];

$totalPrice = array_sum(array_column($products, 'price'));
echo "Total Price: $totalPrice\n";
?>
```

### تمرین 118: مرتب‌سازی آرایه بر اساس طول رشته‌ها

یک آرایه از رشته‌ها ایجاد کنید و آن را بر اساس طول رشته‌ها مرتب کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry', 'date'];
usort($strings, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($strings);
?>
```

### تمرین 119: تبدیل رشته JSON به آرایه

یک رشته JSON ایجاد کنید و آن را به آرایه تبدیل کنید.

```php
<?php
$jsonString = '{"name": "Alice", "age": 25, "city": "New York"}';
$array = json_decode($jsonString, true);

print_r($array);
?>
```

### تمرین 120: محاسبه میانگین وزنی یک آرایه

یک آرایه از اعداد و یک آرایه از وزن‌ها ایجاد کنید و میانگین وزنی را محاسبه کنید.

```php
<?php
$values = [10, 20, 30, 40, 50];
$weights = [1, 2, 3, 4, 5];
$weightedSum = array_sum(array_map(function($value, $weight) {
    return $value * $weight;
}, $values, $weights));
$totalWeights = array_sum($weights);
$weightedAverage = $weightedSum / $totalWeights;

echo "Weighted Average: $weightedAverage\n";
?>
```

### تمرین 121: پیدا کردن عنصر مفقود شده در یک آرایه

یک آرایه از اعداد مرتب ایجاد کنید و یکی از اعداد را حذف کنید. سپس عنصر مفقود شده را پیدا کنید.

```php
<?php
$numbers = range(1, 10);
unset($numbers[array_search(5, $numbers)]);  // حذف عدد 5

$missingNumber = array_diff(range(1, 10), $numbers);
print_r($missingNumber);
?>
```
#unset #range #array_search 


حتما، در ادامه 78 تمرین دیگر برای کار با آرایه‌ها در PHP آورده‌ام که تکراری نباشند.

### تمرین 122: جایگزینی عناصر در آرایه

یک آرایه از اعداد ایجاد کنید و عناصر خاصی را با مقادیر دیگر جایگزین کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];
$replace = [2 => 20, 4 => 40];

$modifiedArray = array_replace($numbers, $replace);
print_r($modifiedArray);
?>
```

### تمرین 123: تولید یک آرایه از تعداد مشخصی عنصر تصادفی

یک آرایه از اعداد تصادفی بین 1 تا 100 ایجاد کنید.

```php
<?php
$randomNumbers = array_map(function() {
    return rand(1, 100);
}, range(1, 10));

print_r($randomNumbers);
?>
```

### تمرین 124: پیدا کردن بیشترین طول رشته در آرایه

یک آرایه از رشته‌ها ایجاد کنید و رشته با بیشترین طول را پیدا کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry', 'date'];
$longestString = array_reduce($strings, function($carry, $item) {
    return strlen($carry) > strlen($item) ? $carry : $item;
});

echo "Longest String: $longestString\n";
?>
```

### تمرین 125: پیدا کردن کلید با بیشترین مقدار در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلید با بیشترین مقدار را پیدا کنید.

```php
<?php
$assocArray = ['Alice' => 25, 'Bob' => 30, 'Charlie' => 28];
$maxKey = array_keys($assocArray, max($assocArray))[0];

echo "Key with max value: $maxKey\n";
?>
```

### تمرین 126: ساخت آرایه انجمنی از دو آرایه

دو آرایه ایجاد کنید و آنها را به یک آرایه انجمنی تبدیل کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$assocArray = array_combine($keys, $values);
print_r($assocArray);
?>
```

### تمرین 127: جمع عناصر دو آرایه عددی

دو آرایه عددی ایجاد کنید و عناصر آنها را با هم جمع کنید.

```php
<?php
$array1 = [1, 2, 3];
$array2 = [4, 5, 6];

$sumArray = array_map(function($a, $b) {
    return $a + $b;
}, $array1, $array2);

print_r($sumArray);
?>
```

### تمرین 128: ادغام چند آرایه انجمنی و جایگزینی مقادیر تکراری

چند آرایه انجمنی ایجاد کنید و آنها را با هم ادغام کنید.

```php
<?php
$array1 = ['a' => 1, 'b' => 2];
$array2 = ['b' => 3, 'c' => 4];
$array3 = ['c' => 5, 'd' => 6];

$mergedArray = array_replace($array1, $array2, $array3);
print_r($mergedArray);
?>
```

### تمرین 129: پیدا کردن عنصر تکراری اول در یک آرایه

یک آرایه از اعداد ایجاد کنید و اولین عنصر تکراری را پیدا کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 2, 5, 3];
$seen = [];

$firstDuplicate = null;
foreach ($numbers as $number) {
    if (isset($seen[$number])) {
        $firstDuplicate = $number;
        break;
    }
    $seen[$number] = true;
}

echo "First duplicate: $firstDuplicate\n";
?>
```

### تمرین 130: حذف عنصر خاص از آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و عنصری با کلید خاص را حذف کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
unset($assocArray['age']);

print_r($assocArray);
?>
```

### تمرین 131: بررسی وجود یک کلید در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و بررسی کنید که آیا یک کلید خاص وجود دارد یا خیر.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$key = 'age';

$exists = array_key_exists($key, $assocArray);
echo $exists ? "Key exists" : "Key does not exist";
?>
```

### تمرین 132: مرتب‌سازی آرایه انجمنی بر اساس کلید

یک آرایه انجمنی ایجاد کنید و آن را بر اساس کلیدها مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
ksort($assocArray);

print_r($assocArray);
?>
```

### تمرین 133: ایجاد آرایه از یک بازه خاص

یک آرایه از اعداد بین 1 تا 10 ایجاد کنید.

```php
<?php
$rangeArray = range(1, 10);
print_r($rangeArray);
?>
```

### تمرین 134: پیدا کردن طول هر رشته در آرایه

یک آرایه از رشته‌ها ایجاد کنید و طول هر رشته را پیدا کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry'];
$lengths = array_map('strlen', $strings);

print_r($lengths);
?>
```

### تمرین 135: ایجاد آرایه چندبعدی از مقادیر تصادفی

یک آرایه چندبعدی از اعداد تصادفی بین 1 تا 100 ایجاد کنید.

```php
<?php
$multiArray = array_map(function() {
    return array_map(function() {
        return rand(1, 100);
    }, range(1, 5));
}, range(1, 3));

print_r($multiArray);
?>
```

### تمرین 136: محاسبه تعداد عناصر یکتا در آرایه

یک آرایه از اعداد ایجاد کنید و تعداد عناصر یکتای آن را محاسبه کنید.

```php
<?php
$numbers = [1, 2, 3, 3, 4, 5, 5, 6];
$uniqueCount = count(array_unique($numbers));

echo "Unique count: $uniqueCount\n";
?>
```

### تمرین 137: مرتب‌سازی آرایه انجمنی بر اساس طول مقادیر

یک آرایه انجمنی از رشته‌ها ایجاد کنید و آن را بر اساس طول مقادیر مرتب کنید.

```php
<?php
$assocArray = ['a' => 'apple', 'b' => 'banana', 'c' => 'cherry'];
uasort($assocArray, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($assocArray);
?>
```

### تمرین 138: حذف عناصر با مقدار خاص از آرایه

یک آرایه از اعداد ایجاد کنید و عناصر با مقدار خاص را حذف کنید.

```php
<?php
$numbers = [1, 2, 3, 2, 4, 5, 2];
$filteredArray = array_filter($numbers, function($value) {
    return $value !== 2;
});

print_r($filteredArray);
?>
```

### تمرین 139: ایجاد آرایه انجمنی از مقادیر دو آرایه

دو آرایه ایجاد کنید و آنها را به یک آرایه انجمنی تبدیل کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$assocArray = array_combine($keys, $values);
print_r($assocArray);
?>
```

### تمرین 140: پیدا کردن بزرگترین مقدار در آرایه چندبعدی

یک آرایه چندبعدی از اعداد ایجاد کنید و بزرگترین مقدار را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$maxValue = max(array_map('max', $multiArray));
echo "Max value: $maxValue\n";
?>
```

### تمرین 141: محاسبه حاصل ضرب عناصر در آرایه

یک آرایه از اعداد ایجاد کنید و حاصل ضرب همه عناصر آن را محاسبه کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];
$product = array_reduce($numbers, function($carry, $item) {
    return $carry * $item;
}, 1);

echo "Product: $product\n";
?>
```

### تمرین 142: ایجاد آرایه از محدوده خاص با فاصله‌های معین

یک آرایه از اعداد بین 1 تا 20 با فاصله 2 ایجاد کنید.

```php
<?php
$rangeArray = range(1, 20, 2);
print_r($rangeArray);
?>
```

#range 

حتماً، در ادامه تمرین‌های بیشتر برای کار با آرایه‌ها در PHP:

### تمرین 143: پیدا کردن کوچکترین مقدار در آرایه چندبعدی

یک آرایه چندبعدی از اعداد ایجاد کنید و کوچکترین مقدار را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$minValue = min(array_map('min', $multiArray));
echo "Min value: $minValue\n";
?>
```
#array_map 
### تمرین 144: تغییر کلیدهای آرایه انجمنی به حروف بزرگ

یک آرایه انجمنی ایجاد کنید و کلیدهای آن را به حروف بزرگ تغییر دهید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$upperKeysArray = array_change_key_case($assocArray, CASE_UPPER);

print_r($upperKeysArray);
?>
```

### تمرین 145: یافتن طولانی‌ترین و کوتاه‌ترین رشته‌ها در آرایه

یک آرایه از رشته‌ها ایجاد کنید و طولانی‌ترین و کوتاه‌ترین رشته‌ها را پیدا کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry', 'date'];
$longestString = array_reduce($strings, function($carry, $item) {
    return strlen($carry) > strlen($item) ? $carry : $item;
});
$shortestString = array_reduce($strings, function($carry, $item) {
    return strlen($carry) < strlen($item) ? $carry : $item;
});

echo "Longest String: $longestString\n";
echo "Shortest String: $shortestString\n";
?>
```
#array_reduce #strlen 
### تمرین 146: بررسی آرایه انجمنی برای مقادیر خالی

یک آرایه انجمنی ایجاد کنید و بررسی کنید که آیا هیچ یک از مقادیر آن خالی هستند یا خیر.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 0, 'city' => ''];
$hasEmptyValues = in_array('', $assocArray, true) || in_array(null, $assocArray, true);

echo $hasEmptyValues ? "Has empty values" : "No empty values";
?>
```
#in_array 
### تمرین 147: ایجاد یک آرایه از رشته‌ها با طول‌های مختلف و مرتب‌سازی بر اساس طول

یک آرایه از رشته‌ها ایجاد کنید و آن را بر اساس طول مرتب کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry', 'date', 'fig'];
usort($strings, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($strings);
?>
```
#usort #strlen 
### تمرین 148: ایجاد یک آرایه انجمنی از رشته‌ها و محاسبه تعداد تکرار هر رشته

یک آرایه از رشته‌ها ایجاد کنید و تعداد تکرار هر رشته را محاسبه کنید.

```php
<?php
$strings = ['apple', 'banana', 'apple', 'cherry', 'banana', 'banana'];
$stringCounts = array_count_values($strings);

print_r($stringCounts);
?>
```
#array_count_values 
### تمرین 149: یافتن تکراری‌ها در آرایه و حذف آنها

یک آرایه از رشته‌ها ایجاد کنید و تکراری‌ها را حذف کنید.

```php
<?php
$strings = ['apple', 'banana', 'apple', 'cherry', 'banana', 'date'];
$uniqueStrings = array_unique($strings);

print_r($uniqueStrings);
?>
```
#array_unique 
### تمرین 150: استخراج یک بخش خاص از آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و یک بخش خاص از آن را استخراج کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York', 'country' => 'USA'];
$sliceArray = array_slice($assocArray, 1, 2, true);

print_r($sliceArray);
?>
```
#array_slice 
### تمرین 151: بررسی وجود مقدار در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و بررسی کنید که آیا یک مقدار خاص در آن وجود دارد یا خیر.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$value = 'Alice';

$exists = in_array($value, $assocArray);
echo $exists ? "Value exists" : "Value does not exist";
?>
```
#in_array 
### تمرین 152: مرتب‌سازی آرایه چندبعدی بر اساس یک کلید خاص

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس سن مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

usort($people, function($a, $b) {
    return $a['age'] <=> $b['age'];
});

print_r($people);
?>
```
#usort 
### تمرین 153: پیدا کردن تعداد تکرار یک مقدار خاص در آرایه

یک آرایه از اعداد ایجاد کنید و تعداد تکرار یک مقدار خاص را پیدا کنید.

```php
<?php
$numbers = [1, 2, 3, 2, 4, 2, 5];
$count = array_count_values($numbers)[2];

echo "Count of 2: $count\n";
?>
```
#array_count_values
### تمرین 154: یافتن و حذف مقدار بیشترین تکرار در آرایه

یک آرایه از اعداد ایجاد کنید و مقدار با بیشترین تکرار را پیدا و حذف کنید.

```php
<?php
$numbers = [1, 2, 3, 2, 4, 2, 5];
$counts = array_count_values($numbers);
$mostFrequentValue = array_search(max($counts), $counts);
$filteredArray = array_filter($numbers, function($value) use ($mostFrequentValue) {
    return $value !== $mostFrequentValue;
});

print_r($filteredArray);
?>
```
#array_count_values #array_search #array_filter #max
### تمرین 155: محاسبه مجموع مقادیر یکتا در آرایه

یک آرایه از اعداد ایجاد کنید و مجموع مقادیر یکتای آن را محاسبه کنید.

```php
<?php
$numbers = [1, 2, 3, 2, 4, 2, 5];
$uniqueSum = array_sum(array_unique($numbers));

echo "Unique sum: $uniqueSum\n";
?>
```

### تمرین 156: مرتب‌سازی آرایه بر اساس آخرین رقم

یک آرایه از اعداد ایجاد کنید و آن را بر اساس آخرین رقم هر عدد مرتب کنید.

```php
<?php
$numbers = [23, 45, 12, 34, 56, 78];
usort($numbers, function($a, $b) {
    return ($a % 10) <=> ($b % 10);
});

print_r($numbers);
?>
```

### تمرین 157: تبدیل آرایه انجمنی به JSON

یک آرایه انجمنی ایجاد کنید و آن را به فرمت JSON تبدیل کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$json = json_encode($assocArray);

echo $json;
?>
```

### تمرین 158: فیلتر کردن آرایه انجمنی بر اساس مقدار خاص

یک آرایه انجمنی ایجاد کنید و عناصر با مقدار خاص را فیلتر کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York', 'country' => 'USA'];
$filteredArray = array_filter($assocArray, function($value) {
    return $value !== 'New York';
});

print_r($filteredArray);
?>
```

### تمرین 159: جایگزینی عناصر در آرایه با استفاده از تابع ناشناس

یک آرایه از اعداد ایجاد کنید و عناصر آن را با استفاده از یک تابع ناشناس جایگزین کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];
$modifiedArray = array_map(function($value) {
    return $value * 2;
}, $numbers);

print_r($modifiedArray);
?>
```

### تمرین 160: ایجاد آرایه انجمنی از پارامترهای URL

یک رشته URL ایجاد کنید و پارامترهای آن را به آرایه انجمنی تبدیل کنید.

```php
<?php
$url = 'https://example.com/?name=Alice&age=25&city=New+York';
parse_str(parse_url($url, PHP_URL_QUERY), $queryParams);

print_r($queryParams);
?>
```

### تمرین 161: پیدا کردن اولین عنصر بزرگتر از مقدار خاص در آرایه

یک آرایه از اعداد ایجاد کنید و اولین عنصر بزرگتر از مقدار خاص را پیدا کنید.

```php
<?php
$numbers = [10, 20, 30, 40, 50];
$threshold = 25;

$firstGreater = null;
foreach ($numbers as $number) {
    if ($number > $threshold) {
        $firstGreater = $number;
        break;
    }
}

echo "First number greater than $threshold: $firstGreater\n";
?>
```

### تمرین 162: ایجاد آرایه چندبعدی از حروف و اعداد

یک آرایه چندبعدی ایجاد کنید که حروف و اعداد را شامل شود.

```php
<?php
$multiArray = [
    ['A', 'B', 'C'],
    [1, 2, 3],
    ['X', 'Y', 'Z']
];

print_r($multiArray);
?>
```

### تمرین 163: تبدیل آرایه به رشته با جداکننده خاص

یک آرایه از رشته‌ها ایجاد کنید و آن را به یک رشته با جداکننده خاص تبدیل کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry'];
$joinedString = implode('-', $strings);

echo $joinedString;
?>
```

### تمرین 164: بررسی یکتا بودن تمامی عناصر آرایه

یک آرایه از اعداد ایجاد کنید و بررسی کنید که آیا تمامی عناصر آن یکتا هستند یا خیر.

```php
<?php
$numbers = [1, 2, 3, 4, 5];
$isUnique = count($numbers) === count(array_unique($numbers));

echo $isUnique ? "All elements are unique" : "There are duplicate elements";
?>
```

### تمرین 165: پیدا کردن دومین بزرگترین مقدار در آرایه

یک آرایه از اعداد ایجاد کنید و دومین بزرگترین مقدار را پیدا کنید.

```php
<?php
$numbers = [10, 20, 30, 40, 50];
rsort($numbers);
$secondLargest = $numbers[1];

echo "Second largest: $secondLargest\n";
?>
```

### تمرین 166: فیلتر کردن آرایه بر اساس نوع داده

یک آرایه مخلوط از انواع داده‌ها ایجاد کنید و فقط عناصر عددی را فیلتر کنید.

```php
<?php
$mixedArray = [1, '2', 3, 'four', 5, '6'];
$numericArray = array_filter($mixedArray, 'is_numeric');

print_r($numericArray);
?>
```

### تمرین 167: حذف مقادیر تکراری از آرایه و حفظ ترتیب

یک آرایه از اعداد ایجاد کنید و مقادیر تکراری را حذف کنید در حالی که ترتیب اصلی حفظ شود.

```php
<?php
$numbers = [1, 2, 2, 3, 4, 4, 5];
$uniqueNumbers = array_values(array_unique($numbers));

print_r($uniqueNumbers);
?>
```

### تمرین 168: محاسبه میانگین مقادیر در آرایه

یک آرایه از اعداد ایجاد کنید و میانگین مقادیر آن را محاسبه کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5];
$average = array_sum($numbers) / count($numbers);

echo "Average: $average\n";
?>
```

### تمرین 169: معکوس کردن کلیدها و مقادیر در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلیدها و مقادیر آن را معکوس کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$flippedArray = array_flip($assocArray);

print_r($flippedArray);
?>
```

### تمرین 170: یافتن تکرار شده‌ترین مقدار در آرایه

یک آرایه از اعداد ایجاد کنید و تکرار شده‌ترین مقدار را پیدا کنید.

```php
<?php
$numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4];
$counts = array_count_values($numbers);
$mostFrequent = array_search(max($counts), $counts);

echo "Most frequent: $mostFrequent\n";
?>
```

### تمرین 171: مرتب‌سازی آرایه انجمنی بر اساس مقادیر نزولی

یک آرایه انجمنی ایجاد کنید و آن را بر اساس مقادیر به صورت نزولی مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
arsort($assocArray);

print_r($assocArray);
?>
```

### تمرین 172: جستجو و جایگزینی مقادیر در آرایه

یک آرایه از رشته‌ها ایجاد کنید و مقداری خاص را با مقدار دیگری جایگزین کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry'];
$search = 'banana';
$replace = 'orange';

$modifiedArray = array_map(function($item) use ($search, $replace) {
    return $item === $search ? $replace : $item;
}, $strings);

print_r($modifiedArray);
?>
```

### تمرین 173: پیدا کردن طولانی‌ترین زیرآرایه متوالی

یک آرایه از اعداد ایجاد کنید و طولانی‌ترین زیرآرایه متوالی را پیدا کنید.

```php
<?php
$numbers = [1, 2, 3, 5, 6, 7, 8, 10];
$maxLength = 0;
$currentLength = 1;

for ($i = 1; $i < count($numbers); $i++) {
    if ($numbers[$i] == $numbers[$i - 1] + 1) {
        $currentLength++;
    } else {
        if ($currentLength > $maxLength) {
            $maxLength = $currentLength;
        }
        $currentLength = 1;
    }
}

$maxLength = max($maxLength, $currentLength);
echo "Longest consecutive subarray length: $maxLength\n";
?>
```

### تمرین 174: تبدیل آرایه چندبعدی به آرایه تک‌بعدی

یک آرایه چندبعدی ایجاد کنید و آن را به یک آرایه تک‌بعدی تبدیل کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];
$flatArray = array_merge(...$multiArray);

print_r($flatArray);
?>
```

### تمرین 175: بررسی آرایه برای وجود مقادیر غیر تکراری

یک آرایه از اعداد ایجاد کنید و بررسی کنید که آیا همه مقادیر آن غیر تکراری هستند یا خیر.

```php
<?php
$numbers = [1, 2, 3, 4, 5];
$isUnique = count($numbers) === count(array_unique($numbers));

echo $isUnique ? "All elements are unique" : "There are duplicate elements";
?>
```

### تمرین 176: ایجاد یک آرایه از تعداد مشخصی عنصر تکراری

یک آرایه از تعداد مشخصی عنصر تکراری ایجاد کنید.

```php
<?php
$element = 'apple';
$count = 5;

$repeatedArray = array_fill(0, $count, $element);
print_r($repeatedArray);
?>
```

### تمرین 177: محاسبه مجموع مقادیر یک کلید خاص در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مجموع سن آنها را محاسبه کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$totalAge = array_sum(array_column($people, 'age'));
echo "Total age: $totalAge\n";
?>
```

### تمرین 178: مرتب‌سازی آرایه انجمنی بر اساس طول کلیدها

یک آرایه انجمنی ایجاد کنید و آن را بر اساس طول کلیدها مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
uksort($assocArray, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($assocArray);
?>
```

### تمرین 179: ایجاد آرایه‌ای از مقادیر تکراری در دو آرایه

دو آرایه ایجاد کنید و مقادیر تکراری بین آنها را پیدا کنید.

```php
<?php
$array1 = [1, 2, 3, 4, 5];
$array2 = [3, 4, 5, 6, 7];

$commonValues = array_intersect($array1, $array2);
print_r($commonValues);
?>
```

### تمرین 180: بررسی وجود مقادیر رشته‌ای در آرایه

یک آرایه از اعداد و رشته‌ها ایجاد کنید و بررسی کنید که آیا مقادیر رشته‌ای وجود دارند یا خیر.

```php
<?php
$mixedArray = [1, '2', 3, 'four', 5, '6'];
$hasString = count(array_filter($mixedArray, 'is_string')) > 0;

echo $hasString ? "Array contains strings" : "Array does not contain strings";
?>
```

### تمرین 181: محاسبه میانگین مقادیر در آرایه چندبعدی

یک آرایه چندبعدی از اعداد ایجاد کنید و میانگین مقادیر هر زیرآرایه را محاسبه کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5
```

, 6], [7, 8, 9] ];

$averages = array_map(function($subArray) { return array_sum($subArray) / count($subArray); }, $multiArray);

print_r($averages); ?>

````

### تمرین 182: حذف مقادیر خالی از آرایه
یک آرایه از مقادیر مختلف ایجاد کنید و مقادیر خالی را حذف کنید.

```php
<?php
$mixedArray = [1, '', 2, null, 3, false, 4, '0', 5];
$filteredArray = array_filter($mixedArray, function($value) {
    return $value !== '' && $value !== null && $value !== false;
});

print_r($filteredArray);
?>
````

### تمرین 183: یافتن عنصر دومین تکرار شده در آرایه

یک آرایه از اعداد ایجاد کنید و دومین مقدار تکرار شده را پیدا کنید.

```php
<?php
$numbers = [1, 2, 3, 2, 4, 2, 5, 5, 6];
$counts = array_count_values($numbers);
arsort($counts);
$secondMostFrequent = array_keys($counts)[1];

echo "Second most frequent: $secondMostFrequent\n";
?>
```

### تمرین 184: ایجاد آرایه‌ای از محدوده‌های عددی

یک آرایه از محدوده‌های عددی ایجاد کنید.

```php
<?php
$start = 1;
$end = 10;
$rangeArray = range($start, $end);

print_r($rangeArray);
?>
```

### تمرین 185: پیدا کردن تعداد عناصر یکتا در آرایه

یک آرایه از اعداد ایجاد کنید و تعداد عناصر یکتای آن را پیدا کنید.

```php
<?php
$numbers = [1, 2, 2, 3, 4, 4, 5];
$uniqueCount = count(array_unique($numbers));

echo "Number of unique elements: $uniqueCount\n";
?>
```

### تمرین 186: مرتب‌سازی آرایه انجمنی بر اساس کلیدها به صورت معکوس

یک آرایه انجمنی ایجاد کنید و آن را بر اساس کلیدها به صورت معکوس مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
krsort($assocArray);

print_r($assocArray);
?>
```

### تمرین 187: جستجو در آرایه چندبعدی بر اساس کلید

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و بر اساس کلید خاص جستجو کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$searchKey = 'name';
$searchValue = 'Bob';

$result = array_filter($people, function($person) use ($searchKey, $searchValue) {
    return $person[$searchKey] === $searchValue;
});

print_r($result);
?>
```

### تمرین 188: ایجاد آرایه‌ای از مقادیر غیر تکراری

یک آرایه از اعداد ایجاد کنید و یک آرایه جدید از مقادیر غیر تکراری ایجاد کنید.

```php
<?php
$numbers = [1, 2, 2, 3, 4, 4, 5];
$uniqueValues = array_values(array_unique($numbers));

print_r($uniqueValues);
?>
```

### تمرین 189: تبدیل آرایه‌ای از کلیدها و مقادیر به آرایه انجمنی

دو آرایه ایجاد کنید، یکی از کلیدها و دیگری از مقادیر، و آنها را به آرایه انجمنی تبدیل کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$assocArray = array_combine($keys, $values);
print_r($assocArray);
?>
```

### تمرین 190: محاسبه فاصله‌های متوالی بین عناصر آرایه

یک آرایه از اعداد ایجاد کنید و فاصله‌های متوالی بین عناصر آن را محاسبه کنید.

```php
<?php
$numbers = [10, 20, 30, 40, 50];
$distances = [];

for ($i = 1; $i < count($numbers); $i++) {
    $distances[] = $numbers[$i] - $numbers[$i - 1];
}

print_r($distances);
?>
```

### تمرین 191: ایجاد آرایه‌ای از مقادیر چند کلید خاص

یک آرایه انجمنی ایجاد کنید و آرایه‌ای از مقادیر چند کلید خاص ایجاد کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York', 'country' => 'USA'];
$keys = ['name', 'city'];

$valuesArray = array_intersect_key($assocArray, array_flip($keys));
print_r($valuesArray);
?>
```

### تمرین 192: مرتب‌سازی آرایه چندبعدی بر اساس چند کلید

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس نام و سپس سن مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30],
    ['name' => 'Alice', 'age' => 22]
];

usort($people, function($a, $b) {
    return $a['name'] <=> $b['name'] ?: $a['age'] <=> $b['age'];
});

print_r($people);
?>
```

### تمرین 193: معکوس کردن کلیدها و مقادیر آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و کلیدها و مقادیر هر زیرآرایه را معکوس کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];

$flippedPeople = array_map('array_flip', $people);
print_r($flippedPeople);
?>
```

### تمرین 194: ایجاد آرایه‌ای از دو آرایه به صورت جفت‌های کلید-مقدار

دو آرایه ایجاد کنید و آنها را به صورت جفت‌های کلید-مقدار در یک آرایه جدید ترکیب کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$combinedArray = [];
for ($i = 0; $i < count($keys); $i++) {
    $combinedArray[] = [$keys[$i] => $values[$i]];
}

print_r($combinedArray);
?>
```

### تمرین 195: پیدا کردن کوچکترین مقدار در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و کوچکترین مقدار هر زیرآرایه را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$minValues = array_map('min', $multiArray);
print_r($minValues);
?>
```

### تمرین 196: محاسبه مجموع عناصر در آرایه چندبعدی

یک آرایه چندبعدی از اعداد ایجاد کنید و مجموع کل عناصر آن را محاسبه کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$totalSum = array_sum(array_map('array_sum', $multiArray));
echo "Total sum: $totalSum\n";
?>
```

### تمرین 197: بررسی وجود کلید خاص در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و بررسی کنید که آیا کلید خاصی در هر زیرآرایه وجود دارد یا خیر.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];

$key = 'age';
$hasKey = array_reduce($people, function($carry, $person) use ($key) {
    return $carry && array_key_exists($key, $person);
}, true);

echo $hasKey ? "Key exists in all subarrays" : "Key does not exist in all subarrays";
?>
```

### تمرین 198: ایجاد آرایه‌ای از اعداد تصادفی

یک آرایه از تعداد مشخصی عدد تصادفی ایجاد کنید.

```php
<?php
$count = 10;
$randomNumbers = array_map(function() {
    return rand(1, 100);
}, range(1, $count));

print_r($randomNumbers);
?>
```

### تمرین 199: فیلتر کردن آرایه بر اساس یک تابع سفارشی

یک آرایه از اعداد ایجاد کنید و فقط اعداد زوج را فیلتر کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
$evenNumbers = array_filter($numbers, function($number) {
    return $number % 2 === 0;
});

print_r($evenNumbers);
?>
```


### تمرین 200: ترکیب دو آرایه به صورت کلید-مقدار در یک آرایه انجمنی

دو آرایه ایجاد کنید و آنها را به صورت کلید-مقدار در یک آرایه انجمنی ترکیب کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$assocArray = array_combine($keys, $values);
print_r($assocArray);
?>

```

### تمرین 201: پیدا کردن بزرگترین مقدار در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و بزرگترین مقدار هر زیرآرایه را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$maxValues = array_map('max', $multiArray);
print_r($maxValues);
?>
```

### تمرین 202: مرتب‌سازی آرایه انجمنی بر اساس طول مقادیر

یک آرایه انجمنی ایجاد کنید و آن را بر اساس طول مقادیر مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
uasort($assocArray, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($assocArray);
?>
```

### تمرین 203: ادغام دو آرایه و حذف مقادیر تکراری

دو آرایه از اعداد ایجاد کنید، آنها را ادغام کنید و مقادیر تکراری را حذف کنید.

```php
<?php
$array1 = [1, 2, 3, 4];
$array2 = [3, 4, 5, 6];

$mergedArray = array_unique(array_merge($array1, $array2));
print_r($mergedArray);
?>
```

### تمرین 204: ایجاد آرایه‌ای از حروف الفبا

یک آرایه از حروف الفبای انگلیسی ایجاد کنید.

```php
<?php
$alphabetArray = range('A', 'Z');
print_r($alphabetArray);
?>
```

### تمرین 205: پیدا کردن تعداد عناصر تکراری در آرایه

یک آرایه از اعداد ایجاد کنید و تعداد عناصر تکراری آن را پیدا کنید.

```php
<?php
$numbers = [1, 2, 2, 3, 4, 4, 5];
$counts = array_count_values($numbers);
$duplicateCount = count(array_filter($counts, function($count) {
    return $count > 1;
}));

echo "Number of duplicate elements: $duplicateCount\n";
?>
```

### تمرین 206: ایجاد یک آرایه از مقادیر یک کلید خاص در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آرایه‌ای از مقادیر یک کلید خاص ایجاد کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$names = array_column($people, 'name');
print_r($names);
?>
```

### تمرین 207: محاسبه فاصله زمانی بین دو تاریخ در آرایه

یک آرایه از تاریخ‌ها ایجاد کنید و فاصله زمانی بین دو تاریخ خاص را محاسبه کنید.

```php
<?php
$dates = ['2023-01-01', '2023-06-01'];
$date1 = new DateTime($dates[0]);
$date2 = new DateTime($dates[1]);

$interval = $date1->diff($date2);
echo "Difference: " . $interval->days . " days\n";
?>
```

### تمرین 208: یافتن مقادیر مشترک بین دو آرایه چندبعدی

دو آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مقادیر مشترک بین آنها را پیدا کنید.

```php
<?php
$people1 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];
$people2 = [
    ['name' => 'Charlie', 'age' => 30],
    ['name' => 'Bob', 'age' => 20]
];

$commonPeople = array_uintersect($people1, $people2, function($a, $b) {
    return $a['name'] <=> $b['name'] ?: $a['age'] <=> $b['age'];
});

print_r($commonPeople);
?>
```

### تمرین 209: ایجاد آرایه‌ای از تاریخ‌های یک ماه

یک آرایه از تمامی تاریخ‌های یک ماه خاص ایجاد کنید.

```php
<?php
$year = 2023;
$month = 6;
$daysInMonth = cal_days_in_month(CAL_GREGORIAN, $month, $year);
$dates = [];

for ($day = 1; $day <= $daysInMonth; $day++) {
    $dates[] = "$year-$month-$day";
}

print_r($dates);
?>
```

### تمرین 210: بررسی برابر بودن دو آرایه چندبعدی

دو آرایه چندبعدی از اطلاعات افراد ایجاد کنید و بررسی کنید که آیا این دو آرایه برابر هستند یا خیر.

```php
<?php
$people1 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];
$people2 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];

$areEqual = $people1 === $people2;
echo $areEqual ? "Arrays are equal" : "Arrays are not equal";
?>
```

### تمرین 211: مرتب‌سازی آرایه انجمنی بر اساس طول کلیدها به صورت معکوس

یک آرایه انجمنی ایجاد کنید و آن را بر اساس طول کلیدها به صورت معکوس مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
uksort($assocArray, function($a, $b) {
    return strlen($b) <=> strlen($a);
});

print_r($assocArray);
?>
```

### تمرین 212: فیلتر کردن آرایه بر اساس طول مقادیر

یک آرایه از رشته‌ها ایجاد کنید و فقط رشته‌هایی که طول آنها بیشتر از مقدار مشخصی است را فیلتر کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry', 'date', 'fig'];
$minLength = 5;

$filteredStrings = array_filter($strings, function($string) use ($minLength) {
    return strlen($string) >= $minLength;
});

print_r($filteredStrings);
?>
```

### تمرین 213: محاسبه تعداد روزهای بین دو تاریخ در آرایه

یک آرایه از تاریخ‌ها ایجاد کنید و تعداد روزهای بین دو تاریخ خاص را محاسبه کنید.

```php
<?php
$dates = ['2023-01-01', '2023-12-31'];
$date1 = new DateTime($dates[0]);
$date2 = new DateTime($dates[1]);

$interval = $date1->diff($date2);
echo "Difference: " . $interval->days . " days\n";
?>
```

### تمرین 214: پیدا کردن بزرگترین مقدار در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و بزرگترین مقدار آن را پیدا کنید.

```php
<?php
$assocArray = ['a' => 10, 'b' => 20, 'c' => 15];
$maxValue = max($assocArray);

echo "Max value: $maxValue\n";
?>
```

### تمرین 215: ایجاد آرایه‌ای از مضارب یک عدد خاص

یک آرایه از مضارب یک عدد خاص ایجاد کنید.

```php
<?php
$number = 5;
$count = 10;
$multiples = [];

for ($i = 1; $i <= $count; $i++) {
    $multiples[] = $number * $i;
}

print_r($multiples);
?>
```

### تمرین 216: مرتب‌سازی آرایه چندبعدی بر اساس طول مقادیر

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و آن را بر اساس طول مقادیر مرتب کنید.

```php
<?php
$multiArray = [
    ['fruit' => 'apple'],
    ['fruit' => 'banana'],
    ['fruit' => 'cherry']
];

usort($multiArray, function($a, $b) {
    return strlen($a['fruit']) <=> strlen($b['fruit']);
});

print_r($multiArray);
?>
```

### تمرین 217: ترکیب دو آرایه انجمنی به صورت کلید-مقدار

دو آرایه انجمنی ایجاد کنید و آنها را به صورت کلید-مقدار در یک آرایه جدید ترکیب کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['city' => 'New York', 'country' => 'USA'];

$combinedArray = $array1 + $array2;
print_r($combinedArray);
?>
```

### تمرین 218: جستجوی مقداری خاص در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مقداری خاص را جستجو کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$searchValue = 'Bob';
$found = array_search($searchValue, array_column($people, 'name'));

echo $found !== false ? "Found at index $found" : "Not found"; 

?>
```


### تمرین 219: فیلتر کردن آرایه چندبعدی بر اساس مقدار خاص
یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و بر اساس مقدار خاص فیلتر کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$minAge = 25;
$filteredPeople = array_filter($people, function($person) use ($minAge) {
    return $person['age'] >= $minAge;
});

print_r($filteredPeople);
?>
````

### تمرین 220: مرتب‌سازی آرایه بر اساس طول کلیدها

یک آرایه انجمنی ایجاد کنید و آن را بر اساس طول کلیدها مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
uksort($assocArray, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($assocArray);
?>
```


### تمرین 221: تبدیل آرایه‌ای از مقادیر به آرایه‌ای از کلید-مقدار

یک آرایه از مقادیر ایجاد کنید و آن را به آرایه‌ای از جفت‌های کلید-مقدار تبدیل کنید.

```php
<?php
$values = ['Alice', 25, 'New York'];
$keyValuePairs = [];

for ($i = 0; $i < count($values); $i += 2) {
    $keyValuePairs[$values[$i]] = $values[$i + 1] ?? null;
}

print_r($keyValuePairs);
?>
```

### تمرین 222: مقایسه دو آرایه چندبعدی و پیدا کردن تفاوت‌ها

دو آرایه چندبعدی از اطلاعات افراد ایجاد کنید و تفاوت‌های آنها را پیدا کنید.

```php
<?php
$people1 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];
$people2 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Charlie', 'age' => 30]
];

$differences = array_udiff($people1, $people2, function($a, $b) {
    return $a['name'] <=> $b['name'] ?: $a['age'] <=> $b['age'];
});

print_r($differences);
?>
```

### تمرین 223: حذف عناصر خاص از آرایه

یک آرایه از اعداد ایجاد کنید و مقادیر خاصی را از آن حذف کنید.

```php
<?php
$numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
$toRemove = [3, 6, 9];

$result = array_diff($numbers, $toRemove);
print_r($result);
?>
```

### تمرین 224: جایگزینی مقادیر در آرایه

یک آرایه از رشته‌ها ایجاد کنید و مقادیر خاصی را با مقدار جدید جایگزین کنید.

```php
<?php
$strings = ['apple', 'banana', 'cherry', 'date', 'fig'];
$toReplace = ['banana', 'date'];
$replacement = 'replaced';

$replacedStrings = array_map(function($string) use ($toReplace, $replacement) {
    return in_array($string, $toReplace) ? $replacement : $string;
}, $strings);

print_r($replacedStrings);
?>
```
#in_array #array_map 
### تمرین 225: ادغام دو آرایه و حفظ ترتیب مقادیر

دو آرایه از اعداد ایجاد کنید و آنها را ادغام کنید و ترتیب مقادیر را حفظ کنید.

```php
<?php
$array1 = [1, 3, 5, 7];
$array2 = [2, 4, 6, 8];

$mergedArray = [];
$length = max(count($array1), count($array2));

for ($i = 0; $i < $length; $i++) {
    if (isset($array1[$i])) $mergedArray[] = $array1[$i];
    if (isset($array2[$i])) $mergedArray[] = $array2[$i];
}

print_r($mergedArray);
?>
```

### تمرین 226: ایجاد آرایه‌ای از جفت‌های کلید-مقدار با استفاده از دو آرایه

دو آرایه ایجاد کنید و آنها را به صورت جفت‌های کلید-مقدار در یک آرایه انجمنی ترکیب کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$assocArray = array_combine($keys, $values);
print_r($assocArray);
?>
```

### تمرین 227: ایجاد آرایه‌ای از مقادیر منحصر به فرد از چند آرایه

چند آرایه از اعداد ایجاد کنید و یک آرایه جدید از مقادیر منحصر به فرد ایجاد کنید.

```php
<?php
$array1 = [1, 2, 3, 4];
$array2 = [3, 4, 5, 6];
$array3 = [5, 6, 7, 8];

$mergedArray = array_merge($array1, $array2, $array3);
$uniqueValues = array_unique($mergedArray);

print_r($uniqueValues);
?>
```

### تمرین 228: محاسبه مجموع مقادیر یک کلید خاص در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مجموع مقادیر یک کلید خاص را محاسبه کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$totalAge = array_sum(array_column($people, 'age'));
echo "Total age: $totalAge\n";
?>
```

### تمرین 229: ایجاد آرایه‌ای از حروف کوچک و بزرگ

یک آرایه از حروف الفبای انگلیسی کوچک و بزرگ ایجاد کنید.

```php
<?php
$lowercase = range('a', 'z');
$uppercase = range('A', 'Z');

$alphabetArray = array_merge($lowercase, $uppercase);
print_r($alphabetArray);
?>
```

### تمرین 230: مرتب‌سازی آرایه انجمنی بر اساس طول مقادیر به صورت معکوس

یک آرایه انجمنی ایجاد کنید و آن را بر اساس طول مقادیر به صورت معکوس مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
uasort($assocArray, function($a, $b) {
    return strlen($b) <=> strlen($a);
});

print_r($assocArray);
?>
```

### تمرین 231: ایجاد آرایه‌ای از تاریخ‌های یک سال

یک آرایه از تمامی تاریخ‌های یک سال خاص ایجاد کنید.

```php
<?php
$year = 2023;
$dates = [];

for ($month = 1; $month <= 12; $month++) {
    $daysInMonth = cal_days_in_month(CAL_GREGORIAN, $month, $year);
    for ($day = 1; $day <= $daysInMonth; $day++) {
        $dates[] = "$year-$month-$day";
    }
}

print_r($dates);
?>
```

### تمرین 232: فیلتر کردن آرایه چندبعدی بر اساس شرط خاص

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس شرط خاص فیلتر کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$filteredPeople = array_filter($people, function($person) {
    return $person['age'] > 20;
});

print_r($filteredPeople);
?>
```

### تمرین 233: ایجاد آرایه‌ای از کلیدهای چند سطحی

یک آرایه چندبعدی ایجاد کنید و یک آرایه از تمامی کلیدهای چند سطحی آن ایجاد کنید.

```php
<?php
$array = [
    'level1' => [
        'level2' => [
            'level3' => 'value'
        ]
    ]
];

function array_keys_multi($array, $prefix = '') {
    $keys = [];
    foreach ($array as $key => $value) {
        $new_key = $prefix === '' ? $key : "$prefix.$key";
        if (is_array($value)) {
            $keys = array_merge($keys, array_keys_multi($value, $new_key));
        } else {
            $keys[] = $new_key;
        }
    }
    return $keys;
}

$keys = array_keys_multi($array);
print_r($keys);
?>
```

### تمرین 234: ایجاد آرایه‌ای از مقادیر یکتا از چند آرایه چندبعدی

چند آرایه چندبعدی از اطلاعات افراد ایجاد کنید و یک آرایه جدید از مقادیر یکتا ایجاد کنید.

```php
<?php
$people1 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];
$people2 = [
    ['name' => 'Charlie', 'age' => 30],
    ['name' => 'Bob', 'age' => 20]
];

$merged = array_merge($people1, $people2);
$uniquePeople = array_unique($merged, SORT_REGULAR);

print_r($uniquePeople);
?>
```

### تمرین 235: پیدا کردن آرایه‌های خالی در یک آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و آرایه‌های خالی را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [],
    [4, 5],
    []
];

$emptyArrays = array_filter($multiArray, function($subArray) {
    return empty($subArray);
});

print_r($emptyArrays);
?>
```

### تمرین 236: تبدیل آرایه‌ای از کلیدها و مقادیر به آرایه انجمنی

دو آرایه ایجاد کنید،

یکی شامل کلیدها و دیگری شامل مقادیر، و آنها را به آرایه‌ای انجمنی تبدیل کنید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$assocArray = array_combine($keys, $values);
print_r($assocArray);
?>
```

### تمرین 237: فیلتر کردن آرایه بر اساس طول کلیدها

یک آرایه انجمنی ایجاد کنید و آن را بر اساس طول کلیدها فیلتر کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
$minLength = 5;

$filteredArray = array_filter($assocArray, function($key) use ($minLength) {
    return strlen($key) >= $minLength;
}, ARRAY_FILTER_USE_KEY);

print_r($filteredArray);
?>
```

### تمرین 238: ادغام چند آرایه انجمنی و اولویت دادن به آخرین مقدار

چند آرایه انجمنی ایجاد کنید و آنها را ادغام کنید، به طوری که مقدار آخرین آرایه در صورت تکراری بودن کلیدها نگه داشته شود.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['name' => 'Bob', 'city' => 'New York'];
$array3 = ['name' => 'Charlie', 'country' => 'USA'];

$mergedArray = array_merge($array1, $array2, $array3);
print_r($mergedArray);
?>
```

### تمرین 239: محاسبه تعداد تکرار مقادیر در آرایه چندبعدی

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد تکرار هر مقدار را محاسبه کنید.

```php
<?php
$multiArray = [
    ['apple', 'banana'],
    ['banana', 'cherry'],
    ['cherry', 'date'],
    ['apple', 'date']
];

$flatArray = array_merge(...$multiArray);
$countValues = array_count_values($flatArray);

print_r($countValues);
?>
```

### تمرین 240: جایگزینی کلیدهای یک آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلیدهای آن را با کلیدهای جدید جایگزین کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$keyReplacements = ['name' => 'full_name', 'age' => 'years', 'city' => 'location'];

$replacedKeysArray = [];
foreach ($assocArray as $key => $value) {
    $newKey = $keyReplacements[$key] ?? $key;
    $replacedKeysArray[$newKey] = $value;
}

print_r($replacedKeysArray);
?>
```

### تمرین 241: ایجاد آرایه‌ای از تاریخ‌های یک هفته

یک آرایه از تمامی تاریخ‌های یک هفته خاص ایجاد کنید.

```php
<?php
$year = 2023;
$week = 24; // Week number
$dates = [];

for ($day = 1; $day <= 7; $day++) {
    $dates[] = date('Y-m-d', strtotime($year . "W" . str_pad($week, 2, "0", STR_PAD_LEFT) . $day));
}

print_r($dates);
?>
```

### تمرین 242: پیدا کردن تفاوت‌های بین دو آرایه چندبعدی با استفاده از کلید خاص

دو آرایه چندبعدی از اطلاعات افراد ایجاد کنید و تفاوت‌های آنها را با استفاده از کلید خاص پیدا کنید.

```php
<?php
$people1 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];
$people2 = [
    ['name' => 'Charlie', 'age' => 30],
    ['name' => 'Bob', 'age' => 20]
];

$differences = array_udiff($people1, $people2, function($a, $b) {
    return $a['name'] <=> $b['name'];
});

print_r($differences);
?>
```

### تمرین 243: محاسبه تعداد روزهای بین دو تاریخ در آرایه چندبعدی

یک آرایه چندبعدی از تاریخ‌ها ایجاد کنید و تعداد روزهای بین دو تاریخ خاص را محاسبه کنید.

```php
<?php
$dates = [
    ['start' => '2023-01-01', 'end' => '2023-06-01'],
    ['start' => '2023-07-01', 'end' => '2023-12-31']
];

$intervals = [];
foreach ($dates as $dateRange) {
    $start = new DateTime($dateRange['start']);
    $end = new DateTime($dateRange['end']);
    $interval = $start->diff($end);
    $intervals[] = $interval->days;
}

print_r($intervals);
?>
```

### تمرین 244: ایجاد آرایه‌ای از جفت‌های کلید-مقدار با استفاده از تابع ناشناس

یک آرایه از اعداد ایجاد کنید و آنها را به صورت جفت‌های کلید-مقدار در یک آرایه جدید ترکیب کنید.

```php
<?php
$numbers = range(1, 10);

$keyValuePairs = array_map(function($number) {
    return [$number => $number * 2];
}, $numbers);

print_r($keyValuePairs);
?>
```

### تمرین 245: پیدا کردن کلیدهایی که مقادیر آنها یکتا هستند

یک آرایه انجمنی ایجاد کنید و کلیدهایی که مقادیر آنها یکتا هستند را پیدا کنید.

```php
<?php
$assocArray = ['a' => 10, 'b' => 20, 'c' => 10, 'd' => 30];
$uniqueValues = array_unique($assocArray);
$uniqueKeys = array_keys($uniqueValues);

print_r($uniqueKeys);
?>
```

### تمرین 246: فیلتر کردن آرایه چندبعدی بر اساس چندین شرط

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس چندین شرط فیلتر کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25, 'city' => 'New York'],
    ['name' => 'Bob', 'age' => 20, 'city' => 'Los Angeles'],
    ['name' => 'Charlie', 'age' => 30, 'city' => 'New York']
];

$filteredPeople = array_filter($people, function($person) {
    return $person['age'] > 20 && $person['city'] === 'New York';
});

print_r($filteredPeople);
?>
```

### تمرین 247: ایجاد آرایه‌ای از مضارب یک عدد با استفاده از تابع ناشناس

یک آرایه از مضارب یک عدد خاص ایجاد کنید.

```php
<?php
$number = 5;
$count = 10;

$multiples = array_map(function($index) use ($number) {
    return $number * $index;
}, range(1, $count));

print_r($multiples);
?>
```

### تمرین 248: پیدا کردن کوچکترین مقدار در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و کوچکترین مقدار هر زیرآرایه را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$minValues = array_map('min', $multiArray);
print_r($minValues);
?>
```

### تمرین 249: مرتب‌سازی آرایه انجمنی بر اساس کلیدها به صورت معکوس

یک آرایه انجمنی ایجاد کنید و آن را بر اساس کلیدها به صورت معکوس مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
krsort($assocArray);

print_r($assocArray);
?>
```

### تمرین 250: محاسبه تعداد عناصر منحصر به فرد در آرایه چندبعدی

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد عناصر منحصر به فرد را محاسبه کنید.

```php
<?php
$multiArray = [
    ['apple', 'banana'],
    ['banana', 'cherry'],
    ['cherry', 'date'],
    ['apple', 'date']
];

$flatArray = array_merge(...$multiArray);
$uniqueCount = count(array_unique($flatArray));

echo "Number of unique elements: $uniqueCount\n";
?>
```

### تمرین 251: ایجاد آرایه‌ای از مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آرایه‌ای از مقادیر یک کلید خاص ایجاد کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$names = array_map(function($person) {
    return $person['name'];
}, $people);

print_r($names);
```

?>

````

### تمرین 252: محاسبه مجموع مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس
یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مجموع مقادیر یک کلید خاص را محاسبه کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$totalAge = array_reduce($people, function($carry, $person) {
    return $carry + $person['age'];
}, 0);

echo "Total age: $totalAge\n";
?>
````

### تمرین 253: ایجاد آرایه‌ای از مقادیر منحصر به فرد در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و آرایه‌ای از مقادیر منحصر به فرد در هر زیرآرایه ایجاد کنید.

```php
<?php
$multiArray = [
    [1, 2, 2, 3],
    [4, 4, 5, 6],
    [7, 8, 8, 9]
];

$uniqueValues = array_map('array_unique', $multiArray);
print_r($uniqueValues);
?>
```

### تمرین 254: ایجاد آرایه‌ای از جفت‌های کلید-مقدار با استفاده از کلیدهای چند سطحی

یک آرایه چندبعدی ایجاد کنید و آن را به جفت‌های کلید-مقدار با استفاده از کلیدهای چند سطحی تبدیل کنید.

```php
<?php
$array = [
    'level1' => [
        'level2' => [
            'level3' => 'value'
        ]
    ]
];

function flatten_array($array, $prefix = '') {
    $result = [];
    foreach ($array as $key => $value) {
        $new_key = $prefix === '' ? $key : "$prefix.$key";
        if (is_array($value)) {
            $result = array_merge($result, flatten_array($value, $new_key));
        } else {
            $result[$new_key] = $value;
        }
    }
    return $result;
}

$flattenedArray = flatten_array($array);
print_r($flattenedArray);
?>
```

### تمرین 255: مرتب‌سازی آرایه چندبعدی بر اساس مقدار خاص

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس مقدار خاص مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

usort($people, function($a, $b) {
    return $a['age'] <=> $b['age'];
});

print_r($people);
?>
```

### تمرین 256: محاسبه تعداد کلیدهای منحصر به فرد در آرایه چندبعدی

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد کلیدهای منحصر به فرد را محاسبه کنید.

```php
<?php
$multiArray = [
    ['name' => 'Alice', 'city' => 'New York'],
    ['name' => 'Bob', 'country' => 'USA'],
    ['name' => 'Charlie', 'city' => 'New York']
];

$keys = array_keys(array_merge(...$multiArray));
$uniqueKeys = count(array_unique($keys));

echo "Number of unique keys: $uniqueKeys\n";
?>
```

### تمرین 257: ایجاد آرایه‌ای از حروف بزرگ و کوچک به صورت معکوس

یک آرایه از حروف الفبای انگلیسی کوچک و بزرگ ایجاد کنید و آن را به صورت معکوس مرتب کنید.

```php
<?php
$lowercase = range('a', 'z');
$uppercase = range('A', 'Z');

$alphabetArray = array_merge($lowercase, $uppercase);
rsort($alphabetArray);

print_r($alphabetArray);
?>
```

### تمرین 258: پیدا کردن کلیدهای مشترک در چند آرایه انجمنی

چند آرایه انجمنی ایجاد کنید و کلیدهای مشترک بین آنها را پیدا کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['name' => 'Bob', 'city' => 'New York'];
$array3 = ['name' => 'Charlie', 'country' => 'USA'];

$commonKeys = array_intersect_key($array1, $array2, $array3);
print_r($commonKeys);
?>
```

### تمرین 259: ایجاد آرایه‌ای از توابع ناشناس و اجرای آنها

یک آرایه از توابع ناشناس ایجاد کنید و آنها را اجرا کنید.

```php
<?php
$functions = [
    function() { return 'Hello'; },
    function() { return 'World'; },
    function() { return '!'; }
];

$results = array_map(function($func) {
    return $func();
}, $functions);

print_r($results);
?>
```

### تمرین 260: مرتب‌سازی آرایه چندبعدی بر اساس چندین مقدار

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس چندین مقدار مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25, 'city' => 'New York'],
    ['name' => 'Bob', 'age' => 20, 'city' => 'Los Angeles'],
    ['name' => 'Charlie', 'age' => 25, 'city' => 'Chicago']
];

usort($people, function($a, $b) {
    return [$a['age'], $a['city']] <=> [$b['age'], $b['city']];
});

print_r($people);
?>
```

### تمرین 261: ایجاد آرایه‌ای از کلیدها و مقادیر منحصر به فرد

یک آرایه انجمنی ایجاد کنید و آن را به آرایه‌ای از کلیدها و مقادیر منحصر به فرد تبدیل کنید.

```php
<?php
$assocArray = ['a' => 10, 'b' => 20, 'c' => 10, 'd' => 30];

$uniqueValues = array_unique($assocArray);
$uniqueKeys = array_keys($uniqueValues);

$result = array_combine($uniqueKeys, $uniqueValues);
print_r($result);
?>
```

### تمرین 262: فیلتر کردن آرایه چندبعدی بر اساس شرط‌های چندگانه با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس شرط‌های چندگانه فیلتر کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25, 'city' => 'New York'],
    ['name' => 'Bob', 'age' => 20, 'city' => 'Los Angeles'],
    ['name' => 'Charlie', 'age' => 30, 'city' => 'New York']
];

$filteredPeople = array_filter($people, function($person) {
    return $person['age'] > 20 && $person['city'] === 'New York';
});

print_r($filteredPeople);
?>
```

### تمرین 263: ایجاد آرایه‌ای از مقادیر مربع با استفاده از تابع ناشناس

یک آرایه از اعداد ایجاد کنید و آرایه‌ای از مقادیر مربع آن‌ها ایجاد کنید.

```php
<?php
$numbers = range(1, 10);

$squares = array_map(function($number) {
    return $number ** 2;
}, $numbers);

print_r($squares);
?>
```

### تمرین 264: پیدا کردن بزرگترین مقدار در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و بزرگترین مقدار هر زیرآرایه را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$maxValues = array_map('max', $multiArray);
print_r($maxValues);
?>
```

### تمرین 265: مرتب‌سازی آرایه انجمنی بر اساس مقادیر به صورت معکوس

یک آرایه انجمنی ایجاد کنید و آن را بر اساس مقادیر به صورت معکوس مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
arsort($assocArray);

print_r($assocArray);
?>
```

### تمرین 266: محاسبه تعداد مقادیر منحصر به فرد در آرایه چندبعدی

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد مقادیر منحصر به فرد را محاسبه کنید.

```php
<?php
$multiArray = [
    ['apple', 'banana'],
    ['banana', 'cherry'],
    ['cherry', 'date'],
    ['apple', 'date']
];

$flatArray = array_merge(...$multiArray);
$uniqueCount = count(array_unique($flatArray));

echo "Number of unique elements: $uniqueCount\n";
?>
```

### تمرین 267: ایجاد آرایه‌ای از مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس

یک آرایه چند

بعدی از اطلاعات افراد ایجاد کنید و آرایه‌ای از مقادیر یک کلید خاص ایجاد کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$names = array_map(function($person) {
    return $person['name'];
}, $people);

print_r($names);
?>
```

### تمرین 268: محاسبه مجموع مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مجموع مقادیر یک کلید خاص را محاسبه کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$totalAge = array_reduce($people, function($carry, $person) {
    return $carry + $person['age'];
}, 0);

echo "Total age: $totalAge\n";
?>
```

### تمرین 269: ایجاد آرایه‌ای از مقادیر منحصر به فرد در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و آرایه‌ای از مقادیر منحصر به فرد در هر زیرآرایه ایجاد کنید.

```php
<?php
$multiArray = [
    [1, 2, 2, 3],
    [4, 4, 5, 6],
    [7, 8, 8, 9]
];

$uniqueValues = array_map('array_unique', $multiArray);
print_r($uniqueValues);
?>
```

### تمرین 270: ایجاد آرایه‌ای از جفت‌های کلید-مقدار با استفاده از کلیدهای چند سطحی

یک آرایه چندبعدی ایجاد کنید و آن را به جفت‌های کلید-مقدار با استفاده از کلیدهای چند سطحی تبدیل کنید.

```php
<?php
$array = [
    'level1' => [
        'level2' => [
            'level3' => 'value'
        ]
    ]
];

function flatten_array($array, $prefix = '') {
    $result = [];
    foreach ($array as $key => $value) {
        $new_key = $prefix === '' ? $key : "$prefix.$key";
        if (is_array($value)) {
            $result = array_merge($result, flatten_array($value, $new_key));
        } else {
            $result[$new_key] = $value;
        }
    }
    return $result;
}

$flattenedArray = flatten_array($array);
print_r($flattenedArray);
?>
```

### تمرین 271: مرتب‌سازی آرایه چندبعدی بر اساس مقدار خاص

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس مقدار خاص مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

usort($people, function($a, $b) {
    return $a['age'] <=> $b['age'];
});

print_r($people);
?>
```

### تمرین 272: محاسبه تعداد کلیدهای منحصر به فرد در آرایه چندبعدی

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد کلیدهای منحصر به فرد را محاسبه کنید.

```php
<?php
$multiArray = [
    ['name' => 'Alice', 'city' => 'New York'],
    ['name' => 'Bob', 'country' => 'USA'],
    ['name' => 'Charlie', 'city' => 'New York']
];

$keys = array_keys(array_merge(...$multiArray));
$uniqueKeys = count(array_unique($keys));

echo "Number of unique keys: $uniqueKeys\n";
?>
```

### تمرین 273: ایجاد آرایه‌ای از حروف بزرگ و کوچک به صورت معکوس

یک آرایه از حروف الفبای انگلیسی کوچک و بزرگ ایجاد کنید و آن را به صورت معکوس مرتب کنید.

```php
<?php
$lowercase = range('a', 'z');
$uppercase = range('A', 'Z');

$alphabetArray = array_merge($lowercase, $uppercase);
rsort($alphabetArray);

print_r($alphabetArray);
?>
```

### تمرین 274: پیدا کردن کلیدهای مشترک در چند آرایه انجمنی

چند آرایه انجمنی ایجاد کنید و کلیدهای مشترک بین آنها را پیدا کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['name' => 'Bob', 'city' => 'New York'];
$array3 = ['name' => 'Charlie', 'country' => 'USA'];

$commonKeys = array_intersect_key($array1, $array2, $array3);
print_r($commonKeys);
?>
```

### تمرین 275: ایجاد آرایه‌ای از توابع ناشناس و اجرای آنها

یک آرایه از توابع ناشناس ایجاد کنید و آنها را اجرا کنید.

```php
<?php
$functions = [
    function() { return 'Hello'; },
    function() { return 'World'; },
    function() { return '!'; }
];

$results = array_map(function($func) {
    return $func();
}, $functions);

print_r($results);
?>
```

### تمرین 276: مرتب‌سازی آرایه چندبعدی بر اساس چندین مقدار

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس چندین مقدار مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25, 'city' => 'New York'],
    ['name' => 'Bob', 'age' => 20, 'city' => 'Los Angeles'],
    ['name' => 'Charlie', 'age' => 25, 'city' => 'Chicago']
];

usort($people, function($a, $b) {
    return [$a['age'], $a['city']] <=> [$b['age'], $b['city']];
});

print_r($people);
?>
```

### تمرین 277: ایجاد آرایه‌ای از کلیدها و مقادیر منحصر به فرد

یک آرایه انجمنی ایجاد کنید و آن را به آرایه‌ای از کلیدها و مقادیر منحصر به فرد تبدیل کنید.

```php
<?php
$assocArray = ['a' => 10, 'b' => 20, 'c' => 10, 'd' => 30];

$uniqueValues = array_unique($assocArray);
$uniqueKeys = array_keys($uniqueValues);

$result = array_combine($uniqueKeys, $uniqueValues);
print_r($result);
?>
```

### تمرین 278: فیلتر کردن آرایه چندبعدی بر اساس شرط‌های چندگانه با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس شرط‌های چندگانه فیلتر کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25, 'city' => 'New York'],
    ['name' => 'Bob', 'age' => 20, 'city' => 'Los Angeles'],
    ['name' => 'Charlie', 'age' => 30, 'city' => 'New York']
];

$filteredPeople = array_filter($people, function($person) {
    return $person['age'] > 20 && $person['city'] === 'New York';
});

print_r($filteredPeople);
?>
```

### تمرین 279: ایجاد آرایه‌ای از مقادیر مربع با استفاده از تابع ناشناس

یک آرایه از اعداد ایجاد کنید و آرایه‌ای از مقادیر مربع آن‌ها ایجاد کنید.

```php
<?php
$numbers = range(1, 10);

$squares = array_map(function($number) {
    return $number ** 2;
}, $numbers);

print_r($squares);
?>
```

### تمرین 280: پیدا کردن بزرگترین مقدار در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و بزرگترین مقدار هر زیرآرایه را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$maxValues = array_map('max', $multiArray);
print_r($maxValues);
?>
```

### تمرین 281: مرتب‌سازی آرایه انجمنی بر اساس مقادیر به صورت معکوس

یک آرایه انجمنی ایجاد کنید و آن را بر اساس مقادیر به صورت معکوس مرتب کنید.

```php
<?php
$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
arsort($assocArray);

print_r($assocArray);
?>
```

### تمرین 282: محاسبه تعداد مقادیر منحصر به فرد در آرایه چندبعدی

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد مقادیر منحصر به فرد را محاسبه کنید.

```php
<?php
$multiArray =
```

[ ['apple', 'banana'], ['banana', 'cherry'], ['cherry', 'date'], ['apple', 'date'] ];

$flatArray = array_merge(...$multiArray); $uniqueCount = count(array_unique($flatArray));

echo "Number of unique elements: $uniqueCount\n"; ?>

````

### تمرین 283: ایجاد آرایه‌ای از مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس
یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آرایه‌ای از مقادیر یک کلید خاص ایجاد کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$names = array_map(function($person) {
    return $person['name'];
}, $people);

print_r($names);
?>
````

### تمرین 284: محاسبه مجموع مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مجموع مقادیر یک کلید خاص را محاسبه کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$totalAge = array_reduce($people, function($carry, $person) {
    return $carry + $person['age'];
}, 0);

echo "Total age: $totalAge\n";
?>
```

### تمرین 285: ایجاد آرایه‌ای از مقادیر منحصر به فرد در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و آرایه‌ای از مقادیر منحصر به فرد در هر زیرآرایه ایجاد کنید.

```php
<?php
$multiArray = [
    [1, 2, 2, 3],
    [4, 4, 5, 6],
    [7, 8, 8, 9]
];

$uniqueValues = array_map('array_unique', $multiArray);
print_r($uniqueValues);
?>
```

### تمرین 286: ایجاد آرایه‌ای از جفت‌های کلید-مقدار با استفاده از کلیدهای چند سطحی

یک آرایه چندبعدی ایجاد کنید و آن را به جفت‌های کلید-مقدار با استفاده از کلیدهای چند سطحی تبدیل کنید.

```php
<?php
$array = [
    'level1' => [
        'level2' => [
            'level3' => 'value'
        ]
    ]
];

function flatten_array($array, $prefix = '') {
    $result = [];
    foreach ($array as $key => $value) {
        $new_key = $prefix === '' ? $key : "$prefix.$key";
        if (is_array($value)) {
            $result = array_merge($result, flatten_array($value, $new_key));
        } else {
            $result[$new_key] = $value;
        }
    }
    return $result;
}

$flattenedArray = flatten_array($array);
print_r($flattenedArray);
?>
```

### تمرین 287: مرتب‌سازی آرایه چندبعدی بر اساس مقدار خاص

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس مقدار خاص مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

usort($people, function($a, $b) {
    return $a['age'] <=> $b['age'];
});

print_r($people);
?>
```

### تمرین 288: محاسبه تعداد کلیدهای منحصر به فرد در آرایه چندبعدی

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد کلیدهای منحصر به فرد را محاسبه کنید.

```php
<?php
$multiArray = [
    ['name' => 'Alice', 'city' => 'New York'],
    ['name' => 'Bob', 'country' => 'USA'],
    ['name' => 'Charlie', 'city' => 'New York']
];

$keys = array_keys(array_merge(...$multiArray));
$uniqueKeys = count(array_unique($keys));

echo "Number of unique keys: $uniqueKeys\n";
?>
```

### تمرین 289: ایجاد آرایه‌ای از حروف بزرگ و کوچک به صورت معکوس

یک آرایه از حروف الفبای انگلیسی کوچک و بزرگ ایجاد کنید و آن را به صورت معکوس مرتب کنید.

```php
<?php
$lowercase = range('a', 'z');
$uppercase = range('A', 'Z');

$alphabetArray = array_merge($lowercase, $uppercase);
rsort($alphabetArray);

print_r($alphabetArray);
?>
```

### تمرین 290: پیدا کردن کلیدهای مشترک در چند آرایه انجمنی

چند آرایه انجمنی ایجاد کنید و کلیدهای مشترک بین آنها را پیدا کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['name' => 'Bob', 'city' => 'New York'];
$array3 = ['name' => 'Charlie', 'country' => 'USA'];

$commonKeys = array_intersect_key($array1, $array2, $array3);
print_r($commonKeys);
?>
```

### تمرین 291: ایجاد آرایه‌ای از توابع ناشناس و اجرای آنها

یک آرایه از توابع ناشناس ایجاد کنید و آنها را اجرا کنید.

```php
<?php
$functions = [
    function() { return 'Hello'; },
    function() { return 'World'; },
    function() { return '!'; }
];

$results = array_map(function($func) {
    return $func();
}, $functions);

print_r($results);
?>
```

### تمرین 292: مرتب‌سازی آرایه چندبعدی بر اساس چندین مقدار

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس چندین مقدار مرتب کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25, 'city' => 'New York'],
    ['name' => 'Bob', 'age' => 20, 'city' => 'Los Angeles'],
    ['name' => 'Charlie', 'age' => 25, 'city' => 'Chicago']
];

usort($people, function($a, $b) {
    return [$a['age'], $a['city']] <=> [$b['age'], $b['city']];
});

print_r($people);
?>
```

### تمرین 293: ایجاد آرایه‌ای از کلیدها و مقادیر منحصر به فرد

یک آرایه انجمنی ایجاد کنید و آن را به آرایه‌ای از کلیدها و مقادیر منحصر به فرد تبدیل کنید.

```php
<?php
$assocArray = ['a' => 10, 'b' => 20, 'c' => 10, 'd' => 30];

$uniqueValues = array_unique($assocArray);
$uniqueKeys = array_keys($uniqueValues);

$result = array_combine($uniqueKeys, $uniqueValues);
print_r($result);
?>
```

### تمرین 294: فیلتر کردن آرایه چندبعدی بر اساس شرط‌های چندگانه با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آن را بر اساس شرط‌های چندگانه فیلتر کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25, 'city' => 'New York'],
    ['name' => 'Bob', 'age' => 20, 'city' => 'Los Angeles'],
    ['name' => 'Charlie', 'age' => 30, 'city' => 'New York']
];

$filteredPeople = array_filter($people, function($person) {
    return $person['age'] > 20 && $person['city'] === 'New York';
});

print_r($filteredPeople);
?>
```

### تمرین 295: ایجاد آرایه‌ای از مقادیر مربع با استفاده از تابع ناشناس

یک آرایه از اعداد ایجاد کنید و آرایه‌ای از مقادیر مربع آن‌ها ایجاد کنید.

```php
<?php
$numbers = range(1, 10);

$squares = array_map(function($number) {
    return $number ** 2;
}, $numbers);

print_r($squares);
?>
```

### تمرین 296: پیدا کردن بزرگترین مقدار در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و بزرگترین مقدار هر زیرآرایه را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$maxValues = array_map('max', $multiArray);
print_r($maxValues);
?>
```

### تمرین 297: مرتب‌سازی آرایه انجمنی بر اساس مقادیر به صورت معکوس

یک آرایه انجمنی ایجاد کنید و آن را بر اساس مقادیر به صورت معکوس مرتب کنید.


```php
<?php

$assocArray = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
arsort($assocArray);

print_r($assocArray);
?>

```


### تمرین 298: محاسبه تعداد مقادیر منحصر به فرد در آرایه چندبعدی
یک آرایه چندبعدی از رشته‌ها ایجاد کنید و تعداد مقادیر منحصر به فرد را محاسبه کنید.

```php
<?php
$multiArray = [
    ['apple', 'banana'],
    ['banana', 'cherry'],
    ['cherry', 'date'],
    ['apple', 'date']
];

$flatArray = array_merge(...$multiArray);
$uniqueCount = count(array_unique($flatArray));

echo "Number of unique elements: $uniqueCount\n";
?>
````

### تمرین 299: ایجاد آرایه‌ای از مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و آرایه‌ای از مقادیر یک کلید خاص ایجاد کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$names = array_map(function($person) {
    return $person['name'];
}, $people);

print_r($names);
?>
```

### تمرین 300: محاسبه مجموع مقادیر یک کلید خاص در آرایه چندبعدی با استفاده از تابع ناشناس

یک آرایه چندبعدی از اطلاعات افراد ایجاد کنید و مجموع مقادیر یک کلید خاص را محاسبه کنید.

```php
<?php
$people = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$totalAge = array_reduce($people, function($carry, $person) {
    return $carry + $person['age'];
}, 0);

echo "Total age: $totalAge\n";
?>
```

### تمرین 301: تبدیل آرایه به فرمت JSON

یک آرایه ایجاد کنید و آن را به فرمت JSON تبدیل کنید.

```php
<?php
$array = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$json = json_encode($array);

echo $json;
?>
```

### تمرین 302: پارس کردن JSON به آرایه

یک رشته JSON ایجاد کنید و آن را به آرایه تبدیل کنید.

```php
<?php
$json = '{"name": "Alice", "age": 25, "city": "New York"}';
$array = json_decode($json, true);

print_r($array);
?>
```

### تمرین 303: ادغام چند آرایه انجمنی

چند آرایه انجمنی ایجاد کنید و آنها را ادغام کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['city' => 'New York', 'country' => 'USA'];

$mergedArray = array_merge($array1, $array2);
print_r($mergedArray);
?>
```

### تمرین 304: ایجاد آرایه‌ای از تاریخ‌های روزانه بین دو تاریخ

دو تاریخ شروع و پایان مشخص کنید و آرایه‌ای از تاریخ‌های روزانه بین این دو تاریخ ایجاد کنید.

```php
<?php
$startDate = new DateTime('2023-01-01');
$endDate = new DateTime('2023-01-10');
$interval = new DateInterval('P1D');
$period = new DatePeriod($startDate, $interval, $endDate->modify('+1 day'));

$dates = [];
foreach ($period as $date) {
    $dates[] = $date->format('Y-m-d');
}

print_r($dates);
?>
```

### تمرین 305: شمارش تکرار مقادیر در آرایه

یک آرایه از اعداد ایجاد کنید و تعداد تکرار هر مقدار را شمارش کنید.

```php
<?php
$array = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4];
$counts = array_count_values($array);

print_r($counts);
?>
```

### تمرین 306: فیلتر کردن آرایه بر اساس مقادیر کلیدی

یک آرایه انجمنی ایجاد کنید و آن را بر اساس مقادیر کلیدی خاص فیلتر کنید.

```php
<?php
$array = ['name' => 'Alice', 'age' => 25, 'city' => 'New York', 'country' => 'USA'];
$keysToKeep = ['name', 'city'];

$filteredArray = array_filter($array, function($key) use ($keysToKeep) {
    return in_array($key, $keysToKeep);
}, ARRAY_FILTER_USE_KEY);

print_r($filteredArray);
?>
```
#array_filter #array_filter 
### تمرین 307: جابجایی کلید و مقدار در آرایه انجمنی

یک آرایه انجمنی ایجاد کنید و کلید و مقدار آن را جابجا کنید.

```php
<?php
$array = ['name' => 'Alice', 'city' => 'New York', 'country' => 'USA'];
$flippedArray = array_flip($array);

print_r($flippedArray);
?>
```

### تمرین 308: حذف عناصر تکراری از آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و عناصر تکراری را حذف کنید.

```php
<?php
$multiArray = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Alice', 'age' => 25]
];

$uniqueArray = array_map('unserialize', array_unique(array_map('serialize', $multiArray)));
print_r($uniqueArray);
?>
```

### تمرین 309: ادغام آرایه‌ها با استفاده از کلیدهای مشترک

چند آرایه انجمنی ایجاد کنید و آنها را بر اساس کلیدهای مشترک ادغام کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['name' => 'Bob', 'age' => 20];
$array3 = ['name' => 'Charlie', 'age' => 30];

$mergedArray = [];
foreach ([$array1, $array2, $array3] as $array) {
    foreach ($array as $key => $value) {
        $mergedArray[$key][] = $value;
    }
}

print_r($mergedArray);
?>
```

### تمرین 310: پیدا کردن کلیدهای مختلف بین دو آرایه انجمنی

دو آرایه انجمنی ایجاد کنید و کلیدهای مختلف بین آنها را پیدا کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$array2 = ['name' => 'Bob', 'country' => 'USA'];

$differentKeys = array_diff_key($array1, $array2);
print_r($differentKeys);
?>
```

### تمرین 311: ایجاد آرایه‌ای از کلیدهای منحصر به فرد از چند آرایه انجمنی

چند آرایه انجمنی ایجاد کنید و آرایه‌ای از کلیدهای منحصر به فرد ایجاد کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25];
$array2 = ['name' => 'Bob', 'city' => 'New York'];
$array3 = ['name' => 'Charlie', 'country' => 'USA'];

$uniqueKeys = array_unique(array_merge(array_keys($array1), array_keys($array2), array_keys($array3)));
print_r($uniqueKeys);
?>
```

### تمرین 312: مرتب‌سازی آرایه چندبعدی بر اساس طول رشته‌ها

یک آرایه چندبعدی از رشته‌ها ایجاد کنید و آن را بر اساس طول رشته‌ها مرتب کنید.

```php
<?php
$array = [
    ['word' => 'apple'],
    ['word' => 'banana'],
    ['word' => 'cherry']
];

usort($array, function($a, $b) {
    return strlen($a['word']) <=> strlen($b['word']);
});

print_r($array);
?>
```

### تمرین 313: ایجاد آرایه‌ای از مقادیر بدون مقدار null

یک آرایه ایجاد کنید و تمامی عناصر null را حذف کنید.

```php
<?php
$array = [1, null, 2, null, 3, null, 4];

$filteredArray = array_filter($array, function($value) {
    return !is_null($value);
});

print_r($filteredArray);
?>
```

### تمرین 314: پیدا کردن کوچکترین و بزرگترین مقدار در هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و کوچکترین و بزرگترین مقدار هر زیرآرایه را پیدا کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$minValues = array_map('min', $multiArray);
$maxValues = array_map('max', $multiArray);

echo "Min values: ";
print_r($minValues);
echo "Max values: ";
print_r($maxValues);
?>
```

### تمرین 315: فیلتر کردن آرایه بر اساس نوع داده

یک آرایه ایجاد کنید و آن را بر اساس نوع داده فیلتر کنید.

```php
<?php
$array = [1, 'apple', 2, 'banana', 3, 'cherry', 4];

$strings = array_filter($array, 'is_string');
$numbers = array_filter($array, 'is_int');

echo "Strings: ";
print_r($strings);
echo "Numbers: ";
print_r($numbers);
?>
```

### تمرین 316: ایجاد آرایه‌ای از مجموع مقادیر هر زیرآرایه

یک آرایه چندبعدی از اعداد ایجاد کنید و مجموع مقادیر هر زیرآرایه را محاسبه کنید.

```php
<?php
$multiArray = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$sums = array_map(function($array) {
    return array_sum($array);
}, $multiArray);

print_r($sums);
?>
```

### تمرین 317: پیدا کردن موقعیت اولین مقدار غیر تکراری در آرایه

یک آرایه از اعداد ایجاد کنید و موقعیت اولین مقدار غیر تکراری را پیدا کنید.

```php
<?php
$array = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 5];
$countValues = array_count_values($array);

foreach ($array as $index => $value) {
    if ($countValues[$value] === 1) {
        echo "First unique value: $value at index $index\n";
        break;
    }
}
?>
```

### تمرین 318: تبدیل آرایه به رشته با جداکننده خاص

یک آرایه از رشته‌ها ایجاد کنید و آن را به یک رشته با جداکننده خاص تبدیل کنید.

```php
<?php
$array = ['apple', 'banana', 'cherry'];
$delimiter = ', ';

$string = implode($delimiter, $array);
echo $string;
?>
```

### تمرین 319: تقسیم رشته به آرایه با جداکننده

خاص یک رشته ایجاد کنید و آن را با استفاده از جداکننده خاص به آرایه تبدیل کنید.

```php
<?php
$string = 'apple, banana, cherry';
$delimiter = ', ';

$array = explode($delimiter, $string);
print_r($array);
?>
```

### تمرین 320: ادغام آرایه‌ها و حذف عناصر تکراری

چند آرایه ایجاد کنید و آنها را ادغام کرده و عناصر تکراری را حذف کنید.

```php
<?php
$array1 = [1, 2, 3];
$array2 = [3, 4, 5];
$array3 = [5, 6, 7];

$mergedArray = array_unique(array_merge($array1, $array2, $array3));
print_r($mergedArray);
?>
```

### تمرین 321: پیدا کردن عناصر مشترک بین چند آرایه

چند آرایه ایجاد کنید و عناصر مشترک بین آنها را پیدا کنید.

```php
<?php
$array1 = [1, 2, 3, 4];
$array2 = [3, 4, 5, 6];
$array3 = [4, 5, 6, 7];

$commonElements = array_intersect($array1, $array2, $array3);
print_r($commonElements);
?>
```

### تمرین 322: ایجاد آرایه‌ای از اعداد فرد

یک آرایه از اعداد ۱ تا ۲۰ ایجاد کنید و فقط اعداد فرد را نگه دارید.

```php
<?php
$numbers = range(1, 20);
$oddNumbers = array_filter($numbers, function($number) {
    return $number % 2 !== 0;
});

print_r($oddNumbers);
?>
```

### تمرین 323: ایجاد آرایه‌ای از اعداد زوج

یک آرایه از اعداد ۱ تا ۲۰ ایجاد کنید و فقط اعداد زوج را نگه دارید.

```php
<?php
$numbers = range(1, 20);
$evenNumbers = array_filter($numbers, function($number) {
    return $number % 2 === 0;
});

print_r($evenNumbers);
?>
```

### تمرین 324: پیدا کردن عنصر تکراری در آرایه

یک آرایه از اعداد ایجاد کنید و اولین عنصر تکراری را پیدا کنید.

```php
<?php
$array = [1, 2, 3, 4, 3, 5, 6];
$seen = [];

foreach ($array as $value) {
    if (in_array($value, $seen)) {
        echo "First duplicate value: $value\n";
        break;
    }
    $seen[] = $value;
}
?>
```
#in_array
### تمرین 325: ایجاد آرایه‌ای از اعداد اول

یک تابع برای پیدا کردن اعداد اول بنویسید و آرایه‌ای از اعداد اول کمتر از ۵۰ ایجاد کنید.

```php
<?php
function is_prime($number) {
    if ($number <= 1) return false;
    for ($i = 2; $i <= sqrt($number); $i++) {
        if ($number % $i === 0) return false;
    }
    return true;
}

$primes = array_filter(range(1, 50), 'is_prime');
print_r($primes);
?>
```

### تمرین 326: ایجاد آرایه‌ای از مقادیر فاکتوریل

یک تابع برای محاسبه فاکتوریل بنویسید و آرایه‌ای از فاکتوریل اعداد ۱ تا ۱۰ ایجاد کنید.

```php
<?php
function factorial($number) {
    return $number === 0 ? 1 : $number * factorial($number - 1);
}

$factorials = array_map('factorial', range(1, 10));
print_r($factorials);
?>
```

### تمرین 327: محاسبه تعداد کلمات در آرایه‌ای از جملات

یک آرایه از جملات ایجاد کنید و تعداد کلمات هر جمله را محاسبه کنید.

```php
<?php
$sentences = ['Hello world', 'PHP is awesome', 'Array manipulation is fun'];

$wordCounts = array_map(function($sentence) {
    return str_word_count($sentence);
}, $sentences);

print_r($wordCounts);
?>
```

### تمرین 328: فیلتر کردن آرایه بر اساس طول رشته‌ها

یک آرایه از رشته‌ها ایجاد کنید و فقط رشته‌هایی که طول آنها بیشتر از ۵ کاراکتر است را نگه دارید.

```php
<?php
$array = ['apple', 'banana', 'cherry', 'fig'];

$longStrings = array_filter($array, function($string) {
    return strlen($string) > 5;
});

print_r($longStrings);
?>
```

### تمرین 329: ایجاد آرایه‌ای از عناصر تصادفی

یک آرایه با ۱۰ عنصر تصادفی بین ۱ تا ۱۰۰ ایجاد کنید.

```php
<?php
$array = array_map(function() {
    return rand(1, 100);
}, range(1, 10));

print_r($array);
?>
```

### تمرین 330: ایجاد آرایه‌ای از توابع ناشناس و اجرای آنها با ورودی

یک آرایه از توابع ناشناس ایجاد کنید که هرکدام ورودی بگیرند و نتیجه را بازگردانند.

```php
<?php
$functions = [
    function($x) { return $x * 2; },
    function($x) { return $x + 3; },
    function($x) { return $x / 2; }
];

$input = 10;
$results = array_map(function($func) use ($input) {
    return $func($input);
}, $functions);

print_r($results);
?>
```

### تمرین 331: ایجاد آرایه‌ای از مقادیر تکراری با استفاده از کلیدهای مشترک

چند آرایه انجمنی ایجاد کنید و مقادیر تکراری با استفاده از کلیدهای مشترک را پیدا کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$array2 = ['name' => 'Bob', 'age' => 25, 'city' => 'Los Angeles'];
$array3 = ['name' => 'Charlie', 'age' => 30, 'city' => 'New York'];

$commonValues = array_intersect_assoc($array1, $array2, $array3);
print_r($commonValues);
?>
```

### تمرین 332: پیدا کردن کلیدهای منحصر به فرد بین دو آرایه انجمنی

دو آرایه انجمنی ایجاد کنید و کلیدهای منحصر به فرد بین آنها را پیدا کنید.

```php
<?php
$array1 = ['name' => 'Alice', 'age' => 25, 'city' => 'New York'];
$array2 = ['name' => 'Bob', 'country' => 'USA'];

$uniqueKeys = array_merge(array_diff_key($array1, $array2), array_diff_key($array2, $array1));
print_r($uniqueKeys);
?>
```
#array_merge #array_diff_key 
### تمرین 333: ایجاد آرایه‌ای از اعداد فیبوناچی

یک تابع برای تولید اعداد فیبوناچی بنویسید و آرایه‌ای از ۱۰ عدد اول فیبوناچی ایجاد کنید.

```php
<?php
function fibonacci($n) {
    $fib = [0, 1];
    for ($i = 2; $i < $n; $i++) {
        $fib[] = $fib[$i - 1] + $fib[$i - 2];
    }
    return $fib;
}

$fibArray = fibonacci(10);
print_r($fibArray);
?>
```

### تمرین 334: مرتب‌سازی آرایه انجمنی بر اساس طول رشته‌ها

یک آرایه انجمنی از رشته‌ها ایجاد کنید و آن را بر اساس طول رشته‌ها مرتب کنید.

```php
<?php
$array = ['a' => 'apple', 'b' => 'banana', 'c' => 'cherry'];

uasort($array, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($array);
?>
```
#uasort #strlen 
### تمرین 335: پیدا کردن عناصر غیر تکراری بین چند آرایه

چند آرایه ایجاد کنید و عناصر غیر تکراری بین آنها را پیدا کنید.

```php
<?php
$array1 = [1, 2, 3, 4];
$array2 = [3, 4, 5, 6];
$array3 = [4, 5, 6, 7];

$uniqueElements = array_diff(array_merge($array1, $array2, $array3), array_intersect($array1, $array2, $array3));
print_r($uniqueElements);
?>
```
#array_diff #array_merge #array_intersect 
### تمرین 336: ایجاد آرایه‌ای از مقادیر کلیدهای خاص در آرایه چندبعدی

یک آرایه چندبعدی از اطلاعات ایجاد کنید و آرایه‌ای از مقادیر کلیدهای خاص ایجاد کنید.

```php
<?php
$array = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

$names = array_column($array, 'name');
print_r($names);
?>
```
#array_column 
### تمرین 337: پیدا کردن تفاوت بین دو آرایه چندبعدی

دو آرایه چندبعدی ایجاد

کنید و تفاوت بین آنها را پیدا کنید.

```php
<?php
$array1 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20]
];
$array2 = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Charlie', 'age' => 30]
];

$diff = array_udiff($array1, $array2, function($a, $b) {
    return $a['name'] <=> $b['name'];
});

print_r($diff);
?>
```
#array_udiff
### تمرین 338: مرتب‌سازی آرایه بر اساس مقادیر کلید خاص

یک آرایه چندبعدی از اطلاعات ایجاد کنید و آن را بر اساس مقادیر یک کلید خاص مرتب کنید.

```php
<?php
$array = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 20],
    ['name' => 'Charlie', 'age' => 30]
];

usort($array, function($a, $b) {
    return $a['age'] <=> $b['age'];
});

print_r($array);
?>
```
#usort 
### تمرین 339: ایجاد آرایه‌ای از زوج‌های مرتب

دو آرایه ایجاد کنید و آرایه‌ای از زوج‌های مرتب از آنها بسازید.

```php
<?php
$array1 = ['a', 'b', 'c'];
$array2 = [1, 2, 3];

$pairs = array_map(null, $array1, $array2);
print_r($pairs);
?>
```
#array_map 
### تمرین 340: محاسبه میانگین مقادیر در آرایه

یک آرایه از اعداد ایجاد کنید و میانگین مقادیر آن را محاسبه کنید.

```php
<?php
$array = [1, 2, 3, 4, 5];

$average = array_sum($array) / count($array);
echo "Average: $average\n";
?>
```
#array_sum #count 
### تمرین 341: معکوس کردن آرایه چندبعدی

یک آرایه چندبعدی ایجاد کنید و ترتیب عناصر هر زیرآرایه را معکوس کنید.

```php
<?php
$array = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

$reversedArray = array_map('array_reverse', $array);
print_r($reversedArray);
?>
```
#array_map
### تمرین 342: ایجاد آرایه‌ای از مقادیر با استفاده از تابع خاص

یک تابع ایجاد کنید که یک مقدار را بگیرد و یک آرایه با استفاده از آن تابع بسازید.

```php
<?php
function square($x) {
    return $x * $x;
}

$array = range(1, 10);
$squaredArray = array_map('square', $array);

print_r($squaredArray);
?>
```
#range #array_map
### تمرین 343: محاسبه مجموع طول رشته‌ها در آرایه

یک آرایه از رشته‌ها ایجاد کنید و مجموع طول همه رشته‌ها را محاسبه کنید.

```php
<?php
$array = ['apple', 'banana', 'cherry'];

$totalLength = array_reduce($array, function($carry, $item) {
    return $carry + strlen($item);
}, 0);

echo "Total length: $totalLength\n";
?>
```
#array_reduce #strlen 
### تمرین 344: ایجاد آرایه‌ای از اعداد تصادفی بدون تکرار

یک آرایه با ۱۰ عدد تصادفی بدون تکرار بین ۱ تا ۱۰۰ ایجاد کنید.

```php
<?php
$array = [];
while (count($array) < 10) {
    $random = rand(1, 100);
    if (!in_array($random, $array)) {
        $array[] = $random;
    }
}

print_r($array);
?>
```
#count #in_array #rand 
### تمرین 345: ادغام آرایه‌ها و مرتب‌سازی بر اساس طول رشته‌ها

چند آرایه از رشته‌ها ایجاد کنید و آنها را ادغام کرده و بر اساس طول رشته‌ها مرتب کنید.

```php
<?php
$array1 = ['apple', 'banana'];
$array2 = ['cherry', 'date'];
$array3 = ['fig', 'grape'];

$mergedArray = array_merge($array1, $array2, $array3);

usort($mergedArray, function($a, $b) {
    return strlen($a) <=> strlen($b);
});

print_r($mergedArray);
?>
```
#array_merge #usort #strlen 
### تمرین 346: ایجاد آرایه‌ای از مقادیر تصادفی در محدوده خاص

یک آرایه با ۱۰ عدد تصادفی در محدوده ۵۰ تا ۱۰۰ ایجاد کنید.

```php
<?php
$array = array_map(function() {
    return rand(50, 100);
}, range(1, 10));

print_r($array);
?>
```
#array_map #rand #range 

### تمرین 347: پیدا کردن اولین مقدار بزرگتر از مقدار خاص در آرایه

یک آرایه از اعداد ایجاد کنید و اولین مقداری که بزرگتر از مقدار خاصی است را پیدا کنید.

```php
<?php
$array = [1, 3, 5, 7, 9, 11, 13];
$threshold = 8;

$firstGreater = null;
foreach ($array as $value) {
    if ($value > $threshold) {
        $firstGreater = $value;
        break;
    }
}

if ($firstGreater !== null) {
    echo "First value greater than $threshold: $firstGreater\n";
} else {
    echo "No value greater than $threshold found.\n";
}
?>
```

### تمرین 348: ایجاد آرایه‌ای از جفت‌های کلید و مقدار با استفاده از آرایه‌ها

دو آرایه از کلیدها و مقادیر ایجاد کنید و یک آرایه انجمنی از آنها بسازید.

```php
<?php
$keys = ['name', 'age', 'city'];
$values = ['Alice', 25, 'New York'];

$assocArray = array_combine($keys, $values);
print_r($assocArray);
?>
```
#array_combine
### تمرین 349: حذف عناصر خالی از آرایه

یک آرایه ایجاد کنید و تمامی عناصر خالی (null، رشته خالی، صفر و ...) را حذف کنید.

```php
<?php
$array = [1, null, '', 0, 'apple', false, 'banana'];

$filteredArray = array_filter($array, function($value) {
    return !empty($value);
});

print_r($filteredArray);
?>
```
#array_filter
### تمرین 350: ایجاد آرایه‌ای از شاخص‌ها بر اساس شرط خاص

یک آرایه از اعداد ایجاد کنید و شاخص‌های مقادیری که بزرگتر از مقدار خاصی هستند را پیدا کنید.

```php
<?php
$array = [1, 3, 5, 7, 9, 11, 13];
$threshold = 8;

$indexes = array_keys(array_filter($array, function($value) use ($threshold) {
    return $value > $threshold;
}));

print_r($indexes);
?>
```
#array_keys #array_filter 
