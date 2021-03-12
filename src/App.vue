<template>
  <div id="app">
    <Tabs @change="onChange">
      <Tab label="Первая вкладка">
        Контент для первой вкладки
      </Tab>

      <Tab label="Вторая вкладка">
        Контент для второй вкладки
      </Tab>

      <Tab label="Третья вкладка">
        <div>
          <span>Контент для третьей вкладки</span>
          <button>Нажми меня</button>
        </div>
      </Tab>
    </Tabs>
  </div>
</template>

<script>
import Tabs from '@/components/Tabs';
import Tab from '@/components/Tab';

export default {
  name: 'Parent',
  methods: {
    onChange() {
      console.log('Таб был переключен');
    },
  },
  components: {Tabs, Tab},
}
</script>
