# Best Funcaptcha Amazon Captcha Solver

## Bonus Code
 A bonus code for Capsolver: **AMN**. After redeeming it, you will get an extra 5% bonus after each recharge, Unlimited
 ![image](https://github.com/ERIZOAT/Amazon-captcha-services/assets/157081315/6478d451-26a0-4b79-ae44-dfc8c9ed5ee0)


## What is Funcaptcha?

Funcaptcha is a type of CAPTCHA technology that was developed by a company called Arkose Labs. Unlike traditional CAPTCHAs, Funcaptcha uses interactive puzzles and games to differentiate between humans and bots. These puzzles are designed to be engaging and fun for humans, but difficult for bots to solve.


![image](https://github.com/ERIZOAT/Amazon-captcha-services/assets/157081315/98b0cfee-211d-4d54-a489-e9a76ad706c3)



## Solving FunCaptcha by Using Capsolver
While FunCaptcha offers an enjoyable experience for human users, it can be a challenge for automated systems or web scrapers. This is where Capsolver comes into play. Capsolver is a powerful captcha-solving service that specializes in resolving various types of captchas, including FunCaptcha.

## Sample scripts for Capsolver to solve Funcaptcha on Amazon

This repository contains sample code for solving CAPTCHA challenges using [Capsolver](https://www.capsolver.com/). These tools that utilize the Capsolver API include python and Node.js


## Solving Amazon Funcaptcha

### Create Task

Create a task with the [createTask](../api-createtask.md) to create a task.

### Task Object Structure

| Properties               | Type   | Required | Description                                                                                                                                                                                                                                                                                                                |
|--------------------------|--------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| type                     | String | Required | `FunCaptchaTaskProxyLess`                                                                                                                                                                                                                                                                                                  |
| websiteURL               | String | Required | Web address of the website using funcaptcha, generally it's fixed value. (Ex: https://google.com)                                                                                                                                                                                                                          |
| websitePublicKey         | String | Required | The domain public key, rarely updated. (Ex: E8A75615-1CBA-5DFF-8031-D16BCF234E10)                                                                                                                                                                                                                                          |
| funcaptchaApiJSSubdomain | String | Optional | A special subdomain of [funcaptcha.com](http://funcaptcha.com/), from which the JS captcha widget should be loaded. Most FunCaptcha installations work from shared domains.                                                                                                                                                |
| data                     | String | Optional | Additional parameter that may be required by FunCaptcha implementation. Use this property to send "blob" value as a stringified array. See example how it may look like. {"\blob\":\"HERE_COMES_THE_blob_VALUE\"}  Learn [how to get FunCaptcha blob data](https://www.capsolver.com/blog/FunCaptcha/funcaptcha-data-blob) |
| proxy                    | String | Optional | Learn [Using proxies](../api-how-to-use-proxy)                                                                                                                                                                                                                                                                             |

### Example Request

``` json
POST https://api.capsolver.com/createTask
Host: api.capsolver.com
Content-Type: application/json

{
    "clientKey": "YOUR_API_KEY_HERE",
    "task": {
        "type":"FunCaptchaTaskProxyLess", //Required
        "websiteURL":"", //Required
        "websitePublicKey":"", //Required
        "data": "{\"blob\": \"flaR60YY3tnRXv6w.l32U2KgdgEUCbyoSPI4jOxU...\"}" // Optional
    }
}
```


After you submit the task to us, you should receive in the response a 'Task id' if it's successfull. Please
read [errorCode: full list of errors](https://captchaai.atlassian.net/wiki/spaces/CAPTCHAAI/pages/394062/FuncaptchaTask+solving+FunCaptcha#)
if you didn't receive the task id.

### Example Response

``` json
{
    "errorId": 0,
    "status": "idle",
    "taskId": "61138bb6-19fb-11ec-a9c8-0242ac110006"
}

```

### **Getting Result**

Use the [getTaskResult](../api-gettaskresult.md) method to get the recognition results

Depending on the system load, you will get the results within the interval of `1s` to `20s`

### Example Request

``` json
POST https://api.capsolver.com/getTaskResult
Host: api.capsolver.com
Content-Type: application/json

{
    "clientKey": "YOUR_API_KEY",
    "taskId": "61138bb6-19fb-11ec-a9c8-0242ac110006"
}
```

### Example Response

``` json
{
    "errorId": 0,
    "solution": {
        "userAgent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36",
        "token": "3AHJ_q25SxXT-pmSeBXjzScW-EiocHwwpwqtk1QXlJnGnU......"
    },
    "status": "ready"
}
```



## Documentation 
[Capsolver API documentation](https://docs.capsolver.com/guide/api-server.html)

In conclusion, solving Funcaptcha Captcha can be a daunting task, but with the help of capsolver.com, it can be done quickly and efficiently. By following the steps outlined above, you can easily solve Funcaptcha

CapSolver Team 💜


         
