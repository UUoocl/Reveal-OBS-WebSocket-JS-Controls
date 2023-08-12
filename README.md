# Reveal-OBS-WebSocket-JS-Controls
a javaScript to connect Reveal Slides to OBS via webSockets

In OBS turn on the WebSocket Server. In the OBS menu choose “Tools → WebSocket Setting
Server”, then check the Enable WebSocket server.	

## OBS WebSocket Connection setup
2 steps are needed to connect the Reveal slides to OBS. 
Include the OBS-WebSocket javaScript library
Enter the OBS WebSocket Server settings
Enter the OBS WebSocket Server settings
Add a <data> element to the index HTML page. The element attributes are for the websocket IP address, Port number and Password.  

<data data-websocket-IP="localhost"  data-websocket-port="4455" data-websocket-password="xxxxxxxxxxxxxxxx"></data>

### Add the OBS Websocket library 
Insert a <script> element to link the OBS WebSocket library.
<script src="lib/reveal-obs-ws-events.js"></script>

In the Reveal Initialize section add the OBS WebSocket library name. 

code `
plugins: [RevealZoom, RevealNotes, RevealMarkdown, RevealHighlight, RevealOBSws],
`

## Configure slides
Reveal controls can be added to slides written in HTML or the Obsidian Markdown Advanced Slides plug-in.     

### slide commands
#### Slide change started event
Markdown
<!-- .slide: data-slide-changed="scene name" -->
HTML
<section data-slide-changed="scene name">

#### Slide change ended event
Markdown
<!-- .slide: data-slide-transitioned="scene name" - ->
HTML
<Section data-slide-transitioned="scene name">

#### Add a name to a slide
<!-- .slide: data-slide-name="scene name" -->


### Slide Fragment Commands

#### Fragment Shown
Add fragment events to the <div> element for the given fragment. 
Add fragment events to a Markdown file using these tags after a fragment
<!-- element class data-fragment-shown="scene name" -->
<!-- element class data-fragment-hidden="scene name  -->

