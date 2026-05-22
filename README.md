<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>TBSE Login Portal</title>

<style>

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:Arial, Helvetica, sans-serif;
  transition:0.3s;
}

:root{
  --main:#39d0a0;
}

body{
  min-height:100vh;
  background:#05070f;
  display:flex;
  justify-content:center;
  align-items:center;
  overflow:auto;
  padding:20px;
}

/* LIGHT MODE */

body.light{
  background:#edf1f7;
}

body.light .container{
  background:white;
}

body.light .right{
  background:white;
  color:black;
}

body.light .subtitle{
  color:#555;
}

body.light .input-box{
  background:#edf1f7;
  border:1px solid #ccd5e1;
  color:black;
}

body.light .theme-btn{
  background:#dbe4ef;
  color:black;
}

body.light .refresh-btn{
  background:#dbe4ef;
  color:black;
}

/* MAIN CONTAINER */

.container{
  width:1000px;
  min-height:600px;
  height:auto;
  background:#0d1018;
  display:flex;
  border-radius:24px;
  overflow:hidden;
  box-shadow:0 0 30px rgba(0,0,0,0.7);
}

/* LEFT PANEL */

.left{
  width:50%;
  background:var(--main);
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  padding:40px;
}

.logo{
  width:170px;
  height:170px;
  border-radius:50%;
  background:white;
  color:var(--main);
  display:flex;
  justify-content:center;
  align-items:center;
  font-size:58px;
  font-weight:bold;
  margin-bottom:35px;
}

.left h1{
  font-size:58px;
  color:white;
  margin-bottom:15px;
}

.left p{
  color:white;
  font-size:22px;
  line-height:1.5;
}

/* RIGHT PANEL */

.right{
  width:50%;
  padding:28px 45px;
  color:white;
  background:#0d1018;
}

.top-bar{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:25px;
}

.theme-btn{
  border:none;
  background:#1f2735;
  color:white;
  padding:10px 18px;
  border-radius:10px;
  cursor:pointer;
  font-size:15px;
}

.color-options{
  display:flex;
  gap:10px;
}

.color{
  width:25px;
  height:25px;
  border-radius:50%;
  cursor:pointer;
  border:2px solid white;
}

