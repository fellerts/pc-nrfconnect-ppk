# nRF Connect Power Profiler

Power Profiler app for [nRF Connect](https://github.com/NordicSemiconductor/pc-nrfconnect-core).

## Introduction

The Power Profiler application is a tool to communicate with the The Power Profiler Kit (PPK), an affordable and flexible tool to obtain real-time current measurements of your designs.
The PPK measures current consumption for a connected nRF5x Development Kit or any external board. It measures current from 1 μA up to 70 mA and gives a detailed picture of the current profile for the user application.

All functionality is described in the [User Guide](http://infocenter.nordicsemi.com/topic/com.nordic.infocenter.tools/dita/tools/power_profiler_kit/PPK_user_guide_Intro.html).

![Power Profiler app](resources/screenshot.png)
## Building from source

### Dependencies

To build the app you will need to install the following tools:

* Node.js (>=6.9)
* npm (>=5.6.0) / yarn (>=1.4.0)

### Clone the repository

Open a terminal, go to the following directory, and clone the repository:

- Linux/macOS: `cd $HOME/.nrfconnect-apps/local`
- Windows: `cd %USERPROFILE%/.nrfconnect-apps/local`

Alternatively, clone the repository in a different directory and symlink it into `.nrfconnect-apps/local`.

### Building

After cloning the repository, install the required dependencies:

    npm install

Then build the app:

    npm run dev

If everything was successful, you should now be able to launch the app in nRF Connect.

## Why does this fork exist?
The default Power Profiler Application does not support logging trigger and average data to file. This fork implements that functionality.
- When you stop measurements, the entire average buffer is written to /tmp/x_average.ppkdata.
- When the application triggers, the trigger buffer is written to /tmp/x_trigger.ppkdata.
- The value of x increments for every time a new buffer is written to file.