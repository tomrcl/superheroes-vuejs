<template>
    <div id="list-superheroes">
        <button v-on:click="shuffle">Mélanger</button>
        <br>
        <transition-group name="list" appear>
            <span v-for="superhero in superheroes" v-bind:key="superhero.id" class="list-complete-item">
                <abbr :title="superhero.name">
                    <img :src="superhero.images.sm" />
                </abbr>
            </span>
        </transition-group>
    </div>
</template>



<script>
import _ from 'lodash';

export  default  {
    el: '#list-superheroes',
    data: function() {
        return {
            superheroes: []
        }
    },
    async beforeCreate() {
        const res = await fetch('https://cdn.jsdelivr.net/gh/akabab/superhero-api@0.3.0/api/all.json');
        this.superheroes = await res.json();
        //console.log(this.superheroes);
    },
    methods: {
        shuffle: function () {
            this.superheroes = _.shuffle(this.superheroes)
        }
    }
}
</script>

<style scoped>
.list-complete-item {
  transition: all 1s;
  display: inline-block;
  margin-right: 10px;
}
.list-complete-enter, .list-complete-leave-to
/* .list-complete-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(30px);
}
.list-complete-leave-active {
  position: absolute;
}
</style>