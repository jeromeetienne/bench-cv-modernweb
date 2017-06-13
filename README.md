# GOAL
- Bench how fast the web can go about image processing
- Example on filtering : convert2Grey + adaptativeThresholding
- Code this in multiple versions : webworkers - webassembly - gpu
- Then mix them together - determine which combinason is best

**STATUS**: in progress

i did a first experiment - it is barely working - no clear result yet - 
here is a [twitter thread](https://twitter.com/jerome_etienne/status/872503583681499136) about it

# Step1 Basic Demo - onecore-purejs
- read the webcam
- display the origianl image
- filter the image - use jsaruco function
- display the filtered image

[Demo on webcam](https://jeromeetienne.github.io/bench-cv-modernweb/onecore-purejs/onecore-purejs.html)

# Step2 Implement webworkers + jsaruco - multicore-purejs
- aka all normal javascript - no webassembly so more stable

[Demo on webcam](https://jeromeetienne.github.io/bench-cv-modernweb/multicore-purejs/multicore-purejs.html)

# Step3 Implement webassembly - onecore-wasm
- code in C the convert2Grey yourself first
- see about getting a horintal/vertical blur in C 
- then do a adaptative thresholding
- result must be the same as the jsaruco version


[Demo on webcam](https://jeromeetienne.github.io/bench-cv-modernweb/onecore-wasm/onecore-wasm.html) -
[Minimal on canvas](https://jeromeetienne.github.io/bench-cv-modernweb/onecore-wasm/minimal.html)


# Step4 Implement a gpu version
- convert2Grey may be done in shader
- horizontal/vertical blur may be done in shader
- which resolution for the texture ?
- how many passes ? 4 different shaders or larger ones ?

[Early version on webcam](https://jeromeetienne.github.io/bench-cv-modernweb/onecore-gpu/onecore-gpu.html)

# Step5 Mix them together
- what is possible ? what is buggy ?
- if all is running as expected, any combinaison would work. 
- it is a matter of picking the fastest
- so try and measure :)
