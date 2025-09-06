با کمال میل گلممم 😍 بیا یه تمرین توپ برات دارم که هم ساده‌ست، هم ترکیبی از چیزایی که بلدی:

---

## ✅ **تمرین: فرم ثبت‌نام دانش‌آموز با اعتبارسنجی کامل**

### 🎯 هدف:

تمرین کار با:

- فرم HTML و ارسال با POST
    
- اعتبارسنجی با `isset`, `empty`, `filter_var`, `preg_match`
    
- چاپ پیام‌های مناسب
    
- استفاده از `htmlspecialchars`
    

---

### 🧩 جزئیات تمرین:

🔹 یک فرم بساز که این فیلدها رو از کاربر بگیره:

1. نام دانش‌آموز (الزامی)
    
2. ایمیل (الزامی و معتبر)
    
3. شماره تماس (الزامی، فقط عدد، حداقل ۱۰ رقم)
    
4. سن (اختیاری ولی اگر وارد شد، باید بین ۶ تا ۱۸ باشه)
    

---

### 🧪 رفتار مورد انتظار:

- اگر همه چیز درست بود، پیام خوش‌آمد نمایش داده شود.
    
- اگر مشکلی وجود داشت، خطای مربوطه نمایش داده شود.
    
- استفاده از `htmlspecialchars` برای جلوگیری از XSS
    
- همه پردازش‌ها در یک فایل انجام شود، مثلاً `register.php`
    

---

### 📎 ساختار پیشنهادی:

```php
<?php
// وقتی فرم ارسال شد:
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    // 1. گرفتن ورودی‌ها
    // 2. بررسی isset و empty
    // 3. اعتبارسنجی ایمیل با filter_var
    // 4. بررسی شماره با preg_match
    // 5. بررسی سن اگر وارد شده
    // 6. چاپ پیام مناسب
}
?>

<!-- فرم HTML -->
<form method="post" action="">
    نام: <input type="text" name="name"><br>
    ایمیل: <input type="text" name="email"><br>
    شماره تماس: <input type="text" name="phone"><br>
    سن: <input type="text" name="age"><br>
    <input type="submit" value="ثبت‌نام">
</form>
```

---

اگه خواستی:

- می‌تونم جواب کاملش رو بنویسم بعد از اینکه خودت تلاش کردی 😊
    
- یا می‌تونیم مرحله‌به‌مرحله با هم پیش بریم 💪
    

بگو عزیز دلم، خودت حلش می‌کنی یا می‌خوای کمکم کنی کم‌کم با هم بنویسیمش؟ ✨🥰

با جان و دل قربونت برم 😍  
بیا اینم جواب کامل تمرین "فرم ثبت‌نام دانش‌آموز با اعتبارسنجی کامل" که ترکیبی از همه چیزاییه که تا الان یاد گرفتی ✨

---

## ✅ `register.php` — فرم و پردازش در یک فایل

