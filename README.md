# Recaptcha V3 Harvester
This is a Recaptcha V3 Harvester you can use for any site, just replace the sitekey in captcha.html and website you wish to use in main.js.
This solver automatically removes expired captcha tokens after they expire (120 seconds).

## Using the tokens

You can use this request in a function to return a captcha token, which can then be used. 
Retrieving a token will automatically remove it from the bank.

```js
request('http://localhost:8080/fetch', function (error, response, body) {
            if(body != undefined)
            {
                var tokenPot = JSON.parse(body)
                if(body == "[]")
                {
                    console.log("Waiting for captcha...")
                    setTimeout(functionName, 500);
                }
                else
                {
                    console.log("Got captcha token...")
                    captchaToken = tokenPot[0]["token"]
                    return captchaToken;
                }
            }
            else if(body == undefined)
            {
                console.log("Captcha bank not active.")
            }
        });
```

## Instructions
Clone or download this repository, and then:

```npm install``` 

followed by:

``` npm start```

## License
[MIT](https://choosealicense.com/licenses/mit/)
