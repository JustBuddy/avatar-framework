# BUDDYWORKS Avatar Framework
This is a repository for organizing and backing up the Avatar Framework files.
It does not accept PR's or Issues, support is handled over our discord.
> [!NOTE]
Please grab the latest release on our distribution sites.

View: https://buddyworks.wtf



## Documentation

### Notes and "License"
Usage of the framework is free of charge, the included icons can be used for private and commercial use,
including using them for commission work or the production of a prefabricated avatar. (free/nitro/sale)
The Icons can also be used in a free public avatar, but please make sure that so can everything else.
The framework comes as is, the author is not to be made responsible for any damage it may induce in any way.
Purpose is to be a quickstart point and a general recommendation around most best practices,
it will however not do the thinking for you. This is a template, adjust it to your needs.
Crediting me is optional, along the lines of "BUDDYWORKS Avatar Framework v5 by Buddy_DE"

Icons not from the SDK are from Carbon-Copy, graciously provided by Dreadrith and JustSleightly.

> [!NOTE]
> USE OF VRCSDK+ FROM DREADRITH IS EXTREMELY RECOMMENDED WHEN WORKING WITH THIS MENU,
> SO IS CONTROLLER EDITOR FOR EDITING THE FX CONTROLLER.


### Expressions
Setting up the expressions should be straightforward if you have done that before already.
The logic is included, you just need to insert the expressions you want in the corresponding slots.
If you want the gestures to mix, you could set up the animations for mouth at one hand and for the
rest of the face on the other. How you end up designing it is up to you. Make use of the "Idle" state
to neutralize all modified blendshapes on each hand. The expressions should be animated with at least
two frames for transitioning, the logic uses a weight float to smoothly animate it.

### Exclusive Switches
The premade layers Tops, Pants and Shoes are written as exclusive INT toggles,
meaning that only one option of each layer can be active at once.
This is useful for things you don't want to let conflict with each other.
Adapt and duplicate as you seem fit.

This system assumes WD On workflow, make sure that the animations
other than default disable whatever default enables, else you will see the default outfit stuck below the selected other outfit.
Means: Animate Default properties OFF in the other outfit clips.

### Presets
This layer is exclusively working with parameter drivers, allowing you to specify parameters to change on each of the states.
This gives you a simple way to create outfit presets which involve multiple pieces,
maybe including some toggles as well. Use as you see fit, or don't, up to you.
Keep the Parameter Driver for "Clothing/Preset" at 0, so it can return back to its idle state properly.

### Toggles and Sliders
What I like to call "The Master Blendtree", here you create non-exclusive toggles and also sliders/radials
 like hue shifts or bodypart compensati... shaping. Using a direct blendtree not only makes creating toggles easier,
 it is also extremely efficient. All parts of the blendtree can work independent from each other,
 meaning you can toggle and slide everything independently.
Double click on "Blend Tree" to open the forest, most of it is already set up in a way that needs you to just slot the animation clips in.
Note: Blendtrees can only work with float parameters, we make use of a technique called "parameter mismatch" to work around this.
Essentially, you create a parameter as bool in your parameter list, but in the FX you instead create it as a float.
This gets translated, false being 0 and true being 1.

Please note the following limitations:
- The Blendtree itself can not have any kind of logic, however you can drive its parameters by parameter drivers on a different layer.
- Things with a constant animation, like image slideshows or tail-wags, are really janky in a blendtree.
Prefer keeping those in a separate layer if they misbehave.

> [!WARNING]
> There is no such thing as a dissolve animation in a direct blendtree toggle!

Since we use parameter mismatch, every animation's state will fling directly to off or on,
you don't get to see the inbetweens. You would need a very convoluted logic and parameter smoothing system to circumvent that,
but at that point you might as well run the thing outside the blendtree.

The tree is written in the Write Defaults ON workflow, using WD Off at any point in your avatar will break its behavior.
If you need WD Off, you need to rewrite the toggles to account for that.

 If you want a throughout guide on how to write and maintain a blendtree, I highly recommend this resource: https://notes.sleightly.dev/dbt-combining/
 Please note that this guide shows you how to write Direct BlendTree toggles in the WD Off workflow, the tree provided by me is written in the WD On workflow.

### Relief
That should be it, anything else is just a matter of exploration, the menu structure should be self explanatory, examples are included.

If you have any questions, don't fear to ask in the BUDDYWORKS Discord,
we happily help with anything avatar and worlds related and you are very welcome to jump in.

https://discord.gg/g7u2qJRc6x
https://buddyworks.wtf/ 

Thank you for choosing BUDDYWORKS assets for your project, cheers!

-Buddy

