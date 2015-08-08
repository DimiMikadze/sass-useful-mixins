# Sass useful mixins Media Queries, Font-size, Transition, Opacity, Background image, Font face, place holder, vertical align

Easy to use Sass useful mixins Media Queries, Font-size, Transition, Opacity, Background image, Font face, place holder, vertical align

## Features

- Media queries
- background-image
- Font-face
- Rem font size with px callback
- Transition
- Opacity
- place-holder color
- vertical-align

## Getting Started

````
include scss/_useful-mixins.scss in your sass project

sass --watch scss:css
````

for compressed output

````
sass --watch scss:css --style compressed
```

## Example Media Queries

````
#box {
	width: 1000px;
	height: 300px;
	border: 1px solid black;
	@include md-medium() {
		width: 500px;
	}
	@include md-small() {
		width: 300px;
	}
}
````

Output

````
#box {
  width: 1000px;
  height: 300px;
  border: 1px solid black; 
  }
  @media (min-width: 992px) and (max-width: 1199px) {
    #box {
      width: 500px; 
  	} 
  }
  @media (min-width: 768px) and (max-width: 991px) {
    #box {
      width: 300px; 
  	} 
  }
````

## Example Background image

````
#box {
	width: 1000px;
	height: 300px;
	@include background-image('stars.jpg', 0, 10%);
}
````

Output

````
#box {
	width: 1000px;
	height: 300px;
	background-image: url(../images/stars.jpg);
	background-position: 0;
	background-repeat: 10%; 
  }

````

## Example Font-Face

````
@include font-face("bpg_algeti", "bpg_algeti");
````

Output

````
@font-face {
	font-family: "bpg_algeti";
	src: url("../fonts/bpg_algeti.eot");
	src: url("../fonts/bpg_algeti.eot?#iefix") format("embedded-opentype"), url("../fonts/bpg_algeti.woff") format("woff"), url("../fonts/bpg_algeti.ttf") format("truetype"), url("../fonts/bpg_algeti.svg#bpg_algeti") format("svg");
	font-style: normal;
	font-weight: normal; 
}

````

## Example Font size in REM with PX callback

````
h1 {
	@include font-size(30px);	
}
````

Output

````
h1 {
  	font-size: 30px;
	font-size: 1.875rem; 
}

````

## Transition

````
#box {
	width: 1000px;
	height: 300px;
	background-color: #000000;
	@include transition('opacity: 1');
}
````

Output

````
#box {
	width: 1000px;
	height: 300px;
	background-color: #000000;
	-webkit-transition: "opacity: 1";
	-moz-transition: "opacity: 1";
	-ms-transition: "opacity: 1";
	-o-transition: "opacity: 1";
	transition: "opacity: 1"; 
}

````
## Cross browser opacity

````
#box {
	width: 1000px;
	height: 300px;
	background-color: #000000;
	@include opacity(0.5);
}
````

Output

````
#box {
	width: 1000px;
	height: 300px;
	background-color: #000000;
	opacity: 0.5;
	filter: alpha(opacity=50); 
}

````

## Example Placeholder Color

````
@include placeholder-color("#3388cc");
````

Output

````
::-webkit-input-placeholder {
	color: "#3388cc"; 
}

:-moz-placeholder {
	color: "#3388cc";
	opacity: 1; 
}

::-moz-placeholder {
	color: "#3388cc";
	opacity: 1; 
}

:-ms-input-placeholder {
	color: "#3388cc"; 
}

````

## Example Vertical Align

````
#box {
	width: 500px;
	height: 500px;
	border: 1px solid black;

	#vertical {
		border: 1px solid black;
		width: 300px;
		@include vertical-align;
	}
}
````

Output

````
#box {
	width: 500px;
	height: 500px;
	border: 1px solid black; 
}
  #box #vertical {
	border: 1px solid black;
	width: 300px;
	position: relative;
	top: 50%;
	transform: translateY(-50%); 
}

````

## Contributing

contributions are more than welcome!

## License

See license.txt