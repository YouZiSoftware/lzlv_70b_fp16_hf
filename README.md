---
license: cc-by-sa-4.0
---


# lzlv_70B 
## A 13B-style merge of 70B models

A multi-model merge of several different LLaMA2 70B finetunes aimed for roleplay and creative work. The goal was to create a model that combines creativity with  intelligence and prompt-following capabilities for an enhanced experience.

Did it work? I think so. 


## How it was done:

The models were used to create this merge:
- NousResearch/Nous-Hermes-Llama2-70b - A great model for roleplay but not the best at following complex instructions
- Xwin-LM/Xwin-LM-7B-V0.1 - Excellent at following instructions and quite creative with some drawbacks, has been my main model since release so I know it quite well.
- Doctor-Shotgun/mythospice-70b - The wildcard of the three. I was looking for creative model aimed at NSFW and came across this while digging through hf. I had never heard of it and apparently nobody had bothered to publish a quantized version before. So I downloaded it and did it myself. Turned out to be more or less what I was looking for so I used it here. 


The merging process was almost entirely lifted from Undi95's approach in Undi95/MXLewdMini-L2-13B. I picked three of my favourite models that would compliment each other and adjusted the ratios at by preference.

To be concrete the components are:

Component 1: Merge of Mythospice x Xwin  with SLERP gradient [0.25, 0.3, 0.5]
Component 2: Merge of  Xwin x Hermes with SLERP gradient [0.4, 0.3, 0.25]

Finally, both Component 1 and Component 2 were merged SLERP weight 0.5

## Benefits

I tested it for a day. It seems to retain the instruction-following capabilities of Xwin while appearing to have adapted a lot of the creativity of the other two models. 
Is it  better? Feels like it to me, subjetively. Is it truly better? I don't know, test it yourself. 

## Prompt Format:
Vicuna
USER: [prompt]
ASSISTANT: 


## NSFW and other content
Due to the nature of many of the models that make up this merge, it can and will  produce inappropriate content when prompted to do so. A jailbreak is not required. If you prompt it directly to commit a hatecrime  with 0 additional context, there is a chance that it will refuse to do so for the first regeneration or two. This should never happen in slightly more complex prompts or while it's acting out a character. 
So be careful or not. 

