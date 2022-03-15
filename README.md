# 158


we want to select the place of our choice and we also want to know which place we selected

We can highlight when the cursor goes on the image.


-------------------------------------------------------------
We need something that can help us to select an A-Frame entity element.
For this, A-Frame has a cursor component which provides hover and click states for interaction.

 cursor component listens to events such as mousedown, mouseup, mouseenter, mouseleave, and click events.
 --------------------------------
 In the index.html file we'll create the cursor entity as the child of the camera entity so that the cursor is always visible to us no matter where we look in the scene.
Also, we should put the cursor in front of the camera by placing it on the negative z-axis.

-------------------
To provide a shape/appearance to the cursor, we can use the geometry or material components.

id = camera-cursor 
cursor
 position = 0 ,0,-1
geometry="primitive: ring; radiusInner: 0.02; radiusOuter: 0.03"
● material="color: #fff; shader: flat"

-------------------------

Let's create a file which will contain all the cursor events.


CursorEvents.js
We'll create a cursor-listener component using the A-FRAME.register component( 'cursor-listener').



------------------
So what do we want to do when our cursor moves on the thumbnail?

we can change the color of the rings.
---------
So let's write a function which will handle the events defined on the A-Frame cursor.
Whenever the cursor is hovering over the entity, the mouseenter event is triggered.

As soon as the cursor is away from the entity, a mouseleave event is triggered.

Let's begin with writing a function, handleMouseEnterEvents().
Inside the function we'll add an event listener, mouseenter, which will continuously listen to the cursor movements.


--------
we have created thumbnails for places and assigned unique id to each of one them in our Tour.js file

We'll use those ids to check where our cursor is.
Let’s define a schema having selectedItemId as the data and write a function, handlePlaceListState(), which will check for the selected thumbnail’s id.


To check if the place is selected-
● First, we'll get the id using the getAttribute() function and
 store it in the constant variable
id.
● Then we'll create an array of all
the ids of the places and call it
placesId.
● Using the if condition we'll
check if the placesId list
contains the id.
● If the id is the same, then
using the
document.querySelector()
method, select the places-container entity and set the cursor-listener component for the entity.
Then we'll change the color of the selected thumbnail ring using the setAttribute() method and then call the function.



-----
You won’t be able to see the output.
The reason is, we need to set the cursor-listener event to the ring entity created for the border of the thumbnail inside the createBorder function (in Tour.js file).




 
