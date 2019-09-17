<template>
  <div>
      <button @click="onDialog" class="toShow">显示对话框</button>
      <Dialog :hasdialog="showDialog" :msg="msg" @offdialog="offDialog"/>
  </div>
</template>

<script>
import Dialog from '../components/Dialog'

export default {
    data(){
        return{
            showDialog:false,
            msg:"对话框内容"
        }
    },
    components:{
        Dialog
    },
    methods:{
        onDialog(){
            this.showDialog=!this.showDialog;
        },
        offDialog(show){
            this.showDialog=false;
        }
    }
}
</script>

<style>
    body{
        padding:0;
        margin:0;
    }
    button.toShow{
        width:250px;
        height:30px;
    }
</style>