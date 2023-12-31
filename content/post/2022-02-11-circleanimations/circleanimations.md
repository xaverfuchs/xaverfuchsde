---
title: Circle Animations
author: Xaver Fuchs
date: '2022-02-20'
slug: circleanimations
categories: [art]
tags: [animation]
---

# Floating circles animation
This is a svg-based animation that uses randomness. Circles have a random starting point when loading the page and then move in a random-walk fashion across the screen. 

<svg style='height: 100%; width:100%; background-color:black' viewBox="0 0 600 600">
       <ellipse id="ellipse01" stroke="Red" stroke-width=12 fill="Red" fill-opacity="0.1"/>
       <ellipse id="ellipse02" stroke="Yellow" stroke-width=10 fill="Yellow" fill-opacity="0.2"/>
       <ellipse id="ellipse03" stroke="Green" stroke-width=8 fill="Green" fill-opacity="0.3"/>
       <ellipse id="ellipse04" stroke="Blue" stroke-width=6 fill="Blue" fill-opacity="0.4"/>
       <ellipse id="ellipse05" stroke="Magenta" fill-opacity="0"/>
       <ellipse id="ellipse06" stroke="Violet" fill-opacity="0"/>
       <ellipse id="ellipse07" stroke="White" fill-opacity="0"/>
       <ellipse id="ellipse08" stroke="Purple" fill-opacity="0"/>
       <ellipse id="ellipse09" stroke="RoyalBlue" fill-opacity="0"/>
       <ellipse id="ellipse10" stroke="SeaGreen" fill-opacity="0"/>
       <ellipse id="ellipse11" stroke="MediumBlue" fill-opacity="0"/>
       <ellipse id="ellipse12" stroke="Fuchsia" fill-opacity="0"/>
       <ellipse id="ellipse13" stroke="DeepPink" fill-opacity="0"/>
       <ellipse id="ellipse14" stroke="Orange" fill-opacity="0"/>
       <ellipse id="ellipse15" stroke="Chartreuse" fill-opacity="0"/>
       <ellipse id="ellipse16" stroke="Crimson" fill-opacity="0"/>
       <ellipse id="ellipse17" stroke="Gold" fill-opacity="0"/>
       <ellipse id="ellipse18" stroke="Lime" fill-opacity="0"/>
       <ellipse id="ellipse19" stroke="OrangeRed" fill-opacity="0"/>
       <ellipse id="ellipse20" stroke="SlateGrey" fill-opacity="0"/>
       <ellipse id="ellipse21" stroke="Red" fill="blue" fill-opacity="0"/>
       <ellipse id="ellipse22" stroke="Yellow" fill-opacity="0"/>
       <ellipse id="ellipse23" stroke="Green" fill-opacity="0"/>
       <ellipse id="ellipse24" stroke="Blue" fill-opacity="0"/>
       <ellipse id="ellipse25" stroke="Magenta" fill-opacity="0"/>
       <ellipse id="ellipse26" stroke="Violet" fill-opacity="0"/>
       <ellipse id="ellipse27" stroke="White" fill-opacity="0"/>
       <ellipse id="ellipse28" stroke="Purple" fill-opacity="0"/>
       <ellipse id="ellipse29" stroke="RoyalBlue" fill-opacity="0"/>
       <ellipse id="ellipse30" stroke="SeaGreen" fill-opacity="0"/>
       <ellipse id="ellipse31" stroke="MediumBlue" fill-opacity="0"/>
       <ellipse id="ellipse32" stroke="Fuchsia" fill-opacity="0"/>
       <ellipse id="ellipse33" stroke="DeepPink" fill-opacity="0"/>
       <ellipse id="ellipse34" stroke="Orange" fill-opacity="0"/>
       <ellipse id="ellipse35" stroke="Chartreuse" fill-opacity="0"/>
       <ellipse id="ellipse36" stroke="Crimson" fill-opacity="0"/>
       <ellipse id="ellipse37" stroke="Gold" fill-opacity="0"/>
       <ellipse id="ellipse38" stroke="Lime" fill-opacity="0"/>
       <ellipse id="ellipse39" stroke="OrangeRed" fill-opacity="0"/>
       <ellipse id="ellipse40" stroke="SlateGrey" fill-opacity="0"/>
</svg>


