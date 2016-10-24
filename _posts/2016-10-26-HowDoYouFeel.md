---
layout: post
title: How Do You Feel?
---


How do YOU feel today? (No this is not what I'm learning at bootcamp)



<div id ="smile" width="1000px" height="750px">plz!</div>


<script type= 'text/javascript' src = 'https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.5/d3.min.js'> </script> 
<script src = 'https://rshap91.github.io/assets/d3.slider.js'></script>
<link rel="stylesheet" href="https://rshap91.github.io/assets/d3.slider.css" />  
<style>
	.d3-slider-vertical {
		border: 4px solid #582A17;
		background: #444444;
		;
	}
	.d3-slider-handle {
		width: 25px;
		height: 40px;
		transform: translate(-2.5px,0)
	}
</style>




<script>
var loc = [{'x': 350, 'y': 250}]
// as happiness goes up (--> smile) 
	// the startY and endY values will DECREASE (thus moving the edges of the mouth HIGER on the canvas)
	// and the curve y values will INCREASE (thus pull the center of the mouth DOWN on the canvas)
// as happiness goes down (--> frown)
	// the startY and endY values will INCREASE (moving the edges of the mouth LOWER on the canvas)	
	// and the curve y values will DECREASE (pullling the center of the mouth up)
// this is neutral (sVal = 50)
var Happiness = [{'startX': 280, 'startY': 320, 'endX': 430, 'endY': 320, 'curve1':{'x': 300, 'y':0}, 'curve2':{'x': 400, 'y':0}}]
var neutral = [{'startX': 280, 'startY': 320, 'endX': 430, 'endY': 320, 'curve1':{'x': 300, 'y':0}, 'curve2':{'x': 400, 'y':0}}]
var maxSmile = [{'startX': 280, 'startY': 300, 'endX': 430, 'endY': 300, 'curve1':{'x': 300, 'y':65}, 'curve2':{'x': 400, 'y':65}}]
var maxFrown = [{'startX': 280, 'startY': 340, 'endX': 430, 'endY': 340, 'curve1':{'x': 300, 'y':-65}, 'curve2':{'x': 400, 'y':-65}}]
var edgeScale = d3.scale.linear()
	.domain([0,100])
	.range([340,300])
var centerScale = d3.scale.linear()
	.domain([0,100])
	.range([-65,65])
var width = 800
var height = 600
// CREATE SVG CONTAINER
var container = d3.select('#smile').append('svg')
	.attr('width', width)
	.attr('height', height)
	.style('border', '1px dashed black')
	.style('position', 'fixed')
// MAKE THE FACE
var head = container.append('circle')
	.data(loc)
	.attr('cx', function(d){return d.x + 'px'})
	.attr('cy', function(d){return d.y + 'px'})
	.attr('r', '125px')
	.style('fill','yellow')
	.style('stroke', 'black')
	.style('stroke-width','1px')
var lEye = container.append('ellipse')
	.data(loc)
	.attr('cx', function(d) {return (d.x * 5/6) + 'px'})
	.attr('cy', function(d) {return (d.y * 5/6) + 'px'})
	.attr('rx', '30px')
	.attr('ry', '20px')
	.style('fill', '#FCFCFC')
	.style('stroke', 'grey')
	.style('stroke-width','1px')
	
	
var lPupil = container.append('ellipse')
		.data(loc)
		.attr('cx', function(d) {return (d.x * 5/6) + 'px'})
		.attr('cy', function(d) {return (d.y * 5/6) + 'px'})
		.attr('rx', '12px')
		.attr('ry', '18px')
		.attr('fill', '#602121')
var rEye = container.append('ellipse')
	.data(loc)
	.attr('cx', function(d) {return (d.x + (d.x/6)) + 'px'})
	.attr('cy', function(d) {return (d.y - (d.y/6)) + 'px'})
	.attr('rx', '30px')
	.attr('ry', '20px')
	.style('fill', '#FCFCFC')
	.style('stroke', 'grey')
	.style('stroke-width','1px')
var rPupil = container.append('ellipse')
		.data(loc)
		.attr('cx', function(d) {return (d.x + (d.x /6)) + 'px'})
		.attr('cy', function(d) {return (d.y - (d.y /6)) + 'px'})
		.attr('rx', '12px')
		.attr('ry', '18px')
		.attr('fill', '#602121')
var nose = container.append('path')
	.data(loc)
	.attr('d', function(d){return 'M' + String(d.x) +' '+  String(d.y - 20) + " L" + String(d.x+15) + ' ' + String(d.y + 25) +  ' L' + (d.x) + ' ' + (d.y+25)})
	.style('stroke-width', '5px')
	.style('stroke', 'black')
	.style('fill', 'none')
var mouth = container.append('path')
	.attr('id','mouth')
	.data(Happiness)
	.attr('d', function(d){
		var m = 'M' + String(d.startX) + ' ' + String(d.startY) + ' ';
		var c = 'C' + String(d.curve1.x) + ' ' + String(d.startY + d.curve1.y) + ' ' + String(d.curve2.x) + ' ' + String(d.endY + d.curve2.y) + ' ' + String(d.endX) + ' ' + String(d.endY)
		console.log(m)
		console.log(c)
		return m + c
	})
	.style('stroke-width', '3px')
	.style('stroke', 'black')
	.style('fill', 'none')
// make text
var header = container.append('text')
	.attr('x', width-270)
	.attr('y', 50)
	.style('font-size', '34px')
	.style('font-weight', 'bold')
	.text('Happiness Meter')
var happy = container.append('text')
	.attr('x', width-200)
	.attr('y', 125)
	.style('font-style', 'italic')
	.style('font-size', '24px')
	.attr('fill', 'green')
	.text('Happy')
var sad = container.append('text')
	.attr('x', width-180)
	.attr('y', 550)
	.style('font-style', 'italic')
	.style('font-size', '24px')
	.attr('fill', 'Red')
	.text('Sad')
// MAKE SLIDER USING D3.SLIDER 
var sliderDiv = d3.select('#smile').append('div')
	.attr('class', 'slider container')
	.style('height', '400px')
	.style('margin', '30px')
	.style('margin-bottom', '100px')
	.style('display', 'inline-block')
	.style('position', 'fixed')
	.style('left', '650px')
	.style('top', '110px')
	
var slider = d3.select('div').call(d3.slider().orientation('vertical').min(0).max(100).value(50)
	.on('slide', function(evt, sVal){
	console.log(sVal)
	Happiness[0].startY = edgeScale(sVal)
	Happiness[0].endY = edgeScale(sVal)
	Happiness[0].curve1.y = centerScale(sVal)
	Happiness[0].curve2.y = centerScale(sVal)
	mouth.data(Happiness)
	.attr('d', function(d){
		var m = 'M' + String(d.startX) + ' ' + String(d.startY) + ' ';
		var c = 'C' + String(d.curve1.x) + ' ' + String(d.startY + d.curve1.y) + ' ' + String(d.curve2.x) + ' ' + String(d.endY + d.curve2.y) + ' ' + String(d.endX) + ' ' + String(d.endY)
		console.log(m)
		console.log(c)
		return m + c
	})
})
	)
</script>


[http://bl.ocks.org/rshap91](http://bl.ocks.org/rshap91)
