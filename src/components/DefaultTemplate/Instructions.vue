<template>
  <div>
    <md-layout class="recipe-title">
      {{ recipeTitle }}
    </md-layout>
    <md-layout>
      <md-layout md-flex="33" v-for="(column, index) in columns"
        :key="index">
        <md-layout md-flex="100"
          v-for="(section, subindex) in column" :key="subindex">
          <div class="section">
            <div class="section-title">
            {{ section.title }}
          </div>
          <div class="section-content">
            <pre>{{ section.content }}</pre>
          </div>
          </div>
        </md-layout>
      </md-layout>
    </md-layout>
  </div>
</template>

<script>
export default {
  name: 'instructions',
  props: {
    recipeTitle: {
      type: String,
      default: 'RECIPE | 5.5 GAL',
    },
    columns: {
      type: Array,
      default() {
        return [
          [{
            title: 'MALT',
            content: 'PILSNER 5.6#\r\nGERMAN WHEAT',
          },
          {
            title: 'MALT',
            content: 'PILSNER 5.6#\r\nGERMAN WHEAT',
          }],
          [{
            title: 'MALT',
            content: 'PILSNER 5.6#\r\nGERMAN WHEAT',
          }],
        ];
      },
    },
  },
};
</script>

<style>
.recipe-title {
  font-size: 7.5px;
  font-weight: bold;
  font-family: "Fjalla One";
}

.section-title {
  font-size: 7.5px;
  font-weight: bold;
  line-height: 100%;
  font-family: "Fjalla One";
}

.section-content pre {
  font-size: 7.5px;
  line-height: 120%;
  margin-top: 0px;
  font-family: Oswald;
}
</style>
