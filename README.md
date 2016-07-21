# Pokemon-Go-Rocket-API

A Pokemon Go bot in C#

## Features
* PTC Login / Google
* Get Map Objects and Inventory
* Search for gyms/pokestops/spawns
* Farm pokestops
* Farm all pokemons in neighbourhood
* Evolve pokemons
* Transfer pokemons
* Auto Updates

## Getting Started

Go to PokemonGo\RocketAPI\Console\App.config -> Edit the Settings you like -> Build and Run (CTRL+F5)

## Transfer Types

The most popular option is probably the duplicate type that removes all duplicates and leaves you one pokemon of each type with the highest CP.

* none - disables transferring
* cp - transfers all pokemon below the CP threshold in the app.config, EXCEPT for those types specified in program.cs in TransferAllWeakPokemon
* leaveStrongest - transfers all but the highest CP pokemon of each type SPECIFIED IN program.cs in TransferAllButStrongestUnwantedPokemon (those that aren't specified are untouched)
* duplicate - same as above but for all pokemon (no need to specify type)
* all - transfers all pokemon

## Persistent Google login
To log in for longer than 30 miutes with google and get rid of the device code:

1. Before you run the bot make sure that google refresh token in app.config has no value 
`<add key="GoogleRefreshToken" value="">`
2. Set your location in App.config and run the code in Visual Studio
3. In the console window you wil be asked to visit google.com/device and you need to input the key. After you input the right key, The refresh token will be printed in the console window. Right click the upper left most icon of your console window, choose EDIT -> MARK . You will be able to highlight the text inside the console, make sure to highlight the refresh code and then right click on it so it will be copied into your clipboard.
4. Stop/Exit the bot and go back to App.config -> Paste the refresh token in like this `<add key="GoogleRefreshToken" value="1/34UibMdc-Qn5AbewpDR-QZv8w_STqik13RFHqXV_Jd6TA">`
5. Now you don't have to go to google.com/device to register your bot, It will automatically login with your credentials and the bot auto restarts when it crashes.
