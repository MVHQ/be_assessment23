# MetaverseHQ Backend Assessment

In this repo, I have initiated a blank repository using cookiecutter-django. If you use docker to run this project, a lot is set up for you out of the box, including a local database config.

The fun stuff:
The object of this assessment will be to use the Etherscan API to pull ETH balances for a group of wallets, save them in a database, and set up an API to produce this data when needed.

Please setup and develop the following:

[![Built with Cookiecutter Django](https://img.shields.io/badge/built%20with-Cookiecutter%20Django-ff69b4.svg?logo=cookiecutter)](https://github.com/cookiecutter/cookiecutter-django/)

This assessment will have three parts:

- Setup
- Models
- API

## Setup

### Getting Up and Running Locally With Docker

Please reference [Getting Up and Running Locally With Docker](https://cookiecutter-django.readthedocs.io/en/latest/developing-locally-docker.html) for setup/startup instructions.

## Models

- Create a model to store all data the wallet balance endpoint returns.
- You will need three models: Wallet, WalletGroup, and WalletResult.
  - Wallet represents a wallet itself.
  - WalletGroup represents the group of wallets in the API request.
  - WalletResult should tie all together. The wallet object, the balance, and the group.
- Extra credit: Feel free to index for performance.

## API

Please create the following endpoint:

### /wallets/wallet/

If the request is sent as a POST, do the following:

- Check the request body and pull the eth balances for all wallets provided.
- You'll notices I left the request structure ambiguous feel free to use any structure you want here.
- Please save an object for Wallet, WalletGroup, and WalletGroupResult.
- Return the balance for the entire group of wallets provided as well as the individual balances for each wallet provided.

If the request is sent as a GET, do the following:

- Return the latest result for that specific wallet if there is one in the database.
- For extra consideration, please write any test you find appropriate to ensure the project requirements above are safely met.
- Feel free to explain your thought process anywhere in the code comments. We find it beneficial to not only see the show but also to understand the why!

## Submission

For submission, please compress your project into a .zip file and submit it via email to kennyg@mvhq.io. Feel free to upload to a cloud provider(ex. Dropbox, Google Drive) if needed.

## Docs

### Docker

- [Docs](https://docs.docker.com/get-docker/)

### Django

- [Docs](https://docs.djangoproject.com/en/3.2/)

### Cookiecutter-Django

- [Github](https://github.com/cookiecutter/cookiecutter-django)
- [Docs](https://cookiecutter-django.readthedocs.io/en/latest/)

### Django-Rest-Framework

- [Docs](https://www.django-rest-framework.org)

### Etherscan API

- [Docs](https://docs.etherscan.io)

## Settings

Moved to [settings](http://cookiecutter-django.readthedocs.io/en/latest/settings.html).

## Basic Commands

### Setting Up Your Users

- To create a **normal user account**, just go to Sign Up and fill out the form. Once you submit it, you'll see a "Verify Your Email Address" page. Go to your console to see a simulated email verification message. Copy the link into your browser. Now the user's email should be verified and ready to go.

- To create a **superuser account**, use this command:

      $ python manage.py createsuperuser

For convenience, you can keep your normal user logged in on Chrome and your superuser logged in on Firefox (or similar), so that you can see how the site behaves for both kinds of users.

### Test coverage

To run the tests, check your test coverage, and generate an HTML coverage report:

    $ coverage run -m pytest
    $ coverage html
    $ open htmlcov/index.html

#### Running tests with pytest

    $ pytest
