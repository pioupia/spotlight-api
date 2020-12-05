## Spotlight-api

This npm package allows you to monetize your Discord bot with the spotlight api !

- Table of content :
  * [Installation](#installation)
  * [Utilisation](#usage)
  * [Credits](#Credits)


## Installation

Use the package manager [npm](https://www.npmjs.com/) to install tiktok-stats.
```bash
npm i tiktok-stats
```

## Usage

First, you’ll need to initialize your Spotlight client.

In the main file/ready event of your bot, you can enter the following data to avoid having to add them again later.

```javascript
const spotlight = require("spotlight-api");

(async () => {
await new new spotlight.init()
	.setAuth("key")
	.setLang("fr")
	.addGif(true)
	.save();
})();
```

| Function Name | Utility | Default | Status
|:-----|:--------:|------:|------:|
| **setAuth**   | _Allows you to add your identification key to the spotlight api._ | `none` | optional |
| **setLang**   |  _Allows you to change the language of advertising._  |  `none` | optional |
| **addGif**   | _Add a gif ad to your embed._ |    `false` | optional |

#### Once done, you can in your commands, when sending your embed add an advertisement in it.

Please do not set the maximum field number. Leave at least a place for the plublicity. 20 fields maximum.

```javascript
const spotlight = require("spotlight-api");

(async () => {
const newEmbed = await new spotlight.Ad().setEmbed(embed)
message.channel.send(newEmbed)
})();
```

| Function Name | Utility | Default | Status
|:-----|:--------:|------:|------:|
| **setEmbed**   | _Add advertising to your embed._ | `none` | required |


#### If you have correctly reseinged all previous options in your main file/event ready, you can follow the code above. Otherwise, use the code below :

```javascript
const spotlight = require("spotlight-api");

(async () => {
const newEmbed = await new spotlight.Ad()
	.setAuth("key")
	.setLang("fr")
	.addGif(true)
	.setEmbed(embed);

message.channel.send(newEmbed)
})();
```

| Function Name | Utility | Default | Status
|:-----|:--------:|------:|------:|
| **setEmbed**   | _Add advertising to your embed._ | `none` | required |
| **setAuth**   | _Allows you to add your identification key to the spotlight api._ | `none` | Optional if not resent in the ready event code/ the main file of your bot. |
| **setLang**   |  _Allows you to change the language of advertising._  |  `none` | Optional if not resent in the ready event code/ the main file of your bot. |
| **addGif**   | _Add a gif ad to your embed._ |    `false` | optional |

## Credits
Made by Pioupia with ❤️


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
