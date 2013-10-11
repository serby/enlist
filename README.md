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

    POST /list

    {
      "id": "1",
      "confirm": "true"
    }

#### Response

    {
      "url": "/list/1",
      "from": "sub-1@enlist.org"
    }

### Subscribe to a list

#### Request

    POST /list/1/
    {
        "email": "paul@serby.net"
    }

#### Response
201

### Confirm a Subscription

#### Request

    PUT /list/1/paul@serby.net

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

    DELETE /list/1/paul@serby.net?hash=<HASH>

#### Response
2??

### Trigger an email

#### Request

    POST /list/1

    {
      "message": "message goes here"
    }

#### Response
200

## Credits
[Paul Serby](https://github.com/serby/) follow me on twitter [@serby](http://twitter.com/serby)

## Licence
Licensed under the [New BSD License](http://opensource.org/licenses/bsd-license.php)
