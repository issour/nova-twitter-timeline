# Nova Twitter Timeline
Add a card to Nova's dashboard that display the latest user timeline and mentions tweets

## Installation

You can install the package in to a Laravel app that uses Nova via composer:

```bash
composer require naif/nova-twitter-timeline
```

## Usage:

```php
// in app/Providers/NovaServiceProvder.php

public function card()
{
    return [
        new \Naif\NovaTwitterTimeline\NovaTwitterTimeline(),
    ];
}
```
Create a twitter app and obtain your API keys from https://developer.twitter.com

```php
// add this to your /config/services.php
    'nova_twitter_timeline' => [
        'consumer_key' => env('TWITTER_CONSUMER_KEY', ''),
        'consumer_key_secret' => env('TWITTER_CONSUMER_SECRET', ''),
        'access_token' => env('TWITTER_ACCESS_TOKEN', ''),
        'access_token_secret' => env('TWITTER_ACCESS_TOKEN_SECRET', ''),
        'timeline' => env('TWITTER_TIMELINE', ''),
        'tweets_count' => env('TWITTER_TWEETS_COUNT', ''),
    ],
```
```php
// add this to your .env file

TWITTER_CONSUMER_KEY=###################################
TWITTER_CONSUMER_SECRET=################################
TWITTER_ACCESS_TOKEN=###################################
TWITTER_ACCESS_TOKEN_SECRET=############################
TWITTER_TIMELINE=mentions_timeline // here you can set what timeline you whoul like to retrieve (mentions_timeline OR user_timeline)
TWITTER_TWEETS_COUNT=5 // here is the count of tweets you would like to retrieve Max: 200

```
## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
