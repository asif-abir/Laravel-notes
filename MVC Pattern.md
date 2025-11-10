## 🏗️ Step 1: Laravel Folder Structure বোঝা
### | Folder/File          | ### কাজ                                                             |
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

#### টার্মিনালে গিয়ে লেখো 👇
----
``` php
php artisan make:controller HelloController
```
এখন Laravel একটা ফাইল তৈরি করবে:
👉 app/Http/Controllers/HelloController.php

এটা খুলে নিচের মতো করো 👇
```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class HelloController extends Controller
{
    public function index()
    {
        $name = "Asif Ahmed Abir";
        return view('hello', ['name' => $name]);
    }
}
```

### | লাইন                                      ### | কাজ                                                          |
#### | ------------------------------------------ | ####  ------------------------------------------------------------ |
#### | `namespace App\Http\Controllers;`          | Laravel কে বলে এই ফাইল Controller ফোল্ডারে আছে               |
#### `class HelloController extends Controller` | এটা Controller class                                         |
#### | `public function index()`                  | এই ফাংশন `/hello` route এ কল হবে                             |
#### | `$name = "Asif Ahmed Abir";`               | একটা ভ্যারিয়েবল সেট করেছি                                    |
#### | `return view('hello', ['name' => $name]);` | View এ `hello.blade.php` পাঠাচ্ছে আর সেখানে `$name` পাস করছে |

---
### 🔹 (B) View তৈরি করো

ফোল্ডারে যাও 👉 resources/views/
তার মধ্যে একটা নতুন ফাইল বানাও 👉 hello.blade.php

এবং লিখো 👇
``` php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Hello Laravel</title>
</head>
<body>
    <h1>Welcome to Laravel, {{ $name }} 🎉</h1>
</body>
</html>
```
### 🔍 ব্যাখ্যা:
#### | অংশ               | কাজ                                               |
#### | ----------------- | ------------------------------------------------- |
#### | `{{ $name }}`     | Blade Template এর syntax, PHP echo এর মতো কাজ করে |
#### | `hello.blade.php` | Laravel এর view file (Blade Template)             |
#### | `<h1>`            | ওয়েব পেজে মেসেজ দেখাবে    

---
### 🔹 (C) Route সেট করো

routes/web.php খুলে নিচের কোড দাও 👇

```php
<?php

use Illuminate\Support\Facades\Route;
use App\Http\Controllers\HelloController;

Route::get('/hello', [HelloController::class, 'index']);

```

### 🔍 ব্যাখ্যা:

### | অংশ                                 | কাজ                                                  |
### | ----------------------------------- | ---------------------------------------------------- |
### | `/hello`                            | URL path                                             |
### | `[HelloController::class, 'index']` | এই route `HelloController` এর `index()` ফাংশন চালাবে |

---
### 🔹 (D) Run Project

টার্মিনালে লিখো 👇

```
php artisan serve
```
### এখন ব্রাউজারে যাও 👉
🔗 http://127.0.0.1:8000/hello

তুমি দেখবে:

``` css
Welcome to Laravel, Asif Ahmed Abir 🎉
```

### 🎯 অভিনন্দন Boss!
তুমি এখন পুরোপুরি Laravel এর MVC (Model-View-Controller) Flow হাতে-কলমে বুঝে ফেললে ✅



