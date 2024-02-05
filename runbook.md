## For Development

You can build the snipe-it image using the Dockerfile at the root directory of Snipe-IT by doing this:

```sh
docker build -t snipe-it .
```

Then you can use your newly built image as snipe-it

When you call docker run - make sure to mount your own snipe-it directory over the /var/www/html directory. Something like:

```sh
docker run -d -v /Path/To/My/snipe-it/checkout:/var/www/html -P --name="snipeit" --link mysql:mysql snipeit
```

Then your local changes to the code will be reflected. You will have to re-run composer install -

```sh
docker debug -i -t snipeit
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
