# node-awesomeCaptcha
Node-awesomeCaptcha utilize node-canvas to generate captcha. It provide a flexible options to generate captcha as you like. If you are lazy to configure the options, just pass empty object, a proper captcha generated  which match bootstrap input well. 
# installation
npm install node-awesomeCaptcha
# Example
This example use default option, and generate a captcha which has the same height as bootstrap's input.

var captcha=require('node-awesomeCaptcha');
var options={};
app.get('/',function(req,res){
  captcha(options,function(text,path){
    res.render('index',{captchaImgPath:path});
  })
})
# Options
The options divided into 3 parts:
1.  define the size of captcha
2.  defien the appearance and color of captcha
3.  define the file realted options if you choose to save captcha a png file

Lets start:
fontSize: the font size of character. Default is 20px.
size: the number of character. Default is 4. A valid range is 2 to 6.
width: the width of captcha. Default is 80px.
height: the height of captcha. Default is 32px.

the final width/height maybe changed if 
