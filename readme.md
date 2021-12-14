Tray Weather
============

# Summary
- [Description](#description)
- [Compilation](#compilation-requirements)
- [Install](#install)
- [Screenshots](#screenshots)
- [Translations](#translations)
- [Repository information](#repository-information)

# Description
Tray Weather is a simple application to retrieve and show weather information for a given geographic location in a small dialog and in the Windows OS system tray. When executed the application sits
in the system tray, showing the current weather icon. The tray icon tooltip shows the location, weather description and temperature. The tray menu provides access to the weather and configuration
dialogs. If there is a network error and the information cannot be retrieved the tray icon will inform of the error and show the error icon. 

The computer location can be automatically obtained by using the services of [http://ip-api.com/](http://ip-api.com/) or entered manually by specifying latitude and longitude coordinates. The weather
and maps information are obtained from [OpenWeatherMap](http://openweathermap.org/). To obtain weather information from OpenWeatherMap you need to register in their website and enter the given API Key
into the Tray Weather configuration dialog. 

> **_NOTE:_**  Please note that after you register in OpenWeatherMap and are given an API key, that key **may not be valid right away**. If you enter the API key in TrayWeather and get an "host requires authentication" error, you must wait a little longer until it becomes valid.

## Options
The temperature units (celsius or fahrenheit) and the frequency of update requests are configurable options. Other visual configuration options can be seen in the configuration dialog screenshot.

# Compilation requirements
## To build the tool:
* cross-platform build system: [CMake](http://www.cmake.org/cmake/resources/software.html).
* compiler: [Mingw64](http://sourceforge.net/projects/mingw-w64/) on Windows.

From version 5.6 onwards the WebKit module has been replaced by a new Chromium-based equivalent that doesn't compile on Mingw. In addition to that, the QtCharts module is only officially available in Qt
from versions 5.6 onwards. So the easiest way to compile the application is to use the 5.5.1 release of Qt and, separately, compile and add to the project the QtCharts module from GitHub. 

## External dependencies
The following libraries are required:
* [Qt 5.5.1 opensource framework](http://www.qt.io/) compiled with SSL support.
* [Qt Charts 2.1.0 submodule](https://github.com/qt/qtcharts).

# Install

Download the latest ![release](https://github.com/FelixdelasPozas/TrayWeather/releases/) installer.

# Screenshots

> **_NOTE:_**  Some screenshots are from older versions of Tray Weather and are missing tabs present in the latest version. 

Tray icon showing the current weather icon. At night and on clear sky days it shows the current moon phase as the weather icon.

![icon](https://cloud.githubusercontent.com/assets/12167134/20938095/f03e2474-bbe9-11e6-83b9-e2bc8c716bf4.jpg)
![icon_menu](https://user-images.githubusercontent.com/12167134/145942029-01678f72-11ae-4b55-b8f4-dbbc70183341.png)

Tray icon can also show the temperature alone or composed with the weather icon. It can also be configured to show two tray icons, one with the temperature and other with the weather icon. 
The temperature text color can be set by the user or can change dynamically between a range of colors according to the current value. 

![icon_temp](https://user-images.githubusercontent.com/12167134/85929400-b6e05280-b8b4-11ea-9574-bf27537f38e3.png)

Configuration dialog. It shows the detected location properties and the options to change the frequency of updates and temperature units. The OpenWeatherMap API Key must be entered here. If the location is better guessed with the DNS IP instead of the IP given by the provider the option
can be enabled here. A 'roaming' mode can be enabled, where the geographical coordinates are requested before any weather data request, so the 
weather information is up to date even if the computer location is moving. Roaming mode can only be enabled if the geolocation services are being used.
The tray and application theme configuration can be found here in the miscellaneous options. Also the frequency of checks for updates can be set here.

Configuration dialog in Spanish with the application light theme.

![config](https://user-images.githubusercontent.com/12167134/145942021-b2b691da-0dde-4f14-9924-82fbd38852d3.png)

Configuration dialog in English with the application dark theme.

![config_dark](https://user-images.githubusercontent.com/12167134/145942026-89cfeb5e-0bac-4728-b19e-89f6eb4a67a2.png)

Weather dialog, showing the current weather tab. 

![weather](https://user-images.githubusercontent.com/12167134/127046991-e2eb1e5c-73d7-4ece-b9c4-dfff8dd1648e.png)

Weather forecast for the next days. If the user puts the mouse over a point in the temperature line a tooltip will provide the weather conditions for that day and hour. 
The graph can be zoomed by selecting the area to zoom with the mouse and resetted to the initial state by using the reset button below the graph.

![forecast_graph](https://user-images.githubusercontent.com/12167134/109207324-4b36e800-77a9-11eb-9891-291c907d0aef.png)

Pollution forecast can be obtained in the third tab, showing the projections for the next days. The chart can be zoomed in the X axis and
resetted by using the reset button below. The pollution chart also has a tooltip with detailed information for each point of the lines and
the background is colored according to air quality value. 

![pollution](https://user-images.githubusercontent.com/12167134/109207327-4bcf7e80-77a9-11eb-89a0-dd704e8969ad.png)

Ultraviolet radiation forecast can be obtained in the "UV" tab, showing the projection for the next 24 hours colored according to the World
Health Organization color code. The UV chart also has a information tooltip that appears when the mouse cursor is near a point of the radiation
index line showing the index value and recommendations.  

![radiation](https://user-images.githubusercontent.com/12167134/127046989-ad7a3d32-adb9-486f-a37b-1dddf95b935a.png)

Weather maps are interactive. While initially the map is centered in the detected location it can be moved and zoomed in and out. The maps consumes much more memory than
the rest of the application so the user can be disable them using the button below. 

![maps0](https://user-images.githubusercontent.com/12167134/109207325-4bcf7e80-77a9-11eb-8744-8b928c5d2c3e.png)
![maps1](https://cloud.githubusercontent.com/assets/12167134/20938099/f07daa22-bbe9-11e6-9efb-07466ef36748.jpg)
![maps2](https://cloud.githubusercontent.com/assets/12167134/20938097/f0623792-bbe9-11e6-8ebf-0ae4b5b679a9.jpg)
![maps3](https://cloud.githubusercontent.com/assets/12167134/20938100/f0851d34-bbe9-11e6-80c9-d7d952632cc4.jpg)

# Translations


Tray Weather is available in:
* English
* Spanish
* Russian
* German
* French
* Chinese (Simplified)

If 'TrayWeather' hasn't a translation for your language you can collaborate and translate the application using the 
[Qt Linguistic Tools](https://doc.qt.io/qt-5/qtlinguist-index.html) (available [here](https://github.com/lelegard/qtlinguist-installers))
or manually editing the ['empty' translation source file](https://raw.githubusercontent.com/FelixdelasPozas/TrayWeather/master/languages/empty.ts)
and making a pull request. Currently it's just 350 texts.

To do it manually just edit the 'empty translation' file and replace the untranslated messages:

```
    <message>
        <location filename="../AboutDialog.ui" line="429"/>
        <source>Weather data provided by</source>
        <translation type="unfinished"></translation>
    </message>
```
    
To the translation in your language. For example in Spanish it is:

```
    <message>
        <location filename="../AboutDialog.ui" line="429"/>
        <source>Weather data provided by</source>
        <translation>Datos meteorológicos proporcionados por</translation>
    </message>
```

# Repository information

**Version**: 1.14.0

**Status**: finished.

**cloc statistics**

| Language                     |files          |blank        |comment           |code  |
|:-----------------------------|--------------:|------------:|-----------------:|-----:|
| C++                          |  10           | 835         |   354            | 4202 |
| C/C++ Header                 |  10           | 253         |   715            |  825 |
| HTML                         |   1           |  33         |     0            |  150 |
| CMake                        |   1           |  18         |    11            |  115 |
| **Total**                    | **22**        | **1139**    | **1080**         | **5292** |
