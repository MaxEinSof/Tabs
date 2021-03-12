<script>
export default {
  name: 'Tabs',
  emits: ['change'],
  data() {
    return {
      selectedTabIndex: 0,
    }
  },
  methods: {
    switchTab(index) {
      this.selectedTabIndex = index;
      this.$emit('change');
    },
  },
  render() {
    const tabs = this.$slots.default;

    const tabList = [];

    tabs.forEach((tab, index) => {
      const { label } = tab.componentOptions.propsData;

      tabList.push(
        <li
            class="tabs__item"
            onClick={() => this.switchTab(index)}
            aria-selected={this.selectedTabIndex === index ? "true" : "false"}
        >
          {label}
        </li>
      );
    });

    return (
      <div class="tabs">
        <ul class="tabs__list">
          {tabList}
        </ul>

        <div class="tabs__content">
          {tabs[this.selectedTabIndex]}
        </div>
      </div>
    );
  },
}
</script>

<style scoped>
  .tabs {
    max-width: 1000px;
    margin: 0 auto;
    padding: 120px 40px;
    background-color: #1a143b;
    border-radius: 10px;
  }

  .tabs__list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    min-height: 40px;
    margin: 0 0 20px 0;
    padding: 0;
    list-style: none;
  }

  .tabs__item {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 5px;
    text-transform: uppercase;
    color: #ffffff;
    background-color: #281f55;
    border: 1px solid #ffffff;
    cursor: pointer;
  }

  .tabs__item[aria-selected="true"] {
    color: #281f55;
    background-color: #ffffff;
  }

  .tabs__item:first-child {
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
  }

  .tabs__item:last-child {
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
  }
</style>