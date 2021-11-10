<template>
    <div class="grid grid-cols-2">
        <div class="font-semibold text-xl">
            {{selected.name}} Chat
        </div>
        <select v-model="selected" @change="$emit('roomChanged',selected)" class="float-right" name="" id="">
            <option :value="room" v-for="(room,index) in rooms" :key="index">
                {{room.name}}
            </option>
        </select>
    </div>
</template>

<script>
export default {
name: "ChatRoomSelection",
    props:['rooms','currentRoom'],
    data() {
        return {
            selected: ''
        }
    },
    created() {
        this.selected = this.currentRoom;
    }
}
</script>

<style scoped>

</style>
