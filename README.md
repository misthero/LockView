# Lock View
Lock View is a <a href="https://foundryvtt.com/">Foundry VTT</a> module that gives the GM control over the zoom and pan capabilities of players, such as locking the zoom or pan, moving the canvas, or setting the view to a specified setting.<br>
The module was originally made as a companion app for my <a href="https://github.com/CDeenen/MaterialPlane">Material Plane</a> module, and to make play using a digital playmat, 
such as a horizontally mounted TV, easier.<br>
Over time, however, the module's features have expanded greatly, including many functions that can be useful for digital play.<br>
<br>
The module has 6 main functions:<br>
<ul>
    <li><b>Autoscaling:</b> Scales the scene in various ways (horizontal fit, vertical fit, automatic fit, or scaled to a physical gridsize)</li>
    <li><b>Zoom lock:</b> Locks the zooming of the scene to prevent the user from (accidentally) messing up the autoscale</li>
    <li><b>Pan lock:</b> Locks the panning of the scene. If you use physical minis you don't want to accidentally pan</li>
    <li><b>Bounding box:</b> Limit zoom and pan to stay within a bounding box</li>
    <li><b>Force initial view:</b> After loading a new scene, the view is forced to the initial view (as set in the scene configuration menu), regardless of the position of tokens</li>
    <li><b>Viewbox:</b> Allows the GM to see what's shown on players screens, and allows the GM to control the pan and zoom of those players</li>
