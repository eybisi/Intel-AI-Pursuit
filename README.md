This is writeup for Intel AI Pursuit challenge.Intel announced challenge at their "Intel Developer Zone" page 21 February.I completed it first but because of my country i cant get grand prize which is $1,5k laptop.

 www.sudo.city
 
![Alt text](https://i.hizliresim.com/BA1NDp.png)  

There will be total of 9 or 8 ciphers 


# Part 1 : Video

Initial post gave youtube video link : https://youtu.be/bXTjLZfibes

Video contains 3 parts of javascript code which will give us first cipher.

First part 00:07 -> ![Alt text](https://i.hizliresim.com/8d3XQr.png) 
Second 00:19     -> ![Alt text](https://i.hizliresim.com/N1dGl5.png)
Third 00:27      -> ![Alt text](https://i.hizliresim.com/VMGBPn.png) 

```
!function(a,b){
	function c(b,d){
		var e,f;
		if("."!=b[0]&&"/"!=b[0]) return a[b];
		if(d=d || "root",e=c.resolve(b),!e&&/\.json$/i.test(b)) return a("./"+c.basename(b));
		if(f=c.cache[e],!f)
			try
			{

				return a(b)
			}
			catch(g)
			{
				throw Error("failed to require "+b+" from "+d+"\n "+g.message+"\n "+g.stack)
			}
	return f.exports||(f.exports={},f.call(f.exports,f,f,exports,c.relative(e))),f.exports
	}
	c.cache={}
	c.basename=a("path").basename

	c.resolve=function(b)
	{
	var d,e,f,g;
	if("."!=b[0])return a.resolve(b);
	for(d="/"===b.slice(-1)?b:b+"/",e=[b,b+".js",d+"index.js",b+".json",d+"index.json"],f=0;g=e[f];f++)
		if(c.cache[g])console.log(g); return g
	}
	c.register=function(a,b)
	{
		//console.log(a)
		//console.log(b)
		c.cache[a]=b
		console.log(c.cache)
	}
	c.relative=function(a)
	{
		function b(b){
		var d,e,f,g,h;
		if("."!= b[0]) return c(b);
		for(d=a.split("/"),e=b.split("/"),d.pop(),f=0,g=e.length;g>f;f+=1)
			h=e[f],".."==h?d.pop():"."!=h&&d.push(h);
		return c(d.join("/"),a)
		}
		return b.resolve =c.resolve
		b.cache=c.cache,b
	}
	c.register("./video.js",function()
  {function d()
      {
      var a,b,c;for(myArr=["S","ud","o"],urArr=["c","it","y"],newStrng="",a=0;a<myArr.length;a++)newStrng+=myArr[a]; 					           for(a=0;a<urArr.lenght;a++)newStrng+=urArr[a];
      b=newStrng.slice(0,4),c=newStrng.slice(-4),console.log(b+"."+c)		}d()	
    }	),
		b.exports=c("./video.js")
}
(require,module);

 ```
Before executing `node file.js` you need to install video.js. ( npm install video.js)

AAAAND it will print  ```Sudo.city``` as output


# Part 2 : sudo city ?

Looks like sudo.city is website :)
We got leaderboard and register page for challenge.
Looking source code of page there is comments and display:none elements;

```<!-- ph'nglui mglw'nafh Cthulhu R'lyeh wgah'nagl fhtagn-->```
-> In his house at R'lyeh dead Cthulhu waits dreaming.

```<!-- y'ai’ng’ngah Yog-Sothoth h’ee-l’geb f’ai throdog uaaah -->```
-> We learn from the lovecraft wiki page that this is pray and Yog-Sothoth uses it to  ressurrect one from the dead.So Cthulhu being resurrected ? Spooky..

```<!-- London, 1857. A city of ill repute. A city of great excess. Here the black tower stands. -->```
-> I couldn't find any info related to this

```<!-- The singularity is approaching. -->```
->If you dont know what singularity means look it up. 

```<!-- The singularity is here. -->```

```<div style="display: none">2834303129203432362d33333831</div>``` 
-> ASCII HEX TO CHR = (401) 426-3381 Telephone number ?

```<!-- The singularity has passed. -->```

```<!-- Sierra, Hotel, India, Echo, Lima, Delta -->```
-> SHIELD ? 
# Part 3 : Spooky sounds

We got telephone number. 
https://scribie.com/files/c0022f7d93cc424b86cb30446c53cdcb9e56f7dd -> audio file from telesecretary
Calling number and you get message from telesecretary that says if you any question email to "deltainducers@gmail.com".
Hmm we emailed them if we can get any reply but no outcome.

# Part 4 : cyb3rpunk's n0t d34d

After googling "deltainducers" we get website. https://deltainducers.bandcamp.com/releases
We can see intel.com reference at the right side of the page.So we are sure that this is right place to be at.
There are 5 songs.What to do with them ? Hmm..
At the end of 2. track "Dark Dreaming" we hear a lot of "bip bip" sounds.Its interesting..
Using sonic visualizer : ![Alt text](https://i.hizliresim.com/MvbBbM.png)  
# Part 5 : who uses IRC in 2k17 LUL
 ec2-54-224-228-99.compute-1.amazonaws.com:6667#yakuzanet  ?? 
 6667 ? IRC port ! and yakuzanet is probably channel.
 
Using irssi on cygwin connecting to host : ![Alt text](https://i.hizliresim.com/0BaW7B.png)  
Typing `/list` command gives 2 channels and yakuzanet is here ![Alt text](https://i.hizliresim.com/4M3WkA.png)

Hmm what's up with second channel..(At the end of challenge it will turn out bad decision from organizers)

Joining YakuzoNet 

![Alt text](https://i.hizliresim.com/JlM83W.png)

Talking with the bot ![Alt text](https://i.hizliresim.com/jWarWj.png)

There is 6 pdf 1 mp4 file. 

From mp4 file : ![Alt text](https://i.hizliresim.com/5Q3EDA.png)


# Part 6 : Woah memories from childhood..Text based Dungeon games !
Website  http://www.cortexoverdrive.com/

This basically text based dungeon game with 26 rooms.

Now there is two approach to solution.One is solving it with pen&paper.Second one is cheating.You can go either way
If you want to cheat:
Look up source code.In order to solve, probably you need to go last room.
![Alt text](https://i.hizliresim.com/kWa7aW.png)

Looking controller js 
![Alt text](https://i.hizliresim.com/WQy8PY.png)

# Part 7 : Twitter page

https://twitter.com/cortexdevlog 

Now this is most frustrating step to complete.Twitter page have 4 pictures and you can see some text on clear area of each picture if you look carefully.
Hmmph.My eyes were bleeding at this step.You need to play with luminosity of pictures. ( i used paint.net for this)
Here best possible outcomes
![Alt text](https://i.hizliresim.com/5Q3EAA.png)
![Alt text](https://i.hizliresim.com/jWapPg.png)
![Alt text](https://i.hizliresim.com/AkvN2Q.png)
I dont even give 4th...No need to harm your eyes.. (like mine :( )

Like first step there are 4 fragments of code.There are arrays.Third one is clear = [ 35,72,65,76,73,88,75 ] == ? HALIXK

# Part 8 : FINAL

Wait what ? HALIXK ? ... Remember second channel on irc ?
![Alt text](https://i.hizliresim.com/lW8pLk.png)

This bot acts different.It lets you ask questions to it and answers them.After that you say "human" or "robot".It's a bit random process but in the end you get "hidden url" at the sudo.city domain.AAAND you are on the list..


![Alt text](https://i.hizliresim.com/jWapjr.png)


Thanks for reading










