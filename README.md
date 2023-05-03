Download Link: https://assignmentchef.com/product/solved-cs174a-assignment-2
<br>
<h3><a id="user-content-repository-setup" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#repository-setup" aria-hidden="true"></a>Repository setup:</h3>

<ol>

 <li>By now you have followed the link to create your assignment repository <a href="https://classroom.github.com/a/epY4EPhl">https://classroom.github.com/a/epY4EPhl</a>. Please use this link once as it will create an repository we will not check for submissions if you use it multiple times. The repository name should lool like <strong>a2-githubusername</strong>. Any others will get removed.</li>

 <li>You should also be sure to share your GitHub username with us via this link if you have not already. <a href="https://forms.gle/Yne8PYVbfGp2vj6j9" rel="nofollow">https://forms.gle/Yne8PYVbfGp2vj6j9</a>

  <ul>

   <li>You should also be sure to setup your local git environment and ssh keys to work with GitHub.</li>

  </ul></li>

 <li>Once your repository is created you will have a copy of the assignment template in your github repository. Now you can clone the repository onto your local computer using the following command. Be sure do execute this command from the directory you wish to locate your work.</li>

</ol>

<ol start="4">

 <li>You can now follow the remaining steps of the assignment.</li>

</ol>

<h3><a id="user-content-gettting-started" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#gettting-started" aria-hidden="true"></a>Gettting Started:</h3>

Open the demo exactly as you did in Assignment 1: Run a dummy web server, navigate to the URL <code>localhost:8000</code>, observe the initial animation we provide, open Chrome developer tools, and perform the steps to map your local file folder as a Chrome workspace.

Note that Chrome might get a bit confused because you already did this before when you made a workspace for Assignment 1, in a different folder, with the same file names. You don’t want it to map to them by mistake. Delete all workspaces out of the “Filesystem” tab before you repeat step 4 from Assignment 1. In other words, you want new green dots from dragging in your Assignment 1 folder, not misleading ones still pointing at Assignment 1’s files.

At that point you’ll be safe to edit your files without your edits disappearing or changing the wrong files. Then, proceed as follows.

<h3><a id="user-content-preliminary-steps---using-the-code-library" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#preliminary-steps---using-the-code-library" aria-hidden="true"></a>Preliminary Steps – Using the Code Library</h3>

In order to use our library, <code>tiny-graphics.js</code>, you the programmer must provide additional code: Three custom JavaScript classes. Each of the three will be a subclass of a different base class from tiny-graphics.js: <code>Shape</code>, <code>Shader</code>, and <code>Scene_Component</code>. A <code>Shape</code> defines a 3D shape to draw, a <code>Shader</code> defines some code for coloring in triangles (perhaps as though they were illuminated by light sources), and a <code>Scene_Component</code> class tells the 3D canvas and web page what you want to happen (usually, drawing a scene by placing shapes). The three subclasses must define certain methods correctly for the library to work, or nothing will get drawn.

In order to get you started, we have provided TWO examples in your code of each of those custom subclasses, and you only have to tweak them to do this assignment. One of the Shapes we give, <code>Cube</code>, is complete, while the other, <code>Cube_Outline</code> is left empty for you to fill in.

The two scenes we provide you are both located inside the file <code>main-scene.js</code>. Of these two <code>Scene_Component</code> subclasses in there, the one called <code>Assignment_One_Scene</code> is incomplete and draws nothing, left for you to fill in. It contains necessary setup code that you will need for making the required scene for credit.

The other scene we provided in <code>main-scene.js</code> is a fully defined working example for you. The class, called <code>Transforms_Sandbox</code>, draws the extremely simple scene of boxes and balls you see when you initially run your Assignment 1 files. It is only thirty lines of code long, and exposes only the function calls that you need to see. It has the bare minimum to start using graphics to build a your first scene. Start your coding work there.

<h3><a id="user-content-experimenting-with-transforms_sandbox" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#experimenting-with-transforms_sandbox" aria-hidden="true"></a>Experimenting with Transforms_Sandbox</h3>

Inside the <code>display()</code> method of class <code>Transforms_Sandbox</code>, you will see some lines of code that call “<code>draw()</code>” on a particular shape, causing one of that shape to appear in the scene. You will also see other lines of code that modify a <code>model_transform</code> variable that contains a 4 by 4 matrix. These lines of code perform translations, rotations and scales — the main math operations you need to understand to get started with graphics. To call them, pass in a 3×1 vector (a <code>Vec</code>, or a regular JavaScript array of three floats). In the case of <code>rotation()</code>, a scalar (representing the angle in radians) must be also provided along with the <code>Vec</code> (representing the axis of rotation).

Read the code comments above the <code>Vec</code> and <code>Mat</code> classes in <code>tiny-graphics.js</code> to see how they work.