</ul>
'Autoscaling', 'Zoom Lock', 'Pan Lock', 'Bounding Box' and 'Force Initial View' can be set for each scene independently.<br>
'Zoom Lock', 'Pan Lock' and 'Bounding Box' can be enabled and disabled at any time using control buttons.<br>
These functions can be applied to selected connected players (must be set in the GM's module settings).<br>
<br>
<b>Note:</b> When 'Zoom Lock' or 'Pan Lock' are enabled, this module disables all zooming and/or panning functionality, regardless of who or what is requesting that zoom or pan. This means that, for example, modules that try to pan or zoom won't work.

## Usage
### Physical Play
When using a horizontally mounted screen, for the purpose of playing with physical minis, you should do the following:<br>
<br>
<b>GM's client, module settings:</b><br>
-Enable the module and viewbox for the player that is connected to the TV in the User Configuration screen<br>
<br>
<b>GM's client, scene configuration menu (for each scene):</b><br>
-Set 'Autoscale' to 'Physical Gridsize', which forces the TV's client to a specific zoom, ensuring the grid is always the same physical size<br>
-Enable 'Lock Pan' and 'Lock Zoom', which prevents the TV's client from accidentally zooming or panning<br>
<br>
<b>TV's client, module settings:</b><br>
-Set 'Gridsize' to the desired physical size of the grid. Usually 25 mm or 1 inch. Only fill in the number, not the units<br>
-Set 'Screen Width' to the physical width of your screen (the actual screen, without bezel). Must be in the same units as 'Gridsize'<br>
<br>
Refer to the 'Settings and Controls' section below to see how the GM can manipulate the view of the TV's client.

### Digital Play
The module can also be used when playing digitally (every player has their own computer). When doing so, you can ignore the following settings:<br>
-'Gridsize' and 'Screen Width' in the module settings<br>
-'Physical Gridsize' in the scene configuration menu (Autoscale option) and in the 'Set View' dialog box<br>
<br>
In the User Configuration screen, enable the module and viewbox for each player whose view you want to control/view.<br>
Refer to the 'Settings and Controls' section below to see how the GM can manipulate the view of the player clients.<br>
<br>

<b>Example for a static landing page or full screen 'splashscreen':</b><br>
Make sure the module is enabled for all players in the module settings.<br>
In the Scene Configuration:<br>
-Set 'Autoscale' to 'Automatic Fit'. You can choose either the inside (crops a part of the canvas to make it full screen) or outside option (shows the whole canvas,
but can show some padding)<br>
-Enable 'Lock Pan' and 'Lock Zoom'<br>
-Make sure 'Bounding Box' is disabled<br>
-Optionally enable 'Exclude Sidebar' and 'Blacken Sidebar' to make sure the sidebar isn't blocking part of the scene<br>
-Set the scene background color to black ('#000000')<br>

## Settings and Controls
### Module Settings
In the module settings, as a GM you will find a button to open the player configuration screen, where you can enable the module and viewbox for each player. By default, both are enabled for non-GM users.<br>
The module must be enabled for each player if you want to use any of the functions of this module, except for displaying the viewbox, which has its own enable setting.<br>
<br>
All connected players will also see two more settings which are only relevant if 'Autoscaling' is set to 'Physical Gridsize' (see below), as these settings allow the module to calculate the correct grid scale.<br>
<br>
The settings are:
<ul>
<li><b>Screen Width</b> - Fill in the physical screen width in mm or inch of the TV</li>
<li><b>Gridsize</b> - Fill in the desired gridsize in mm or inch (must be the same unit as 'Screen Width'). This is usually 25 mm or 1 inch</li>
</ul>

![moduleSettings](https://github.com/CDeenen/LockView/blob/master/img/examples/ModuleSettings.png)

#### Configure Initial View Position
By pressing the 'Congigure Initial View Position' button to the right of the 'Force Initial View' checkbox, a dialog box opens and a red box is drawn on the canvas. 
This red box corresponds with the 'Initial View Position' as set in the 'Ambience and Atmosphere' section of the 'Scene Configuration Screen'.<br>
Pressing the 'move' icon at the top left of the red box moves the box around while pressing the 'scale' icon at the right bottom scales the box.
<br>
<br>
In the dialog box, you'll find the following values and buttons:
<ul>
    <li><b>Old initial view position</b> - The old initial view position as it is currently set in the scene configuration</li>
    <li><b>New initial view position</b> - The new initial view position as displayed by the red box. These values are user editable</li>
    <li><b>Size in grid spaces</b> - The size of the view expressed in grid spaces. These values are user editable</li>
    <li><b>Set to physical gridsize</b> - Scales the 'new initial view position' to correspond with the physical gridsize as set in the module settings</li>
    <li><b>Set to player view</b> - By selecting the name of a player that's currently connected, you can set the initial view position to the view of that player by pressing 'Capture View'</li>
    <li><b>Snap to grid</b> - Snaps the 'new initial view poisition' to the grid. With the dropdown menu you can select which corner of the box should be snapped to the grid</li>
</ul>
<b>Note: </b>The displayed red box has the aspect ratio of the your (the GM's) screen. This does not necessary correspond to the aspect ratio of your players' view. The center of the red box
will correspond with the center of the players' view (it ignores the sidebar).
<br>
By pressing the 'Cancel', 'Save', or 'Close' button, you'll return to the scene configuration. Only when the 'Save' button is pressed the initial view position on the scene configuration will be updated.<br>
Don't forget to save the scene configuration to have the new settings take effect.

![SetInitialViewPosition](https://github.com/CDeenen/LockView/blob/master/img/examples/SetInitialViewPosition.png)

### Scene Settings
In the scene configuration screen, you'll find a new Lock View section with the following settings:<br>
<ul>
  <li><b>Pan Lock</b> - Initial 'Pan Lock' setting</li>
  <li><b>Zoom Lock</b> - Initial 'Zoom Lock' setting</li>
  <li><b>Bounding box:</b> Initial 'Bounding Box' settings</li>
  <li><b>Autoscale</b> - Automatically scales the screen</li>
  <li><b>Exclude Sidebar</b> - Exclude the area behind the sidebar from the bounding box or autoscaling. This can be enabled because the sidebar can obscure parts of the map</li>
  <li><b>Blacken Sidebar</b> - Blackens the background of the sidebar to prevent users from seeing outsie of the bounding box or canvas (only works if 'Exclude Sidebar' is enabled)</li>
  <li><b>Collapse Sidebar on Scene Load</b> - Collapses the sidebar when the scene is loaded, mainly useful in combination with 'Hide UI on Sidebar Collapse'</li>
  <li><b>Hide UI Elements on Sidebar Collapse</b> - Hides selected UI elements (such as the macro hotbar, scene navigation, etc) when the sidebar is collapsed, great for landing pages or splash screens. You can configure which elements to hide by pressing the 'cog' button next to the checkbox. By default all elements except for the sidebar are enabled.
  The 'Ctrl+u' hotkey can hide/unhide the elements in case they need to be accessed</li>
  <li><b>Force Initial View</b> - Forces the view to the 'Initial View Position' after loading the scene. Only works if 'Autoscale' is set to 'Off' or 'Physical Gridsize'</li>
  <li><b>Configure Initial View Position button</b> - The button is located to the right of the 'Force Initial View' checkbox. Pressing it opens the 'Configure Initial View Position dialog screen (see below)</li>
</ul>
Autoscale can be set to the following options:<br>
<ul>
<li><b>Off</b> - Autoscale disabled</li>
<li><b>Horizontal Fit</b> - Automatically scales the scene to fit the browser window. Horizontal fit, so it may cut off vertical parts of the scene</li>
<li><b>Vertical Fit</b> - Automatically scales the scene to fit the browser window. Vertical fit, so it may cut off horizontal parts of the scene</li>
<li><b>Automatic Fit (inside)</b> - Automatically chooses horizontal or vertical fit so no non-image background will ever be seen</li>
<li><b>Automatic Fit (outside)</b> - Automatically chooses horizontal or vertical fit so the full background can be seen, but can show the padding (area outside of the background image)</li>
<li><b>Physical Gridsize</b> - Scales the scene so the on-screen gridsize corresponds with a real world value (for example 25mm or 1"). The gridsize is determined by setting the 'Screen Width' and 'Gridsize' in the module settings. These settings are local, which means that they can be different for each connected client</li>
</ul>
<b>Note 1:</b> The 'Pan Lock', 'Zoom Lock' and 'Bounding Box' settings determine the initial settings. These are applied when a scene is loaded, or after closing the scene configuration screen. After that, you can enable or disable them by pressing the control buttons (see below).<br>
<b>Note 2:</b> 'Horizontal Fit', 'Vertical Fit', 'Automatic Fit' and 'Physical Gridsize' are applied when a scene is loaded, or after closing the scene configuration screen. After that, the player can zoom and pan around (if Zoom Lock or Pan Lock are disabled)<br>

![sceneSettings](https://github.com/CDeenen/LockView/blob/master/img/examples/SceneSettings.png)

### Control Buttons
On the left of the screen, there are new control buttons for the GM that display and toggle the current setting on the scene.<br>
From the top to the bottom:<br>
<ul>
<li><b>Set View</b> - Creates a dialog box with options to set the view, see below</li>
<li><b>Pan Lock</b> - Shows/switches the current state of 'Pan Lock'. If on, panning is disabled</li>
<li><b>Zoom Lock</b> - Shows/switches the current state of 'Zoom Lock'. If on, zooming is disabled</li>
<li><b>Bounding Box</b> - Shows/switches the current state of 'Bounding Box'. If on, zoom and pan are limited to the bounding box</li>
<li><b>Viewbox</b> - Draws a square on the canvas that shows what enabled players can see. The color of the square corresponds with the 'Player Color'</li>
<li><b>Edit Viewbox</b> - Allows the GM to edit the viewbox, and the players view. Right-click dragging drags the viewbox and pans all enabled players sceens, the scrollwheel increases or decreases the size of the viewbox and zooms the screen of all enabled players in or out. Additionally, two icons appear next to each viewbox which can be used to zoom or pan the view of individual players.</li>
</ul>

![controlButtons](https://github.com/CDeenen/LockView/blob/master/img/examples/ControlButtons.png)

#### Set View Dialog
After clicking the 'Set View' control button, a dialog box appears that gives multiple options to control the view of players. There's 2 dropdown menu's, and 3 number boxes<br>
<b>Top dropdown menu (X & Y movement)</b><br>
<ul>
<li><b>Reset to initial view</b> - Resets the view to the initial view position, as set in the scene configuration screen</li>
<li><b>Horizontal fit</b> - Scale and move the view so the scene fits horizontally</li>
<li><b>Vertical fit</b> - Scale and move the view so the scene fits vertically</li>
<li><b>Automatic Fit (inside)</b> - Automatically chooses horizontal or vertical fit so no non-image background will ever be seen</li>
<li><b>Automatic Fit (outside)</b> - Automatically chooses horizontal or vertical fit so the full background can be seen, but can show the padding (area outside of the background image)</li>
<li><b>Move grid spaces</b> - Moves the view in grid-units, relative to the current view. So setting X to 1 will move the view 1 gridspace to the right</li>
<li><b>Move to coordinates</b> - Moves the view to the absolute coordinates as set in the number boxes</li>
</ul>

<b>Bottom dropdown menu (Zooming)</b><br>
<ul>
<li><b>Ignore scale</b> - No zooming will occur</li>
<li><b>Set scale</b> - Zooms to the scale size set in the 'Scale' box</li>
<li><b>Reset scale</b> - Resets the zoom to the initial zoom factor, as set in the scene configuration screen</li>
<li><b>Physical gridsize</b> - Automatically scales the gridsize to make it correspond to a physical gridsize (in mm or inch), as set in the module settings </li>
</ul>

![setViewDialog](https://github.com/CDeenen/LockView/blob/master/img/examples/SetViewDialog.png)

## Bounding Box
The bounding box function limits how much a user can zoom or pan. It needs to be enabled, either in the scene configuration screen, or using control buttons. This function ensures that they always stay within a defined box.<br>
To enable the bounding box function on a scene load, you can enable the function in the scene configuration screen. The function can also be enabled on the fly by pressing the control button.<br>
<br>
By default this box is the canvas size (size of your background image), so users will not see the background color and padding.<br>
It is also possible to define a bounding box by drawing a rectangle (control buttons => drawing tools => draw rectangle). After drawing the rectangle, you can edit it (double clicking the rectangle) to set the rectangle as a bounding box. This can be done in the Lock View tab, where you have the following options:
<ul>
<li><b>Disabled:</b> The rectangle is not used as a bounding box</li>
<li><b>Owned Tokens:</b> Use the rectangle as bounding box if a token that's owned by the user is within the rectangle. You can set multiple rectangles to 'Owned Tokens'. Moving a token from one 'Owned Tokens' rectangle to another forces the view to the new rectangle. If you have multiple owned tokens in different 'Owned Tokens' rectangles, the bounding box will extend to fit all of these rectangles</li>
<li><b>Always:</b> The rectangle is always used as bounding box, also if no tokens are within the rectangle. This overrides all other rectangles. Only one rectangle should be set to 'Always'. If more rectangles are set to 'Always', only one is chosen</li>
</ul>

![drawingConfiguration](https://github.com/CDeenen/LockView/blob/master/img/examples/DrawingConfiguration.png)

## Viewbox
The viewbox is a function that allows the GM so see what users can see.<br>
If enabled (enable for the user in the User Configuration screen in the module settings, and enable the 'Viewbox' control button), 
a rectangle is drawn that corresponds with the view of the user. The color of the rectangle is the user color, and above the rectangle you can find the user name.<br>
<br>
It is possible for the GM to control the view of the users by enabling the 'Edit Viewbox' control button.<br>
If enabled, the GM can either control the view of all enabled users: pan by left-click dragging and zoom by using the scroll wheel.<br>
Or control the view of individual users by dragging the icons next to each viewbox that appear when the 'Edit Viewbox' control button is pressed: Drag the upper-left icon to pan, drag the lower-right icon to zoom.<br>

![viewBox](https://github.com/CDeenen/LockView/blob/master/img/examples/ViewBox.png)

<h1>Feedback</h1>
If you have any suggestions or bugs to report, feel free to contact me on Discord (Cris#6864), or send me an email: cdeenen@outlook.com.

<h1>Credits</h1>
<b>Author:</b> Cristian Deenen (Cris#6864 on Discord)<br>
<br>
If you enjoy using my modules, please consider supporting me on <a href="https://www.patreon.com/materialfoundry">Patreon</a>.

## Abandonment
Abandoned modules are a (potential) problem for Foundry, because users and/or other modules might rely on abandoned modules, which might break in future Foundry updates.<br>
I consider this module abandoned if all of the below cases apply:
<ul>
  <li>This module/github page has not received any updates in at least 3 months</li>
  <li>I have not posted anything on "the Foundry" and "the League of Extraordinary Foundry VTT Developers" Discord servers in at least 3 months</li>
  <li>I have not responded to emails or PMs on Discord in at least 1 month</li>
  <li>I have not announced a temporary break from development, unless the announced end date of this break has been passed by at least 3 months</li>
</ul>
If the above cases apply (as judged by the "League of Extraordinary Foundry VTT Developers" admins), I give permission to the "League of Extraordinary Foundry VTT Developers" admins to assign one or more developers to take over this module, including requesting the Foundry team to reassign the module to the new developer(s).<br>
I require the "League of Extraordinary Foundry VTT Developers" admins to send me an email 2 weeks before the reassignment takes place, to give me one last chance to prevent the reassignment.<br>
I require to be credited for my work in all future releases.
