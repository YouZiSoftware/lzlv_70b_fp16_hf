---
license: cc-by-sa-4.0
---


# lzlv_70B 
## A Mythomax/MLewd_13B style merge of 70B models

A multi-model merge of several different LLaMA2 70B finetunes for roleplaying and creative work. The goal was to create a model that combined creativity with intelligence and prompt following capabilities for an enhanced experience.

Did it work? I think it did. Probably. 


## Procedure:

Models used:
- NousResearch/Nous-Hermes-Llama2-70b - A great model for roleplaying, but not the best at following complex instructions.
- Xwin-LM/Xwin-LM-7B-V0.1 - Excellent at following instructions and quite creative with some drawbacks, has been my main model since release so I know it quite well.
- Doctor-Shotgun/Mythospice-70b - The joker of the three. I was looking for a creative, NSFW-oriented model and came across this while digging through hf. I had never heard of it before, and apparently no one had bothered to release a quantized version of this model. So I downloaded it and did it myself to test it. It turned out to be more or less what I was looking for as my third component, so I used it here. 

A big thank you to the creators of the models above. If you look up Mythospice, you will notice that it also includes Nous-Hermes so it's technically present twice in this mix. This is common practice in 13B merges so I didn't bother to correct it her either. 


The merging process was heavily inspired by Undi95's approach in Undi95/MXLewdMini-L2-13B. I chose three of my favourite models that seemed to complement each other, and adjusted the ratios according to my preference.

To be specific, the ratios are:

Component 1: Merge of Mythospice x Xwin with SLERP gradient [0.25, 0.3, 0.5].
Component 2: Merge Xwin x Hermes with SLERP gradient [0.4, 0.3, 0.25].

Finally, both Component 1 and Component 2 were merged SLERP weight 0.5

## Advantages

I tested this model for a day before publishing it. It seems to retain the instruction-following capabilities of Xwin-70B, while seeming to have adapted a lot of the creativity of the other two models. 
It handls the elaborate instructions in my more complex roleplay SillyTavern cards about as well as the best 70b-Instruct models I've tested. More creative models like Hermes/Mythospice tend to struggle here. At the same time, it seemed to display enhanced creativity that previous go-to models did not have.
So, is it better? Feels like it to me, subjectively. Is it really better? I don't know, try it for yourself. 

## Prompt format:
Vicuna
USER: [Prompt]
ASSISTANT: 



## NSFW
Due to the nature of some of the models that make up this merge, it can and will produce inappropriate content when prompted. Jailbreaking is not required. The same is the case the other way around: if you ask it directly to commit a hate crime with 0 additional context, it may refuse to do so for the first regeneration or two. This should never happen with more complex prompts or when it's playing a character. 
So be careful (or not). 


