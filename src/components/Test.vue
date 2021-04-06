<template>
    <div>
        {{hello}}
    </div>
</template>

<script>
export default {
    name: 'Test',
    props:{
        msg: String
    },
    data(){
        return{
            books: 1,
            hello: 'welcome to Vue JS'
        }
    },
    beforeCreate() {
        alert('beforeCreate hook has been called. Notice the Image has not loaded yet')
        console.log('beforeCreate hook has been called!')
    },
    created(){
        alert('Created hook has been called');
        console.log(`books is of type ${typeof this.books}`);
        console.log(`# of books ${this.books}`)
    },
    beforeMount() {
        alert('beforeMount is called')
    },
    mounted() {
        alert('mounted has been called'); 
    },
    beforeUpdate(){
        alert('beforeUpdate hook has been called');
    },
    updated(){
        alert('Updated hook has been called');
    },
    beforeDestroy() {
        this.books = null
        delete this.books
    },
    destroyed() {
        this.$destroy() 
        console.log(this)
    }
}
</script>

<style scoped>

</style>