<script>
  //Script to randomize starting attributes
	function getRandomInt(min, max) {
  		return Math.floor(Math.random() * (max - min + 1) + min);
	}

  function getRandColor(brightness){

    // Six levels of brightness from 0 to 5, 0 being the darkest
    var rgb = [Math.random() * 256, Math.random() * 256, Math.random() * 256];
    var mix = [brightness*51, brightness*51, brightness*51]; //51 => 255/5
    var mixedrgb = [rgb[0] + mix[0], rgb[1] + mix[1], rgb[2] + mix[2]].map(function(x){ return Math.round(x/2.0)})
    return "rgb(" + mixedrgb.join(",") + ")";
  }

  shapes=["#ellipse01", "#ellipse02", "#ellipse03", "#ellipse04", "#ellipse05", "#ellipse06", "#ellipse07", "#ellipse08", "#ellipse09", "#ellipse10",
    "#ellipse11", "#ellipse12", "#ellipse13", "#ellipse14", "#ellipse15", "#ellipse16", "#ellipse17", "#ellipse18", "#ellipse19", "#ellipse20",
    "#ellipse21", "#ellipse22", "#ellipse23", "#ellipse24", "#ellipse25", "#ellipse26", "#ellipse27", "#ellipse28", "#ellipse29", "#ellipse30",
    "#ellipse31", "#ellipse32", "#ellipse33", "#ellipse34", "#ellipse35", "#ellipse36", "#ellipse37", "#ellipse38", "#ellipse39", "#ellipse40"];

  //add random startpoint and radius
  for (let i = 0; i < shapes.length; i++) {
      var shape = document.querySelector(shapes[i]);

      // random position and size
      cx_start = getRandomInt(0, 500);
      cy_start = getRandomInt(0, 500);
      rx_start = getRandomInt(10, 100);
      ry_start = getRandomInt(10, 100);
      shape.setAttribute("cx", cx_start);
      shape.setAttribute("cy", cy_start);
      shape.setAttribute("rx", rx_start);
      shape.setAttribute("ry", ry_start);

      //radnom color
      //stroke_start = getRandColor(5);
      //shape.setAttribute("stroke", stroke_start);
      //fill_start = getRandColor(0);
      //shape.setAttribute("fill", fill_start);

      //randomize stroke width
      if (i>3) {
        //stroke_width_start = getRandomInt(1, 100)/25;
        stroke_width_start = 2;
        shape.setAttribute("stroke-width", stroke_width_start);
      }

      //set stroke opacitiy
      shape.setAttribute("stroke-opacity", 0.85);

      //fill_opacity_start = getRandomInt(0, 50)/100.0;
      //shape.setAttribute("fill-opacity", fill_opacity_start);
    }

</script>

<script>
  // Script to manipüulate/randomize while website displayed
	function getRandomInt(min, max) {
  		return Math.floor(Math.random() * (max - min + 1) + min);
	}
  shapes=["#ellipse01", "#ellipse02", "#ellipse03", "#ellipse04", "#ellipse05", "#ellipse06", "#ellipse07", "#ellipse08", "#ellipse09", "#ellipse10",
    "#ellipse11", "#ellipse12", "#ellipse13", "#ellipse14", "#ellipse15", "#ellipse16", "#ellipse17", "#ellipse18", "#ellipse19", "#ellipse20",
    "#ellipse21", "#ellipse22", "#ellipse23", "#ellipse24", "#ellipse25", "#ellipse26", "#ellipse27", "#ellipse28", "#ellipse29", "#ellipse30",
    "#ellipse31", "#ellipse32", "#ellipse33", "#ellipse34", "#ellipse35", "#ellipse36", "#ellipse37", "#ellipse38", "#ellipse39", "#ellipse40"];

  //this could also be randomized
  //shapes_speed=[0.5, 0.5, 0.5, 0.5, 1, 1, 1, 1, 1, 1,
  //              1, 1, 1, 1, 1, 1, 12, 1, 1, 1,
  //              1, 1, 1, 12, 1, 1, 1, 1, 1, 1,
  //              1, 1, 1, 1, 2, 3, 4, 5, 6, 7,];
  shapes_speed=[];
  for (let i = 0; i < shapes.length; i++) {
    //newSpeed=getRandomInt(1, 100)/20;
    newSpeed=5*i/shapes.length+1;
    shapes_speed.push(newSpeed);
  }


  var rx_random = 1;
  var ry_random = 1;
  var cx_random = 1;
  var cy_random = 1;

  //var shape = document.querySelector("#ellipse1")

	setInterval(function() {
      for (let i = 0; i < shapes.length; i++) {
          var shape = document.querySelector(shapes[i]);
          var speed = parseFloat(shapes_speed[i]);
          //var shape = document.querySelector("#ellipse1");

          rx_random = Math.abs(shape.getAttribute("rx")*1.0 + getRandomInt(-100, 100)/250.0*speed);
    	  	shape.setAttribute("rx", rx_random);
          ry_random = Math.abs(shape.getAttribute("ry")*1.0  + getRandomInt(-100, 100)/250.0*speed);
          shape.setAttribute("ry", ry_random);
          cx_random = shape.getAttribute("cx")*1.0  + getRandomInt(-100, 100)/250.0*speed;
          shape.setAttribute("cx", cx_random);
          cy_random = shape.getAttribute("cy")*1.0  + getRandomInt(-100, 100)/250.0*speed;
          shape.setAttribute("cy", cy_random);
        }
	}, 50); //x ms
  function animate(time) {        // Animieren mit requestAnimationFrame
  }
</script>


