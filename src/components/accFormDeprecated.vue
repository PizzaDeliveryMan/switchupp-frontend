<!--
accForm
container component for the sign up/sign in form

TODO:
- need to connect with the drawer
- need to add it into the index, add directly into its child to make it show

NOTE:
- v-once here can be removed later if it cause problems
-->

<template>
  <!--
  <transition name="fade" mode="out-in" key="active">
    <div v-if="formShow === true" class="overlayForm" >

      <div class="overlayForm-click" @click="toggleForm"></div>
      <div class="formBox card">
        <accFormContent  />
      </div>

    </div>

    <div v-else key="inactive">
    </div>
  </transition> -->
  <q-modal ref="accountForm">
    <accFormContent />
  </q-modal>
</template>


<script>
/*
TODO:
  the form-btn
*/
// import accFormContent from './accFormContent'
export default{
  name: 'accFormDeprecated',

  methods:
  {
    toggleForm: function () {
      // document.getElementById('accountForm').style.opacity = '0'
      // document.getElementById('accountForm').style.display = 'none'
      this.formShow = !this.formShow
    }
  },

  data: function () {
    return {
      formShow: false
    }
  }
  //
  // components: {
  //   accFormContent
  // }
}
</script>


<style>


.overlayForm
{
  background-color: rgba(12,23,40,0.7);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom:0;
  z-index:40;

  display: flex;
  align-items:     center;
  justify-content: center;

}


.overlayForm-click
{
  position: fixed;
  top:    0;
  left:   0;
  right:  0;
  bottom: 0;

  z-index: 50;
}

/* for transition effect */
.fade-enter-active, .fade-leave-active {
  transition: opacity .2s
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0
}

.formBox
{
  background-color: #F9F9F9;

  position: fixed;
  z-index: 99;

  width: 400px;
  height: 420px;
  padding: 25px 25px 25px 25px;

}


</style>
