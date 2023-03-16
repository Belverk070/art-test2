<!-- eslint-disable vuejs-accessibility/mouse-events-have-key-events -->
<template>
  <div class="circle">

    <div
    class="circle__sector-gray"
    @mouseover="isGraySelected = true"
    @mouseleave="isGraySelected = false">
      <img src="../assets/images/circle.svg" alt="Серый сектор" />
    </div>

    <div
    class="circle__sector-pink"
    @mouseover="isPinkSelected = true"
    @mouseleave="isPinkSelected = false">
      <img src="../assets/images/pink-segm.svg" alt="Розовый сектор" />
    </div>

    <div
    class="circle__sector-green"
    @mouseover="isGreenSelected = true"
    @mouseleave="isGreenSelected = false">
      <img src="../assets/images/green-segm.svg" alt="Зеленый сектор" />
    </div>
  </div>

  <ul class="legend">
    <li
    class="legend-item"
    :class="{ 'legend-item_active': isPinkSelected }">
      <div class="square square_pink" />
      <p class="legend-text">Розовый сегмент</p>
    </li>

    <li
    class="legend-item"
    :class="{ 'legend-item_active': isGreenSelected }">
      <div class="square square_green" />
      <p class="legend-text">Зеленый сегмент</p>
    </li>

    <li
    class="legend-item"
    :class="{ 'legend-item_active': isGraySelected }">
      <div class="square square_gray" />
      <p class="legend-text">Серый сегмент</p>
    </li>

  </ul>
</template>

<script>
export default {
  name: 'CircleComponent',
  data() {
    return {
      isPinkSelected: false,
      isGreenSelected: false,
      isGraySelected: false,
    };
  },
};
</script>

<style scoped>
.circle {
  width: 515px;
  height: 515px;
  margin: auto 100px;
  position: relative;
  clip-path: circle(49.5% at 50% 50%);
}
.circle__sector-gray {
  position: absolute;
  top: 0;
  right: 0;
  clip-path: polygon(50% 49.3%, 100.59% 256px, 100% 99.04%, 77.19% 102.5%, 193px 100.39%);
}
.circle__sector-gray::after {
  content: "";
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0);
  transition: all 0.25s linear;
}
.circle__sector-gray:hover::after {
  background-color: rgba(0, 0, 0, 0.2);
}
.circle__sector-pink {
  position: absolute;
  top: 0;
  right: 0;
  clip-path: polygon(0% 0%, 100% 0, 100% 100%, 77% 100%, 0 100%);
  transition: all 0.25s linear;
}
.circle__sector-pink::after {
  content: "";
  width: 100%;
  height: 257px;
  position: absolute;
  top: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0);
  transition: all 0.25s linear;
}
.circle__sector-pink:hover::after {
  background-color: rgba(0, 0, 0, 0.2);
}
.circle__sector-green {
  position: absolute;
  bottom: 1px;
  left: 1px;
  clip-path: polygon(-0.39% -2.24%, 55.05% -14px, 100.39% 47.8%, 74.67% 103.66%, 0px 100%);
}
.circle__sector-green::after {
  content: "";
  width: 100%;
  height: 100%;
  position: absolute;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0);
  transition: all 0.25s linear;
}
.circle__sector-green:hover::after {
  background-color: rgba(0, 0, 0, 0.2);
}
.circle__sector-green:hover{
  opacity: 1;
  border-bottom: 1px solid #97bb31;
}
.legend-item {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
  opacity: 0.6;
  transition: all 0.25s ease-in-out;
}
.legend-item:last-of-type {
  margin-bottom: 0;
}
.legend-item_active {
  opacity: 1;
  transition: all 0.25s ease-in-out;
}
.legend-text {
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 1;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}
.square {
  width: 14px;
  height: 14px;
  margin-right: 13px;
}
.square_pink {
  background-color: #ff69b4;
}
.square_green {
  background-color: #97bb31;
}
.square_gray {
  background-color: #d9d9d9;
}
</style>
