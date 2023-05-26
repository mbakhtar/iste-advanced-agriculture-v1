# Sustainable Agriculture : The Power of Innovation 
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
ledRing=github:climate-action-kits/pxt-fwd-edu
soilMoisture=github:climate-action-kits/pxt-fwd-edu
```
## 
``||Step 1||`` 
Plug your USB cable into the micro:bit and insert it into the Climate Action Kit board. 
Click on the button to the right of download and follow the steps to pair your micro:bit. 

## 
``||Step 2||`` Click on the "Sensors" drawer and find the ``||fwdSensors:set all ledRing LEDs to 10||`` block. 
Drag the block under the ``||basic:forever loop||`` and hit download to activate your LED. 

## 
``||Step 3||`` Open the ``||logic: Logic||`` drawer and add a ``||logic:If Else||`` statement to your code.
Click the ``||fwdSensors:Sensors||`` drawer and add ``||fwdSensors:is soilMoisture1 moisture level over 5%||`` 
to the ``||logic:true||`` condition of the ``||logic:If Else||`` block.

## 
``||Step 4||`` To show when your plant needs watering or not, go to the ``||basic:basic||`` drawer 
and drag the ``||basic:show leds||`` ``||basic:show icon||`` block nest it under the ``||logic:if||`` condition. 
Change the icons to a smiley ``||basic: :)||`` and ``||basic: :(||``.

## 
``||Step 5||`` Check your code by downloading and holding the moisture sensor between your fingers. 
When you pinch it will mimic moisture and display a ``||basic: :)||`` face and when you let go, it should display ``||basic: :(||``. 

## 
``||Step 6||`` Now to water your plant automatically when the soil is dry, go to the ``||fwdMotors:Motors||`` drawer 
 and add ``||fwdMotors:run pump for 500||`` under the ``||basic: :(||`` in the ``||logic:If Else||`` block.

## 
``||Step 7||`` "To let the water soak in before your moisture sensor reads again, go to your ``||basic:on start||`` drawer 
to add a ``||basic:pause (ms) 500||`` and a ``||basic:clear screen||`` block after your find ``||fwdMotors:run pump for 500||`` block. 

## 
``||Step 8||`` Clip your moisture sensor onto the side rail and place your tube into another empty cup. 
Then download your code to test your automated watering system. 

## 
``||Step 9||`` Congratulations on completing your Automatic Irrigation System! - everyone can use tech to make the world a better place! Go back to the Forward Edu lesson for more activities and extensions"

## @showhint
``||Step 8||``
The flashing sad smiley ``||basic::(||`` indicates the plant needs water. So, the 
water pump should run and pump water. To add this coding block, go to ``||fwdMotors:Motors||``
block and find ``||fwdMotors:run pump for 500||``. Nest this block under the sad smiley
``||basic::(||``. We want the smiley face to flash as long the plant does not have
enough water. To do this, go to ``||basic:basic||`` drawer and find ``||basic:clear screen||``
nest it after the ``||fwdMotors:run pump for 500||`` block. This will make the sad smiley ``||basic::(||``
disappear. Add a ``||basic:pause (ms) 100||`` block to add a short delay before the 
sad smiley ``||basic::(||`` reappears.
Click on the bulb to show your hint.
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
