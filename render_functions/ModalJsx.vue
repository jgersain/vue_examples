<script>
export default {
  name: 'ModalJsx',
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  render() {
    return (this.show) 
      ? <div id="modal" class="shadow-lg m-20">
          <div class="content p-10">
            {this.$slots.default}
          </div>
          <div class="flex justify-center p-3">
            <button class="text-white bg-red-500 py-2 px-4 m-1" onClick={this.clickCancelHandler}>Cancelar</button>
            <button class="text-white bg-blue-500 py-2 px-4 m-1" onClick={this.clickOkHandler}>Ok</button>
          </div>
        </div> 
      : null
  },
  methods: {
    clickCancelHandler () {
      alert("Se presiono el botón de cancelar")
    },
    clickOkHandler () {
      alert("Se presiono el botón de ok")
    }
  }
}
</script>