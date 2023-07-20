## Operator Types, and the Create OP Dialogue
After the parameters window, the most used window in our Touchdesigner Program will be the `OP Create Dialog`.  
You can open the dialog by tapping `tab` on your keyboard, `RMB > Add Operator`, or `MMB` on a node's output. 

 If you want to be able to **search** for a specific node, your cursor is automatically placed in the search bar at the top of the dialogue box and will highlight all nodes that match your search, as you type it.
   
You can click, or tap `tab` to cycle through the colored labels near the top of the window to see different **Operator Families** available to you in Touchdesigner.

### TOPS
![Alt text](<1.5_Images/Screenshot 2023-07-16 220929.png>)

Let's take a second to get accustomed to what we are seeing here. You will automatically open up to a page full of purple buttons corresponding to nodes that you can produce in your node editor. You may also notice that some of the buttons are darker and some are lighter. **dark nodes produce new information in our scene, and lighter nodes manipulate information already in our scene** 

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

Without going into too much detail, you can see from the image above that in some cases, manipulation of a TOP or another DAT can come from external **floating DAT windows** . As you can see there is text to edit in those nodes, and you can edit within Touchdesigner quite easily, but those windows can be rather small, and editing on them isn't really that great. So I advise that you either edit from Touchdesigner's `Texport` (RMB + click on node >  edit in Textport) OR edit from your favorite Text editor, by [changing preferences](https://medium.com/partical.grt/how-to-use-external-text-editor-in-touchdesigner-touch-touchdesigner-tip-2-d7c4bed47c68).

### MATS 
![Alt text](<1.5_Images/Screenshot 2023-07-18 234932.png>)
 
MATS define a SOP'S ***material***, and can only be used in conjunction with a rendering system. They basically are the nodes that let you **create textures for 3D objects, and define how they react to light**. Some nodes will not render if a light isn't placed in your scene, and others will render regardless. MATs can accept TOPS for **color, bump, and normal maps**.


### Viewer Active Aside
- Viewer active is the star or `+` shaped button at the bottom right of all basic nodes, up until now, it hasn't been that useful, but Viewer active can speed up your workflow.
- It doesn't don't do much for TOPs
- For **Timeslice** CHOPS, the viewer active button turns your whole node into a `button` that you can drag and drop into certain arguments of the parameters window to create a quick **python expression**. When you release from your drag you can click `chop reference``, and now whenever the CHOP value changes, the referenced parameter will change too. 

- For SOPS, the viewer active button will make the TV window in the middle of all of your sops a simple 3D workspace. You get to pan, and orbit around your scene, see wireframes/ normal directions, and a HUD with polycount.  The orbiting and panning will also affect your camera object in real time.
- For DATS, viewer active is the only way you can interact with a typed script, but most people don't use that so it's fine 

### COMPs
![Alt text](<1.5_Images/Screenshot 2023-07-19 193017.png>)

Comps are where stuff gets crazy. COMPs stand for 'components' and they are great because they allow you to make full use of **layering** your Touchdesigner file. **Comps allow you to place parts of your node network ***within*** other node** Typically this is done with the 'container' or 'base' comp, and by zooming as far as you can on a comp. this lets large, complicated part of your node network, distilled to a single operation, kind of like wrapping your network in a function. Not all COMPS come in handy at all times, in all truth this is one of the more obscure family of operators for me, but they are a big part of modularity and sharing in Touchdesigner. In short, you can make comment blocks in your network editor, simple GUI elements for your scene, lights and geometry compositing, and much more.

While we are still on the topic of 'layers', this is a good time to mention that **everything you have seen in your network editor so far has been inside of a Container COMP**, go ahead, and try zooming out as far as you can.  

The text bar directly above your node editor has gone from 

![Alt text](<1.5_Images/Screenshot 2023-07-19 194841.png>)  

to 
 
 ![Alt text](<1.5_Images/Screenshot 2023-07-19 194914.png>)
 
 Meaning you have left the project1 node. This **path** will change based on what layer you are currently editing in; and can make referencing nodes on different layers much easier.

 With the Create Dialog op open, start typing **null**, and click the null button. Now that it's in your scene, you can connect it to the default `movie file in` top from before. 
![Alt text](<1.5_Images/Screenshot 2023-07-16 220930.png>)
