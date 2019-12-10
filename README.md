# bootboot-example

This is an example of using Shopify's
[bootboot](https://github.com/Shopify/bootboot) to dual-boot an app, switching
with an environment variable.

To start, run:

```
$ bundle install
$ bundle bootboot
```

This should create `Gemfile.lock` and `Gemfile_next.lock` files for you, but it
won't ([apparently](https://github.com/Shopify/bootboot/issues/28)) install the
`RAILS_NEXT` gems, so you'll also need to run:

```
$ RAILS_NEXT=1 bundle install
```

Once both sets of gems are installed, you can run the little program in this
repo under each version, with:

```
$ bundle exec ruby program.rb
Hello! Rails is version 5.0.7.2 because RAILS_NEXT=""
```

And under the `RAILS_NEXT` version:

```
$ RAILS_NEXT=1 bundle exec ruby program.rb
Hello! Rails is version 5.1.7 because RAILS_NEXT="1"
```
