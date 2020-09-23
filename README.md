<div align="center">

## Text Slab Scroller


</div>

### Description

This shows you how you can dynamically scroll text using Javascript! It shows text (from Dear Abby) in a large text box. When you pass the mouse over (or click) the 'scroll up' or 'scroll down' link, the text in the text box scrolls in the proper direction.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mike McGrath](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mike-mcgrath.md)
**Level**          |Beginner
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |
**Category**       |[Controls/ Forms/ Graphics/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-graphics-menus__2-59.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mike-mcgrath-text-slab-scroller__2-1757/archive/master.zip)





### Source Code

```
<HTML><HEAD><TITLE>Slab Scroller Javascript &copy; Mike McGrath UK 2000</TITLE>
</HEAD>
<BODY BGCOLOR="silver">
<!-- To install Slab Scroller into your own page copy everything between the script tags -->
<!-- Paste the code into the BODY of your html document - note BODY section - not HEAD. -->
<!-- adjust the variable values and enter the content required in your scrolling area.  -->
<!-- Some experimentation with these values may be needed to suit your particular needs. -->
<!-- Add rest of content below the scroller area in a layer with a z-index value of 3 + -->
<SCRIPT TYPE="text/javascript">
<!-- Original: Mike McGrath  (mike_mcgrath@lineone.net) -->
<!-- Website : http://website.lineone.net/~mike_mcgrath/ -->
<!--
// adjust the position values here, and in the html, to suit your use
var pos=20;   // initial top position
var stp=10;   // step increment size
var spd=150;  // speed of increment
var upr=-450;  // upper limiter
var lwr=20;   // lower limiter
var tim;    // timer variable
var off_l=20;  // left offset
var off_t=20;  // top offset
var off_b=270; // bottom offset
var slb_w=300; // slab width
var slb_h=800; // slab height
var fnt_f="verdana"; // font name
var fnt_h="10pt";  // font size
var bgc_t="silver"; // top backgroundcolor
var bgc_b="silver"; // bottom backgroundcolor
var bgc_s="white"; // slab backgroundcolor
// enter the content of your scrolling area as slab_content here
var slab_content = ('<b>These are ACTUAL letters to "Dear Abby"</b><hr><P><br>Dear Abby, I have a man I never could trust. He cheats so much on me I\'m not even sure this baby I\'m carrying is his.<P><br>Dear Abby, I am a twenty-three year old liberated woman who has been on the pill for two years. It\'s getting expensive and I think my boyfriend should share half the cost, but I don\'t know him well enough to discuss money with him.<P>Dear Abby, I suspected that my husband had been fooling around, and when I confronted him with the evidence he denied everything and said it would never happen again.<P>');
slab_content+=('Dear Abby, Our son writes that he is taking Judo. Why would a boy who was raised in a good Christian home turn against his own?<P>Dear Abby, I joined the Navy to see the world. I\'ve seen it. Now how do I get out?<P>Dear Abby, I was married to Bill for three months and I didn\'t know he drank until one night he came home sober.<P>Dear Abby, My forty-year-old son has been paying a psychiatrist $50 an hour every week for two-and-a-half years. He must be crazy.<P>Dear Abby, I have always wanted to have my family history traced, but I can\'t afford to spend a lot of money to do it. Any suggestions? Signed, Sam Dear Sam, Yes. Run for public office.');
// top slab border
var divTop_content="";
// bottom slab border
var divBtm_content =('<HR><TABLE BORDER="0" WIDTH="100%"><TR><TD ALIGN="left"><A HREF="javascript://" ONMOUSEOVER="scroll_dn()" ONMOUSEOUT="no_scroll()"><B>SCROLL DOWN</B></A></TD><TD ALIGN="right"><A HREF="javascript://" ONMOUSEOVER="scroll_up()" ONMOUSEOUT="no_scroll()"><B>SCROLL UP</B></A></TD></TR></TABLE>');
if(window!=top)top.location.href=location.href;
msg="This page requires version 4 or later of\n Netscape Navigator or Internet Explorer"
dyn=(document.layers||document.all)?true:alert(msg);
nav=(document.layers);
iex=(document.all);
function scroll_dn(){
if(pos>upr)pos-=stp;
do_scroll(pos);
tim=setTimeout("scroll_dn()",spd);
}
function scroll_up(){
if(pos<lwr)pos+=stp;
do_scroll(pos);
tim=setTimeout("scroll_up()",spd);
}
function do_scroll(pos){
if(iex) document.all.divTxt.style.top=pos;
if(nav) document.divTxt.top=pos;
}
function no_scroll(){
clearTimeout(tim);
}
if(iex){
document.write('<DIV ID="divTop" STYLE="position:absolute; top:0; left:'+off_l+'; width:'+slb_w+'; height:'+off_t+'; background-color:'+bgc_t+'; z-index:2">'+divTop_content+'</DIV>');
document.write('<DIV ID="divBtm" STYLE="position:absolute; top:'+off_b+'; left:'+off_l+'; width:'+slb_w+'; height:'+slb_h+'; background-color:'+bgc_b+';font-size:'+fnt_h+'; z-index:2">'+divBtm_content+'</DIV>');
document.write('<DIV ID="divTxt" STYLE="position:absolute; top:'+off_t+'; left:'+off_l+'; width:'+slb_w+'; font-family:'+fnt_f+'; font-size:'+fnt_h+'; background-color:'+bgc_s+'; z-index:1">'+slab_content+'</DIV>');
}
if(nav){
document.write('<LAYER ID="divTop" position="absolute" top="0" left="'+off_l+'" width="'+slb_w+'" height="'+off_t+'" bgcolor="'+bgc_t+'" z-index="2">'+divTop_content+'</LAYER>');
document.write('<LAYER ID="divBtm" position="absolute" top="'+off_b+'" left="'+off_l+'" width="'+slb_w+'" height="'+slb_h+'" bgcolor="'+bgc_b+'" font-size="'+fnt_h+'" z-index="2">'+divBtm_content+'</LAYER>');
document.write('<LAYER ID="divTxt" position="absolute" top="'+off_t+'" left="'+off_l+'" width="'+slb_w+'" font-family="'+fnt_h+'" font-size="'+fnt_h+'" bgcolor="'+bgc_s+'" z-index="1">'+slab_content+'</LAYER>');
}
//-->
</SCRIPT>
</BODY></HTML>
```

