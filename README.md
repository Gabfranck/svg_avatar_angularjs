# SvgAvatarAngularJs

by Gabriel Franck

SvgAvatarAngularJs  is an AngularJS module based on [SvgAvatar](https://github.com/Gabfranck/svg_avatar) allow us to use svgAvatar methods and add some directives. 


## Demo

No demo for now (coming soon).
[Here](http://embed.plnkr.co/lS0mFYevQgzXaiVnhiSJ/) is a link to the svgAvatar live demo.


## Installation 

Install it via npm :
```bash
npm install svg_avatar_angularjs
```

Include the svg_avatar_angularjs.js in your index.html :
```html
<script src="node_modules/svg_avatar_angularjs/svg_avatar_angularjs.js"></script>
```

and then include it to your app :
```javascript
app = angular.module('myApp',['svgAvatarAngularjs'])
```


## Usage

### Directives

#### svgAvatar

The svgAvatar directive allow us to easily display an avatar. 

##### Syntax

~~~html
<svg-avatar avatar-id="avatar_id" avatar="avatar_svg" avatar-width="50" avatar-height="50"></svg-avatar>
~~~

|Parameters| value | description|
|---|---|---|
|avatar-id | String | id for the svg element of the avatar to use getElementById(avatar_id) |
|avatar | String (Svg code) | svg code of the avatar |
|avatar-width | Int | width of the avatar |
|avatar-height | Int | height of the avatar |


### Methods

Before using methods you need to require the svgAvatarService in your controller, service ... : 
```javascript
app.controller('myController', function(svgAvatarService){
	// Your controller code
})
```

---

#### lib_json()

Return the content of the current avatar_lib.json (wich contains all svg parts of the avatar) in a JSON object

##### Syntax

```javascript
svgAvatarService.lib_json() //-> JSON object (content of avatar_lib.json by default)
```

---

#### stringify_avatar()

Return the value of an avatar converted to string, could be useful to store avatars into a database

##### Syntax

```javascript
svgAvatarService.stringify_avatar(avatar_json) //-> String (avatar)
```

|Parameters| value | description|
|---|---|---|
|avatar_json | JSON Object | the avatar value in json |

---

#### render_svg()

Return an avatar svg value in string

##### Syntax

```javascript
svgAvatarService.render_svg(avatar) //-> SVG String (avatar_svg)
```

|Parameters| value | description|
|---|---|---|
|avatar | Object or String | the avatar value in json or in string |

---

#### random_avatar()

Generate a random avatar object

##### Syntax

```javascript
svgAvatarService.random_avatar() //-> Object (avatar)
```

---

#### render_random_svg()

Generate a random avatar in svg

##### Syntax

```javascript
svgAvatarService.render_random_svg() //-> SVG String (avatar_svg)
```

---

#### next_part_avatar() and previous_part_avatar()

Return an avatar object with a part changed (it loops when max value is reached)

##### Syntax

```javascript
svgAvatarService.next_part_avatar(avatar, part) //-> Object (avatar)
svgAvatarService.previous_part_avatar(avatar, part) //-> Object (avatar)
```

|Parameters| value | description|
|---|---|---|
|avatar | Object or String | the avatar value in json or in string |
|part|"forms","eyes","mouths","color1" or "color2"| the part to increment or decrement |

---

#### next_part_svg() and previous_part_svg()

Return an avatar in svg with a part changed (it loops when max value is reached)

##### Syntax

```javascript
svgAvatarService.next_part_svg(avatar, part) //-> SVG String (avatar_svg)
svgAvatarService.previous_part_svg(avatar, part) //-> SVG String (avatar_svg)
```

|Parameters| value | description|
|---|---|---|
|avatar | Object or String | the avatar value in json or in string |
|part|"forms","eyes","mouths","color1" or "color2"| the part to increment or decrement |


## Tests

There's no test for now.


## Build / Contribute

In order to make svgAvatarAngularsvg working with SvgAvatar you need to put the content of svgAvatar/bundle.js at the beginning of the code of svgAvatarAngularjs/svg_avatar_angularjs.js. 
Look at [this](https://github.com/Gabfranck/svg_avatar#tests) if you want to make a new bundle.js 