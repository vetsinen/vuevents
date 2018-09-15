<template>
    <div class="events">
        <ul>
            <li v-for="event in events">
                <button v-on:click="selected(event.id)">submit</button>
                {{event.title}}
            </li>
        </ul>
        <button v-on:click="next">next</button>
        <footer>
            footer: For guide and {{ msg }} on how to
        </footer>
    </div>
</template>

<script>
    //https://jsonplaceholder.typicode.com/ ajax testing
    export default {
        name: 'events',
        data: function () {
            return {
            }
        },
        props: {
            msg: String
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
