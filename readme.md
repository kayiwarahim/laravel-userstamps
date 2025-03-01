# Laravel Userstamps

Laravel Userstamps is a simple Laravel package for your Eloquent Model user specific fields.
This package automatically inserts/updates an user id on your table on who created, last updated and deleted the record.

## Install

1. Add repositories in composer.json

```
"repositories": [
   {
     "url": "https://github.com/kayiwarahim/laravel-userstamps.git",

      "type": "git"
    }
 ],
```

2. Add the package name in `composer.json` require section:
   - For Laravel 5.x use [v1.0.1](https://github.com/hrshadhin/laravel-userstamps/releases/tag/v1.0.1)
   ```
    "hrshadhin/laravel-userstamps": "^1.0.0"
   ```
   - For Laravel 6.x use [v2.0.1](https://github.com/hrshadhin/laravel-userstamps/releases/tag/v2.0.1)
   ```
    "hrshadhin/laravel-userstamps": "^2.0.0"
   ```
   - For Laravel 7.x use [v3.0.0](https://github.com/hrshadhin/laravel-userstamps/releases/tag/v3.0.0)
   ```
    "hrshadhin/laravel-userstamps": "^3.0.0"
   ```
   - For Laravel 8.x use [v4.0.0](https://github.com/hrshadhin/laravel-userstamps/releases/tag/v4.0.0)
   ```
    "hrshadhin/laravel-userstamps": "^4.0.0"
   ```
   - For Laravel 9.x use [v5.0.0](https://github.com/hrshadhin/laravel-userstamps/releases/tag/v5.0.0)
   ```
    "hrshadhin/laravel-userstamps": "^5.0.0"
   ```
   - For Laravel 10.x use [v6.0.0](https://github.com/kayiwarahim/laravel-userstamps/releases/tag/v5.0.0)
   ```
    "kayiwarahim/laravel-userstamps": "^6.0.0"
   ```

## Usage

Update your model's migration and add `created_by`, `updated_by` and `deleted_by` field using the `userstamps()` blueprint macro.

```php
Schema::create('users', function (Blueprint $table) {
    $table->increments('id');
    $table->string('name', 100);
    $table->userstamps();
    $table->timestamps();
});
```

Then use `UserstampsTrait` on your model.

```php
namespace App;

use Hrshadhin\Userstamps\UserstampsTrait;

class User extends Model
{
    use UserstampsTrait;
}
```

## Dropping columns

You can drop auditable columns using `dropUserstamps()` method.

```php
Schema::create('users', function (Blueprint $table) {
    $table->dropUserstamps();
});
```

And your done!

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
