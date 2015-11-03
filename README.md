# L5scaffold


L5 Scaffold Generator



## Usage

### Step 1: Installation

Add this in composer.json

```
    "require": {
    ...
        "fromz/l5scaffold": "dev-master"
    },
    "repositories": [
        {
            "type": "vcs",
            "url": "git@github.com:pkfrom/l5-scaffold.git"
        }
    ],
```

### Step 2: Run composer
```
composer update
```

### Step 3: Add the Service Provider

Open `config/app.php` and, to your **providers** array at the bottom, add:

```
Fromz\L5scaffold\GeneratorsServiceProvider::class,
```

### Step 4: Run Artisan!

You're all set. Run `php artisan` from the console, and you'll see the new commands `make:scaffold`.

## Examples


```
php artisan make:scaffold Product --schema="company_id:integer:unsigned,name:string,detail:text,activate:boolean:default('1'),picture:binary:nullable"
```
This command will generate:

```
app/Product.php
app/Http/Controllers/ProductController.php
database/migrations/2015_10_10_112233_create_products_table.php
database/seeds/ProductTableSeeder.php
resources/views/layout.blade.php
resources/views/products/index.blade.php
resources/views/products/show.blade.php
resources/views/products/edit.blade.php
resources/views/products/create.blade.php
```
And don't forget to run:

```
php artisan migrate
```

