## Operator Types, and the Create OP Dialogue
After the parameters window, the most used window in our Touchdesigner Program will be the `OP Create Dialog`.  
You can open the dialog by tapping `tab` on your keyboard, `RMB > Add Operator`, or `MMB` on a node's output. 

 If you want to be able to **search** for a specific node, your cursor is automatically placed in the search bar at the top of the dialogue box and will highlight all nodes that match your search, as you type it.
   
You can click, or tap `tab` to cycle through the colored labels near the top of the window to see different **Operator Families** available to you in Touchdesigner.

### TOPS
![Alt text](<1.5_Images/Screenshot 2023-07-16 220929.png>)

Let's take a second to get accustomed to what we are seeing here. You will automatically open up to a page full of purple buttons corresponding to nodes that you can produce in your node editor. You may also notice that some of the buttons are darker and some are lighter. **Dark nodes** produce new information in our scene, and lighter nodes manipulate information already in our scene** 

Right now we are looking at all of the TOPS or Texture Operator Family. All TOPS  are purple and will be your main method for working **with 2D images, in an RGBA format**. These are some of the most commonly used operators in Touchdesigner, especially for screen-based uses. If you ***hover*** your mouse over a button in the create dialog box, the grey box at the bottom of the window will fill with a short description of that node. 

In a few words, TOPs are responsible for 
 - importing/exporting all video and photos
 - Connecting to video recording devices 
 - rendering 3D scenes 
 - filters/direct RGBA control for all textures in your scene   

### CHOPS

![Alt text](<1.5_Images/Screenshot 2023-07-16 225647.png>) 

This is our **CHOP family** or **Channel Operator Family**. This family of operators is in charge of all of the important static and dynamic **values** available to us in Touchdesigner.    

CHOPS can be expressed as single values called `Timeslices` that show integers and floats at one point in time, or as `channels` that map a set of the same value on a graph, often with the x-axis as time since the program has started. 

Roughly CHOPs are responsible for 
- breaking down 2D and 3D scenes into multiple streams that can be manipulated individually
- sliders pattern makers, position data
- Controlling input from and output to **capture devices** like lidar, instruments, DAWS, pixel controllers etc.    

In Touchdesigner it is easy to interact with high-concept operators that have very complicated systems running behind the scenes, but it is equally valuable to be able to control simpler transformations in CHOPS that are **quick**. and can be the **building blocks** of larger systems in Touchdesigners

### SOPS
![Alt text](<1.5_Images/Screenshot 2023-07-16 235003.png>)

Onto the next **Operator family** are `SOPs, or Surface Operators`. These operators are our main tools to create 3D scenes. They can generate and 
edit objects in our 3D editor. This tool is very powerful, you can define particle systems, rearrange point cloud data, import and animate scenes and bones, and create generative 3D pieces. These are the operators usually used to ***DEFINE*** geometry, but in order to unlock their full potential, or even render them, we have to ***COMBINE*** the other operator families. SOPs are also one of the more CPU-intensive operations that Touchdesigner can perform, so overloading on SOPS, and complex SOP transformation can completely slow a scene.  

### DATS
![Alt text](<1.5_Images/Screenshot 2023-07-18 232825.png>)

DAT, or Data Operators are essential to getting good in Touchdesigner. These operators let you control a data stream, output, or calculation in a much more concise and direct format than in any of the other three operators we have discussed. All traditional text editing in Touchdesigner will happen through a DAT. You can script in Python, write JSON files, write in C++, send and receive certain messaging protocols such as TCP, sockets and web servers. You can even do your large calculations in DATS, and convert back to other operator family formats like SOPS and TOPS. S

![Alt text](<Screenshot 2023-07-18 233757.png>) 

