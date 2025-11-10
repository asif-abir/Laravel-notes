## 🏗️ Step 1: Laravel Folder Structure বোঝা
### | Folder/File          | কাজ                                                             |
### | -------------------- | --------------------------------------------------------------- |
### | **app/**             | এখানে থাকে **Model**, **Controller**, এবং **Core Logic**        |
### | **routes/**          | এখানে সব **URL route** define করা হয় (`web.php` সবচেয়ে ব্যবহৃত) |
### | **resources/views/** | এখানে থাকে **Blade file (HTML পেজ)**                            |
### | **database/**        | এখানে থাকে **Migration (table তৈরি করার ফাইল)**                 |
### | **public/**          | এখানেই থাকে **CSS, JS, image** ফাইলগুলো                         |
### | **.env**             | এখানে তোমার **Database & App configuration** থাকে               |
### | **artisan command**  | Laravel-এর নিজের command system — যেমন: `php artisan serve`     |

-----

## 🧭 Step 2: MVC Pattern
#### 📘 সহজভাবে:

Route: কোন URL খুললে কোন কোড চলবে সেটা বলে

Controller: লজিক চালায় (ডেটা আনে, পাঠায়, প্রোসেস করে)

View: ইউজারকে যা দেখা যায় (HTML/Blade)

Model: ডেটাবেসের সাথে কাজ করে

---
### 🧱 Step 3: ছোট একটা প্রজেক্ট তৈরি করি

আমরা “Hello Laravel” প্রজেক্টটা এবার MVC অনুযায়ী করবো।

### 🔹 (A) Controller তৈরি করো

টার্মিনালে গিয়ে লেখো 👇
----
``` php
php artisan make:controller HelloController
```
