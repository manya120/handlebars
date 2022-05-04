// working with EJS in express

var express= require("express");
var app= express();
app.listen(7070,function(){
console.log("server start at port 7070");
});

// handlebars
var expresshandlebars=require("express-handlebars");
app.engine("hbs" , expresshandlebars());
app.set("view engine" , "hbs"); //set view engine as mustache

app.get("/" , function(req,res){
var model={student:{x:10 , y:20 }, pass:this.x>this.y};
res.render("index",model);
 //ejs file
});


//index.hbs - code
<!-- // handlebars is better than mustache -->
<html>
    <head>
        <title>Index
        </title>
    </head>
    <body>
        <h4>Index</h4>
        {{ student.x }}
        <br>
        {{student.y}}
        <br>

        <!-- if-else syntax for handlebars -->
  
     {{#ifpass}}
          congratulations. Passsed!!
 {{else}}
     Failed!
{{/pass}}

    </body>
</html>
