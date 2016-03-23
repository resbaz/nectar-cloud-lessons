# X11 with OSX

If XQuartz is not installed, follow the [installation instructions](../Prerequisites/OSX.md).

## Enable X11 forwarding in ssh

The ssh command simply needs another flag added to it.
 
```bash
ssh -i key.pem -X ubuntu@115.146.84.207
```

The `-X` enables X11 forwarding

So simply open a new ssh session to your remote server by re-issuing the ssh command you previously used, this time
with the  `-X` flag...

Now you can hold up a <span style="color:green">Green</span> card...