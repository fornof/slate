---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - maml

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

#What is Maml?
What is Maml Pellet Feed ? 
Pellet feed is a set of words. A word is a set of notes and beats separated by // . 
a word can also be an actual word. 
>type  '' Hello World '' 

<aside class="warning">MAML is awesome!</aside>

```Maml
You can add beats to your notes. 
P is a quarter note (pie)
A is two eighths (Apple)
H is four sixteenths (Huckleberry)
L is 3 thirds (Lemonade)
```

(etc, see the pie game for more information)
>type '' helloo//PAPA ''

notes can also be inserted, the octaves split is on c, default octave is 3.

>type '' 4cdefgab5cdefgab6c//P '' 

it puts a quarter note on each of the notes. The beats are in a modulo of size, so if the beats are less than the notes, then the beat picker loops over and plays the next note in the loop.   

##Beats
Beats can be a number next to a comma or a named group of numbers:
>type '' aaaaa//8,16,12,7 ''

this plays a 5 times, with an 8th, a 16th, a 12th , and a 7th note.

##Rests
rests can be on notes or beats after the note or beat. They currently can only be heard when the midi is downloaded. 

>type '' 4c_defgab5c//8,4,8,4,8,4,8,4,8, ''

>this rests a 8th note, and then plays the rest of the notes. It turns the notes off, but keep the beat there. 

##Sharps and Flats
Sharps are '#', flats are '@' and come before the note. '#c' is a c sharp, #c_ is a rest note. 

>type cfl@t#harp//8,8,16,16, 

<aside class="aside">Horah! MAML is awesome!</aside>  



# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens
What is Maml Pellet Feed ? 
 Pellet feed is a set of words. A word is a set of notes and beats separated by // . 


/// maml documentation: 
This is a sentence. It is also a set of letters and lengths that make up a note and a beat when typed into maml. Hodge-podge notes can be played in a sort of noise this way. 
type  '' Hello World '' 
You can add beats to your notes. 
P is a quarter note (pie)
A is two eighths (Apple)
H is four sixteenths (Huckleberry)
L is 3 thirds (Lemonade)

(etc, see the pie game for more information)
type '' helloo//PAPA ''
notes can also be inserted, the octaves split is on c, default octave is 3, so this works:
type '' 4cdefgab5cdefgab6c//P '' 
it puts a quarter note on each of the notes. The beats are in a modulo of size, so if the beats are less than the notes, then the beat picker loops over and plays the next note in the loop.   

Beats: 
Beats can be a number next to a comma or a named group of numbers:
type '' aaaaa//8,16,12,7 ''
this plays a 5 times, with an 8th, a 16th, a 12th , and a 7th note.

Rests: 
rests can be on notes or beats after the note or beat. They currently can only be heard when the midi is downloaded. 
``` maml   4c_defgab5c//8,4,8,4,8,4,8,4,8, ''
this rests a 8th note, and then plays the rest of the notes. It turns the notes off, but keep the beat there. 

Sharps and Flats: 
Sharps are '#', flats are '@' and come before the note. '#c' is a c sharp, #c_ is a rest note. 
  type cfl@t#harp//8,8,16,16, 

```funkfuns
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

