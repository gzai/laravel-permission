---
title: Prerequisites
weight: 3
---

This package can be used in Laravel 5.8 or higher.

This package uses Laravel's Gate layer to provide Authorization capabilities.
The Gate/authorization layer requires that your `User` model implement the `Illuminate\Contracts\Auth\Access\Authorizable` contract. 
Otherwise the `can()` and `authorize()` methods will not work in your controllers, policies, templates, etc.

In the `Installation` instructions you'll see that the `HasRoles` trait must be added to the User model to enable this package's features.

Thus, a typical basic User model would have these basic minimum requirements:

```php
use Illuminate\Foundation\Auth\User as Authenticatable;
use Spatie\Permission\Traits\HasRoles;

class User extends Authenticatable
{
    use HasRoles;

    // ...
}
```