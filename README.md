<h1 align="center">Web clock</h1>

<h3 align="center">This program implements a simple clock implementation scheme, and there are two options for a web clock. Links to the design of the two versions of the project: <a href="https://heorhiizemlianko.github.io/Web-clock/clock%201%20variant/clock.html">1 Variant</a> , <a href="https://heorhiizemlianko.github.io/Web-clock/clock%202%20variant/clock.html">2 Variant</a>
</h3>

<p align="center">
  <img src="https://badges.frapsoft.com/os/v1/open-source.svg?v=103" >
</p>
<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original-wordmark.svg" title="html" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original-wordmark.svg" title="css" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" title="js" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/photoshop/photoshop-line.svg" title="photoshop" width="50" height="50"/>
</p>

## The goal of the work
The main goal of this project is to develop an effect that shows two variants of the clock.

## Task statement
<p>A simple experiment with <b>css and html as well as javascript</b>, showing the possibilities in two versions.</p>
<p>The demo implementation of the first version of the clock can be viewed again at this link:<a href="https://heorhiizemlianko.github.io/Web-clock/clock%201%20variant/clock.html"> <b>1 variant clock</b> </a></p>
<p>The demo implementation of the second version of the clock can be viewed again at this link:<a href="https://heorhiizemlianko.github.io/Web-clock/clock%202%20variant/clock.html"> <b>2 variant clock</b> </a></p>

## Schematic representation of the HTML structure
```
html
├── head
│   ├── meta
│   ├── title
├── body
│   └── div.clock
└── script
```

## Schematic representation of the CSS structure
```
css
├── body
├── .clock
├── .num
├── .hand
├── .sec
├── .min
└── .hour
```

## Code from the project of 1 variant
- HTML
```html
<!DOCTYPE html>
<html>
<!--Задаем название страницы и прикрепляем файлы-->
<head>
	<meta charset="utf-8">
	<title>JS Clock</title>
	<link rel="stylesheet" type="text/css" href="style.css">
</head>

<body>
	<!--Задаем переменные времение и теги где будут отображаться минуты, секунды и часы-->
	<div class="clock">
		<div class="hour">
			<div class="hr" id="hour"></div>
		</div>
		<div class="min">
			<div class="mn" id="min"></div>
		</div>
		<div class="sec">
			<div class="sc" id="sec"></div>
		</div>
	</div>
	<script type="text/javascript">
		const secDiv = document.getElementById('sec');
		const minDiv = document.getElementById('min');
		const hourDiv = document.getElementById('hour');

		setInterval(updateClock, 1000);

		function updateClock() {
			let date = new Date();
			let sec = date.getSeconds() / 60;
			let min = (date.getMinutes() + sec) / 60;
			let hour = (date.getHours() + min) / 12;

			secDiv.style.transform = "rotate(" + (sec * 360) + "deg)";
			minDiv.style.transform = "rotate(" + (min * 360) + "deg)";
			hourDiv.style.transform = "rotate(" + (hour * 360) + "deg)";

		}
	</script>
</body>

</html>
```
- CSS
```css
*{
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
body{
	display: flex;
	justify-content: center;
	align-items: center;
	min-height: 100vh;
	background: #68a546;
}
.clock{
	width: 350px;
	height: 350px;
	display: flex;
	justify-content: center;
	align-items: center;
	background: #fff url(clock.png);
	background-size: cover;
	background-position: center;
	border-radius: 50%;
	border: 20px solid #fff;
	box-shadow: inset 0 0 30px rgba(0,0,0,.1),
				0 20px 20px rgba(0,0,0,.2),
				0 0 0 4px rgba(255,255,255,1);
}
.clock::before{
	content: '';
	position: absolute;
	width: 15px;
	height: 15px;
	background: #848484;
	border: 2px solid #fff;
	z-index: 100000;
	border-radius: 50%;
}
.hour,.min,.sec{
	position: absolute;
}
.hour,.hr{
	width: 160px;
	height: 160px;
}
.min,.mn{
	width: 190px;
	height: 190px;
}
.sec,.sc{
	width: 230px;
	height: 230px;
}
.hr,.mn,.sc{
	display: flex;
	justify-content: center;
	position: absolute;
	border-radius: 50%;
}
.hr::before{
	content: '';
	position: absolute;
	width: 8px;
	height: 80px;
	background: #848484;
	z-index: 10;
	border-radius: 6px 6px 0 0;
}
.mn::before{
	content: '';
	position: absolute;
	width: 4px;
	height: 90px;
	background: #d6d6d6;
	z-index: 11;
	border-radius: 6px 6px 0 0;
}
.sc::before{
	content: '';
	position: absolute;
	width: 2px;
	height: 150px;
	background: #ff6767;
	z-index: 12;
	border-radius: 6px 6px 0 0;
}
```

