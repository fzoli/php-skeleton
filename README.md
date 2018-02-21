# Init project

`./composer create-project "symfony/skeleton" api`

`cd api`

# Setup API

`./composer req api`

# Create database

Do not forget to change the Database URL in `.env`.

## Implement Hello Entity (and API resource)

`nano src/Entity/Hello.php`

```php
<?php

namespace App\Entity;

use ApiPlatform\Core\Annotation\ApiResource;
use Doctrine\ORM\Mapping as ORM;
use Doctrine\Common\Collections\ArrayCollection;
use Symfony\Component\Validator\Constraints as Assert;

/**
 * @ApiResource
 * @ORM\Entity
 * @ORM\Table(name="hello")
 */
class Hello // The class name will be used to name exposed resources
{

    /**
     * @ORM\Column(type="integer")
     * @ORM\Id
     * @ORM\GeneratedValue(strategy="AUTO")
     */
    public $id;

    /**
     * @param string $name A name property - this description will be available in the API documentation too.
     *
     * @ORM\Column(type="string", length=100)
     * @Assert\NotBlank
     */
    public $name;

}
```

## Init the database

`./bin/console doctrine:database:create`

`./bin/console doctrine:schema:create`

# Web server

## Install Symfony web server

`./composer req server`

## Start

`./bin/console server:start`

## Browse

`http://localhost:8000/api`

# More info

http://fabien.potencier.org/symfony4-demo.html
