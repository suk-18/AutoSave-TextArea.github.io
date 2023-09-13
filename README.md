# AutoSave-TextArea

This is a application which is developed with the help of simple concepts of HTML,CSS and JS.In this task we are create a auto save textarea card where we enter the details store in the local Storage.

### Step-1: HTML

Firstly a html file is created and the following code is added:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AutoSave Textarea</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1 id="heading">Auto Save Textarea</h1>
        <div class="color-change">
            <input type="color" id="colors">
            <button id="changeColor">Change Color</button>
        </div>
        <textarea  id="mytextarea" cols="30" rows="10" placeholder="start type here...." spellcheck="false"></textarea>
    </div>
    <script src="script.js"></script>
</body>
</html>

```

### Step-2: CSS

Secondly a css file is created and the following code is added:

```

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  width: 100%;
  height: 100vh;
  background-color: black;
}

.container{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-family: cursive;
  width: 50%;
  margin: 2rem auto;
  background-color: rgb(185, 255, 127);
  padding: 2rem 2rem;
  border: 1px solid blueviolet;
  border-radius: 20px;
  box-shadow: red 1px 3px 6px;
  position: relative;
}

.container h1{
  margin-bottom: 2rem;
  letter-spacing: 3px;
  border-bottom: 3px outset thistle;
}

#mytextarea{
  padding: 5px 10px;
  font-size: 1.6rem;
  border-radius: 10px;
  box-shadow: royalblue 0px 2px 6px;
  width: 90%;
  height: 15rem;
 
}

.color-change{
  position: absolute;
  top: 0;
  right: 4;
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin: 5px 9px;

}

.color-change input{
  margin: 8px;
  cursor: pointer;
}

.color-change button{
  width: 7rem;
  height: 1.7rem;
  cursor: pointer;
  border-radius: 5px;
  color: #ffffff;
  background-color: rgb(18, 146, 146);
  font-family: cursive;
}

.color-change button:hover{
  color: blueviolet;
  background-color: cadetblue;
  scale: 0.9;
  font-weight: 600;
}

```

### Step-3: JS

Lastly to add the respect functionality to the appliation we need to create a JS file and the following code is added int the file:

```

const textArea=document.getElementById("mytextarea")
const changeColor=document.getElementById("changeColor")


function saveToLocal(){
    localStorage.setItem("auto save",textArea.value);
}

if(localStorage.getItem("auto save")){
    textArea.value=localStorage.getItem("auto save");
}


textArea.addEventListener("input", saveToLocal);

const colorChoose=document.getElementById("colors")
const container=document.querySelector(".container");

colorChoose.addEventListener("click",()=>{
    container.style.color=colorChoose.value;
    textArea.style.color=colorChoose.value;
})

```

## Code Explanation

In the above the HTML code we create one main div with class container inside this we are adding textarea tag, inside this we are add another div for change color area input type color and one button for color change. The style of the html page is done with the help of css code which styles the textarea element.For adding the functionality to the application the Js code is added in the js file for store the date local storage we are using localStorage concepts.