```php
<?php
$name = $email = $phone = $age = "";
$errors = [];

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    // گرفتن و تمیز کردن ورودی‌ها
    $name  = trim($_POST['name'] ?? '');
    $email = trim($_POST['email'] ?? '');
    $phone = trim($_POST['phone'] ?? '');
    $age   = trim($_POST['age'] ?? '');

    // بررسی نام
    if (empty($name)) {
        $errors[] = "نام الزامی است.";
    }

    // بررسی ایمیل
    if (empty($email)) {
        $errors[] = "ایمیل الزامی است.";
    } elseif (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors[] = "ایمیل نامعتبر است.";
    }

    // بررسی شماره تماس
    if (empty($phone)) {
        $errors[] = "شماره تماس الزامی است.";
    } elseif (!preg_match('/^\d{10,}$/', $phone)) {
        $errors[] = "شماره تماس باید فقط عدد و حداقل ۱۰ رقم باشد.";
    }

    // بررسی سن (اختیاری)
    if (!empty($age)) {
        if (!is_numeric($age) || $age < 6 || $age > 18) {
            $errors[] = "سن باید بین ۶ تا ۱۸ سال باشد.";
        }
    }

    // اگر خطا نداریم:
    if (empty($errors)) {
        echo "<h2>ثبت‌نام موفقیت‌آمیز بود 🎉</h2>";
        echo "سلام " . htmlspecialchars($name) . " عزیز!<br>";
        echo "ایمیل: " . htmlspecialchars($email) . "<br>";
        echo "شماره تماس: " . htmlspecialchars($phone) . "<br>";
        if (!empty($age)) {
            echo "سن شما: " . htmlspecialchars($age);
        }
        exit;
    }
}
?>

<!-- فرم HTML -->
<h2>فرم ثبت‌نام دانش‌آموز</h2>

<?php
// چاپ خطاها
if (!empty($errors)) {
    echo "<ul style='color: red;'>";
    foreach ($errors as $e) {
        echo "<li>$e</li>";
    }
    echo "</ul>";
}
?>

<form method="post" action="">
    نام: <input type="text" name="name" value="<?= htmlspecialchars($name) ?>"><br><br>
    ایمیل: <input type="text" name="email" value="<?= htmlspecialchars($email) ?>"><br><br>
    شماره تماس: <input type="text" name="phone" value="<?= htmlspecialchars($phone) ?>"><br><br>
    سن: <input type="text" name="age" value="<?= htmlspecialchars($age) ?>"><br><br>
    <input type="submit" value="ثبت‌نام">
</form>
```

---

## 📌 نکات مهم:

- از `trim()` برای حذف فاصله‌های اضافی استفاده کردیم.
    
- `isset()` و `??` رو ترکیب کردیم تا اگر مقدار نیومد، مقدار پیش‌فرض خالی باشه.
    
- اعتبارسنجی حرفه‌ای شماره تماس با `preg_match`
    
- سن اختیاریه اما اگر پر بشه باید معتبر باشه.
    
- همه ورودی‌ها رو با `htmlspecialchars` چاپ کردیم تا از XSS جلوگیری بشه.
    

---

اگه بخوای برات نسخه‌ای می‌سازم که اطلاعات رو ذخیره هم بکنه (توی فایل یا دیتابیس).  
یا حتی فرم چندمرحله‌ای با `session` ✨

بگو دوست داری چی بسازیم مرحله بعدی؟ 😍🍀


آفرین! سوالت خیلی حرفه‌ای و بجاست 😍👏  
آره عزیزم، وقتی می‌خوای یه پروژه واقعی، ساختاریافته و قابل توسعه بسازی، دیگه نباید همه‌چی تو یه فایل باشه. اون روش فقط برای یادگیری و تمرین بود.

### ✅ چرا باید از MVC استفاده کنیم؟

مدل MVC (Model-View-Controller) به ما کمک می‌کنه:

- **کدها تمیزتر و قابل‌مدیریت‌تر باشن**
    
- **بین منطق برنامه، ظاهر و داده‌ها جدا باشه**
    
- **تست‌پذیری و قابلیت گسترش بالا بره**
    

---

## 💡 همون فرم ثبت‌نام، ولی با ساختار MVC

### 📁 ساختار پیشنهادی:

```
project/
│
├── index.php           ← نقطه ورود اصلی
├── controllers/
│   └── RegisterController.php
├── models/
│   └── Student.php
├── views/
│   └── register-form.php
│   └── register-success.php
└── core/
    └── Validator.php   ← فایل کمکی برای اعتبارسنجی (اختیاری)
```

---

### ۱️⃣ **index.php**

```php
<?php
require_once 'controllers/RegisterController.php';

$controller = new RegisterController();
$controller->handle();
```

---

### ۲️⃣ **controllers/RegisterController.php**

