```json
{
	// Place your snippets for javascript here. Each snippet is defined under a snippet name and has a prefix, body and
	// description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the
	// same ids are connected.
	// Example:
	// "Print to console": {
	// 	"prefix": "log",
	// 	"body": [
	// 		"console.log('$1');",
	// 		"$2"
	// 	],
	// 	"description": "Log output to console"
	// }


  "log": {
    "prefix": "log",
    "body": "console.log($1)",
    "description": "console.log(...)",
  },
  "param": {
    "prefix": "param",
    "body": "\"$SELECTION:\", $SELECTION",
    "description": "labels selected variable in console.log",
    "scope": "source.js,text.html"
  },
  "clog": {
    "prefix": "clog",
    "body": "console.log(\"${1:data}:\", ${1:data})",
    "description": "create console.log command for a given variable",
  },
  "jlog": {
    "prefix": "jlog",
    "body": "console.log(\n  \"${1:data}\", JSON.stringify(${1:data}, null, \"  \")\n)",
    "description": "console.log(\"data\", JSON.stringify(data))",
  },
  "jsfy": {
    "prefix": "jsfy",
    "body": "JSON.stringify($SELECTION$1)",
    "description": "JSON.stringify(<SELECTION>)",
  },
  "jsp": {
    "prefix": "jsp",
    "body": "JSON.parse($1)",
    "description": "JSON.parse(...)",
  },


	"add": {
		"prefix": "add",
		"body": "classList.add(\"${1:className}\")",
		"description": "classList.add(\"<className>\")",
	},
	"ael": {
		"prefix": "ael",
		"body": "addEventListener(\"${1:mousedown}\", ${2:listener}, ${3:false})",
		"description": "addEventListener",
	},
  "dqs": {
    "prefix": "dqs",
    "body": "document.querySelector(\"${1:body}\")",
    "description": "document.querySelector(\"<selector>\")",
    },
  "dce": {
    "prefix": "dce",
    "body": "document.createElement(\"${1:div}\")",
    "description": "document.createElement(\"<tag>\")",
  },
  "qsa": {
    "prefix": "qsa",
    "body": "[].slice.call($1.querySelectorAll(\"$2\"))",
    "description": "slice.call.querySelectorAll(...)",
  },


	"com": {
		"prefix": "com",
		"body": "/**\n * ${1:component_filename}.jsx\n */\n\n\nimport React, { Component } from 'react';\nimport styled from 'styled-components'\n\n\nconst Styled${3:Component} = styled.${4:input.attrs(props => ({\n  type: \"text\"\n\\}))}`\n  background-color: #fee;\n`\n\n\nclass ${2:ComponentName} extends Component {\n  constructor(props) {\n    super(props)\n\n    this.method = this.method.bind(this)\n  }\n\n\n  method() {\n\n  }\n\n\n  render() {\n    return (\n      <Styled${3:Component}\n        ${5:placeholder=\"replace me with something useful\"}\n      />\n    )\n  }\n}\n\n\nexport default ${2:ComponentName}",
		"description": "template for styled component script",
	},
	"bind": {
		"prefix": "bind",
		"body": "this.${1:trigger} = this.${1:trigger}.bind(this)",
		"description": "binds a method to `this`",
  },


	"delay": {
		"prefix": "delay",
		"body": "function randomDelay(atLeast, randomness, callback) {\n  setTimeout(\n    callback\n  , Math.floor(Math.random() * randomness) + atLeast\n  )\n}",
		"description": "create randomDelay function",
	},
	"drag": {
		"prefix": "drag",
		"body": "$1.onmousedown = ontouchdown = startDrag\n\nfunction startDrag(event) {\n  var target = event.target\n  if (!target.classList.contains(\"$2\")) {\n    return\n  }\n  var clickX = event.pageX\n  var clickY = event.pageY\n  var startX = target.offsetLeft\n  var startY = target.offsetTop\n\n  $1.onmousemove = ontouchmove = drag\n  $1.onmouseup = ontouchend = stopDrag\n\n  function drag(event) {\n    target.$3 = startX - clickX + event.pageX\n    target.$3 = startY - clickY + event.pageY\n  }\n\n  function stopDrag(event) {\n\n    $1.onmousemove = ontouchmove = null\n    $1.onmouseup = ontouchend = null\n  }\n}",
		"description": "creates functions for dragging an element",
	},
	"dragsvg": {
		"prefix": "dragsvg",
		"body": "$1.onmousedown = ontouchdown = startDrag\n\nfunction startDrag(event) {\n  var target = event.target\n  if (!target.classList.contains(\"$2\")) {\n    return\n  }\n  var clickX = event.pageX\n  var clickY = event.pageY\n  var startX = target.offsetLeft\n  var startY = target.offsetTop\n  var left\n    , top\n    , transform\n\n  $1.onmousemove = ontouchmove = drag\n  $1.onmouseup = ontouchend = stopDrag\n\n  function drag(event) {\n    left = startX - clickX + event.pageX\n    top = startY - clickY + event.pageY\n    transform = \"translate(\" + left + \" \" + top + \")\"\n    target.setAttributeNS(null, \"transform\", transform)\n  }\n\n  function stopDrag(event) {\n\n    $1.onmousemove = ontouchmove = null\n    $1.onmouseup = ontouchend = null\n  }\n}",
		"description": "creates functions for dragging an SVG element",
	},
  "random": {
    "prefix": "random",
    "body": "function getRandom(array, maxIndex, dontRecycle) {\n  maxIndex = Math.min(array.length, maxIndex)\n  var random = Math.floor(Math.random() * maxIndex)\n  var value = array.splice(random, 1)[0]\n\n  if (!dontRecycle) {\n    array.push(value)\n  }\n\n  return value\n}",
    "description": "creates getRandom function",
  },
  "shuffle": {
    "prefix": "shuffle",
    "body": "function shuffle(array) {\n  var current = array.length\n    , swap\n    , random\n\n  while (current) {\n    random = Math.floor(Math.random() * current--)\n    swap = array[current];\n    array[current] = array[random];\n    array[random] = swap;\n  }\n}",
    "description": "creates shuffle function",
  },

	"elf": {
		"prefix": "elf",
		"body": "\n else if (${1:condition}) {\n  ${2:// action}\n}",
		"description": "else if (...) {...}",
	},
	"else": {
		"prefix": "else",
		"body": " else {\n  $1\n}",
		"description": "else {...}",
	},


	"ii": {
		"prefix": "ii",
		"body": "\r\nvar total = ${1:array.length}\r\nfor ( let ii = 0; ii < total; ii += 1 ) {\r\n  $2\r\n}\r\n",
		"description": "creates for loop",
	},
	"iii": {
		"prefix": "iii",
		"body": "for ( let ii = 0, total = ${1:array.length}; ii < total; ii += 1 ) {\n  $2\n}",
		"description": "creates for loop for an array",
	},
	"iife": {
		"prefix": "iife",
		"body": ";(function $1($2){\n})()",
		"description": "creates iife function",
	},


	"try": {
		"prefix": "try",
		"body": "try {\n  $1\n} catch (error) {\n  ${2:console.log(\"catch ERROR\", error)}\n}",
		"description": "try {...} catch (error) {...}",
	},


	"us": {
		"prefix": "us",
		"body": "/** $1 **\n *\n * $3\n */\n\n;(function $2(){\n  \"use strict\"\n\n  $4\n})()",
		"description": "create file header with \"use strict\"",
	},
  "hard": {
    "prefix": "hard",
    "body": "/// <<< HARD-CODED\n$SELECTION\n/// HARD-CODED >>>",
    "description": "wraps selection with <<< HARD-CODED >>>",
  }
}
```
