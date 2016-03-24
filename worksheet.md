# Window on the weather

Wouldn't it be nice if you could have a magic window that you could look through and instantly tell what the weather outside is like, *anywhere in the world*? Well, in this resource that's exactly what you're going to make, and all using the power of the Scratch programming language.

## Getting the weather

The first thing you'll have to do is get access to a **weather API**. *API* stands for Application Programming Interface. This sounds complicated, but really it's just a set of rules telling your programs how talk to other software.

1.  The weather service you're going to use in this resource is called [OpenWeatherMap](http://openweathermap.org/). It's a completely free service, and has an easy-to-use API. You're going to need your own account though, so click on the link and head on over to the website.

1.  Click on `Sign Up`:

    ![](images/screen1.png)

1.  Choose a username, type in your email address and then provide a password:

    ![](images/screen2.png)

1.  Once you are logged in, you should see a page with your **secret** API key. This is important, so copy it to your clipboard:

![](images/screen3.png)

## A little help from Python

Scratch 1.4 isn't able to communicate over the internet on its own, so you're going to need a little Python script to help Scratch communicate with the OpenWeatherMap API.

1.  Open Scratch (`Menu` > `Programming` > `Scratch`).

1.  Click on 'Sensing': 

![](images/screen10.png)

1.  Then if you right-click on the `slider sensor value` block, you can select `enable remote sensor connections` from the context menu that appears.

1.  It's probably a good idea to save this file now. Call it `magic-window`.

1.  With Scratch all set up, you can now download [this script](code/weather.py).

1.  You can run this script by opening a terminal and typing:

    ``` python
    python3 weather.py
    ```

    or you could open the file using *IDLE* and then press `F5` to run it.

1.  You must make sure this script is running, or your Scratch program won't work. Every time you want to use your Scratch program, you'll need to run this script first.

## A room with a view

You're going to need to pick a view from your window to start with.

1.  Click on the `Stage` object:

    ![](images/screen4.png)

1.  You can now change the `Background` for the stage. Click on the `Import` button and choose an image that you like. You could even go online and find an image from the web:

![](images/screen5.png)

## The *variable* weather

You're going to need a few variables to get this project working.

1.  Click on `Make a variable` and call your first variable `key`, then make a second variable called `location`. It's important to spell both variables correctly, and make sure they're all *lowercase*:

    ![](images/screen7.png)

1.  Now you need to use your secret API key. When the green flag is clicked, you need to set the variable `key` to the API key you have copied to your clipboard.

    ![](images/screen8.png)

1.  This *key* will be sent to the Python script, which will then send it to OpenWeatherMap. But to get the weather, OpenWeatherMap also needs to know the city where you want to find the weather. You can keep asking for this information using a `forever` loop, so that the user can keep changing the location where they want to see the weather.

![](images/screen9.png)

### Testing the API

1.  Click on the green flag then type in a city and country code in the dialogue box that appears. Cities should end with a comma. Country codes should be two-letter abbreviations and all in lowercase. There are some examples below:

    ![](images/screen12.png)

    1.  London,uk
    2.  Nassau,bs
    3.  Sofia,bg
    4.  Berlin,de
    5.  Pyongyang,kp
    6.  Lusaka,ze

1.  When you type the city and country code in and press `Enter`, the Scratch program will send the data to the Python script, which will then request the weather from OpenWeatherMap. You can see some of the weather values by clicking on the little black arrow next to the word `slider`. You should be able to see the words `clouds`, `rainfall`, `temperature`, `wind_direction` and `wind_speed`:

    ![](images/screen13.png)

1.  If the values are not there, make sure that the Python script is still running.

## Bring me sunshine

1.  A good way to indicate the temperature might be the size of the sun that can be seen outside the window.
1.  First, you need to find a nice picture of the sun. You can find your own if you like, or use the one below:

    ![](images/sun.png)

1.  Click on the button to import a new `Sprite`:

    ![](images/screen14.png)

1.  Now import your `sun` image. Position your sun near the top of your screen.

1.  You now need to use the temperature to size the sun. You may wish to play with the values, depending on the size of your sun sprite. In the example below, the sun is sized to the `temperature + 60`. The whole thing is placed in a `forever` loop so that every time you change the city, the temperature is updated.

![](images/screen15.png)

## Little fluffy clouds

1.  The percentage cloud cover is stored as `clouds`, and can easily be shown by the transparency of a cloud image.
1.  You can find your own cloud image, or use the one below:
  
  ![](images/cloud.png)

1.  The cloud above is a little light in colour, so you could edit the costume and use the fill tool to make it black if you wanted: 
  
  ![](images/screen16.png)
 
1.  In a forever loop, you need to set the ghost effect to `100 - clouds sensor value`. So if there was 20% cloud cover (100 - 20 = 80), the ghost effect would be set to `80`. 
  
  ![](images/screen17.png)

1.  Test out your program by checking different cities and see if the cloud changes.

## Blowin' in the wind

1.  When it's windy the clouds move faster, so you can use the speed of the wind to alter how fast your cloud moves:

    ![](images/screen18.png)

1.  The cloud bounces as it hits the edge, and then flips upside down. To stop this from happening you need to set the sprite to `do not rotate`, by clicking on the little black square as shown below:

![](images/screen19.png)

## Wind of change

The wind can change direction, so it would be nice if your script could show the user which direction it's blowing in.

1.  You'll need an arrow sprite for this. There's one in the Scratch library, or you could get your own from the web.

1.  Add this script to your arrow sprite, so that it points in the direction of the wind:

![](images/screen20.png)

## Make it rain

1.  The last bit of weather data to display is the rain. Download [this zip file](images/rain.zip). You can extract the images inside it by typing the following into the terminal:

    ``` bash
    unzip rain.zip
    ```

1.  Now make a new sprite by importing the first of the rain images.
1.  In the costumes tab, import the other rain images one by one:

    ![](images/screen21.png)

1.  If the rainfall is `0` then the sprite needs to be hidden. If the rainfall is greater than (`>`) `0`, then the sprite should be visible and the costume should constantly change. The time between costume changes can depend on the rainfall, so the more rain there is, the faster the costume will change:

![](images/screen22.png)

## From a window

To finish off your program you can add a new sprite, designed to look like a window frame.

![](images/screen23.png)

## What next?

There's lots you could do with this project:

-   Why not try and add in some physical computing, using LEDs to indicate if it's raining or not?
-   Maybe you could change the backdrop in Scratch so that it matches the country or city that is being requested.
-   You could try and investigate the Python script, and see what other weather data is available.

