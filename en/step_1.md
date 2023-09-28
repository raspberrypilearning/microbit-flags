You can use `true`{:class='microbitlogic'} and `false`{:class='microbitlogic'} blocks to check (flag) when something has happened in your code.

In the Sound meter project, you made sure the alarm noise did not add to the already noisy environment.

You did this by setting the `alarm`{:class='microbitvariables'} variable to `false`{:class='microbitlogic'} when your code started.

<div style="position:relative;height:calc(100px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_gKpgmbh6fJo8" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

You then checked that it was `false`{:class='microbitlogic'} if the sound level was too high before setting off the alarm. 

You then changed it to `true`{:class='microbitlogic'} when the alarm sounded. 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_UmibCbeCJhPm" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

You changed it back to `false`{:class='microbitlogic'} when the touch logo is pressed.

<div style="position:relative;height:calc(100px + 5em);width:50%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_2eDAPFTsAVxh" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

This let you only trigger the alarm if it was not already triggered.

- You can find the `true`{:class='microbitlogic'} and `false`{:class='microbitlogic'} blocks in the `Logic`{:class='microbitlogic'} menu in your Toolbox.