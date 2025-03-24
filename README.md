# ComfyUI_SillyTavernCharacterImageCreator

Description
Created for a friend of mine who wanted a way to create a character and all the expressions with ease.



This is a work in progress, however it already works well 80% of the time (have had the odd person get extra arms when sad lol)

I have done testing using photo realistic people however the goal i was set was anime.... I dont know much about anime so I am open to pointers on how to improve the prompts for that style.



Notes from the workflow (and in the workflow)

1) First there is an adult section, you will want to make sure that group is disabled when creating characters that would be inappropriate for!

Why is there an adult section when Silly Tavern does not support a nude/underwear/topless emotions? Well it was asked for, meh why not?



2) Keep the person description and clothing description separate.



3) It will put the emotions into a folder called emotions, that needs to be renamed to match the name of your character in silly tavern.



4) In the renamed folder create a .ps1 file with the text: get-childitem *.png | foreach { rename-item $_ $_.Name.Replace("_00001_", "") }

right click that and choose run with powershell to remove the _00001_ from the filenames, Only way I could do it.

NOTE THIS SHOULD NOW BE DONE FOR YOU! (EDIT....it should...but alas its not lol)



5) Should handle any style your model supports.



6) Bottom of the groups is a step setting, more steps mean better detail (to a degree) les means faster.



7) This is not a fast process! It is also not flawless! I am doing my best.



8) you can disable the groups, I tried to separate core emotions from extras, and adult is sperate too.



9) missing nodes? red boxes? use comfy manager to install custom nodes, I am using a lot to achieve this.



10) SDXL resolution node. This sets the resolution of the images, should you wish to use the old, outdated 1.5 then remove that node and atach the two primitive nodes under it to the width and height of empty latent. set as desired.



11) yes its messy, yes it gives OCD people nightmares.... but its a WIP



12) It is important to add neutral expression to the physical description or it will effect the emotion pictures.



13) a few methods have come out for changing the face, which could be used for expressions, I may look into that as an alternative. But this is 32 images, that would take even longer!



14) This is set up for the open dalle model, you may need to change cfg and lower step count for a different model.

15) The local LLM option is at the mercy of your used LLM. I have specified ages and the AI has then adjusted that to something less appropirate. I recommend leaving the adult section bypassed if using LLM's as far as i can tell Silly tavern does not use those anyway?

TODO:

Get a good way to remove the background so I am left with just the person. DONE

Work on making the pose match the emotion, not just the face.

Allow for more to be customised with ease.... annoyingly tricky.

Fix the emotions so they always show.

Find a way to keep the same clothes that doesn't cause massive slow down.

CHANGE LOG

V2:

Added the ability to use an existing image, follow the notes in the workflow.

Added a warning about the LLM and how it can and does change ages.

Moved a couple of bits about and added re-routers to enable the existing image input to be used with releitive ease

*****************************************************
Node Details:
---------------------------------------------------
Primitive Nodes (74)

Note (6)

PrimitiveNode (5)

Query Local LLM (2)

Reroute (28)

workflow/Basic Person (1)

workflow/Emotion (32)

Custom Nodes (93)

Batch Rembg for ComfyUI

- Image Remove Background (rembg) (34)

ComfyMath

- CM_SDXLResolution (1)

ComfyUI

- EmptyLatentImage (1)

- VAEDecode (1)

- SaveImage (34)

- CLIPTextEncode (3)

- VAELoader (1)

- CheckpointLoaderSimple (1)

- VAEEncode (1)

- LoadImage (1)

ComfyUI Impact Pack

- ToBasicPipe (1)

- ImpactKSamplerBasicPipe (1)

ComfyUI Inspire Pack

- GlobalSeed //Inspire (1)

ComfyUI_experiments

- ReferenceOnlySimple (1)

pythongosssss/ComfyUI-Custom-Scripts

- SaveText|pysssss (3)

- ShowText|pysssss (2)

Quality of life Suit:V2

- Concat Text _O (2)

WAS Node Suite

- Text to Conditioning (1)

- Text Multiline (2)

- Image Resize (1)
----------------------------------------------------
Model Details:
----------------------------------------------------
Checkpoints (1)

Dalle\OpenDalleV1.1.safetensors
*****************************************************


