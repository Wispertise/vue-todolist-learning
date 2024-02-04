<template>
<div class="root1" >
<h3>ToDolist</h3>

<input v-model="addContent" type="text" >
<button @click="addNewItem" >添加</button>
<ul>
    <li v-for="(item,index) in list" :key="item.id">
        <div v-on:mouseenter="showdel(item.id)"  v-on:mouseleave="hiddenbtn"  class="mainForm">
            <div class="notes" >
            <div class="number" >{{ index + 1 }}</div>
            <div class="events">{{ item.name }}</div>
        </div>
        <button @click="deleteitem(item.id)" v-show="delbtn==item.id" v-bind:id="'deleteBtn'+item.id"  class="deleteBtn">X</button>
        </div>
    </li>
</ul>
<div>总计:{{ list.length }}</div>
</div>
</template>

<script>

export default{
    el:".root1",
    data(){
        return{
            list:[
            
            ],
            delbtn:0,
            addContent:'',
        }
       
    },
    methods:{
        showdel(id){
            this.delbtn=id;
            // console.log(id);
        },
        hiddenbtn(){
            this.delbtn=-1;
        },
        deleteitem(id){
            this.list = this.list.filter(item=>item.id!=id)
        },
        addNewItem(){
            this.list.unshift({id:+new Date(),name:this.addContent});
            this.addContent='';
        },
    },
}



</script>
<style>
.root1{
    width: 300px;
    height: 600px;
    justify-content: center;
    margin: 0 auto;
}
li,ul{
    text-decoration: none;
    list-style: none;
}
.mainForm{
    display: flex;
    flex-direction: row;
}
.notes{
    display: flex;
    flex-direction: row;
    height: 60px;
    justify-content: space-between;
}
.number,.events{
    width: 30px;
    font-size: 2rem;
    font-weight: 600;
    height: inherit;
    line-height: 60px;
}
.deleteBtn{
    border: none;
    background: none;
    font-size: 1.5rem;
    cursor: pointer;
}
.events{
    width: 200px;
}
</style>