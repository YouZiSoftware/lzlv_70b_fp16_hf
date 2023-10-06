---
license: cc-by-nc-2.0
---


# lzlv_70B 
## A Mythomax/MLewd_13B style merge of selected 70B models

A multi-model merge of several  LLaMA2 70B finetunes for roleplaying and creative work. The goal was to create a model that combines creativity with intelligence for an enhanced experience.

Did it work? Probably, maybe. 


## Procedure:

Models used:
- NousResearch/Nous-Hermes-Llama2-70b - A great model for roleplaying, but not the best at following complex instructions.
- Xwin-LM/Xwin-LM-7B-V0.1 - Excellent at following instructions and quite creative out of the box, so it seemed like the best available model to act as the base of the merge.
- Doctor-Shotgun/Mythospice-70b - The wildcard of the three. I was looking for a creative, NSFW-oriented model and came across this while digging through hf. I had never heard of it before, and apparently no one had bothered to release a quantized version of this model. So I downloaded it and did it myself to test it. It turned out to be more or less what I was looking for as my third component, so I used it here. 

A big thank you to the creators of the models above. If you look up Mythospice, you will notice that it also includes Nous-Hermes so it's technically present twice in this mix. This is common practice in 13B merges so I didn't bother to correct it her either. 


I chose three of my favourite models that seemed to complement each other, and adjusted the ratios according to my preference.

The merging process was heavily inspired by Undi95's approach in Undi95/MXLewdMini-L2-13B. To be specific, the ratios are:

Component 1: Merge of Mythospice x Xwin with SLERP gradient [0.25, 0.3, 0.5].
Component 2: Merge Xwin x Hermes with SLERP gradient [0.4, 0.3, 0.25].

Finally, both Component 1 and Component 2 were merged with SLERP using weight 0.5.

## Advantages

I tested this model for a few days before publishing it. It seems to retain the instruction-following capabilities of Xwin-70B, while seeming to have adapted a lot of the creativity of the other two models. 
It handles my more complex scenarios that creative models otherwise tend to struggle with quite well. At the same time, its outputs felt more creative and possibly a bit more nsfw-inclined than Xwin-70b.
So, is it better? Feels like it to me, subjectively. Is it really better? No clue, test it. 

## Prompt format:
Vicuna
USER: [Prompt]
ASSISTANT: 
