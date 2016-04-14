# ForgeLisk
Become a Delegate and Forge LISK

How to become an Active Delegate for LISK
by MalReynolds from Bitcointalk


So you want to become a Lisk delegate and forge some Lisk.  Here’s what to do.


First, fund a Lisk account.  On the testnet, send joel a direct message on lisk.chat and ask that some test Lisk be sent to your account.  Otherwise, you bought some Lisk in the ICO before launch or at an exchange after launch.  


Next, go to the online Lisk web wallet at https://login.lisk.io/ , enter your passphrase, and pay the fee to register a Lisk delegate name.  Your lisk.chat name is a good choice.   Another good choice is to create a separate new delegate account and fund it with just a minimum amount from your main Lisk account.  


Go to www.putty.org and download Putty for Windows because you are not a Linux God...yet.  Note that you can copy a line from this cheat sheet, go to the putty window, do a right click and the copied text will show up in your server control window prompt.  Then you can just hit enter to execute the line.


Create a new Ubuntu 14.04 server at an VPS provider of your choice, such as DigitalOcean: https://m.do.co/c/8949111a23b1


Note the address of your server:  aaa.bbb.ccc.ddd.  Start putty and enter aaa.bbb.ccc.ddd into putty to start a putty session.  You should get a new window connected to your freshly created, brand new VPS now on the internet at aaa.bbb.ccc.ddd.


Log in as root and enter your server password (NOT your Lisk passphrase!) 


Consider doing some server security setup before proceeding.  Check out this article:
http://plusbryan.com/my-first-5-minutes-on-a-server-or-essential-security-for-linux-servers


To setup a Lisk delegate node, start copying and executing these lines with putty:


sudo apt-get install ntp
sudo service ntp stop
sudo ntpdate pool.ntp.org
sudo service ntp start
apt-get install unzip
wget https://downloads.lisk.io/lisk/test/lisk-0.1.4-Linux-x86_64.zip
cd lisk-0.1.4-Linux-x86_64
wget https://downloads.lisk.io/blockchain.db.zip
unzip blockchain.db.zip
bash lisk.sh autostart


Now in a new browser window  go to http://aaa.bbb.ccc.ddd:7000 , where the Lisk web client you just launched should display successfully (maybe after a brief boot-up time).  This shows your VPS is working and running a new instance of Lisk server software.


Back to the putty window:


bash lisk.sh stop
nano config.json


Use arrow keys to get down to the section:


"forging": {
  "secret" : []


Enter your Lisk passphrase IN QUOTATIONS between the brackets after “secret”


Ctrl+ X Then Y Then Enter to write your passphrase to config.json.  


Back to putty:


bash lisk.sh start


Try http://aaa.bbb.ccc.ddd:7000/ again, the Lisk web client should launch successfully again.  Open it up with the same passphrase you entered above, go to the forging section, and move the forging slider bar to “on”.  This lets the Lisk Active Delegate network know that your new node is now available as a Standby Delegate. 


Just because you clicked this button does not mean you are forging Lisk yet.


Your name must be in the top 101 at  https://explorer.lisk.io/delegateMonitor before you are actually forging Lisk. 


Now go solicit votes to get your delegate listed in these top 101 Active Delegates.  


Keep your VPS node running and updated while you solicit votes.


Once you are voted into this circle of top 101 delegates, you should have a green dot and uptime > 0%  at https://explorer.lisk.io/delegateMonitor within a half hour.

Congrats! You are forging Lisk as an Active Delegate!
