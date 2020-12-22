# AvataaarsJs
Use the awesome Avataaars Library by Pablo Stanley ([avataaars.com](https://avataaars.com/)) in any javascript application.   
   
This Project uses parts of the [Dicebear Avatars Library](https://github.com/DiceBear/avatars) to generate Avatars with a specified configuration.    
I fitted this Library for my puposes, if you need functionalitys like random avatar generation or avatars based on seeds have a look at the DiceBear Avatars Library. 
    
The main intention is to have all configuration options in one single file with a simple, extensible structure.

## Getting Started
Include the JavaScript file into your application
```html
<script src="avataaars.js"></script>
```
#### The default Avatar
The Library dont uses any random features, so if you dont specify any paramter it will return the same Avatar every time.
```javascript
Avataaars.create();
// --> "<svg width [...] </svg>"
```
#### Customize Avatar
Avaliable options:
| name             | type   | default          | description                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------|--------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| width            | number | `null`           | Fixed width                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| height           | number | `null`           | Fixed height                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| style            | string | `circle`         | One of: `transparent`, `circle`                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| background       | string | `null`           | Background color for style: 'circle'                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| svgBackground    | string | `transparent`    | Background color for the whole svg                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| skin             | string | `tanned`         | Possible values: `tanned`, `yellow`, `pale`, `light`, `brown`, `darkBrown`, `black`                                                                                                                                                                                                                                                                                                                                                                                       |
| top              | string | `shortWaved`     | Possible values: `dreads01`, `dreads02`, `frizzle`, `shaggyMullet`, `shaggy`, `shortCurly`, `shortFlat`, `shortRound`, `sides`, `shortWaved`, `theCaesarAndSidePart`, `theCaesar`, `bigHair`, `bob`, `bun`, `curly`, `curvy`, `dreads`, `frida`, `froAndBand`, `fro`, `longButNotTooLong`, `miaWallace`, `shavedSides`, `straightAndStrand`, `straight01`, `straight02`, `eyepatch`, `turban`, `hijab`, `hat`, `winterHat01`, `winterHat02`, `winterHat03`, `winterHat04` |
| hairColor        | string | `auburn`         | Possible values: `auburn`, `black`, `blonde`, `blondeGolden`, `brown`, `brownDark`, `pastelPink`, `platinum`, `red`, `silverGray`                                                                                                                                                                                                                                                                                                                                         |
| hatColor         | string | `blue02`         | Possible values: `black`, `blue01`, `blue02`, `blue03`, `gray01`, `gray02`, `heather`, `pastelBlue`, `pastelGreen`, `pastelOrange`, `pastelRed`, `pastelYellow`, `pink`, `red`, `white`                                                                                                                                                                                                                                                                                   |
| accessories      | string | `none`           | Possible values: `none`, `kurt`, `prescription01`, `prescription02`, `round`, `sunglasses`, `wayfarers`                                                                                                                                                                                                                                                                                                                                                                   |
| accessoriesColor | string | `black`          | Possible values: `black`, `blue01`, `blue02`, `blue03`, `gray01`, `gray02`, `heather`, `pastelBlue`, `pastelGreen`, `pastelOrange`, `pastelRed`, `pastelYellow`, `pink`, `red`, `white`                                                                                                                                                                                                                                                                                   |
| facialHair       | string | `none`           | Possible values: `none`, `beardLight`, `beardMagestic`, `beardMedium`, `moustaceFancy`, `moustacheMagnum`                                                                                                                                                                                                                                                                                                                                                                 |
| facialHairColor  | string | `auburn`         | Possible values: `auburn`, `black`, `blonde`, `blondeGolden`, `brown`, `brownDark`, `pastelPink`, `platinum`, `red`, `silverGray`                                                                                                                                                                                                                                                                                                                                         |
| clothing         | string | `shirtCrewNeck`  | Possible values: `blazerAndShirt`, `blazerAndSweater`, `collarAndSweater`, `graphicShirt`, `hoodie`, `overall`, `shirtCrewNeck`, `shirtScoopNeck`, `shirtVNeck`                                                                                                                                                                                                                                                                                                           |
| clothingGraphic  | string | `pizza`          | Possible values: `skrullOutline`, `skrull`, `resist`, `pizza`, `hola`, `diamond`, `deer`, `dumbia`, `bear`, `bat`                                                                                                                                                                                                                                                                                                                                                         |
| clothingColor    | string | `black`          | Possible values: `black`, `blue01`, `blue02`, `blue03`, `gray01`, `gray02`, `heather`, `pastelBlue`, `pastelGreen`, `pastelOrange`, `pastelRed`, `pastelYellow`, `pink`, `red`, `white`                                                                                                                                                                                                                                                                                   |
| eyes             | string | `default`        | Possible values: `squint`, `closed`, `cry`, `default`, `eyeRoll`, `happy`, `hearts`, `side`, `surprised`, `wink`, `winkWacky`, `xDizzy`                                                                                                                                                                                                                                                                                                                                   |
| eyebrows         | string | `defaultNatural` | Possible values: `angryNatural`, `defaultNatural`, `flatNatural`, `frownNatural`, `raisedExcitedNatural`, `sadConcernedNatural`, `unibrowNatural`, `upDownNatural`, `raisedExcited`, `angry`, `default`, `sadConcerned`, `upDown`                                                                                                                                                                                                                                         |
| mouth            | string | `default`        | Possible values: `concerned`, `default`, `disbelief`, `eating`, `grimace`, `sad`, `screamOpen`, `serious`, `smile`, `tongue`, `twinkle`, `vomit`                                                                                                                                                                                                                                                                                                                          |   


### Create a custom Avataaar
You can use all options from the upper table.   
```javascript
var svg = Avataaars.create({
    eyes: "wink",
    clothing: "hoodie",
    hair: "dreads",
    hairColor: "blonde"
});
```
### Get avaliable options in Javascript
This is recommended if you want to build for example an Avatar customizer.
```javascript
// Read all customizable Paths/Shapes as Array
console.log(Object.keys(Avataaars.paths));
// >> ["skin", "top", ...]

//Get Color palletes as Object
console.log(Avataaars.colors);
// >> {skin:{tanned: ""}}

// Get customisation options for one body part as Array
console.log(Object.keys(Avataaars.paths.clothing));
// >> ["blazerAndShirt", "blazerAndSweater", ...]
```   
