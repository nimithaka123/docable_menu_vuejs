<template>
    <div class="menu">
        <MenuItem
            v-for="(item,index) in menuTree"
            :key="index"
            :label="item.label"
            :depth="0"
            :data="item.children"
        />
    </div>
</template>

<script>
import MenuItem from './MenuItem'

export default{
    name: "docmenu",
    data: () => ({
        menuTree: [
            {   
                label: "File",
                children:[
                    {
                        label: "Open Folder",
                    },
                    {
                        label: "Open Window",
                    },
                    {
                        label: "Open Recent",
                    },
                ]
            },
            {
                label: "Edit",
                children:[
                    {
                        label: "Undo",
                    },
                    {
                        label: "Redo",
                    },
                ]

            },
            {
                label: "settings",
            }
        ]

    }),
    components:{
        MenuItem
    }

 }
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.menu{
    position: fixed;
    height: 300px;
    width: 150px;
    background-color:#F7F9F9  ;
    border-right: 1px solid ;
    border-bottom: 1px solid ;
    border-radius: 8px;
    padding: 5px;
    cursor: pointer;
}
</style>