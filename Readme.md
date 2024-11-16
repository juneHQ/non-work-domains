# Non work domains

This is a list of domains that are not work related.

We use this list to block non-professional domains from creating new accounts for [June](https://june.so).

## How to use this list

You can use this list to block non-professional domains from creating new accounts for your B2B SaaS product.

This is helpful for both reducing the amount of spam accounts on your platform and making it easier for your sales team to understand if a lead is a good fit for your product.

The way you'd use it is by loading this list into your application during its build process or at runtime.

Here's an example of how you could do this in a Rails application:

```ruby
# config/initializers/non_work_domains.rb

NON_WORK_DOMAINS = File.read(Rails.root.join('data', 'domains.txt')).split("\n")
```

Then in your application you can use the `NON_WORK_DOMAINS` constant to check if a domain is a non-work domain.

```ruby
if NON_WORK_DOMAINS.include?(domain)
  # do something
end
```

## How to contribute

If you have a domain that you think should be added to this list, please open a PR adding it to the `data/domains.txt` file.

If you have a domain that you think should be removed from this list, please open a PR removing it from the `data/domains.txt` file.

Once you've added or removed a domain, please run the `scripts/sort_and_clean` script to sort the list and remove any duplicate or empty lines.

## Credits

The first version of this list was created copying this [list](https://github.com/willwhite/freemail/blob/master/data/free.txt) from [willwhite](https://github.com/willwhite) and adapting it to our needs.