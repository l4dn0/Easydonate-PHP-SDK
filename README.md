# EasyDonate SDK
Форк SDK на PHP для работы с [EasyDonate API](https://api.easydonate.ru/ "EasyDonate API"). Оригинальный SDK на основе API v2 находится [здесь](https://github.com/EasyDonate/PHP-SDK).

## Поддерживаемые версии
- ~~[EasyDonate API v1](https://api.easydonate.ru/v/v1/ "EasyDonate API v1")~~
- ~~[EasyDonate API v2](https://api.easydonate.ru "EasyDonate API v2")~~
- [EasyDonate API v3](https://api.easydonate.ru/api/v3/ "EasyDonate API v3")

**Внимание!** Данный SDK не поддерживает EasyDonate API v1 и v2.

## Как это работает?
Несколько примеров использования EasyDonate SDK ниже.
```php
<?php

/**
 * Пример кода.
 * Возвращает информацию о существующем магазине.
 *
 * @link https://api.easydonate.ru/methods/shop
 */

use EasyDonate\Sdk;

$key = '12aeb1f345h5gdrf5fj6ds869h33f8fe';

$sdk = new Sdk($key);
$shop = $sdk->getShop();

print_r($shop);
```

```php
<?php

/**
 * Пример кода.
 * Создает платеж и перенаправляет на страницу оплаты.
 *
 * @link https://api.easydonate.ru/methods/payment-create
 */

require_once __DIR__ . '/vendor/autoload.php';

$sdk = new EasyDonate\Sdk('12aeb1f345h5gdrf5fj6ds869h33f8fe');
$payment = $sdk->payment()
               ->setCustomer('DontFollow')
               ->setServerId(1435)
               ->setProducts([14256 => 1])
               ->setEmail('mail@mail.com')
               ->setCoupon('SALE10')
               ->create(true);

```

На данный момент SDK не поддерживает работу с плагинами EasyDonate
