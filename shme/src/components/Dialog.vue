<template>
  <body class="dialog" v-if="showdialog">
    <div class="dia">
        <div class="title">
            <b>对话框标题</b>
            <button class="close-btn" @click="closeD">X</button>
        </div>
        <div class="content">
            <span v-text="msg"></span>
        </div>
        <div class="sub">
            <button class="cancel" @click="closeD">取消</button>
            <button class="confirm" @click="confirmD">确定</button>
        </div>
    </div>
  </body>
</template>

<script>
export default {
    data(){
        return{
            showdialog:this.hasdialog,
        }
    },
    props:{
        hasdialog:{type:Boolean},
        msg:{type:String}
    },
    watch:{
        hasdialog(e){
            this.showdialog=e
        }
    },
    methods:{
        closeD(){
            this.showdialog=false;
            this.toShme();
            alert("关闭对话框");
        },
        confirmD(){
            this.showdialog=false;
            this.toShme();
            alert("确认对话框");
        },
        toShme(){
            this.$emit("offdialog")
        }    
    }
}
</script>

<style>
    .dialog{
        display:flex;
        align-items:center;
        justify-content:center;
        background:rgba(0,0,0,0.5);
        position:fixed;
        top:0;
        bottom:0;
        right:0;
        left:0;
    }
   .dia{
       width:450px;
       padding:10px;
       background-color:#fff;
   }
   .dia button{
       background:none;
       border:0;
   }
   .dia .title{
        box-sizing: border-box;
       width:100%;
       height:40px;
       line-height: 40px;
       padding:0 10px;
       position:relative;
   }
   .dia .title>button{
       position:absolute;
       right:20px;
       top:10px;
   }
   .dia .content{
        box-sizing: border-box;
       padding:10px;
       margin:10px 0;
       width:100%;
   }
   .dia .sub{
       height:40px;
       text-align: end;
   }
   .dia .sub button{
       width:50px;
       height:30px;
       margin:10px;
       border-radius:5px;
   }
   .dia .sub button:last-child{
       background:#409eff;
       color:#fff;
   }
    .dia button:hover{
        opacity:0.8;
    }
</style>
