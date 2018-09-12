<template>
    <div class="events">
        <ul>
            <li v-for="event in events">{{event}}</li>
        </ul>
        <button v-on:click="next">next</button>
        <footer>
            footer: For guide and {{ msg }} on how to
        </footer>
    </div>
</template>

<script>
    export default {
        name: 'events',
        props: {
            msg: String
        },
        data: function () {
            return {
                events: ['party', 'conference', 'concert']
            }
        },
        methods: {
            next: function () {
                console.log('ok');
                this.evbar();
                this.readTextFile("file:////home/vhodzevych/test.txt");
            },
            evbar: function(){},
            readTextFile: function (file) {
                var rawFile = new XMLHttpRequest();
                rawFile.open("GET", file, false);
                rawFile.onreadystatechange = function () {
                    if (rawFile.readyState === 4) {
                        if (rawFile.status === 200 || rawFile.status == 0) {
                            var allText = rawFile.responseText;
                            alert(allText);
                        }
                    }
                };
                rawFile.send(null);
            }

        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