Note I: Only the <code>Vec.of()</code> function can generate new <code>Vec</code>s.

Note II: JavaScript has no operator overloading, so operations like <code>+, -, *, +=, *=,</code> etc. will not compile if you try to use them on the vector and matrix types (<code>Vec</code> and <code>Mat</code>). Instead use <code>times()</code> as shown in the <code>Transforms_Sandbox</code> class definition, and assign its return value back into your matrix to incrementally modify it. These can be chained together like so:

<a href="https://i0.wp.com/github.com/Luke-ZL/CS174A/blob/master/project2/a2-Luke-ZL/docs/image-0.gif?ssl=1" target="_blank" rel="noopener noreferrer"><img decoding="async" alt="image-0" data-recalc-dims="1" data-src="https://i0.wp.com/github.com/Luke-ZL/CS174A/raw/master/project2/a2-Luke-ZL/docs/image-0.gif?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

  <noscript>

   <img decoding="async" src="https://i0.wp.com/github.com/Luke-ZL/CS174A/raw/master/project2/a2-Luke-ZL/docs/image-0.gif?w=980&amp;ssl=1" alt="image-0" data-recalc-dims="1">

  </noscript></a>

Play with the code in <code>Transforms_Sandbox</code> and re-run your program until you are comfortable with the effects of changing numbers passed in to the transforms. Move around the calls to <code>draw()</code> to place new shapes. Put your operations into loops to draw lots of shapes and test your understanding of JavaScript.

Once you are comfortable with this, begin implementing the graded requirements below (a stack of cubes). You can paste code without issue from <code>Transform_Sandbox</code> to Assignment_One_Scene as long as it goes in <code>display()</code>, and you’ll want to move over to there before going any farther.

<strong>Your final scene must go in the <code>Assignment_One_Scene</code> class in order to be graded.</strong>

That class exposes its constructor to you, where you can see how it sets up the camera, lighting shader, and materials (which contain quantities related to how shapes and lights will interact), which are all defined there to help you do the actual assignment requirements.

In order to select the scene <code>Assignment_One_Scene</code> to display instead of <code>Transforms_Sandbox</code>, once you are ready to switch you must change your <code>index.html</code> file. Simply replace where the <code>Transforms_Sandbox</code> name appears with <code>Assignment_One_Scene</code>. It will draw that instead.

We have marked places in the code with “<strong>// TODO</strong>” to demark anywhere we intend for your final code to be in order to get points. All of these places you modify are inside the file <code>main-scene.js</code>.

<h3><a id="user-content-graded-steps" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#graded-steps" aria-hidden="true"></a>Graded Steps</h3>

<h4><a id="user-content-up-to-50-points-of-credit-there-is-no-partial-credit-any-individual-requirement" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#up-to-50-points-of-credit-there-is-no-partial-credit-any-individual-requirement" aria-hidden="true"></a>Up to 50 points of credit. There is no partial credit any individual requirement.</h4>

Implement the assignment in clean and understandable code. Each required part must successfully draw and show up onscreen in order to count.

NOTE: Please use the default camera definition defined in the <code>Assignment_One_Scene</code> class.

<strong>If any parts are unclear, ask on Piazza.</strong>

<h4><a id="user-content-point-distribution" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#point-distribution" aria-hidden="true"></a>Point distribution:</h4>

