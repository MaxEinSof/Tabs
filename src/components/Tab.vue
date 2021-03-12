<script>
export default {
  name: 'Tab',
  props: {
    label: {
      type: String,
      required: true,
    },
  },
  render() {
    return (
      <div class="tab">
        {this.$slots.default}
      </div>
    );
  },
}
</script>

<style scoped>
  .tab {
    min-height: 100px;
    padding: 20px;
    color: #ffffff;
    background-color: #281f55;
    border: 1px solid #ffffff;
    border-radius: 10px;
  }

  .tab button {
    display: block;
    margin-top: 10px;
  }
</style>