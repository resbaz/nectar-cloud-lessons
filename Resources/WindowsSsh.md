# SSH with PuTTY

This is a two step process. 

* You need to prepare your key for use with PuTTY (a one off step)
* Then use the resultant prepared key with PuTTY

So follow the instructions below, step by step.

As ever, hold up a card as follows: 

* <span style="color:red">Red</span> = Won't you please, please help me!
* <span style="color:green">Green</span> = I'm done!

If PuTTY is not installed, follow the [installation instructions](../Prerequisites/Windows.md).

## Prepare your key for use with PuTTY

1. Fire up PuTTYgen (Start menu -> All Programs -> PuTTY->PuTTYgen)
2. Load an existing private key file by clicking the button marked "Load"
3. In the resultant "Load private key:" dialogue
   Change the drop down from "PuTTY Private Key Files (*.ppk)" to "All Files (*.*)"
4. Browse to the location of the private key you downloaded earlier (should have `.pem` extension)
5. Select your file and click "Open"
6. PuTTYgen should show a "Successfully imported foreign key..." dialogue. 
   If so, click the "OK" button.
7. You can now enter a descriptive comment if you so desire.
8. You can also enter and confirm a passphrase. 
   **Note:** If you use a passphrase you will have to enter this passphrase whenever you use the key.
9. Then click the "Save private key" button.
   **Note:** Make sure that you save it in a secure location. 
   By example a shared network drive is **not** a secure location!

## Use the prepared key with PuTTY

1. Run PuTTy (Start menu -> All Programs -> PuTTY -> PuTTY)
2. Open up the tree to the left to the "Auth" node (Connection -> SSH -> Auth)
3. Click the "Browse..." button below the label "Private key file for authentication"
4. In the resultant dialogue, find and select your prepared key then click "Open"
5. In the tree on the left select the "Session" node (you might have to scroll it up to see this node)
6. In the "Host Name (or IP address) edit box enter:
   `ubuntu@<The IP number of your running VM>`
   For example: `ubuntu@144.6.235.227` <- This is an example IP number, probably not yours!
   Here `ubuntu is the name of the user account on the remote machine that we are connecting as.  
7. Enter a name for the session in the "Saved Sessions" edit box, then click the "Save" button.
   This saves all your settings (including the private key), and allows you simply "Load" them the next time you
   run PuTTY. It's a convenience to save setup time.
8. Click the "Open" button to connect to your running VM.
9. On your first time connecting to a computer, you will be asked if you trust the computer you are connecting to.
   Ordinarily you can click "Yes".
   If you are connecting to a new computer is reusing an IP number that you used before you will also get this message.
   Ordinarily you can click "Yes".
10. You should now have a terminal session on your remote computer!
11. <span style="color:green">Green Card</span>!