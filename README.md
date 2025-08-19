📘 Detailed Notes for BCA Students – MVC & Laravel
0) Big Picture

What MVC is and why it helps in software development.

How Laravel (a PHP framework) uses MVC.

Basics of Laravel installation, routing, and controllers.

Quick exam-ready points for revision.

1) Introduction to MVC

MVC (Model–View–Controller) is a software design pattern used to keep applications organized, scalable, and easier to maintain.

🔹 Model

Handles data and business logic.

Talks to the database.

Example: Student model for adding/updating/deleting student info.

🔹 View

Deals with UI (User Interface).

Displays data to users.

Example: HTML page showing student details.

🔹 Controller

Acts as a middleman between Model & View.

Handles requests, updates model, and returns responses.

Example: If user clicks Show Students, controller fetches data from model and passes it to view.

👉 This separation makes development clean, structured, and teamwork-friendly.

2) Uses of MVC Framework

Clean application structure.

Reusability → components can be reused.

Scalability → supports large projects.

Teamwork-friendly → designers (views), developers (models), testers (controllers).

Easier debugging & testing.

Used in modern frameworks: Laravel (PHP), Django (Python), Rails (Ruby), ASP.NET MVC (C#).

3) Advantages & Disadvantages

✅ Advantages

Separation of concerns.

Faster development with teams.

Scalable for large systems.

Code reusability.

Better testing.

❌ Disadvantages

More files (model, view, controller for each feature).

Complex for small apps.

Steeper learning curve for beginners.

Needs well-managed communication between parts.

4) Laravel – Introduction

Laravel = A modern, open-source PHP MVC framework created by Taylor Otwell (2011).

✨ Key Features

MVC architecture.

Blade template engine → cleaner UI code.

Eloquent ORM → simple DB interaction.

Routing system → clean URL handling.

Artisan CLI → automates tasks.

Security features → CSRF, hashed passwords.

Migrations → manage database schema.

Huge community support.

5) Why Laravel is Better than Other Frameworks

Clean, simple syntax.

Blade templates (no messy PHP inside HTML).

Eloquent ORM → DB without writing raw SQL.

Built-in authentication & security.

Artisan CLI saves time.

Huge ecosystem of packages (Payments, APIs, etc.).

Better documentation & tutorials.

6) Steps to Install & Configure Laravel
# 1. Install Composer
Download from https://getcomposer.org

# 2. Create new Laravel project
composer create-project laravel/laravel myproject

# 3. Move into project folder
cd myproject

# 4. Run server
php artisan serve

# 5. Open in browser
http://127.0.0.1:8000


🎉 Laravel is ready!

7) Laravel Directory Structure

app/ → Core code (Models, Controllers, Middleware).

bootstrap/ → Loads application.

config/ → App configurations.

database/ → Migrations, seeders.

public/ → Entry point, CSS/JS/images.

resources/ → Views (Blade templates), CSS, JS.

routes/ → Defines routes (web.php, api.php).

storage/ → Caches, logs, uploads.

tests/ → Automated tests.

vendor/ → Composer packages.

8) Routing in Laravel

Defined in routes/web.php (web) and routes/api.php (API).

Example:

Route::get('/', function () {
    return view('welcome');
});


👉 Shows welcome.blade.php when user visits /.

9) Route File Functions
Route::get('/url', ...);      // GET request
Route::post('/url', ...);     // POST request (forms)
Route::put('/url', ...);      // Update data
Route::delete('/url', ...);   // Delete data
Route::any('/url', ...);      // Accept any type
Route::redirect('/from', '/to'); // Redirect
Route::view('/url', 'viewName'); // Directly show view

10) Controllers in Laravel
Create Controller
php artisan make:controller StudentController

Example Controller
namespace App\Http\Controllers;
use Illuminate\Http\Request;

class StudentController extends Controller {
    public function index() {
        return "Welcome to Student Controller";
    }

    public function show($id) {
        return "Student ID: " . $id;
    }

    public function getData(Request $request) {
        $name = $request->input('name');
        return "Hello, " . $name;
    }
}

Connect Routes & Controller

In routes/web.php:

use App\Http\Controllers\StudentController;

Route::get('/student', [StudentController::class, 'index']);
Route::get('/student/{id}', [StudentController::class, 'show']);
Route::post('/submit', [StudentController::class, 'getData']);

Handling Form Data

Blade form:

<form method="POST" action="/submit">
    @csrf
    <input type="text" name="name" placeholder="Enter name">
    <button type="submit">Submit</button>
</form>


Controller:

public function getData(Request $request) {
    $name = $request->input('name');
    return "Welcome, " . $name;
}

✅ Quick Exam-Ready Summary

MVC = Model (data), View (UI), Controller (logic).

Uses → Clean, reusable, teamwork-friendly.

Laravel = PHP MVC framework with Blade, Eloquent, Routing, Artisan.

Install → Composer → Create project → php artisan serve.

Structure → app/, routes/, resources/, config/, database/, public/.

Routes → GET, POST, PUT, DELETE, view(), redirect().

Controllers → Created by Artisan, linked via routes.

Form data → $request->input('name').
