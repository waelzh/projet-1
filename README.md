# projet-1 editeur de photo

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="editeur de photo" content="filtre,  modifier photo">
    <title>editeur photo</title>
    <link rel="stylesheet" href="projet1.css">
    
</head>
<body>

<div class="container" >
  <div class="img">
    <div class="img-box">
      <img id="img">
   </div>
   <div class="upload">
    <label for="upload">upload</label>
    <input type="file" id="upload">
   </div>
 </div>
   <div class="filtre">
<ul>
    <li>
 <label for="saturate">saturate</label>
 <input type="range" id="saturate" min="0" max="200" value="100"> 
</li>
<li>
 <label for="contraste">contraste</label> 
 <input type="range" id="contraste" min="0" max="200" value="100"> 
</li>
<li>
 <label for="brightness">brightness</label>
 <input type="range" id="brightness" min="0" max="200" value="100"> 
</li>
<li>
 <label for="sepia">sepia</label>
 <input type="range" id="sepia" min="0" max="200" value="0">
</li>
<li>
 <label for="grayscale">grayscale</label>
 <input type="range" id="grayscale" step="0.1" min="0" max="1" value="0">
</li>
<li>
    <label for="blur">blur</label>
    <input type="range" id="blur" step="0.1" min="0" max="1" value="0">
</li>
<li>
    <label for="hue-Rotate">hue-rotate</label>
    <input type="range" id="hue-rotate"  min="0" max="350" value="0">
</li>
   <li>
    <a download="true" id="download">download</a>
    <a reset="true" id="reset">reset</a>
   
   </li>
</ul>
   </div>
</div>
</body>

// css
*{
    padding: 0;
    margin: 0;
    font-family: sans-serif;
}
body{
    background-color:#333;    
}
.container {
    background-color: #222;
    width: 80vh;
    margin: auto;
    padding:20px ;
    border-radius: 10px;
    display: grid;
    grid-template-columns: 5fr 3fr;
}
.img{
    display: flex;
    flex-direction: column;
    gap: 50px;
    justify-content: center;
    align-items: center;
   
}
.img img{
    max-width: 45vh;
    max-height: 60vh;
}
.upload input{
    display: none;

}
.upload label{
    color:#fff ;
    padding: 8px 20px ;
    border: 2px #fff dashed;
    cursor: pointer;
}
.filtre ul{
    display: flex;
    flex-direction: column;
    gap: 30px;
}
.filtre ul li{
    display: flex;
    flex-direction: column;
    gap: 20px;
    direction: rtl;
}
.filter ul li label{
    color: #fff;
}
.filtre ul li:last-child{
    flex-direction: row;
    justify-content: space-around;
}
.filtre ul li a,span {
    color:#fff;
    padding:10px 20px;
    background-color: #060; 
}
@media screen and (max-width:650px) {
    .container{
        grid-template-columns: 1fr;
        gap: 50px;
    }
}

//java script 
<script>
let saturate = document.getElementById("saturate") ; 
let contraste = document.getElementById("contraste") ;
let brightness = document.getElementById("brightness");
let sepia = document.getElementById("sepia");
let sgrayscale = document.getElementById("grayscale");
let blur = document.getElementById("blur");
let hueRotate = document.getElementById("hue-Rotate");

let upload = document.getElementById("upload");
let download = document.getElementById("download") ;
let img = document.getElementById("img");

let reset = document.getElementById('reset');
let imgbox = document.getElementById ('.img-box');

window.onload = function(){
    download.style.display='none';
    reset.style.display='none';
    imgbox.style.display='none';
}
upload.onchange=function(){
    download.style.display='block'; 
    reset.style.display='block';
    imgbox.style.display='block'; 
    let file=new FileReader();
    file.readAsDataURL(upload.files[0]);
     file.onload=function(){
        img.src=file.result;
     }
    }
    

</script>

</html>
