<template>
    <div class="menu-item">
        <div class="label"   @click="toggleMenu()">
            <span>{{label}}</span>
        </div>
        <div class="items-container" v-show="showChildren">
            <menu-item
                v-for="(item,index) in data"
                :key="index"
                :label="item.label"
                :depth="depth + 1"
                :data="item.children"
            />
        </div>
    </div>
</template>

<script>
    export default{
        name: "docmenu",
        data: () => ({
            showChildren: false
        }),
        props: {
            label: {
                type: String,
                required: true
            },
            depth: {
                type: Number,
                required: true
            },
            data: {
                type: Array
            }
        },
        methods: {
            toggleMenu(){
                this.showChildren = !this.showChildren
            }
        }


    }
</script>

<style>
.menu-item{
    position: relative;
    width: 100%;
}
.label{
    width: 100%;
    box-sizing: border-box;
    color:black ;
    font-family: 'Times New Roman', Times, serif;
    font-weight: bold;
    font-size: 17px;
}
.label:hover{
    background-color:#D5D8DC ;
}
.items-container{
    margin:10px
}
</style>