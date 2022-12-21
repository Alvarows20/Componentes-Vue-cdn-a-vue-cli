<template>
  <tr>
    <td>
      <img :src="img.url" :alt="img.imagen" />
      <p class="text-center">{{ name }}</p>
    </td>
    <td>
      <p>{{ data }}</p>
    </td>
    <td>
      <p :class="changeColorcategory(category)" class="tagCategory">
        {{ category }}
      </p>
    </td>
    <td>
      <p class="d-flex">
        <span class="startYellow">{{ starYellowValue(start) }}</span>
        <span class="startGrey">{{ starGreyValue(start) }}</span>
      </p>
    </td>
  </tr>
</template>
<script>
export default {
  props: {
    img: Object,
    name: String,
    data: String,
    category: String,
    start: Number,
  },
  data() {
    return {
      starType: "★",
    };
  },
  methods: {
    changeColorcategory(value) {
      let style = "";
      if (value === "Documental") {
        style = "categoryGreen";
      } else if (value === "Aventura") {
        style = "categoryBlue";
      } else {
        style = "categoryYellow";
      }
      return style;
    },
    starYellowValue(value) {
      let countStart = "";
      for (let index = 0; index < value; index++) {
        countStart = countStart + this.starType;
      }
      return countStart;
    },
    starGreyValue(value) {
      let valueTotal = 5 - value;
      let countStart = "";
      for (let index = 0; index < valueTotal; index++) {
        countStart = countStart + this.starType;
      }
      return countStart;
    },
  },
};
</script>
<style>
.d-flex {
  display: flex;
  justify-content: center;
  margin: 3rem 0;
}
tr > th {
  padding: 0.5rem;
}
td {
  padding: 1rem;
}
.text-left {
  text-align: left;
}
.text-center {
  text-align: center;
}
table {
  width: 85%;
}
.tagCategory {
  color: #02326b;
  padding: 0.5rem;
  border-radius: 0.5rem;
  box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px,
    rgba(0, 0, 0, 0.22) 0px 15px 12px;
  text-align: center;
}
.categoryGreen {
  background-color: #4dd69e;
}
.categoryBlue {
  background-color: #50bef8;
}
.categoryYellow {
  background-color: #fedda9;
}
.startYellow {
  font-size: 1.5rem;
  color: #fedda9;
}
.startGrey {
  font-size: 1.5rem;
  color: grey;
}
</style>
