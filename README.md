# enlist

Subscribe to get emails on certain events

[![build status](https://secure.travis-ci.org/serby/enlist.png)](http://travis-ci.org/serby/enlist)

## Installation

    npm install -g enlist

## Usage

Start server

    enlist

## API

### Create list

#### Request

    POST /sub

    {
      "id": "1"
    }

#### Response

    {
      "url": "/sub/1",
      "from": "sub-1@enlist.org",
      "confirm": "true"
    }

### Subscribe to a list

#### Request

    POST /sub/1/paul@serby.net

#### Response
201

### Confirm a Subscription

#### Request

    PUT /sub/1/paul@serby.net

    {
      "hash": "<HASH>"
    }

#### Response
200

### See subscriptions

#### Request

    GET /email/paul@serby.net?hash=<HASH>

#### Response
201

### Remove from a list

#### Request

    DELETE /sub/1/paul@serby.net?hash=<HASH>

#### Response
2??

### Trigger an email

#### Request

    POST /sub/1

    {
      "message": "message goes here"
    }

#### Response
200

## Credits
[Paul Serby](https://github.com/serby/) follow me on twitter [@serby](http://twitter.com/serby)

## Licence
Licensed under the [New BSD License](http://opensource.org/licenses/bsd-license.php)