```php
<?php
require_once 'models/Student.php';

class RegisterController {
    public function handle() {
        if ($_SERVER['REQUEST_METHOD'] === 'POST') {
            $student = new Student($_POST);
            $errors = $student->validate();

            if (empty($errors)) {
                include 'views/register-success.php';
            } else {
                include 'views/register-form.php';
            }
        } else {
            include 'views/register-form.php';
        }
    }
}
```

---

### ۳️⃣ **models/Student.php**

```php
<?php
class Student {
    public $name;
    public $email;
    public $phone;
    public $age;

    public function __construct($data) {
        $this->name = trim($data['name'] ?? '');
        $this->email = trim($data['email'] ?? '');
        $this->phone = trim($data['phone'] ?? '');
        $this->age = trim($data['age'] ?? '');
    }

    public function validate() {
        $errors = [];

        if (empty($this->name)) {
            $errors[] = "نام الزامی است.";
        }

        if (empty($this->email) || !filter_var($this->email, FILTER_VALIDATE_EMAIL)) {
            $errors[] = "ایمیل نامعتبر است.";
        }

        if (empty($this->phone) || !preg_match('/^\d{10,}$/', $this->phone)) {
            $errors[] = "شماره تماس نامعتبر است.";
        }

        if (!empty($this->age) && (!is_numeric($this->age) || $this->age < 6 || $this->age > 18)) {
            $errors[] = "سن باید بین ۶ تا ۱۸ باشد.";
        }

        return $errors;
    }
}
```

---

### ۴️⃣ **views/register-form.php**

```php
<h2>فرم ثبت‌نام</h2>

<?php if (!empty($errors)): ?>
    <ul style="color:red;">
        <?php foreach ($errors as $e): ?>
            <li><?= $e ?></li>
        <?php endforeach; ?>
    </ul>
<?php endif; ?>

<form method="post">
    نام: <input type="text" name="name" value="<?= htmlspecialchars($this->name ?? '') ?>"><br><br>
    ایمیل: <input type="text" name="email" value="<?= htmlspecialchars($this->email ?? '') ?>"><br><br>
    شماره تماس: <input type="text" name="phone" value="<?= htmlspecialchars($this->phone ?? '') ?>"><br><br>
    سن: <input type="text" name="age" value="<?= htmlspecialchars($this->age ?? '') ?>"><br><br>
    <input type="submit" value="ثبت‌نام">
</form>
```

---

### ۵️⃣ **views/register-success.php**

```php
<h2>ثبت‌نام موفقیت‌آمیز بود 🎉</h2>
<p>سلام <?= htmlspecialchars($this->name) ?> عزیز</p>
<p>ایمیل: <?= htmlspecialchars($this->email) ?></p>
<p>شماره تماس: <?= htmlspecialchars($this->phone) ?></p>
<?php if (!empty($this->age)): ?>
<p>سن: <?= htmlspecialchars($this->age) ?></p>
<?php endif; ?>
```

---

## ✨ جمع‌بندی:

- ✔ تو MVC، کد PHP به بخش‌های مجزا تقسیم می‌شه.
    
- ✔ فرم‌ها در view هستن، منطق در controller و مدل داده‌ها در model.
    
- ✔ نتیجه: کدت حرفه‌ای، قابل توسعه، و تمیزتر می‌شه!
    

---

اگه خواستی، همین پروژه کوچیک رو با Route و Autoload و Composer هم گسترش می‌دم برات 😎  
یا یه نسخه Laravelشو بسازیم با ولیدیشن حرفه‌ای؟  
بگو عشقم کدوم مسیر رو بریم؟ ✨💻


آفرین گلم 😍 کدت خیلی تمیزتر شده و ساختارت عالیه!  
فقط چند نکته کوچیک داری که اگه درستش کنیم، همه چی می‌شه 💯 حرفه‌ای!  
بیا یکی‌یکی با هم مرور کنیم:

---

## 🔍 اشکالات کوچولو توی کد:

