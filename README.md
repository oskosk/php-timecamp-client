#timecamp-php

A [Timecamp](http://www.timecamp.com/) PHP client. Presents returned data from the [Timecamp API](https://github.com/timecamp2/timecamp-api) JSON as associative arrays.

## Installation

```shell
$ composer require osk/timecamp-client
```

## Usage

```php

$timecamp = new Timecamp\Client("52253438676fd6dffe7a636f0e");
$entries= $timecamp->timeEntries(array(
  'from'=> '2015-06-01',
  'to'=> '2015-06-30'
));

// var_dump($entries);
foreach($entries as $v) {
  echo "$v[name]\n";
}

```

##Authentication

Authentication is very simple. You must pass your Timecamp API token when instantiating `Timecamp\Client`. Example:

```php
$client = new Timecamp\Client("52253438676fd6dffe7a636f0e");
```

To get your API token go to [your Timecamp Account Settings](https://www.timecamp.com/people/edit).

## Client methods

### Users

### users()

Return all users from account.

**Example**

```php
$users = $client->users();
// var_dump($users);
foreach($users as $v) {
  var_dump($v);
}
```

### tasks

### tasks($options)

Return all tasks If you want to get only one specific task you can provide a `'task_id'` key in `$options`.


### Time entries

####entries($options)

_Alias for `timeEntries($options)`_

####timeEntries($options)

Get time entries started in a specific time range.

* **$options** - Associative array
 * `'from'` - date range of the time entries returned.
 * `'to'` - date range of the time entries returned.
 * `'task_ids'` *(optional)* - array of tasks ids you can leave this option undefined, so it will get all tasks.
 * `'with_subtasks'` - *(optional)* - If set to `'1'` , get entries for all subtasks for provided one specific task_ids. **Default**: `'1'`.
 * `'user_ids'` - *(optional)* - Array of user ids. you can leave this option undefined, so it willl get all users

**Returns** an array of time entries associative arrays.

*Example*

```php
$entries = $client->timeEntries(array(
  'from'=> '2015-06-01',
  'to'=> '2015-06-30'
));
// var_dump($entries);
foreach($entries as $v) {
  var_dump($v);
}
```

## License

Distributed under the MIT License.

The MIT License (MIT)

Copyright (c) 2015 Oscar Lopez <oskosk@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

https://github.com/educoder/pest
https://github.com/guzzle/guzzle
https://github.com/Respect/Rest/
