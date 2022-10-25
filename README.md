# Library for CloudLog.me
## Using
Just a few lines of code:
```php
$apiToken = YOUR_TOKEN_HERE;
$channelId = YOUR_CHANNEL_ID_HERE; 

$cloudLog = new CloudLog($apiToken);
$cloudLog->channel($channelId);
$cloudLog->info('Hello world!');
$cloudLog->error('Whoops!');
$cloudLog->critical('OMG!');
```       
That's all!

## Laravel

You can use this package as a Laravel logger.

```bash
php artisan vendor:publish --provider="Ermolinme\CloudLog\CloudLogServiceProvider" --tag="config"
```

Create log config in *config/logging.php*

```php
...
'cloud' => [
    'driver' => 'custom',
    'via'    => \Ermolinme\CloudLog\CustomLogger::class,
    'level'  => 'debug',
],
...
```

And use it!

```php
Log::channel('cloud')->info('Hello world');
```