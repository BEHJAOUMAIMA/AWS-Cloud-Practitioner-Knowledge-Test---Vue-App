<template>
    <body>
    
     <div class="section" id="section">
        <div>
            <p class="logo"><span class="p1">Quiz</span><span class="p2">izy</span> <span class="p3"> !</span> </p>
        </div>
        <div class="form">
            <input id="input" type="text" placeholder="Entrer votre Nom" />
            <div id="errorname" class="errorname"></div>
            <button id="btnvalider">Valider</button>
        </div>
    </div>
</body>
</template>

<style>
body .section .logo .p1 {
  color: #243763;
  font-size: 83px;
}
body .section .logo .p2 {
  color: #ff6319;
}
body .section .logo .p3 {
  color: #3E6D9C;
  font-size: 85px;
}
body .section .form {
  display: flex;
  flex-direction: column;
  margin: 5px auto;
  padding: 15px 20px;
  width: 490px;
  background-color: #fff;
}
body .section .form #input {
  padding: 15px;
  margin-top: 15px;
  margin-bottom: 7px;
  text-align: center;
  border-radius: 30px;
  border: 3px solid black;
  font-family: "Poppins", sans-serif;
  font-weight: bold;
  font-size: 15px;
}
body .section .form .errorname {
  color: #243763;
  font-family: "Poppins", sans-serif;
  font-size: 14px;
  font-weight: bold;
  text-align: center;
  margin: 10px 0;
}
body .section .form #btnvalider {
  cursor: pointer;
  padding: 15px;
  margin-bottom: 10px;
  text-align: center;
  background-color: #243763;
  border: none;
  color: white;
  font-family: "Poppins", sans-serif;
  font-weight: bold;
  font-size: 18px;
}
body .section .form #btnvalider:hover {
  background-color: #ff6319;
  color: white;
  font-weight: bolder;
  font-size: 20px;
}
</style>