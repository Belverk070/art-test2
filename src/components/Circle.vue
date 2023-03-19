<template>
  <div class="circle">
    <div
      v-for="section in sections"
      :key="section.id"
      @mouseover="section.isSelected = true"
      @mouseout="section.isSelected = false"
      class="circle__sector"
      :class="{
        ['circle__sector-' + section.color]: section.color,
        'circle__sector_active': section.isSelected,
      }"
      :style="`clip-path: ${section.polygon}`"
    />
  </div>
  <ul class="legend">
    <li
      v-for="legend in sections"
      :key="legend.id"
      @mouseover="legend.isSelected = true"
      @mouseout="legend.isSelected = false"
      class="legend__item"
      :class="{ 'legend__item_active': legend.isSelected }"
    >
      <div class="square" :class="'square-' + legend.color" />
      <p class="legend-text" :class="{['underline__color--' + legend.color]: legend.isSelected}">
        {{ legend.description }}
      </p>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CircleComponent',
  data() {
    return {
      sections: [
        {
          id: 1,
          color: 'pink',
          isSelected: false,
          polygon: 'polygon(0% 0%, 100% 0, 100% 100%, 77% 100%, 0 100%)',
          description: 'Розовый сегмент',
        },
        {
          id: 2,
          color: 'gray',
          isSelected: false,
          polygon: 'polygon(48.75% 50%, 0% -25%, 0% 0%, 100% 0%, 100% 50%)',
          description: 'Серый сегмент',
        },
        {
          id: 3,
          color: 'green',
          isSelected: false,
          polygon: 'polygon(48.75% 50%, 0% -25%, 0% 100%, 60% 100%)',
          description: 'Зеленый сегмент',
        },
      ],
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
  clip-path: circle(50% at 50% 50%);
}
.circle__sector {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
}
.circle__sector-gray {
  background-color: #d9d9d9;
}
.circle__sector-pink {
  background-color: #ff69b4;
}
.circle__sector-green {
  background-color: #97bb31;
}
.circle__sector_active {
  filter: brightness(60%);
  transition: all 0.5s ease-in-out;
}
.legend__item {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
  opacity: 0.6;
  transition: all 0.5s ease-in-out;
}
.legend__item_active {
  opacity: 1;
  transition: all 0.5s ease-in-out;
}
.legend-text {
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 1;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  text-decoration: underline;
  text-underline-offset: 10px;
  text-decoration-color: transparent;
  transition: 0.5s;
}
.underline__color--pink {
  text-decoration-color: #ff69b4;
}
.underline__color--gray {
  text-decoration-color: #d9d9d9;
}
.underline__color--green {
  text-decoration-color: #97bb31;
}
.square {
  width: 14px;
  height: 14px;
  margin-right: 13px;
}
.square-pink {
  background-color: #ff69b4;
}
.square-gray {
  background-color: #d9d9d9;
}
.square-green {
  background-color: #97bb31;
}
</style>
