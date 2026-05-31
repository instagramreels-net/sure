<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Janya 🥰</title>
<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}
body{
    background:#ffd6e7;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    text-align:center;
    overflow:hidden;
    font-family:Verdana,sans-serif;
    font-weight:bold;
}
.page{
    max-width:750px;
    padding:30px;
    position:relative;
    z-index:2;
}
h1{
    color:#b30059;
    font-size:2.3rem;
    line-height:1.4;
    margin-bottom:35px;
}
button{
    padding:14px 40px;
    border:none;
    border-radius:15px;
    background:#d63384;
    color:white;
    font-size:1.1rem;
    cursor:pointer;
    transition:0.3s;
    font-weight:bold;
}
button:hover{
    transform:scale(1.08);
}
#page2{
    display:none;
}
#page2 p{
    color:#b30059;
    font-size:2rem;
    line-height:1.7;
}
.fade-in{
    animation:fadeIn 2.5s ease forwards;
}
@keyframes fadeIn{
    from{
        opacity:0;
        transform:translateY(20px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}
.floating-container{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    pointer-events:none;
    z-index:1;
}
.float-emoji{
    position:absolute;
    opacity:0.8;
    animation:floatUp linear forwards;
}
@keyframes floatUp{
    from{
        transform:translateY(100vh);
        opacity:0;
    }
    20%{
        opacity:0.8;
    }
    to{
        transform:translateY(-120px);
        opacity:0;
    }
}
</style>
</head>
<body>
<div class="floating-container" id="floatingContainer"></div>
<div id="page1" class="page">
    <h1>
        Can't believe a dumbaah like you actually made it all the way here 🥰
    </h1>
    <button onclick="showPage2()">
        okay?
    </button>
</div>
<div id="page2" class="page">
    <p>
        Janya Yb,
        <br><br>
        You've made me the happiest person on Earth.
        Thank you for making this the best month of my life.
        <br><br>
        I really, really love ya sm 🥰
    </p>
</div>
<script>
function showPage2(){
    document.getElementById("page1").style.display = "none";
    const page2 = document.getElementById("page2");
    page2.style.display = "block";
    page2.classList.remove("fade-in");
    void page2.offsetWidth;
    page2.classList.add("fade-in");
}
function createEmoji(){
    const emoji = document.createElement("div");
    emoji.classList.add("float-emoji");
    emoji.innerHTML = "🥰";
    emoji.style.left = Math.random() * 100 + "vw";
    emoji.style.fontSize =
        (22 + Math.random() * 20) + "px";
    emoji.style.animationDuration =
        (6 + Math.random() * 5) + "s";
    document
        .getElementById("floatingContainer")
        .appendChild(emoji);
    setTimeout(() => {
        emoji.remove();
    }, 11000);
}
setInterval(createEmoji, 450);
</script>
</body>
</html>
