# Branch Prediction and the Performance of Interpreters -
Don’t Trust Folklore

Link: [Document](https://hal.inria.fr/hal-01100647/document)

Hypothesis: 

> Interpreters have a fame of being slow, mainly due to the big switch statement at the core of the execution loop (dispatch) (_ I guess that other techniques such as subclassing and visitors just defer those branches to the class implementation_). Perhaps that is no longer the case, since branch prediction is much better in recent Intel architectures.

Notes:

- Seem to be focusing on bytecode interpreters, so it makes sense to assume a switch for dispatch.

- They review the last 3 intel processor generations to compare branch prediction. THe last one (Haswell) is orders of magnitude better in terms of MPKI than the first.

- MPKI: Mis-predictions per 1000 instrs.

- They compare the branch prediction of Haswell (undisclosed by Intel) to some state of the art predictor TAGE(conditional branches)/ITTAGE (indirect branches). Turns out they are comparably good.

Conclusion:

WITHOUT having checked the methodology, their results for MPKI reductions from Nehalem to Haswell seem promising. If we take them as true, the extrapolation to number of instruction slots wasted and therefore the conclusions on performance seem valid. 

How inpactful this is for interpreters as a whole is hard to say, but it's easy to aggree that the experiments dismantle the claim of branch mispredictions in the dispatch stage as a major source of performance issues in interpreters.


