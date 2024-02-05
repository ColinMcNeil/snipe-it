## For Development

```sh
docker compose up
```

Then your local changes to the code will be reflected. You will have to re-run composer install -

```sh
docker debug snipe-it-snipeit
```

Re-run composer

```sh
# Docker Debug Session
composer install
```

And you may still need to generate the key with -

```sh
# Docker Debug Session
php artisan key:generate --env=production
```

While you're developing, you may need to occasionally run:

```sh
# Docker Debug Session
composer dump
```

To fix the autoloading cache (if, for example, your class names change, or you add new ones...)