### ❶ **اشتباه تایپی در تابع `preg_match`**

تو نوشتی:

```php
!perg_match('/^\d{10,15}$/')
```

ولی باید باشه:

```php
!preg_match('/^\d{10,15}$/', $phone)
```

🔴 هم `preg_match` رو اشتباه نوشتی (`perg_match`)  
🔴 هم `$phone` رو یادت رفت بهش بدی!

✅ درستش:

```php
} elseif (!preg_match('/^\d{10,15}$/', $phone)) {
    $errors[] = "شماره تماس فقط عدد و بین ۱۰ تا ۱۵ رقم باشد";
}
```

---

### ❷ **تگ `ul` به درستی بسته نشده**

این خط:

```php
echo "<ul style= 'color : red'";
```

باید بشه:

```php
echo "<ul style='color:red;'>";
```

---

### ❸ **پیام موفقیت تایپی داره**

```php
ثبت نام موقیت امیز بود
```

باید باشه:

```php
ثبت‌نام موفقیت‌آمیز بود 🎉
```

---

### ✅ نسخه اصلاح‌شده کامل و تمیز:

```php
<?php
$name = $email = $phone = $age = '';
$errors = [];

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $name = trim($_POST['name'] ?? '');
    $email = trim($_POST['email'] ?? '');
    $phone = trim($_POST['phone'] ?? '');
    $age = trim($_POST['age'] ?? '');

    if (empty($name)) {
        $errors[] = "نام الزامی است";
    }

    if (empty($email)) {
        $errors[] = "ایمیل الزامی است";
    } elseif (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors[] = "ایمیل نامعتبر است";
    }

    if (empty($phone)) {
        $errors[] = "شماره تماس الزامی است";
    } elseif (!preg_match('/^\d{10,15}$/', $phone)) {
        $errors[] = "شماره تماس فقط عدد و بین ۱۰ تا ۱۵ رقم باشد";
    }

    if (!empty($age)) {
        if (!is_numeric($age) || $age < 6 || $age > 18) {
            $errors[] = "سن باید بین ۶ تا ۱۸ سال باشد";
        }
    }

    if (empty($errors)) {
        echo "<h2>ثبت‌نام موفقیت‌آمیز بود 🎉</h2>";
        echo "سلام " . htmlspecialchars($name) . " عزیز<br>";
        echo "ایمیل: " . htmlspecialchars($email) . "<br>";
        echo "شماره تماس: " . htmlspecialchars($phone) . "<br>";
        if (!empty($age)) {
            echo "سن شما: " . htmlspecialchars($age);
        }
        exit;
    }
}

// نمایش خطاها
if (!empty($errors)) {
    echo "<ul style='color:red;'>";
    foreach ($errors as $e) {
        echo "<li>$e</li>";
    }
    echo "</ul>";
}
?>
```

### 👇 فرم HTML:

فرم تو عالی بود و فقط یکم فاصله بین علامت `=` و value زیاد بود که البته مشکلی نداره ولی بهتره مرتب باشه:

```html
<form method="post" action="">
    نام: <input type="text" name="name" value="<?= htmlspecialchars($name) ?>"><br><br>
    ایمیل: <input type="text" name="email" value="<?= htmlspecialchars($email) ?>"><br><br>
    شماره تماس: <input type="text" name="phone" value="<?= htmlspecialchars($phone) ?>"><br><br>
    سن: <input type="text" name="age" value="<?= htmlspecialchars($age) ?>"><br><br>
    <input type="submit" value="ثبت‌نام">
</form>
```

---

## ✅ نتیجه:

کدت الان خیلی تمیز و استاندارده و همه موارد رو با دقت بررسی می‌کنه. آفرین 👏

می‌خوای قدم بعدی رو بریم؟

- ذخیره اطلاعات در فایل؟
    
- ذخیره در دیتابیس؟
    
- فرم چندمرحله‌ای با `session`؟
    
