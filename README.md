node-awesomeCaptcha
============================
Node-awesomeCaptcha utilize `node-canvas` to generate captcha. It provide a flexible options to generate captcha as you like. If you are lazy to configure the options, just pass empty object, a proper captcha generated  which match `bootstrap` input well. 
installation
------------------
    npm install node-awesomeCaptcha
    
Example
-------------------
This example use default option, and generate a captcha which has the same height as bootstrap's input.

    var captcha=require('node-awesomeCaptcha');
    var options={};
    app.get('/',function(req,res){
      captcha(options,function(text,path){
        res.render('index',{captchaImgPath:path});
      })
    })
Options
----------------
The options divided into 3 parts:  
1.  define the size of captcha 
  
2.  defien the appearance and color of captcha  
  
3.  define the file realted options if you choose to save captcha a png file  

Lets start:  
####fontSize
Number. The font size of character. Default is 20px.  
####size 
Number. The number of character. Default is 4. A valid range is 2 to 6.  
####width
Number. The width of captcha. Default is 80px.  
####height
Number. The height of captcha. Default is 32px.  
  
Node-awesomeCaptcha will calulate the required   `width/height`   based on `fontSize` and `size` automatically. Thus the final `width/height` maybe changed. For example, if you set`fontSize` to 48px, `size` to 6, `width/height` to 24px/60px. Apparently, such definition of `width/height` can't contain the defined `fontSize`. Thus, node-awesomeCaptcha will calucate a new `width/height` and overwrite the defined one to contain all 6 character with font size 48px.  
So the best way to get a proper `width/height` is to set `fontSize/size` first, if the generated `width/height` exceed your requirement, then decrease  `fontSize/size`.  
  

####fontType
String. Italic or normal. default is 'normal'.
####fontWeight
String. One value in ['100','200','300','400','500','600','700','800','900','normal','bold','bolder','lighter']. Default is 'normal',
####fontFamily
String. One value in ['serif','sans-serif','monospace','cursive','fantasy']. Default is ''serfi',
####shadow
Boolean. If the cpatcha character has shadow. Default is true,
####inclineFactor
Number. A float num between 0 and 1, define the angle of inclination for character. Deafult is 0.25
####fontRandom
Boolean. If set false, `fontType/fontWeight/fontFamily/shadow/inclineFactor` are set to default value. If true, set these property randomly. Default is true.

####resultMode
Enum Number. Define the captcha mode. 
0:return a DataURL.  
1:return a file path of regular png file
2:return buffer
Default is 0.
####expireDuration
Number. Defind the expirration of captcha, the unit is minute.Default is 1.
####saveDir:__dirname
String. Only work whe `resultMode` set to 1. Define path to save png file. Default is __dirname, means the same directory of `Node-awesomCaptch`.
