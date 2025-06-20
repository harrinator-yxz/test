

#diy hotas Readme wip






## Getting started.

To get started I will show and talk about some of the main componetns and parts of the joystick including the gimbal, grip and electronics. <br>
## Grip
The stick/grip that I will be using is the [F-16 Sidestick Grip](https://www.printables.com/model/233472-f-16-sidestick-grip) By [Spock](https://www.printables.com/@Spock) On [printables.com](Printables) I found that it is one of the better free joystick grips. little to no supports and lots of customization options for multiple way switches, buttons, and potentiometers. Some of the buttons even have the ability to be 5 way switches, that is left, right up, down, and in. 
## Gimbal
The next big part is the gimabl, is am using is the [Real Robots Modular Joystick](https://www.thingiverse.com/thing:4732811) which is a big modular kit with some great stuff. You can check out the real robots kickstarter where you can buy a full kit with throttle and other code [here](https://www.kickstarter.com/projects/realrobots/real-robots-game-controller-construction-kits) But I will not be using any of this other than the gimbal from the joystick base as it is one of the cheaper easier to build gimbals aviable. it also has very few parts and is extremly staight forward to build.

## Electronics.
For my joystick I used an STM32F103C8T6 dev kit board, I would recommend buying one from a trusted source on Aliexpress or Digikey. However if you are tight on budget, then I found the Chineses CS32 f103 to be the best fake stm32. These CS32's are all over places like Temu and Aliexpress. I bought two different ones from temu, One was alright and could take the code/software, and the other could not hold the high baud rate. The fake chips do tend to have extremly bad ADC's which is neccacary for this as we will be using multiple buttons and potentiometers. The bad ADC's on the fake chips tend to have lots of noise, mine even had crosstalk between ADC channels.

> ### **why use an STM32?**

I decided to use an stm32 because they support HID, which stands for Human Interface Device. HID is used for averything that we use to interact with computers. For example: Mice, keyboards, touchpads, and even touchscreens. Most HID devices transfer data over USB: (Universal Serial Bus). STM32's are extremly easy to set up and configure HID, alternativly you could use an arduino nano or raspberry pi Pico these both also have HID. But these are much harder as you have to right the code yourself.

## Software

For this project I will be using [Freejoy](https://github.com/FreeJoy-Team/FreeJoy). Freejoy is an open source STM32 USB HID device controller. I used this because is has great compatibility in terms of encoders, buttons and inputs.

<img src="https://github.com/FreeJoy-Team/FreeJoy/blob/master/images/main.png">

### Features
FreeJoy supports the following external periphery:

- 8 analog inputs (12 bit output resolution)
- axis to buttons function (up to 12 buttons per axis)
- buttons/encoders to axis functions
- 128 digital inputs (buttons, toggle switches, hat povs, encoders)
- 5 shift modifiers
- 4 hat povs
- 16 incremental encoders
- shift registers 74HC165 and CD4021
- digital sensors  TLE5010/5011, TLE5012B, AS5048A, AS5600, MLX90393 (SPI interface only)
- external ADCs ADS1115 and MCP3201/02/04/08
- 4 PWM channels for lighting
- 24 LEDs (single or matrix) bindable to buttons' states
- device name and other USB settings

> [!NOTE]
> all this is packaged in one file to upload with an app with UI that is great for editing inputs and other pins.
> Take a look a the [Freejoy](https://github.com/FreeJoy-Team/FreeJoy) Wiki: [Here](https://github.com/FreeJoy-Team/FreeJoyWiki)

#### Freejoy Configurator QT
[Freejoy Configurator](https://github.com/FreeJoy-Team/FreeJoyConfiguratorQt) is an app that lets you edit settings on you STM32 without having to reflash the hole board which you will learn about later. You can look at their Github page: [here](https://github.com/FreeJoy-Team/FreeJoyConfiguratorQt). Freejoy configurator has the featues to change and adapt all of the amazing Freejoy features in an easy way. For example on the configurator you can set up axis curves for different axis. This would be helpful for something like a throttle or a trigger. All of these features can help make the feel of your joystick just a little better.

<img src="https://github.com/FreeJoy-Team/FreeJoyWiki/blob/master/images/main.jpg" width="800"/>
