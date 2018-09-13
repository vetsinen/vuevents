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
        props: {
            msg: String
        },
        created: function(){
            console.log('component started');
            fetch('https://jsonplaceholder.typicode.com/users')
                .then(function(response) {
                    return response.json();
                })
                .then(function(json) {
                    console.log(json);
                    this.events = json;
                })
                .catch( alert );
        },
        data: function () {
            return {
                events: [{id:2423423,name:'party'},{id:5345463,name:'conference'},{id:47363433,name:'concert'}]
            }
        },
        methods: {
            selected: function(id){
              console.log(id);
            },
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
