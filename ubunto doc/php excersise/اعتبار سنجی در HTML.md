---
tags:
  - valid
---


---

## ✅ **مهم‌ترین ویژگی‌های اعتبارسنجی در HTML**

---

### 1. **`required`**

اجباری بودن فیلد

```html
<input type="text" name="name" required>
```

---

### 2. **`type`** برای فیلد ایمیل، عدد، URL و...

```html
<input type="email" name="email" required>
<input type="number" name="age">
<input type="url" name="website">
```

---

### 3. **`min` و `max`** برای اعداد

```html
<input type="number" name="age" min="18" max="60">
```

---

### 4. **`minlength` و `maxlength`** برای تعداد کاراکتر

```html
<input type="text" name="username" minlength="3" maxlength="10">
```

---

### 5. **`pattern`** برای استفاده از Regex (الگوی خاص)

مثلاً فقط حروف انگلیسی و عدد مجاز باشند:

```html
<input type="text" name="username" pattern="[A-Za-z0-9]+" title="فقط حروف انگلیسی و عدد مجاز است">
```

---

### 6. **`step`** برای مقادیر عددی با فاصله مشخص

مثلاً فقط اعداد زوج:

```html
<input type="number" name="evenNumber" step="2">
```

---

### 7. **`placeholder`** برای نمایش راهنمای ورود

(جزو اعتبارسنجی نیست ولی تجربه کاربری رو بهتر می‌کنه)

```html
<input type="text" name="name" placeholder="نام خود را وارد کنید">
```

---

### 8. **`disabled` و `readonly`**

برای غیرقابل ویرایش کردن یا غیرفعال کردن فیلد

```html
<input type="text" value="فقط خواندنی" readonly>
<input type="text" value="غیرفعال شده" disabled>
```

---

## 🔥 مثال کامل از فرم با اعتبارسنجی HTML:

```html
<form action="process.php" method="post">
  نام: <input type="text" name="name" required minlength="3"><br><br>
  ایمیل: <input type="email" name="email" required><br><br>
  سن: <input type="number" name="age" min="18" max="99"><br><br>
  رمز عبور: <input type="password" name="password" required minlength="6"><br><br>
  <input type="submit" value="ثبت‌نام">
</form>
```

---

