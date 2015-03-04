# ZfcUserLastConnectionDate
[![Build Status](https://travis-ci.org/momzor/ZfcUserLastConnectionDate.svg)](https://travis-ci.org/momzor/ZfcUserLastConnectionDate)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/momzor/ZfcUserLastConnectionDate/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/momzor/ZfcUserLastConnectionDate/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/momzor/ZfcUserLastConnectionDate/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/momzor/ZfcUserLastConnectionDate/?branch=master)
Created by inovia-team

Introduction
------------

ZfcUserLastConnectionDate is a ZF2 module providing an automatic update of user's last connection
date for each connection with ZfcUser.

For more informations about ZfcUser : [ZfcUser](https://github.com/ZF-Commons/ZfcUser)

Storage Adapter Modules
-----------------------


Requirements
------------

* [Zend Framework 2](https://github.com/zendframework/zf2) (latest master)
* [ZfcBase](https://github.com/ZF-Commons/ZfcBase) (latest master).
* [ZfcUser](https://github.com/ZF-Commons/ZfcUser)
* PHP version >= 5.4

Installation
------------

### Main Setup

#### With composer

1. Add this project and in your composer.json:

    ```json
    "require": {
        "momzor/zfc-user-last-connection-date": "dev-master"
    }
    ```

2. Run the command:

    ```bash
    $ php composer.phar update
    ```

#### Module Activation

1.  In your `application.config.php`file.

    ```php
    <?php
    return array(
        'modules' => array(
            // ...
            'LastConnectionDate',
        ),
        // ...
    );
    ```

2. Update your User table and  Entity.

By Extending LastConnectionDate User entity:

    ```php
    <?php

    namespace User\Entity;

    use LastConnectionDate\Entity\User as ZfcUser;

    class User extends ZfcUser
    {

    }

    ```
OR if you don't want to extends it you can use the Trait :
        ```php
        <?php

        namespace User\Entity;

        use LastConnectionDate\Entity\LastConnectionTrait;

        class User extends ZfcUser
        {
            use LastConnectionTrait;

        }

        ```

2. There are some SQL example in  `./vendor/momzor/zfc-user-last-connection-date/data/`



Navigate to http://yourproject/user/login.

