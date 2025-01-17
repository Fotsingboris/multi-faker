# multi-faker
Package for generating Faker by country

**Version :** 1.0.0 (in version 1.0.0 , currently being tested and developed)
[![GitHub License](https://img.shields.io/github/license/Dilane05/multi-faker)](LICENSE.md)
[![GitHub Release](https://img.shields.io/github/release/Dilane05/multi-faker)](https://github.com/Dilane05/multi-faker/releases)
## Table of Contents

- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Contributions](#Contributions)
- [Formatters](#Formatters)


## Installation

Install the Package by the following command,

    composer require cupidontech/multi-faker

If you encounter an error during package installation, just type this command:

    composer require cupidontech/multi-faker --ignore-platform-reqs

## Add Provider

Add the provider to your `config/app` into `provider` section if using lower version of laravel,

    Cupidontech\MultiFaker\MultiFakerServiceProvider::class,

## Add the country configuration to your .env file

    MULTI_FAKER_DEFAULT_COUNTRY= {Country}

    e.g = MULTI_FAKER_DEFAULT_COUNTRY=Cameroon
    e.g = MULTI_FAKER_DEFAULT_COUNTRY=Nigeria
    e.g = MULTI_FAKER_DEFAULT_COUNTRY=France
    e.g = MULTI_FAKER_DEFAULT_COUNTRY=Canada

## Basic Usage

To use this package, follow these steps:

    use Cupidontech\MultiFaker\MultiFakerGenerator;

    $faker = new MultiFakerGenerator();

    $name = $faker->firstName();
    $address = $faker->address();
    $email = $faker->email();

use in a controller

    <? php
    namespace App\Http\Controllers;

    use Cupidontech\MultiFaker\MultiFakerGenerator;

    class Test extends Controller
    {
        public function generateData(MultiFakerGenerator $faker)
        {
            // Example of use
            $name = $faker->last_name();
            $address = $faker->address();
            // ...
        return view('data', compact('name', 'address'));
        }
    }

    Make sure you add the necessary classes and import the package correctly into your Laravel application.  


## Formatters
# Local names
    $firstName = $faker->first_name();
    $lastName = $faker->last_name();
# username
    $username = $faker->username();
# Gender
    $gender = $faker->gender();
# Local addresses
    $address = $faker->address();
# Local phone numbers
    $phoneNumber = $faker->phone();
# email
    $email = $faker->email();
# date
    $date = $faker->date();
# Generation of city and region names
    $region = $faker->region();
    $city = $faker->cities();
    $city = $faker->city($region);
# Location
    $region = $faker->region(); 
# coordinates
    $coordinates = $faker->coordinates();
# password
    $password = $faker->password();
# text
    $text = $faker->text(30);
# companyName
    $companyName = $faker->companyName();
# creditCardNumber
    $creditCardNumber = $faker->creditCardNumber();
# product
    $product = $faker->product();
# food
    $food = $faker->food();


## Countries supported

Cameroon ,  Nigeria , France , Canada<br>
(coming soon) ... Ivory Coast ,United States , Brazil , United Kingdom , Germany , Spain , South Africa , Ghana , Ethiopia , Kenya , Morocco , Algeria , India , China , Australia 
## Contributions

We welcome contributions from the community. If you would like to contribute to this project, please follow these steps:

1. Fork the project.
2. Create a branch for your feature (`git checkout -b new-feature`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push the branch (`git push origin new-feature`).
5. Create a pull request on GitHub.

## License

This package is distributed under the [MIT] license. See [LICENSE.md](LICENSE.md) for details.
