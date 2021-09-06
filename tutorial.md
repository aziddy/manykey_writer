# ManyKey Writer
You're now ready to connect your new keyboard to your computer and program some useful functionality onto it!

If you haven't already, download the ManyKey Writer software <a href="https://github.com/epbarger/manykey_writer/releases">here</a>. Unzip the archive and run the app (macOS) or exe (Windows). Once the software is running, connect your new keyboard to a USB port on your computer. If you're on Windows, a driver dialog may pop up - let it do its thing.

Once you're ready, click the "Refresh Devices" button to populate the dropdown. In the dropdown, select your device - it is very likely to be identified as "Arduino Leonardo". If you do not see anything that looks like your device, try reconnecting your keyboard and restarting ManyKey Writer.

If everything has gone correctly, ManyKey writer will have loaded the current key configuration off your keyboard automatically, and should look like the screenshot below.

<img align="top" style="vertical-align:top" src="https://github.com/aziddy/manykey_writer/blob/master/media/writer_1.png?raw=true" width="300"/> 

Next, let's make the keyboard do something more than print out a single letter.

We've been using the Mac version of ManyKey Writer, so let's give our foot keyboard some macOS functionality. I'm going to set it up so that the left button switches between active apps, the middle button prints "abc", and the right button goes back in the browser. Here's what that looks like.

<img align="top" style="vertical-align:top" src="https://github.com/aziddy/manykey_writer/blob/master/media/writer_2.png?raw=true" width="300"/> 

The first line is defining the action for "Switch 0", which is the first switch we declared in the Arduino code. In this case, we know that is the left button. Our action is defined as "LEFT_GUI TAB". Actions are a list of keys separated by spaces. The complete list of compatible keys can be found here.

The second line is "a b c". This is telling the keyboard to press the "a", "b", and "c" keys all at once. It is not telling the computer to print "abc". This distinction is important. To illustrate this, take the example of setting the key to "a b c a b". This would also print "abc" on the computer while pressed, because the "a" and "b" keys can not be pressed twice at the same time.

The final line is pretty simple, "RIGHT_GUI LEFT_ARROW". This key combination will make most browsers on macOS go back.

With new key combinations entered, we can now write to the keyboard. Hit that "Write" button!

<img align="top" style="vertical-align:top" src="https://github.com/aziddy/manykey_writer/blob/master/media/writer_3.png?raw=true" width="400"/>

After clicking "OK", the software will automatically read the new configuration back from the keyboard. This will let you confirm that your commands were successfully saved. Everything you write to the keyboard is saved into special memory called EEPROM - this means your settings will persist even after disconnecting your keyboard from the computer.

What if you want your keyboard to control something that doesn't have a keyboard shortcut? You create a keyboard shortcut of course! Software like AutoHotkey (for Windows), or Karabiner (for macOS) can help you set up custom keyboard shortcuts. And once you have those, you should be good to go!
