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

Of course, your blinks will differ from those of your friends, family, or a stranger on the street. But more importantly, each spontaneous blink you make is unique [{% cite guttmannflury2023thesis %}].

Why is that?

Every time you spontaneously close your eyes, the upper eyelid doesn’t always need to fully close to lubricate the eye or to give your brain a quick break — so it often doesn’t. 

The upper eyelid is lazy like that.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Blink-comparison.gif" title="Blink comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Laurel and Hardy of blinks
</div>

Also, quick side note for the Bell's phenomenon fans out there. Unless you press on your eyeball while blinking, it won't move [<a href="https://royalsocietypublishing.org/doi/pdf/10.1098/rstl.1823.0017">1</a>，<a href="https://link.springer.com/article/10.1007/BF00154383">2</a>]. The effects of spontaneous blinks in EEG signals are mostly due to the muscle activity of the upper eyelid [<a href="https://doi.org/10.1016/j.clinph.2004.11.001">3</a>，<a href="https://doi.org/10.1073/pnas.1214804110">4</a>].


### Your blinks propagate on your head

Well, thanks Captain Obvious. Why does it matter?

A blink typically propagates smoothly, with signals gradually attenuating from the frontal electrodes (near the eyes) to the occipital electrodes. If this pattern deviates, we can use it to detect faulty electrodes (hint: the orange one on the picture).


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


### Blinks happen more often than they should

You probably have _not_ noticed that you are blinking at strategic moments [<a href="https://www.frontiersin.org/articles/10.3389/fnsys.2023.1242654/pdf">5</a>]. This behavior adjusts according to what you’re doing and your emotional state. For instance, when reading, you are more likely to blink at the end of a sentence or while turing a page. And perhaps counter-intuitevely, during conversations,  blink patterns don’t differ between sighted and congenitally blind people [<a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC510520/pdf/brjopthal00688-0001.pdf">6</a>]. 



---

## 🤔 What we don't know (yet) 🤔

### Is it _your_ head?

Can we use blinks to identify people? Link a "blinkprint".

Probably. The characteristics of blink propagation seem like a good starting point.


### Why refer to a blink a a "pulsar"?

Blinks have a distinctive, easy-to-detect shape and consistent characteristics, making them a potential tool for calibration. They're one of the few signals in the EEG that remain stable across sessions.


### What happens when something new appears during a blink?

I'm guessing the brain goes "Aaaaaaaaaah". But more importantly, _when_ does it process that new information? We need to understand this to avoid mistaking it for another signal or task.


### Are there differences between blind and sighted people?

Still only talking about blinks. 

It would be reasonable to assume that the visual evoked potential after the eye reopens is not present for blind people. However, the brain might be performing a "before-and-after" check with each blink, as if to make sure nothing unexpected — like a lurking predator — has appeared. If that’s the case, we might actually be detecting a "memory evoked potential," which could also occur in blind individuals.



---

