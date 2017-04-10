<template>
  <div class="test">
    <input type="text" v-model="title">
    <h1>
      {{ title }}
    </h1>
    <p v-if="showName">
      {{user.name}}
    </p>
    <ul>
      <li v-for="item in items"> {{item.title}} </li>
    </ul>
    <button v-on:click="greet">Say hello</button>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">

    <br>
    <br>

    <label>
      First name:
    </label>
    <input type="text" v-model="user.name">
    <br>
    <label>
          Last name:
        </label>
        <input type="text" v-model="user.lastname">
        <br>
    <h3> {{fullName}} </h3>
    <h2> {{ msg }} </h2>
  </div>
</template>



<script>
    export default {
        name: 'test',
        props: {
            msg: {
                type: String,
                default: 'Foobar'
            }
        },
        data() {
            return {
                title: 'test hello',
                user: {
                    name: 'John',
                    lastname: 'Doe',
                },
                showName: true,
                items: [{
                        title: 'Item 1'
                    },
                    {
                        title: 'Item 2'
                    },
                    {
                        title: 'Item 3'
                    },
                    {
                        title: 'Item 4'
                    }
                ]
            }

        },
        methods: {
            greet: function() {
                alert('Hello');
            },
            pressKey: function(e) {
                console.log(e.target.value);
            },
            enterHit: function() {
                console.log('Enter');
            }
        },
        computed: {
            fullName: function() {
                return this.user.name + ' ' + this.user.lastname
            }
        }

    }
</script>


<style scoped>

</style>