<ol>

 <li>Modify our template, which displays WebGL in an HTML canvas, without introducing errors – <strong>5 points.</strong></li>

 <li>Display a stack of eight (8) unit cubes starting from the origin and extending upward – <strong>10 points.</strong>Instance each of the eight cubes from the same geometry data (we defined this as “box” in your scene’s constructor function). Due to our other provided code in the constructor, the boxes will appear with a symmetric perspective projection, with square aspect ratio (not stretched or squeezed). The initial camera position at the given position (-5, 10, 30) is far back enough to view the scene. Note that to place a camera there is the opposite transform action that would be used to place a regular shape.</li>

 <li>Make the stack of boxes sway like a blade of grass in the wind. It should sway back and forth three times per second. Be exact if you can. Here is a GIF, slowed down. It shows other parts of the assignment completed as well.<a href="https://i0.wp.com/github.com/Luke-ZL/CS174A/blob/master/project2/a2-Luke-ZL/docs/image-1.gif?ssl=1" target="_blank" rel="noopener noreferrer"><img decoding="async" alt="image-1" data-recalc-dims="1" data-src="https://i0.wp.com/github.com/Luke-ZL/CS174A/raw/master/project2/a2-Luke-ZL/docs/image-1.gif?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

   <noscript>

    <img decoding="async" src="https://i0.wp.com/github.com/Luke-ZL/CS174A/raw/master/project2/a2-Luke-ZL/docs/image-1.gif?w=980&amp;ssl=1" alt="image-1" data-recalc-dims="1">

   </noscript></a>(a) Without passing through one another, the boxes must rotate over time to a maximum angle of <code>.04*Math.PI</code>. Place the hinge of each box’s rotation motion exactly at the top right edge of the box underneath it. Each box touches the previous in exactly the same way and remains in constant contact, precisely connected only by the correct edge. The boxes may not separate from each other along this edge; no floating geometry is allowed – <strong>10 points.</strong><pre><code>Hint: Remember that you can chain more than just one translation and rotation together when adjusting your transformation between drawing shapes. You might need to.</code></pre>(b) Fluidity of your rotation motion matters. Functions of the form <code>f(t) = a + b*sin(w*t)</code> are useful for modeling periodic motion, where “<code>a</code>” is large enough that the rotation angle does not go negative and cause boxes to collide. Use <code>graphics_state.animation_time</code> for <code>t</code>, which is how long the program’s been running in milliseconds – <strong>4 points.</strong>(c) Iteratively place the rest of the moving box segments on top of one another to complete the swaying motion. Use a hierarchical approach – each box’s transform is the “child” of the previous transform, derived from its matrix value – <strong>2 points.</strong><pre><code>Hint: To make structures that have a parent-child hierarchy like this, you must incrementally create your transform using `times()` to **post-multiply** each new term onto the right side of your matrix variable. Do this to incrementally change it from the value that drew the previous (parent) box. Never do a pre-multiply for this assignment; for certain reasons that's not as useful for designing structures that you think of as a hierarchy of shapes.</code></pre>You should learn to organize your code into functions, instead of describing your whole scene in <code>display()</code>. For part (c) we recommend moving your code for drawing one box into the blank <code>draw_box()</code> method, and then calling it many times from <code>display()</code> using a for loop. Changing the function signature (arguments) to <code>draw_box()</code> is allowed, since it may be necessary to know which box (numbered from bottom to top) you’re drawing for color purposes.(d) Fill in code inside your class method <code>make_control_panel()</code> to implement a button to help us with grading. To do this, call <code>key_triggered_button()</code> as already shown inside the method, and make sure the second argument is [ “m” ] so that we can press the m key to test your button. Fill in the third argument, the function that gets executed each button press, so as to make it toggle the swaying motion on and off. When the swaying is turned off, your blade of grass must be extended out to the maximum possible angle of <code>.04*Math.PI</code> so that we can see the gaps between your boxes along the left side – <strong>2 points.</strong></li>

 <li>(a) Color each box differently from the one underneath, for contrast. So that colors stay the same from one frame to the next, base your colors on persistent variables you store in your class, which means you’ll use the “this” keyword to declare them – <strong>7 points.</strong>(b) Fill in the <code>set_colors()</code> function to somehow cause your class’s colors to reset to different values. Once you do this, pressing the ‘c’ key (which already calls <code>set_colors</code>) should cycle the colors between the cubes – <strong>2 points.</strong></li>

 <li>Draw each cube’s outline (the edges) in white. For this, you will need to design a new <code>Shape</code> subclass. Fill in the empty parts we left in the <code>Cube_Outline</code> class, defined in your <code>main-scene.js</code> file. It will be like your <code>Cube</code>‘s definition above it, except with your own brand new arrays. Each vertex gets a position and a color (<code>colors</code> replaces <code>normals</code> in this example). Define the positions of your cube outline as x,y,z coordinates of the cube points. Order them in pairs, so that each pair is one edge of the outline. You may NOT have any extra edges going across diagonals. Set each color value in the <code>colors</code> array to full white – making sure the list has as many entries as the <code>positions</code> list. Do not make an indices list – instead use “<code>this.indexed = false</code>“.(a) To actually draw your outline, you will need to call <code>draw()</code> on it and pass in a material that is compatible with it. That’s because you just changed its available <code>Shape</code> fields to “positions” and “colors”, and so the type of <code>Shader</code> we use on it has to know what to do with that information. The variable we called “<code>this.white</code>” already holds such a proper, compatible material — so just pass that one in as your third parameter to <code>draw()</code> your outline. This should draw it using exactly the colors you made for it (white colors). Lastly, to actually draw lines instead of triangles (letting it know that there’s <strong>pairs</strong> of vertices instead of triples), you must pass in the string “LINES” as the fourth argument to <code>draw()</code> – <strong>6 points.</strong>(b) Rather than drawing your outline at all times, fill in code inside your class method <code>make_control_panel()</code> to implement another button. Call <code>key_triggered_button()</code> as shown, and make sure the second argument is [ “o” ] so that we can press the o key to test your button. Fill in the third argument, the function that gets executed each button press, so as to toggle a flag that you’ll use to turn the outline on and off. When the outline is off, draw the boxes normally (colors, lighting, etc.). When the outline is on, draw the outline instead on all boxes (it’s OK to skip doing this for the bottom-most box since it’s special, as explained below) – <strong>2 points.</strong></li>