## Code from the project of 2 variant
- HTML
```html
<!DOCTYPE html>
<html lang="en">
<link rel="stylesheet" href="style.css" type="text/css">
<head>
	<meta charset="UTF-8">
	<title>Analog Clock</title>
</head>

<body>
	<div class="clock">
		<div class="num num1">
			<div>1</div>
		</div>
		<div class="num num2">
			<div>2</div>
		</div>
		<div class="num num3">
			<div>3</div>
		</div>
		<div class="num num4">
			<div>4</div>
		</div>
		<div class="num num5">
			<div>5</div>
		</div>
		<div class="num num6">
			<div>6</div>
		</div>
		<div class="num num7">
			<div>7</div>
		</div>
		<div class="num num8">
			<div>8</div>
		</div>
		<div class="num num9">
			<div>9</div>
		</div>
		<div class="num num10">
			<div>10</div>
		</div>
		<div class="num num11">
			<div>11</div>
		</div>
		<div class="num num12">
			<div>12</div>
		</div>

		<div class="hand" id="sec">
			<div class="sec"></div>
		</div>
		<div class="hand" id="min">
			<div class="min"></div>
		</div>
		<div class="hand" id="hour">
			<div class="hour"></div>
		</div>
	</div>
	<script type="text/javascript" src="app.js"></script>
</body>

</html>
```
- CSS
```css
*{
	padding: 0;
	margin: 0;
	box-sizing: border-box;
	font-family: 'exo 2', sans-serif;
}
body{
	width: 100vw;
	height: 100vh;
	overflow: hidden;
	display: flex;
	justify-content: center;
	align-items: center;
	background: linear-gradient(45deg, #2ecc71, #16a085);
}
.clock{
	position: relative;
	width: 500px;
	height: 500px;
	border-radius: 250px;
	overflow: hidden;
	border: 10px solid #111;
	background-color: #fff;
}
.clock:after{
	content: '';
	position: absolute;
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	background: linear-gradient(285deg, rgba(0,0,0,0.175) 50%, rgba(0,0,0,0.1) 50%);
}
.clock:before{
	content: '';
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%,-50%);
	width: 20px;
	height: 20px;
	background-color: black;
	border-radius: 50%;
}
.num{
	position: absolute;
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	text-align: center;
	font-size: 2rem;
	font-weight: 700;
	padding: 18px;
}
.num:after{
	content: '';
	position: absolute;
	top: 0;
	left: 50%;
	transform: translateX(-50%);
	width: 5px;
	height: 15px;
	background-color: black;
}
.num1{
	transform: rotate(30deg);
}
.num1 div{
	transform: rotate(-30deg);
}
.num2{
	transform: rotate(60deg);
}
.num2 div{
	transform: rotate(-60deg);
}
.num3{
	transform: rotate(90deg);
}
.num3 div{
	transform: rotate(-90deg);
}
.num4{
	transform: rotate(120deg);
}
.num4 div{
	transform: rotate(-120deg);
}
.num5{
	transform: rotate(150deg);
}
.num5 div{
	transform: rotate(-150deg);
}
.num6{
	transform: rotate(180deg);
}
.num6 div{
	transform: rotate(-180deg);
}
.num7{
	transform: rotate(210deg);
}
.num7 div{
	transform: rotate(-210deg);
}
.num8{
	transform: rotate(240deg);
}
.num8 div{
	transform: rotate(-240deg);
}
.num9{
	transform: rotate(270deg);
}
.num9 div{
	transform: rotate(-270deg);
}
.num10{
	transform: rotate(300deg);
}
.num10 div{
	transform: rotate(-300deg);
}
.num11{
	transform: rotate(330deg);
}
.num11 div{
	transform: rotate(-330deg);
}
.hand{
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
.hand div{
	position: absolute;
	bottom: 50%;
	left: 50%;
	transform: translateX(-50%);
	background-color: #000;
}
.sec{
	width: 1px;
	height: 40%;	
}
.min{
	height: 38%;
	width: 4px;
	border-radius: 2px;
}
.hour{
	height: 28%;
	width: 8px;
	border-radius: 8px;
}
```
