---
layout: page
title: Classical Music Generator
description: CS180 Artificial Intelligence, Fall 2021
img: assets/img/music_gen.jpg
importance: 3
category: Class
---
#### TL;DR:
 We present a classical music generator which can extend a given tune into complete music composition with melody and chords as accompaniments.
feat. HMM, MC, DBN, LSTM
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-4 mt-md-0">
        {% include figure.html path="assets/img/music_gen.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overall Architecture
</div>
In this work, we experimented with both
## Markov models 
We extend the melody using:
*  **Markov Chain** (1-3 orders)
*  **Dynamic Bayes Network** \\
where we exploit the correlation between features of one note: from MIDI note numbers (0-127) into scientific pitch notation (C0-G\#9)\\
e.g. Note G4: pitch name (sol) and pitch group (the fourth group) may have certain correlation given the evidence from the previous note, say A5. 
(Simplest intuition: choose G4 because G4 is closer to A5 than G5 )
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-4 mt-md-0">
        {% include figure.html path="assets/img/bn.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our Dynamic Bayesian Net.
</div>

We predict chords given melody using:
* **Hidden Markov Models**\\
where the hidden states are chords and evidence are melody, because chord progressions are the defining feature on which melody and rhythm are built.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/trans.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/ems.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    HeatMap of matrices in HMM.
</div>

We trained our HMM model using 490 classical musical compositions from Bach. From the above figures, we can detect some hidden patterns. For example, Bach preferred to use Major triads. We can read from the heatmap of the chords transition matrix that, whether the previous chord is a Major triad or a Minor triad, it is al- ways with a low probability for it to turn into a Minor triad.
## LSTM network	
Where we generate melody and chords together (i.e. multiple notes can be pressed at the same time step) via a multi-label classification objective.	

## Results
<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/markov.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-1">
        {% include figure.html path="assets/img/lstm.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Visualization of the generated music
</div>