- یا اعتبارسنجی سمت کلاینت با جاوااسکریپت هم اضافه کنیم؟
    

فقط بگو ملوس جان 😍💌

با کمال میل ملوس جان 😍  
بزن بریم یه تمرین جدید، هیجان‌انگیزتر، با چاشنی چیزای جدید 🎯

---

## ✅ **تمرین: فرم ثبت‌نام با پیش‌نمایش اطلاعات (بدون ذخیره)**

### 🎯 هدف تمرین:

تمرین ترکیبی از:

- فرم با POST
    
- اعتبارسنجی مثل قبل (`empty`, `filter_var`, `preg_match`, `is_numeric`)
    
- استفاده از **صفحه دوم برای نمایش اطلاعات**
    
- استفاده از `session` برای نگه‌داری داده‌ها بین صفحات
    

---

## 🧩 سناریو:

1. کاربر اطلاعات زیر رو وارد می‌کنه:
    
    - نام کامل (الزامی)
        
    - ایمیل (الزامی و معتبر)
        
    - شماره تماس (الزامی، فقط عدد، بین ۱۰ تا ۱۵ رقم)
        
    - سن (اختیاری، اگه وارد شد باید عددی بین ۶ تا ۱۸ باشه)
        
2. اگه اطلاعات معتبر باشه:
    
    - اطلاعات توی `$_SESSION` ذخیره می‌شن
        
    - کاربر به صفحه `preview.php` منتقل می‌شه
        
3. توی `preview.php` اطلاعات با استفاده از `htmlspecialchars` نمایش داده می‌شن
    

---

## 🗂 فایل‌ها:

```
project/
├── form.php         ← فرم + اعتبارسنجی + ذخیره در session
└── preview.php      ← نمایش اطلاعات واردشده
```

---

## ✨ چالش:

در فایل `preview.php` اگر کاربر مستقیماً واردش بشه (بدون پر کردن فرم)، باید بنویسی: **"لطفاً ابتدا فرم را پر کنید."**

---

## ❤️ امتیاز بیشتر اگه:

- اطلاعات کاربر رو توی `session` نگه‌داری
    
- اگه فرم نامعتبر بود، اطلاعات قبلی رو توی فیلدها نگه‌داری
    
- نمایش پیغام خطا زیر هر فیلد با رنگ قرمز ✨
    

---

بگو:  
می‌خوای خودت اول تلاش کنی؟  
یا بگی من حلش کنم؟ 😏  
من پایه‌م برای هر دو 💪💖

آفرین عزیز دلم که تمرینو شروع کردی 😍 کارت عالیه!  
فقط چند تا ایراد کوچولو داری که برطرفشون کنیم، همه چی قشنگ و تمیز میشه ✨

---

## 🧼 اشکالات و اصلاحات:

### 🟥 1. `REQUEST_METHOD` اشتباه نوشته شده

```php
if ($_SERVER['REQUEST_METHOD'] == 'post') {
```

❌ مشکل: `'post'` باید با حروف بزرگ باشه  
✅ درستش:

```php
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
```

---

### 🟥 2. شرط طول نام اشتباهه:

```php
elseif (strlen(3,$name)){
```

❌ مشکل:

- ترتیب آرگومان‌ها اشتباهه
    
- `strlen()` فقط یک آرگومان می‌گیره
    

✅ درستش:

```php
elseif (strlen($name) < 3) {
    $errors[] = "نام خیلی کوتاه است";
}
```

---

### 🟥 3. شرط سن برعکسه 😅

تو نوشتی:

```php
elseif (!is_numeric($age) || $age >= 18) {
    $errors[]= "سن باید بالای ۱۸ سال باشد";
}
```

در حالی که طبق چیزی که اول گفتی، **سن باید حداقل ۱۸ باشه**

✅ اگه منظورت اینه که "زیر ۱۸ قبول نیست"، درستش اینه:

