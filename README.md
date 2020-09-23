<div align="center">

## Simple analog/digital clock


</div>

### Description

This is an easy, yet cool analog/digital clock.

It's compatible with IE5+, NN6/Mozilla and Opera (without the digital part)

I hope you enjoy my script...

Please give some feedback...
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jeffman](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jeffman.md)
**Level**          |Advanced
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |
**Category**       |[Clocks](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/clocks__2-88.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jeffman-simple-analog-digital-clock__2-2812/archive/master.zip)





### Source Code

```
<script type="text/javascript">
// Made by Jeffrey Nieuwenburg - jeffman@dolfijn.nl
// Check out more javascripts at http://www.bestscripts.nl
for (i=0;i<60;i++){
	var angle = i * 6;
	var piangle = Math.PI - Math.PI / 180 * angle;
	var fromleft = 85 + Math.round(80 * Math.sin(piangle));
	var fromtop = 85 + Math.round(80 * Math.cos(piangle));
	document.write('<div style="position:absolute;left:'+fromleft+';top:'+fromtop+';cursor:default"><font face="Times New Roman" size="'+(i%5?3:4)+'">.<\/font><\/div>');
  if(i < 26){ // The pointers
	document.write('<div id="dot'+i+'" style="position:absolute;left:-10;top:-10;cursor:default;z-index:50"><font face="Arial" size="4">.<\/font><\/div>');
  }
}
	if (!window.opera) document.write('<div id="Digi" style="position:absolute;left:57px;top:0px;width:60px;height:15px;border:1px solid #DDDDDD;font:12px Arial;cursor:default;text-align:center"><\/div>');
function tick(){
	var now = new Date();
	var min = now.getMinutes();
	var hour = now.getHours();
	var sec = now.getSeconds();
  for(i=0;i<26;i++){
	var angle = (i < 10) ? Math.round(sec*6):(i<19)?Math.round(min*6):Math.round((hour*30)+((min/2)));
	var minus = (i<10)?0:(i<19)?10:19;
	var piangle = Math.PI - Math.PI / 180 * angle;
	var fromleft = 85 + Math.round(((i-minus)*8) * Math.sin(piangle));
	var fromtop = 85 + Math.round(((i-minus)*8) * Math.cos(piangle));
	document.getElementById("dot"+i).style.color = (i < 10) ? "green" : (i < 19) ? "blue" : "red";
	document.getElementById("dot"+i).style.left = fromleft+"px";
	document.getElementById("dot"+i).style.top = fromtop+"px";
 }
	if (!window.opera) document.getElementById("Digi").innerHTML = (hour<10?"0"+hour:hour)+":"+(min<10?"0"+min:min)+":"+(sec<10?"0"+sec:sec);
	setTimeout("tick()",1000);
}
	window.onload = tick;
</script>
```

