# pumpkinjob-php-getting-started [![PHP Version](https://img.shields.io/packagist/v/pumpkinjob/pumpkinjob-client-php)](https://packagist.org/packages/pumpkinjob/pumpkinjob-client-php) [![PHP CI](https://github.com/coco-gene/pumpkinjob-php-getting-started/workflows/PHP%20CI/badge.svg)](https://github.com/coco-gene/pumpkinjob-php-getting-started/actions?query=workflow%3A%22PHP+CI%22)

PHP PumpkinJob Starter Project Template that Works Out-of-the-Box

[![PumpkinJob in PHP](https://img.shields.io/badge/PumpkinJob-PHP-blue)](https://github.com/coco-gene/PumpkinJob-Client-PHP)

## Connecting Chatbots

[![Powered by PumpkinJob](https://img.shields.io/badge/Powered%20By-PumpkinJob-brightgreen.svg)](https://github.com/coco-gene/PumpkinJob-Client-PHP)
[![PHP Version](https://img.shields.io/packagist/v/coco-gene/PumpkinJob-Client-PHP)](https://packagist.org/packages/coco-gene/PumpkinJob-Client-PHP)

## PumpkinJob

```php
$pumpkinJobClient = new PumpkinJobClient($domain, $appName, $password);

$jobId = 2;
$params = array(
    "id" => $jobId,
    "jobName" => "OpenAPIJob",
    "jobDescription" => "test OpenAPI",
    "jobParams" => "ls -al",
    "timeExpressionType" => TimeExpressionType::$TYPE[TimeExpressionType::$API],
    "executeType" => ExecuteType::$TYPE[ExecuteType::$STANDALONE],
    "processorType" => ProcessorType::$TYPE[ProcessorType::$BUILT_IN],
    "processorInfo" => "com.yunqiic.pumpkinjob.official.processors.impl.script.ShellProcessor",
    "designatedWorkers" => "",
    "minCpuCores" => 1.1,
    "minMemorySpace" => 1.2,
    "minDiskSpace" => 1.3,

);
// if there is no id param it will add a new job otherwise if will modify the job
$result = $pumpkinJobClient->saveJob($params);

$result = $pumpkinJobClient->runJob($jobId);
```

## Usage

### Install

```sh
# Install make sure php is 7.4+
# curl -sS https://getcomposer.org/installer | php
php -r "copy('https://install.phpcomposer.com/installer', 'composer-setup.php');"
php composer-setup.php
php -r "unlink('composer-setup.php');"
mv composer.phar /usr/local/bin/composer

make install
```

### Run

```sh
export DOMAIN=xxx
export APP_NAME=xxx
export PASSWORD=xxx

make job
```

## Copyright & License

- Code & Docs © 2022 PumpkinJob Contributors <https://github.com/coco-gene>
- Code released under the Apache-2.0 License
- Docs released under Creative Commons
