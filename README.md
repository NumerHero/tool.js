# tool.js
enclose some common js function 

# Why

In order to finish homework which arraged by [ife](https://github.com/baidu-ife/ife)

On the other hand, I want to strengthen my ability of using native js grammar.

# install

```
<script src="util.js"></script>
```

# Use

Before use we need instantiate a constructor

```
$ = new u();
```

And then let's get element by Id or other css selector

```
var a = $.$("#a");
var b = $.$(".b");
var c = $.$("[c]");
var d = $.$("[d=2016]");
```

# some accidental function

## typewriter

just like this layout

```
<div id="input" style="display:none;">owen love zyz</div>
<div id="output"></div>
```

and state some param

```
$ = new u();
$.typewriter({
	delay : 120,
	input : $.$("#input"),
	output : $.$("#output"),
	animate : "3d-rotate",
});
```

then you can make a typewriter effect

<a href="./typewriter-demo.html" target="blank"></a>

MeanWhile , I also provide some animate function such as

```
easeOut  	
number   
scale    
shake    
3d-rotate	
```

If the animate doesn't have value then It will be defalut effect