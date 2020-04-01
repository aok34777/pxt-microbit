# Puma RS Computer Shoe

In 1986, Puma and Dr Cavanagh from the University of Washington released the **RS Computer Shoe**, a computerized shoe that could measure the distance travelled and how many calories the runner had spent.

In this project, we will recrate the shoe using a few @boardname@.

What is RS shoe?
https://www.youtube.com/watch?v=BcrkoL_ZWHg

## How did the shoe work?

Patent 4,771,394
https://patentimages.storage.googleapis.com/57/a3/e9/b91d4c96cfb126/US4771394.pdf

In today's world, one can easily use GPS to measure precisely the distance travelled. Back in the 80ies, the engineers had to be more creative. At that time, they were able to build a shoe that could measure running time and a foot strike. They could count steps and time - just like in the @boardname@ step counter activity.

### How do you measure distance?

To compute the distance, the engineers relied on the relationship between stride time and running speed (The algorithm is described in the US patent 4,771,394 starting on line 65) column 6.). The faster you run, the faster your stride and the less time between foot strikes. The runner had to go through a calibration of the shoe and then it was able to estimate distance **without a GPS!**.


Assuming``T`` is the elapsed time, ``S`` is the number of foot strikes
and ``A``, ``B`` are constants that have been identified in the calibration phase, the 
speed ``V`` is computed as follows:

    V = A * T / S + B


Once the speed ``V`` is estimated and the running time ``T`` is known, then distance ``D`` can be calculated.

    D = V * T

### How do you measure calories?

The relationship between distance run and caloric cost is something referred to in the literature as “the oxygen cost of transport” or more simply “running economy” and, to a first approximation, once body weight is accounted for, is considered to be independent of speed.
 
There are actually many subtleties to this relationship (level of fitness, footwear, weather, change in elevation, individual running biomechanics and anatomy, some speed dependence at the higher running speeds -see Lacour-Bourdin attached) but the first approximation is that **the cost of running is 100 calories per mile** – and that this needs to be modified based on body weight (https://www.healthline.com/health/fitness-exercise/running-burn-calories-per-mile#per-mile ).

## Let's do it

The project is done in 3 phases. 

* [Measure the stride](/projects/puma-rs-computer-shoe/measuring-stride): collect data to determine the stride/speed relationship
* [Calibration](/projects/puma-rs-computer-shoe/calibration): analyse the data and identify the stride equation constants
* [Measuring distance](projects/puma-rs-computer-shoe/measuring-distance): build the shoe software that computes distance