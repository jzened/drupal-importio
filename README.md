# Drupal Import.IO

## Try it yourself!

Clone this repository somewhere local.

I've included a [Drupal VM](http://www.drupalvm.com/) environment which, with light configuration, should work. See their [Quick Start Guide](https://github.com/geerlingguy/drupal-vm#quick-start-guide) first to make sure you have everything you need.

Then, edit `config.yml` and change your `local_path` to wherever you've cloned this repository:

```
local_path: ~/projects/drupal_importio
```

Once all the requirements are fulfilled:

```
vagrant up
drush cc drush
drush @drupal-importio.drupal-importio.dev -y en feeds_import_io feeds_ui admin_menu_toolbar admin_views views_ui feeds_tamper_ui features feedspreview
drush @drupal-importio.drupal-importio.dev -y dis overlay toolbar comment
drush @drupal-importio.drupal-importio.dev -y pm-uninstall overlay toolbar comment
drush @drupal-importio.drupal-importio.dev cc all
```

New Magic

http://school-ratings.com/schoolRatings.php?zipOrCity=94606&schName=&lastOB=distance&qty=64&searchRadius=50&orderBy=rank&dir=

Click "Get API"

How would you like to use this API?

Bulk Extract

http://school-ratings.com/schoolRatings.php?zipOrCity=94606&schName=&lastOB=distance&qty=64&searchRadius=50&orderBy=rank&dir=
http://school-ratings.com/schoolRatings.php?zipOrCity=94606&schName=&lastOB=rank&qty=64&searchRadius=50&startAt=64&orderBy=rank&dir=
http://school-ratings.com/schoolRatings.php?zipOrCity=94606&schName=&lastOB=rank&qty=64&searchRadius=50&startAt=128&orderBy=rank&dir=
http://school-ratings.com/schoolRatings.php?zipOrCity=94606&schName=&lastOB=rank&qty=64&searchRadius=50&startAt=192&orderBy=rank&dir=
http://school-ratings.com/schoolRatings.php?zipOrCity=94606&schName=&lastOB=rank&qty=64&searchRadius=50&startAt=256&orderBy=rank&dir=

Export: Import.io Data Set

d90b8e3d-957c-4757-bec8-98b22f64b11b

https://import.io/data/set/?mode=loadSource&source=d90b8e3d-957c-4757-bec8-98b22f64b11b

---

http://drupal-importio.dev/admin/structure/types/add

Name: School

Save and Add Fields

State Rank
API Score
School
District
Location
Class Sizes
Parent Education

drush @drupal-importio.drupal-importio.dev field-create school district,text,text_textfield class_sizes,text_long,text_textarea parent_education,text_long,text_textarea state_rank,number_float,number api_score,number_float,number location,text_long,text_textarea

Location:

Location name: Do not collect
Street location: Allow
Additional: Do not collect
City: Do not collect
State/Provice: Do not collect
Postal code: Do not collect
Country: Force Default: United States
Coordinate Chooser: Do not collect

Display Settings:

Structure > Feeds Importers > add Importers

California School Ratings
Ratings, ranking, test scores for schools

Fetcher: change

import.io Fetcher

import.io Fetcher: Settings

Specify Data Set ID, User ID, and API Key

Parser: change

import.io Parser

Node processor: Settings

Bundle: School

Update existing nodes: Update existing nodes

Save

Mapping

Hover over the data set headings to get the machine name.

number_1 - state_rank
number_2 - api_score
value_1 - title - click gear, [X] Unique, Update
content - location
values - class_sizes
alttext_value_numbers - parent_education

Tamper

location

Add plugin: Find replace

Text to find: " map " (without the spaces)
Text to replace: ", " (without the spaces)

Click Save

---

http://drupal-importio.dev/import

Click "California School Ratings"

Click Import

Go to Content