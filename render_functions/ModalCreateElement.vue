<script>
export default {
  name: 'ModalCreateElement',
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  render (createElement) {
    return (this.show) ? createElement('div', {
      class: 'modal',
    }, [
      createElement('p', {
        class: 'message'
      }, this.message),
      createElement('button', {
        class: 'btn',
        on: {
          click: this.clickCancelHandler,
        }
      }, 'Cancel'),
      createElement('button', {
        class: 'btn',
        on: {
          click: this.clickOkHandler,
        }
      }, 'Ok')
    ]) : null
  },
  methods: {
    clickCancelHandler () {
      alert("click cancel button")
    },
    clickOkHandler () {
      alert("click ok button")
    }
  }
}
</script>