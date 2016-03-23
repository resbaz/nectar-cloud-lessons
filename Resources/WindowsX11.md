# X11 with Windows

If Xming is not installed, follow the [installation instructions](../Prerequisites/Windows.md).

Then do the following.

Again, hold up a <span style="color:red">Red</span> card if you need help!

## Enable X11 forwarding in PuTTY

1. Run PuTTy (Start menu -> All Programs -> PuTTY -> PuTTY)
2. Load the previous settings that you saved.
   (Select the "Session" node in the tree on the left, 
   select your session name in the list,
   then hit the "Load" button.
3. Open up the tree to the left to the "X11" node (Connection -> SSH -> X11)
4. Check "Enable X11 forwarding"
5. In the "X display location" edit box enter:
   `localhost:0`
5. In the tree on the left select the "Session" node (you might have to scroll it up to see this node)
6. If you want to, enter a new name for the session with X11 forwarding enabled in the "Saved Sessions" edit box, 
   then click the "Save" button.
   This saves all your settings (including the private key), and allows you simply "Load" them the next time you
   run PuTTY. It's a convenience to save setup time.
8. Click the "Open" button to connect to your running VM.
9. You should now have a terminal session on your remote computer!
10. <span style="color:green">Green Card</span>!