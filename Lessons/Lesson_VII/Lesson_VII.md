# Lesson VII: Securing and maintaining your instance (45 min)


>  “Paranoid? Probably. But just because you're paranoid doesn't mean there isn't an invisible demon about to eat your 
> face.” ― Jim Butcher, Storm Front 

And it is a scary world out there: the minute you put a server onto the internet, automated scanners start probing it 
for weaknesses.

Experiment: Can we show a server being scanned/attacked in real time?



## Shared Responsibility Model

When it comes to security, NeCTAR follow the shared responsibility model.

That is: 

* NeCTAR will make a best effort attempt to look after the security of the cloud
* You will look after the security of the instances, images applications and content that you put onto the NeCTAR cloud.

Or put another way: NeCTAR manages the security **of** their cloud, you manage the security of the stuff you choose 
to put **in** that cloud. Hence the term "shared responsibility model"

What this really boils down to is that NeCTAR looks after the infrastructure, and you take final responsibility for
what you put up in the cloud.


*Q* Rather than editing the known_hosts file to remove entries that have knowingly changed, some people simply delete
the whole file. Do you think that this good practice?

Hold up a Red sticky note if you approve,
and a Green sticky note if you don't.

*A* You are hoping for a see of Greens here!

Ask random members of the audience for their opinions as to why they chose their answer.

The truth is that deleting the file is certainly very convenient, but that if there is any server with sensitive data
on it, then you really, really want to know if there is a man in the middle style attack in progress!

If there is a wide variance if answers, try to get the audience to debate it and then reask the question. Hopefully you
wil be able to move them to the green side of the answer spectrum. You might want to mention that foreign countries are
dead hot keen on research data (or movie companies on proof of piracy).

