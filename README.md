# Sustainable Agriculture : The Power of Innovation 
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
ledRing=github:climate-action-kits/pxt-fwd-edu
soilMoisture=github:climate-action-kits/pxt-fwd-edu
```
## 
``||Step 1||`` 
On your screen you can see an ``||basic: on start||`` block and a ``||basic:forever||``
block. Insert or nest a ``||basic: show leds||`` under the ``||basic:on start||``.
Click on the boxes of the ``||basic:show leds||`` to turn the ``||basic:leds||``
ON or OFF. Let's try to write ``||Hi||`` by turning on the ``||basic:leds||`` of the 
``||basic:show leds||`` blocks. Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
```
## 
``||Step 2||``
Click on the ``||fwdSensors:Sensors||`` drawer. 
Find the ``||fwdSensors:set all ledRing LEDs to 10||`` block. 
Drag the block and nest it under ``||basic:forever loop||`` on the coding screen.
Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
```

## 
``||Step 3||``
In this step add the conditional ``||logic:If Else||`` statement block from 
``||logic: Logic||`` drawer.
Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if () {
          } 
    else {
        }
})
```
## 
``||Step 4||``
The ``||fwdSensors:LED Light||`` is set to a particular color to enhance 
plant growth and supplement the absence of sunlight. Next is to control the operation
of the ``||Smart Irrigation System||``. To water the plants the ``||water pump||`` 
should know when to turn on. From the ``||fwdSensors: Sensors||`` drawer find 
``||fwdSensors:is soilMoisture1 moisture level over 5%||`` block.
Nest it in the ``||logic:true||`` condition of the ``||logic:If Else||`` block.
Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        } else {
        }
})
```
## 
``||Step 5||``
Let's add a bit of animation to our code to indicate that our plant is happy
and does not need more water. Go to the ``||basic:basic||`` drawer and drag
``||basic:show icon||`` block nest it under the ``||logic:if||`` condition.
Change the ``||basic:icon||`` to a smiley ``||basic: :)||`` face.
Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        } else {
        }
})
```
## @showhint 
``||Step 6||``
If the plant is happy and does not need water then let's flash the smiley ``||basic::)||`` face.
For the flashing action the smiley ``||basic::)||`` has to disappear and reappear. To perform this action
go to ``||basic: basic||`` drawer and find ``||basic:clear screen||`` block. This would
make the smiley ``||basic: :)||`` disappear. Now add how long should the screen 
should stay cleared before the smiley ``||basic: :)||`` reappears. To do this go to 
``||basic:basic||`` drawer find and drag the ``||basic:pause (ms) 100||``
block and nest it after the ``||basic:clear screen||`` block.
Click on the blub to show your hint.   
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        basic.clearScreen()
        basic.pause(1000)
    } else {
        }
})
```
## @showhint
``||Step 7||``
Now if our plant is sad and needs water then let's add a sad smiley 
``||basic: :(||`` block to the ``||logic:else||`` condition. 
Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        basic.clearScreen()
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Sad)
           }
})
```

## @showhint
``||Step 8||``
The flashing sad smiley ``||basic::(||`` indicates the plant needs water and the 
water pump should run and pump water. To add this coding block go to ``||fwdMotors:Motors||``
block and find ``||fwdMotors:run pump for 500||``. Nest this block under the sad smiley
``||basic::(||``. Next step is flash the smiley face as long the plant does not have
enough water. To do this go to ``||basic:basic||`` drawer and find ``||basic:clear screen||``
nest it after the ``||fwdMotors:run pump for 500||`` block. This would make the sad smiley ``||basic::(||``
disappear. Add a ``||basic:pause (ms) 100||`` block to add a delay before the 
smiley sad ``||basic::(||`` reappears
Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        basic.clearScreen()
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(2000)
        basic.clearScreen()
        basic.pause(1000)
        }
})
```

## @showhint
``||Step 9||``
Next add the ``||logic:true||`` condition ``||input: on button A pressed||`` turn on the 
``||fwdSensors:LED Light||`` of a particular color or ``||input : on button B pressed||`` the 
``||logic: Else||`` condition the ``||fwdSensors:LED Light||`` should be turned off.
Click on the blub to show your hint.
```blocks
basic.showLeds(`
    # . # . #
    # . # . .
    # # # . #
    # . # . #
    # . # . #
    `)
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        basic.clearScreen()
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(2000)
        basic.clearScreen()
        basic.pause(1000)
        }
})
```


> Open this page at [https://mbakhtar.github.io/iste-advanced-agriculture-v1/](https://mbakhtar.github.io/iste-advanced-agriculture-v1/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [Sustainable Agriculture : The Power of Innovation Tutorial v1](https://makecode.microbit.org/#tutorial:github:mbakhtar/iste-advanced-agriculture-v1/advancedagriculture)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/mbakhtar/iste-advanced-agriculture-v1** and import

## Edit this project ![Build status badge](https://github.com/mbakhtar/iste-advanced-agriculture-v1/workflows/MakeCode/badge.svg)

To edit this repository in MakeCode.

* open [https://makecode.microbit.org/](https://makecode.microbit.org/)
* click on **Import** then click on **Import URL**
* paste **https://github.com/mbakhtar/iste-advanced-agriculture-v1** and click import

## Blocks preview

This image shows the blocks code from the last commit in master.
This image may take a few minutes to refresh.

![A rendered view of the blocks](https://github.com/mbakhtar/iste-advanced-agriculture-v1/raw/master/.github/makecode/blocks.png)

#### Metadata (used for search, rendering)

* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
