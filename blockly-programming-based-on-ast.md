<h1> Blockly IDE in AST for mobile</h1>
---------------------------------------------------

<h2>Motivation</h2>

Click button and pressing key on PC is so convenience for most people.
However, in recent year, the input device is replaced with a touch screen, 
the mobile devices,  smartphone, pad are built without keyboard. 

Let we make an assumption, what if one day those input device like keyboard and mouse are gone ?
What if there comes a good idea in programming, and you want try it in instantly? But what you
bring is exactly a smartphone. 

That is the problem, technology estimates keyboard and mouse, what it leave is nothing but a touch screen.
When we coalesce our hand, the distance is much more bigger than the touch screen of smart phone. 
When we click something on the screen, there is not physical feed back like keyboard. there is no hint bar under F and J, that is, we do not know what we are touching.
Response time of touch screen is much longer than physical keyboard, since the input is translated in such path: touch-screen -> hit-test of position and component -> send key.

Now you realize that typing words on your smartphone is inconvenient. So you give up writing your idea into program right now. 

So, there must be something leak for the technique nowaday. 
Why does they remove keyboard?
Why not design a new IDE style without type any word?

That is the idea. 

Refer to [blockly](https://code.google.com/p/blockly/ "Blockly:A visual programming editor") we can see that there are lots of project use blockly as their front-end for user.

