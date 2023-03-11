<template>
  <div class="container">
    <div id="stepper">
      <ul id="prog">
        <li>
          <i class="icon uil uil-user-exclamation"></i>
          <div class="progress one">
            <p class="number">1</p>
            <i class="uil uil-check"></i>
          </div>
          <p class="step">Informations</p>
        </li>
        <li>
          <i class="icon uil uil-file-question-alt"></i>
          <div class="progress two">
            <p class="number">2</p>
            <i class="uil uil-check"></i>
          </div>
          <p class="step">Quiz</p>
        </li>
        <li>
          <i class="icon uil uil-trophy"></i>
          <div class="progress three">
            <p class="number">3</p>
            <i class="uil uil-check"></i>
          </div>
          <p class="step">Résultats</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<style>
body .container #stepper ul {
  display: flex;
  margin: 5px;
}
body .container #stepper ul li {
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-family: "Poppins", sans-serif;
}
body .container #stepper ul li .icon {
  font-size: 27px;
  margin: 0 200px;
  color: #fff;
}
body .container #stepper ul li .step {
  font-size: 15px;
  font-weight: 600;
}
body .container #stepper ul li .progress {
  margin: 2px 0;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: #fff;
  display: grid;
  place-items: center;
  position: relative;
  cursor: pointer;
}
body .container #stepper ul li .progress .uil {
  display: none;
}
body .container #stepper ul li .progress .number {
  font-size: 14px;
  color: #ff6319;
  font-weight: 800;
}
body .container #stepper ul li .progress::after {
  content: " ";
  position: absolute;
  width: 397px;
  height: 5px;
  background-color: #fff;
  right: 30px;
}
body .container #stepper ul li .one::after {
  width: 0;
  height: 0;
}
body .container #stepper ul li .active {
  background-color: #ff6319;
}
body .container #stepper ul li .active .number {
  display: none;
}
body .container #stepper ul li .active .uil {
  display: flex;
}
body .container #stepper ul li .active::after {
  background-color: #ff6319;
}
</style>
