<script>
export default {
  name: 'Modal',
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  render() {
    return (this.show) ? <div class="modal">
      <div class="modal-header">
        <a href="#" onClick={this.onClose}>Close</a>
      </div>
      <div class="modal-content">
        { this.$slots.default }
        <button onClick={ this.clickOkHandler }>Aceptar</button>
        <button onClick={ this.clickCancelHandler }>Cancelar</button>
      </div>
    </div> : null;
  },
  methods: {
    clickOkHandler: () => alert('Ok'),
    clickCancelHandler: () => alert('Cancel'),
    onClose() { this.$emit('close-modal'); },
  },
};
</script>