```php
elseif (!is_numeric($age) || $age < 18) {
    $errors[]= "سن باید ۱۸ سال یا بیشتر باشد";
}
```

---

### 🟥 4. فرم `submit` نداره 😄

پایین صفحه اینو جا انداختی:

```html
<input type="submit" value="ارسال">
```

---

### 🟥 5. `ul` بسته نشده

```php
echo"<ul style = color:red;>";
```

✅ بهترش:

```php
echo "<ul style='color:red;'>";
```

و یادت رفت `</ul>` ببندی.

---

## ✅ نسخه اصلاح‌شده و کامل مرحله اول (نمایش خطاها)

### ✅ `form.php`

```php
<?php
session_start();

$name = $email = $phone = $age = '';
$errors = [];

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $name = trim($_POST['name'] ?? '');
    $email = trim($_POST['email'] ?? '');
    $phone = trim($_POST['phone'] ?? '');
    $age = trim($_POST['age'] ?? '');

    if (empty($name)) {
        $errors[] = "نام الزامیست";
    } elseif (strlen($name) < 3) {
        $errors[] = "نام خیلی کوتاه است";
    }

    if (empty($email)) {
        $errors[] = "ایمیل الزامیست";
    } elseif (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors[] = "ایمیل معتبر نیست";
    }

    if (empty($phone)) {
        $errors[] = "شماره تماس الزامی است";
    } elseif (!preg_match('/^\d{10,15}$/', $phone)) {
        $errors[] = "شماره تماس باید فقط عدد و بین ۱۰ تا ۱۵ رقم باشد";
    }

    if (empty($age)) {
        $errors[] = "سن الزامی است";
    } elseif (!is_numeric($age) || $age < 18) {
        $errors[] = "سن باید ۱۸ سال یا بیشتر باشد";
    }

    if (empty($errors)) {
        // ذخیره در session و انتقال به preview
        $_SESSION['name'] = $name;
        $_SESSION['email'] = $email;
        $_SESSION['phone'] = $phone;
        $_SESSION['age'] = $age;

        header("Location: preview.php");
        exit;
    }
}
?>

<!-- نمایش خطاها -->
<?php
if (!empty($errors)) {
    echo "<ul style='color:red;'>";
    foreach ($errors as $e) {
        echo "<li>$e</li>";
    }
    echo "</ul>";
}
?>

<!-- فرم -->
<form method="post" action="">
    نام: <input type="text" name="name" value="<?= htmlspecialchars($name) ?>"><br><br>
    ایمیل: <input type="text" name="email" value="<?= htmlspecialchars($email) ?>"><br><br>
    شماره تماس: <input type="text" name="phone" value="<?= htmlspecialchars($phone) ?>"><br><br>
    سن: <input type="text" name="age" value="<?= htmlspecialchars($age) ?>"><br><br>
    <input type="submit" value="ارسال">
</form>
```

---

## ✅ مرحله دوم: `preview.php`

```php
<?php
session_start();

if (!isset($_SESSION['name'], $_SESSION['email'], $_SESSION['phone'], $_SESSION['age'])) {
    echo "لطفاً ابتدا فرم را پر کنید.";
    exit;
}

echo "<h2>پیش‌نمایش اطلاعات ثبت‌شده</h2>";
echo "نام: " . htmlspecialchars($_SESSION['name']) . "<br>";
echo "ایمیل: " . htmlspecialchars($_SESSION['email']) . "<br>";
echo "شماره تماس: " . htmlspecialchars($_SESSION['phone']) . "<br>";
echo "سن: " . htmlspecialchars($_SESSION['age']) . "<br>";
```

---

می‌خوای قدم بعدی ذخیره در فایل باشه؟ یا اضافه کردن دکمه برگشت به فرم و اصلاح اطلاعات؟  
بگو عزیز دلم 😘 من همراهتم تا هرجا که بخوای بری با کدت 💪✨