Without going into too much detail, you can see from the image above that in some cases, manipulation of a TOP or another DAT can come from external **floating DAT windows**. As you can see there is text to edit in those nodes, and you can edit within Touchdesigner quite easily, but those windows can be rather small, and editing on them isn't really that great. So I advise that you either edit from Touchdesigner's `Texport` (RMB + click on node >  edit in Textport) OR edit from your favorite Text editor, by [changing preferences](https://medium.com/partical.grt/how-to-use-external-text-editor-in-touchdesigner-touch-touchdesigner-tip-2-d7c4bed47c68).

### MATS 
![Alt text](<1.5_Images/Screenshot 2023-07-18 234932.png>)
 
MATs define a SOP's **material**, and can only be used in conjunction with a rendering system. They basically are the nodes that let you **create textures for 3D objects, and define how they react to light**. Some nodes will not render if a light isn't placed in your scene, and others will render regardless. MATs can accept TOPS for **color, bump, and normal maps**.


### Viewer Active Aside
- Viewer active is the star or `+` shaped button at the bottom right of all basic nodes, up until now, it hasn't been that useful, but Viewer active can speed up your workflow.
- It doesn't don't do much for TOPs
- For **Timeslice** CHOPS, the viewer active button turns your whole node into a `button` that you can drag and drop into certain arguments of the parameters window to create a quick **Python expression**. When you release from your drag you can click `chop reference``, and now whenever the CHOP value changes, the referenced parameter will change too. 

- For SOPS, the viewer active button will make the TV window in the middle of all of your SOPs a simple 3D workspace. You get to pan, and orbit around your scene, see wireframes/ normal directions, and a HUD with polycount.  The orbiting and panning will also affect your camera object in real-time.
- For DATS, viewer active is the only way you can interact with a typed script, but most people don't use that so it's fine 

### COMPs
![Alt text](<1.5_Images/Screenshot 2023-07-19 193017.png>)

Comps are where stuff gets crazy. COMPs stand for 'components' and they are great because they allow you to make full use of **layering** your Touchdesigner file. **Comps allow you to place parts of your node network ***within*** other nodes** Typically this is done with the 'container' or 'base' comp, and by zooming as far as you can on a comp. This lets large, complicated parts of your node network be consolidated into a single operator, kind of like wrapping your network in a function. Not all COMPS come in handy at all times, in all truth this is one of the more obscure family of operators for me, but they are a big part of modularity and sharing in Touchdesigner. In short, you can make comment blocks in your network editor, simple GUI elements for your scene, lights and geometry compositing, and much more. They are like modifying the actual flow of the program.

While we are still on the topic of 'layers', this is a good time to mention that **everything you have seen in your network editor so far has been inside of a Container COMP**, go ahead, and try zooming out as far as you can.  

The text bar directly above your node editor has gone from 

![Alt text](<1.5_Images/Screenshot 2023-07-19 194841.png>)  

to 
 
 ![Alt text](<1.5_Images/Screenshot 2023-07-19 194914.png>)
 
 Meaning you have left the project1 node. This **path** will change based on what layer you are currently editing in; and can make referencing nodes on different layers much easier.

 With the Create Dialog op open, start typing **null**, and click the null button. Now that it's in your scene, you can connect it to the default `movie file in` top from before. 
![Alt text](<1.5_Images/Screenshot 2023-07-16 220930.png>)

# Special topics 

 ## Ettiquite and Organization  
 
 Once you start building larger Touchdesigner files, you may notice it becoming hard to go back to very specific portions of your logic. Large and sprawling node networks can be hard to distinguish with little visual difference so here are some tricks to make your files more ***legible, organized, and efficient***  
 ### Wires / Reference / Bind
  - There are two main types of connection in Touchdesigner, wired connections between nodes `wired connections are for connecting nodes of the same family`  
  and `referenced connections` where a node or piece of data can be used as a parameter 
  ![Alt text](<Special-topics-diagnostics/Screenshot 2023-08-26 011610.png>)
 ### Annotate and color
 ![Screenshot 2023-07-25 220128](https://github.com/elugo1/Touchdesigner-Resources/assets/82634063/71c22454-6e6d-438b-9ccb-2cda021c2441)
 Annotations are one of the newly added, and most helpful features in Touchdesigner as it allows you to create **comments as you go**. Annotations sit behind everything in your network and allow you to **group together operators with similar functions** You can write a paragraph about how a particular set of operators works, just as you would with comments in code. When you move an annotation block, it will move all of the nodes that are sitting on top of it.  

  The Annotate tool is great but is even better with the use of **The node color tool* 
 
 Let's take a quick peek inside of a popular pallete operator: **Particles GPU** and see which of the two looks easier to follow. 
 ![Screenshot 2023-07-25 222442](https://github.com/elugo1/Touchdesigner-Resources/assets/82634063/b860af99-908f-4bd3-bf33-190b55ffd732)

 ![Screenshot 2023-07-25 221403](https://github.com/elugo1/Touchdesigner-Resources/assets/82634063/f27ec40d-d16c-4d60-889d-03a51338297a) 

 Particles GPU naturally comes with no colors added to the annotations, 
 #### We can add  additional color to nodes by tapping `C` to bring up the node color box in the bottom left > `LMB` on a node > `LMB` desired color on the `color picker`
![Screenshot 2023-07-25 223717](https://github.com/elugo1/Touchdesigner-Resources/assets/82634063/530b1f65-f0a5-478a-bd87-cc1ed5c05481) 
 ![Screenshot 2023-07-25 224222](https://github.com/elugo1/Touchdesigner-Resources/assets/82634063/dd2956b5-727a-425f-80c0-28456e3dc4fb)
As shown in the image above, color changes to **Annotations** make the whole node change color. On the right, we can see color changes made to all of our operator types making the border change to the corresponding color. 
 
 ### Null Operator 
 
