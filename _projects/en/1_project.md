---
page_id: project_1
layout: page
title: Blinks
description: A pulsar for EEG signals
img: assets/img/white_blink.jpg
importance: 1
category: work
related_publications: true
bibliography: other_papers.bib
---

## 🎓 What we know 🎓

### Every blink is different

Of course, your blinks will differ from those of your friends, family, or a stranger on the street. But more importantly, each spontaneous blink you make is unique.

How so?

Because every time you spontaneously close your eyes, the upper eyelid doesn't need to fully descend to lubricate your eyeball or pause your attention. So it just doesn't. 

The upper eyelid is lazy like this.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Blink-comparison.gif" title="Blink comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Laurel and Hardy of blinks
</div>

Also, quick side note for the Bell's phenomenon fans out there. If you don't press your eyeball with your finger when blinking, it won't move. The effects of blinks in EEG signals are primarily caused by the muscular activity associated with the movement of the upper eyelid [{% cite IWASAKI2005878 nakano2013blink %} ].

### Your blinks propagate on your head

Well, thanks Sherlock. How is that of interest?

Because we know how a blink _should_  propagate, with a smooth and gradual attenuation from the frontal electrodes (closest to the eyes) to the occipital electrodes. When this pattern deviates, we can identify a faulty electrode (the orange one). 


<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/blink_propagation.jpg" title="Blink propagation" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/bad_channel.jpg" title="Bad channel detection" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Using blink propagation to identify bad EEG channels.
</div>



## 🤔 What we don't know (yet) 🤔

### Is it _your_ head?

Can we use blinks to identify people? 

Probably. The characteristics of blink propagation seem like a good starting point.


### Why call a blink a pulsar?

With their easy-to-detect shape and well-known characteristics, blinks could serve as a calibration tool. They are one of the few signals that seem stable across sessions.


### What happens when something new appears during a blink?

I'm guessing the brain goes "Aaaaaaaaaah". But more importantly, is _when_ is it processed? We need to be sure we don't mistake it for another signal or task.


### Are there differences between blind and sighted people?

Still only talking about blinks. 

It would be reasonable to assume that the visual evoked potential after the eye reopens is not present for blind people. However, it could also be that the brain routinely checks the before versus after blink to ensure that a pesky lion did not suddenly appear from behind the bushes. 



---

