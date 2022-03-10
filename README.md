# ISSUE : 

Reproduce in :
OS : macOS (v12.1 ; v12.2.1)
Browser : chrome (v98; v99) , safari, firefox

Outline pass adding render issue effect.

# HOW TO REPRODUCE

At root, 
- Launch npm i (install modules)
- Launch npm start (launch web server at https://localhost:8080/)
Check the server url inside terminal 

[HTTP] server started on ::8080 for path: /Users/a.delforges/Documents/Dev/forked-three.js
[HTTP] available on:
[HTTP]    http://localhost:8080 -> server url
[HTTP]    http://127.0.0.1:8080
[HTTP]    http://192.168.1.17:8080
[HTTP] press CTRL-C to stop the server.

- Open Chrome at [serverurl]/examples/webgl_postprocessing_outline
- See incorrect results (black and white stripes on the building).

# HOW TO SHOW CORRECT RESULTS

- In ./examples/webgl_postprocessing_outline.html ; line 206 "composer.addPass( outlinePass );" comment this line to not add the pass to the postprocessing stack.
- See correct results (white building, no stripes).
- Cannot outline objects anymore

# EXPECTED RESULTS

- Outline pass should not add render issue effect (black and white stripes).
- Possibly related forum : https://discourse.threejs.org/t/special-effect-caused-by-outlinepass/25001/5 (tested on this project).


