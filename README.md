# Notes for BCA Students – MVC & Laravel

## 1) MVC (Model–View–Controller)
- Design pattern for software development
- Divides app into 3 parts:
  - **Model** → Handles data & database
  - **View** → Handles user interface
  - **Controller** → Handles logic & connects Model + View
- Makes apps organized, scalable, easy to maintain

## 2) Uses of MVC
- Clean structure
- Reusable components
- Good for teamwork
- Easier debugging
- Used in Laravel, Django, Rails, ASP.NET etc.

## 3) Advantages
- Separation of concerns
- Faster development with teams
- Scalable for large projects
- Code reusability
- Easier testing

### Disadvantages
- More files to manage
- Complex for small apps
- Hard for beginners
- Needs proper communication between parts

## 4) Laravel Introduction
- PHP MVC framework (created in 2011 by Taylor Otwell)
- Open-source, modern, widely used

### Features
- MVC architecture
- Blade template engine
- Eloquent ORM (database handling)
- Routing system
- Artisan CLI (command line tool)
- Security features
- Migrations (database version control)
- Large community

## 5) Why Laravel is Better
- Simple, clean syntax
- Blade templates (no messy PHP in HTML)
- Eloquent ORM (no raw SQL)
- Built-in authentication & security
- Artisan CLI saves time
- Many packages available
- Good documentation

## 6) Installation
1. Install Composer → [https://getcomposer.org](https://getcomposer.org)  
2. Create new Laravel project  
composer create-project laravel/laravel myproject

markdown
Copy
Edit
3. Go to project folder → `cd myproject`  
4. Run server → `php artisan serve`  
5. Open in browser → `http://127.0.0.1:8000`

## 7) Laravel Directory Structure
- **app/** → Models, Controllers, Middleware  
- **bootstrap/** → Loads application  
- **config/** → Configuration files  
- **database/** → Migrations, Seeders  
- **public/** → Entry point, assets  
- **resources/** → Views, CSS, JS  
- **routes/** → web.php, api.php  
- **storage/** → Logs, cache, uploads  
- **tests/** → Automated tests  
- **vendor/** → Composer packages  

## 8) Routing in Laravel
- Routes are defined in `routes/web.php` (web) and `routes/api.php` (API)

### Example
```php
Route::get('/', function () {
 return view('welcome');
});
9) Route Types
php
Copy
Edit
Route::get('/url', ...);        // GET
Route::post('/url', ...);       // POST
Route::put('/url', ...);        // PUT
Route::delete('/url', ...);     // DELETE
Route::any('/url', ...);        // Any request
Route::redirect('/from', '/to'); // Redirect
Route::view('/url', 'viewName'); // Show view directly
10) Controllers
Create Controller
go
Copy
Edit
php artisan make:controller StudentController
Example
php
Copy
Edit
class StudentController extends Controller {
    public function index() {
        return "Welcome to Student Controller";
    }
    public function show($id) {
        return "Student ID: " . $id;
    }
    public function getData(Request $request) {
        return "Hello, " . $request->input('name');
    }
}
Connect Routes
php
Copy
Edit
Route::get('/student', [StudentController::class, 'index']);
Route::get('/student/{id}', [StudentController::class, 'show']);
Route::post('/submit', [StudentController::class, 'getData']);
✅ Quick Summary
MVC = Model (data), View (UI), Controller (logic)

Laravel = PHP MVC framework with Blade, Eloquent, Routing, Artisan

Install with Composer → run php artisan serve

Structure → app/, routes/, resources/, config/, database/, public/

Routes → GET, POST, PUT, DELETE, view(), redirect()

Controllers → created with Artisan, connected via routes

Form data → $request->input('name')
