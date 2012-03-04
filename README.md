##A  Better ATMega 128rfa1 Dev Board

See http://www.sparkfun.com/products/9734


Some of the complaints in the comments that I've started to address:

1) If you solder headers into the battery (for hitec connector), ISP,
and uart pins, you won’t be able to insert the ISP programmer
connector – there isn’t any room! If you use this, put your
battery/uart headers underneath your board. A bit silly, but no other
choice.  
[Moved the ISP header left, hopefully gives enough room]

2) With nothing connected but a fully charged 6V battery, this board still has bad voltage drops when turning on the transmitter. You must solder on a capacitor between ground and 3.3V or it won’t work. I put a 20uF tantelum on it, and the resets went away.
<br>[suggested 20uF tantalum in the C5 silkscreen]

4) The traces look like someone used Eagle CAD auto-route and called it a day, without doing much of any touching up.
<br>[Reduced number of vias by about 50%, made antenna signal lines straighter and kept them on top of the board, beefed up power and ground lines where I could]

My suggestion: get rid of the power jack and then by careful redesign a similar board can be made small enough to fit in a breadboard, maybe even cheap enough for some of the people complaining about the high price tag.
<br>[to do, but not sure that'll make it super small anyway]

Oh heck, if any of you guys at SparkFun are listening, here’s my wish-list for a hypothetical future revision of this board:
1) Drop the regulator, or make it an optional DIY addition.
<br>[You're populating your own board, drop away.  :]

2) Make all of the break out pins on the top and bottom aligned to a 0.1" grid.
<br>[All the pins on the side are aligned.  The three connectors at the bottom/end of the board should probably go up, not down]

3) Add a JTAG port in addition to the ISP port. Feel free to use a 0.05" pitch connector for the JTAG port is space is tight.
<br>[to do]

4) Add a U.FL connector (or at least the landing pattern for it) to the board, so that I can solder off the chip antenna and add a Real antenna without too much headache.
<br>[to do]

The result would be a more affordable and more desirable product. I'd by another one. Or two.

Thanks to JÃ¶rg Wunsch on avrfreaks.com, the problem is that the TST
pin is left floating. After connecting this pin to ground, reset and
power on reset works reliably.
<br>[added solderable/cuttable jumper "GND-TST"]
