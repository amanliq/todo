<template>
    <div>
      <transition name="modal">
       <div class="modal-mask">
        <div class="modal-wrapper">
          <div class="modal-container">
           <slot name="header"></slot>
           <div class="modal-footer">
            <button  class="modal-default-button" @click="$emit('delete')">Ok</button>
            <button class="modal-default-button" @click="$emit('close')">Cancel</button>
           </div>
          </div>
        </div>
        </div>
     </transition>
    </div>
</template>

<script>
export default {
  props: {
    personId: null
  }
}
</script>

<style scoped>
.modal-footer {
    border:none;
}
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .5);
  display: table;
  transition: opacity .3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width:40%;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
  transition: all .3s ease;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header h3 {
  margin-top: 0;
}

.modal-default-button {
  float: right;
}
</style>