</ol>

<h4><a id="user-content-extra-credit-each-can-be-attempted-individually-there-is-no-partial-credit-on-any-individual-extra-credit" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#extra-credit-each-can-be-attempted-individually-there-is-no-partial-credit-on-any-individual-extra-credit" aria-hidden="true"></a>Extra Credit: Each can be attempted individually. There is no partial credit on any individual extra credit.</h4>

I. Triangle strips are a common graphics primitive. Implement the very bottom box’s geometry as a single triangle strip primitive. This is like making a cube that can unfold into a single line of triangles.

Create a new <code>Shape</code> subclass with whatever correct entries in the <code>positions</code> and <code>indices</code> lists that will make that happen. Give each vertex a <code>normal</code> too that is simply equal to the position. When calling <code>draw()</code> to make this box, pass in the string “TRIANGLE_STRIP” for the fourth argument so that the graphics card uses triangle strip indexing. This box should appear lit up differently than the others, especially near edges as you move the camera around it, because of its unusual layout – <strong>5 points.</strong>

II. Scale your boxes so that instead of being unit cubes, they are stretched to 1.5x their length only along the Y axis. Adjust your translations accordingly so that the correct hinge contact points are maintained throughout the swaying motion. Again, no floating geometry is allowed. Neither are any shearing effects that deform the boxes to non-right angles during motion. Prepare your left-to-right chain of transformations accordingly for each separate shape so that those things cannot happen – <strong>5 points.</strong>

<h3><a id="user-content-submitting-assignment-1-on-github" class="anchor" href="https://github.com/Luke-ZL/CS174A/tree/master/project2/a2-Luke-ZL#submitting-assignment-1-on-github" aria-hidden="true"></a>Submitting Assignment 1 on GitHub:</h3>

<ol>

 <li>Once you are finished working it is time to ‘commit’ your work to your remote respository on GitHub. You will also want to do this periodically while you are working to make a backup of your work and to make your final submission. We will keep the process very simple by just ‘committing’ the master branch of your local repository into the remote repository on GitHub.</li>

 <li>The first step is to add any new files into the respository so they can be tracked.</li>

</ol>

<ol start="3">

 <li>Then we commit any new and or changed files to the repository. The text after the -m is for you to describe what is included in this commit to the respository.</li>

</ol>

<ol start="4">

 <li>Finally, we need to push these changes up to our remote repository on GitHub. This is a very important step! Without it you are not copying your work back to GitHub and we will not be able to see it if you forget.</li>

</ol>

<ol start="5">

 <li>You can repeat these commands as often as you feel the need as your work on your assignment. However, again, you must always make a final push to GitHub when you are finished in order to submit your work. We will make a clone of all of the assignment repositories at the deadline. That implies two things. First, make your final push to GitHub ahead of time and second, any pushes you make after the deadline will not be seen by us.</li>

</ol>

5/5 - (1 vote)

<pre>$ git clone <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="e2858b96a2858b968a9780cc818d8f">[email protected]</a>:intro-graphics-master-F19/a2-githubusername.git</pre>

<pre><span class="pl-v">M</span> <span class="pl-c1">=</span> <span class="pl-v">M</span><span class="pl-kos">.</span><span class="pl-en">times</span><span class="pl-kos">(</span> <span class="pl-v">T</span> <span class="pl-kos">)</span><span class="pl-kos">.</span><span class="pl-en">times</span><span class="pl-kos">(</span> <span class="pl-v">R</span> <span class="pl-kos">)</span><span class="pl-kos">.</span><span class="pl-en">times</span><span class="pl-kos">(</span> <span class="pl-v">S</span> <span class="pl-kos">)</span><span class="pl-kos">;</span><span class="pl-smi">this</span><span class="pl-kos">.</span><span class="pl-c1">shapes</span><span class="pl-kos">.</span><span class="pl-c1">box</span><span class="pl-kos">.</span><span class="pl-en">draw</span><span class="pl-kos">(</span> <span class="pl-s1">graphics_state</span><span class="pl-kos">,</span> <span class="pl-v">M</span><span class="pl-kos">,</span> <span class="pl-smi">this</span><span class="pl-kos">.</span><span class="pl-c1">clay</span><span class="pl-kos">.</span><span class="pl-en">override</span><span class="pl-kos">(</span><span class="pl-kos">{</span> <span class="pl-c1">color</span>: <span class="pl-s1">blue</span> <span class="pl-kos">}</span><span class="pl-kos">)</span> <span class="pl-kos">)</span><span class="pl-kos">;</span></pre>

<pre>$ git add <span class="pl-k">*</span></pre>

<pre>$ git commit -m <span class="pl-s"><span class="pl-pds">"</span>Description of what I did<span class="pl-pds">"</span></span></pre>