.green{background:#39d0a0;}
.blue{background:#3b82f6;}
.purple{background:#8b5cf6;}
.orange{background:#f97316;}

.right h2{
  font-size:52px;
  margin-bottom:10px;
}

.subtitle{
  color:#bcc3cf;
  margin-bottom:20px;
  font-size:18px;
}

.label{
  display:block;
  margin-bottom:10px;
  font-size:18px;
  font-weight:600;
}

.input-box{
  width:100%;
  height:56px;
  border-radius:10px;
  border:1px solid #394252;
  background:#2a3447;
  color:white;
  padding:0 18px;
  font-size:20px;
  outline:none;
  margin-bottom:18px;
}

.password-wrapper{
  position:relative;
}

.eye{
  position:absolute;
  right:18px;
  top:15px;
  font-size:22px;
  cursor:pointer;
}

.captcha-section{
  display:flex;
  gap:15px;
  align-items:center;
  margin-bottom:18px;
}

.captcha-box{
  width:140px;
  height:55px;
  background:white;
  border-radius:8px;
  color:black;
  display:flex;
  justify-content:center;
  align-items:center;
  font-size:26px;
  font-weight:bold;
  letter-spacing:2px;
}

.refresh-btn{
  width:55px;
  height:55px;
  border:none;
  border-radius:10px;
  background:#1f2735;
  color:white;
  font-size:24px;
  cursor:pointer;
}

.register{
  color:var(--main);
  text-decoration:none;
  display:inline-block;
  margin-bottom:25px;
  font-size:18px;
}

.button-group{
  display:flex;
  gap:15px;
}

.login-btn{
  flex:1;
  height:58px;
  border:none;
  border-radius:10px;
  background:var(--main);
  color:black;
  font-size:26px;
  font-weight:600;
  cursor:pointer;
}

.home-btn{
  width:130px;
  border-radius:10px;
  border:2px solid orange;
  background:transparent;
  color:orange;
  font-size:22px;
  cursor:pointer;
}

/* RESULT PAGE */

.result-page{
  display:none;
  width:100%;
  min-height:100vh;
  background:#111827;
  color:white;
  justify-content:center;
  align-items:center;
  flex-direction:column;
  text-align:center;
  padding:20px;
}

.result-page h1{
  font-size:60px;
  margin-bottom:20px;
}

.result-page p{
  font-size:24px;
  margin-bottom:30px;
}

.back-btn{
  padding:15px 30px;
  border:none;
  border-radius:12px;
  background:var(--main);
  font-size:22px;
  cursor:pointer;
}

/* MOBILE */

@media(max-width:900px){

  .container{
    width:100%;
    flex-direction:column;
  }

  .left,
  .right{
    width:100%;
  }

  .right{
    padding:25px;
  }

  .top-bar{
    flex-direction:column;
    align-items:flex-start;
    gap:15px;
  }

  .right h2{
    font-size:40px;
  }

}

</style>

</head>

<body>

<!-- LOGIN PAGE -->

<div class="container" id="loginPage">

  <!-- LEFT -->

  <div class="left">

    <div class="logo">
      TB
    </div>

    <h1>TBSE</h1>

    <p>
      Thara Board of Secondary Education
      <br><br>
      Photocopy • Verification • Re-evaluation Services
    </p>

  </div>

  <!-- RIGHT -->

  <div class="right">

    <!-- TOP BAR -->

    <div class="top-bar">

      <button class="theme-btn" onclick="toggleTheme()">
        🌙 Day / Night
      </button>

      <div class="color-options">

        <div class="color green" onclick="changeColor('#39d0a0')"></div>

        <div class="color blue" onclick="changeColor('#3b82f6')"></div>

        <div class="color purple" onclick="changeColor('#8b5cf6')"></div>

        <div class="color orange" onclick="changeColor('#f97316')"></div>

      </div>

    </div>

    <h2>Sign In</h2>

    <p class="subtitle">
      Enter your credentials to continue
    </p>

    <!-- ROLL -->

    <label class="label">
      Roll Number
    </label>

    <input 
      type="text"
      class="input-box"
      id="roll"
      placeholder="Enter 10 digit roll number"
      maxlength="10"
    >

    <!-- PASSWORD -->

    <label class="label">
      Password
    </label>

    <div class="password-wrapper">

      <input 
        type="password"
        class="input-box"
        id="password"
        placeholder="Enter password"
      >

      <span class="eye" onclick="togglePassword()">
        👁
      </span>

    </div>

    <!-- CAPTCHA -->

    <div class="captcha-section">

      <div class="captcha-box" id="captcha">
        JW44TY
      </div>

      <button class="refresh-btn" onclick="refreshCaptcha()">
        ↻
      </button>

    </div>

    <input 
      type="text"
      class="input-box"
      id="captchaInput"
      placeholder="Enter captcha"
    >

    <!-- REGISTER -->

    <a href="#" class="register" onclick="registerAlert()">
      Register
    </a>

    <!-- BUTTONS -->

    <div class="button-group">

      <button class="login-btn" onclick="login()">
        Login
      </button>

      <button class="home-btn" onclick="goHome()">
        ⌂ Home
      </button>

    </div>

  </div>

</div>

<!-- RESULT PAGE -->

<div class="result-page" id="resultPage">

  <h1>Welcome To TBSE</h1>

  <p>
    Login Successful ✅
  </p>

  <button class="back-btn" onclick="backToLogin()">
    Back
  </button>

</div>

<script>

/* THEME */

function toggleTheme(){
  document.body.classList.toggle("light");
}

/* COLOR CHANGE */

function changeColor(color){
  document.documentElement.style.setProperty('--main', color);
}

/* PASSWORD SHOW */

function togglePassword(){

  let pass = document.getElementById("password");

  if(pass.type === "password"){
    pass.type = "text";
  }
  else{
    pass.type = "password";
  }

}

/* CAPTCHA */

function refreshCaptcha(){

  document.getElementById("captcha").innerHTML = "JW44TY";

}

/* REGISTER */

function registerAlert(){

  alert("TBSE Registration Portal Coming Soon!");

}

/* HOME */

function goHome(){

  window.scrollTo({
    top:0,
    behavior:"smooth"
  });

  alert("You are already on the Home Page.");

}

/* LOGIN */

function login(){

  let roll = document.getElementById("roll").value;
  let password = document.getElementById("password").value;
  let captcha = document.getElementById("captchaInput").value;

  /* ROLL NUMBER CHECK */

  if(roll.length !== 10 || isNaN(roll)){

    alert(`
Unexpected JSON Parse Error

{
  "status": 400,
  "error": "Invalid Roll Number",
  "code": "TBSE_JSON_101"
}
    `);

    return;
  }

  /* PASSWORD CHECK */

  if(password !== "NEHAISAFOOL"){

    alert(`
Unexpected JSON Error

{
  "status": 401,
  "message": "Authentication Failed",
  "error": "Invalid Password",
  "code": "TBSE_AUTH_403"
}
    `);

    return;
  }

  /* CAPTCHA CHECK */

  if(captcha !== "JW44TY"){

    alert(`
Unexpected JSON Error

{
  "status": 500,
  "message": "Captcha Validation Failed",
  "error": "Unexpected token JW44TY",
  "code": "TBSE_CAPTCHA_500"
}
    `);

    return;
  }

  /* SUCCESS */

  document.getElementById("loginPage").style.display = "none";

  document.getElementById("resultPage").style.display = "flex";

}

/* BACK */

function backToLogin(){

  document.getElementById("resultPage").style.display = "none";

  document.getElementById("loginPage").style.display = "flex";

}

</script>

</body>
</html>
