# HabtmGenerator


## Installation

Add this line to your application's Gemfile:

    gem 'habtm_generator', :group => :development

And then execute:

    $ bundle


## Usage


```bash
rails generate habtm user post
```

This will generate a migration, for:
* creating table "posts\_users" with user\_id, post\_id, no primary key
* index on both columns

And will copy the "has\_and\_belongs\_to\_many :model" into both models (near the top of the models)

This process is reversible (with ``rails destroy habtm model1 model2``).

## Potential Caveats

* Namespaced models will not work
* unique-constraint on index. I find this most useful for most situations. Just remove that from the generated migration before rake db:migrate
