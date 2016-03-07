# tool.js

Enclose some common js and some accidental function by myself

# Why

In order to finish homework which arraged by [ife](https://github.com/baidu-ife/ife).

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

## sizzle

Then let's get element by Id or other css selector

```
var a = $.$("#a");
var b = $.$(".b");
var c = $.$("[c]");
var d = $.$("[d=2016]");
```

caveat :  if you find a element ,It will return a HTMLdocumentElement while if you find elements it will return a Array;

like Jquery, you can find a element sheet by sheet

```
var a = $.$("#a .b");
```

```
var b = $.$("[aaa=bbb] .ccc #ddd");
```

## findElement

if you want find a Element 's child , you can use findElement

such as this layout

```
<ul class="a-list">
	<li>aaa</li>
	<li class="aaa bbb">bbb</li>
	<li>ccc</li>
</ul>
```

Now you get the ul element , however you need get the li with class of "aaa bbb"

```
$.findElement( "aaa" , ulElement , $.findByClass );
```

## getToday

return the date of today which take computer's time as standard

```
$.getToday(); // "2016-03-07"
```

## viewWidth[viewHeight]

return browser 's width[height] of view 

## addEvent

bind event(s)

```
$.addEvent( Element , event , handle );
```

you can bind same function on different events with namespace

```
$.addEvent( document , "click.a mousemove.b" , function() {
	console.log($.namespace);
} );
```

if you want unbind some event use the namespace like Jq

```
$.removeEvent( document , "mousemove.b" , [callback] );
```

## delegateEvent

if you want to delegate a Event

first example:
such as this layout
```
<ul>
	<div>sss</div>
	<li>ss</li>
	<li>aasa</li>
	<li>ss</li>
</ul>	
```

```
$ = new u();
window.onload = function () {
	var ul = $.$("ul");
	$.delegateEvent( ul , "li" , "click" , function () {
		console.info("Beind every successful time that is a lot of unsuccessful years");
	})
}
```

second example:
such as this layout
```
<ul>
	<div>sss</div>
	<li class="sa">ss</li>
	<li>aasa</li>
	<li class="sa">ss</li>
</ul>	
```

and you want to active event when just click tags with class of "sa".

```
$ = new u();
window.onload = function () {
	var ul = $.$("ul");
	$.delegateEvent( ul , "li.sa" , "click" , function () {
		console.info("Beind every successful time that is a lot of unsuccessful years");
	})
}
```

third example:
such as this layout
```
<ul>
	<div class="ab">sss</div>
	<li class="sa">ss</li>
	<li>aasa</li>
	<li class="sa">ss</li>
</ul>	
```

if you want to active event when you click different tags with different class.

```
$ = new u();
window.onload = function () {
	var ul = $.$("ul");
	$.delegateEvent( ul , "li.sa div.ab" , "click" , function () {
		console.info("Beind every successful time that is a lot of unsuccessful years");
	})
}
```

the delegateEvent is inherit by addEvent
so you also can use the namespace to bind event

```
$ = new u();
window.onload = function () {
	var ul = $.$("ul");
	$.delegateEvent( ul , "li" , "click.show" , function () {
		console.info("Beind every successful time that is a lot of unsuccessful years");
	})
}
```

Meanwhile you can use the undelegateEvent to unbind this event
And you can give a callback to execute

```
$ = new u();
window.onload = function () {
	var ul = $.$("ul");
	$.delegateEvent( ul , "li" , "click.show" , function () {
		console.info("Beind every successful time that is a lot of unsuccessful years");
	});

	$.undelegateEvent( ul , "click.show" , function () {
		console.log("unbind event is successful!!");
	});
}
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

Then you can make a typewriter effect

[demo](http://numerhero.github.io/assets/download/tool.js/typewriter-demo.html)

Meanwhile , I also provide more animate effect , such as

```
easeOut  	
number   
scale    
shake    
3d-rotate	
```

caveat: If the animate doesn't give param. It will be defalut effect.