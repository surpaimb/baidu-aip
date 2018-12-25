
<h1 align="center">
  Baidu Aip 2.2.9
</h1>

baidu-aip 用composer 封装了 aip-php-sdk（当前版本2.2.9）


## :rocket: 5 minutes quick start for exports

:bulb: Require this package in the `composer.json` of your Laravel project. This will download the package and PhpSpreadsheet.

```
composer require surpaimb/baidu-aip
```


This should have created:

```php
<?php

namespace App\Http\Controllers;

use Surpaimb\Baidu\Aip\AipOcr;

class ExampleController extends Controller
{

    public $client;
    /**
     * Create a new controller instance.
     *
     * @return void
     */
    public function __construct()
    {
        //
        $this->client = new AipOcr(APP_ID, APP_KEY, SECRET_KEY);
    }

    //
    
    public function ocr($filename)
    {
        $image = file_get_contents($filename);
        $templateSign = null;
        $param = ['classifierId' => '1'];

        // 调用自定义模板文字识别
        return $this->client->custom($image, $templateSign ,$param);
    }
}

```



