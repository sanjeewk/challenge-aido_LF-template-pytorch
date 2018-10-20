# AI Driving Olympics

<a href="http://aido.duckietown.org"><img width="200" src="https://www.duckietown.org/wp-content/uploads/2018/07/AIDO-768x512.png"/></a>


## Warning

The policy that ships with this template currently predicts the action as `[speed,steering angle]` and not `[speed left wheel, speed right wheel] `. You can still use this template. This just means that until we added the right inverse kinematics action wrapper, the submission will just make simulated donuts on the simulated road.
But since you're supposed to put your own model in here anyway, this shouldn't be that big of a deal.

## Quickstart

To make a submission,... 
    
1) Make sure you have the duckietown shell installed and updated:

        pip2 install --no-cache-dir --user -U duckietown-shell
    
    (Yes, I know it's Py2 for now... we are working on making it Py3-compatible too)

2) Clone this repo:

        git clone https://github.com/duckietown/challenge-aido1_LF1-template-pytorch.git

3) Change into the directory that you cloned:
    
        cd challenge-aido1_LF1-template-pytorch
        
4) Submit :)

        dts challenges submit
        
5) Once this finishes, you'll receive a link where you can follow the progress of your evaluation.


## Template "PyTorch template" for challenge `aido1_LF1-v3`

This is a template for one of the challenges in the [the AI Driving Olympics](http://aido.duckietown.org/).

The [online description of this challenge is here][online].

For submitting, please follow [the instructions available in the book][book].
 
[book]: http://docs.duckietown.org/DT18/AIDO/out/

[online]: https://challenges.duckietown.org/v3/humans/challenges/aido1_LF1-v3

## Description

This is a simple template for an agent that uses PyTorch/DDPG for inference.

[This code is documented here](https://docs.duckietown.org/DT18/AIDO/out/pytorch_template.html).

## How to change the model

Once you trained your own policy, check out line 20-45 of file [solution.py](solution.py#L20).

Basically, you need to copy your PyTorch network here (and probably replace the `model.py` file with one that contains your own model). And also copy the weights of the network you trained into the `models` directory.

Also include any gym wrappers if you included any during training (however, only observation/action wrappers, not reward wrappers).

Finally, change the code in `solution.py` line 20-45 to represent the steps to load your model and load the saved network weights and the wrappers.
