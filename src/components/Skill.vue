<template>
    <v-card class="pa-4 ma-2">
        <v-layout row wrap>
            <v-flex xs11 md11 lg11>
                <slot></slot>
            </v-flex>
            <v-flex xs1 md1 lg1 align-self-center>
                <v-spacer></v-spacer>
                <i @click="deleteSkill()" class="fas fa-times-circle"></i>
            </v-flex>
        </v-layout>
    </v-card>
</template>

<script>
import {EventBus} from "../eventbus.js"
    export default {
        // props: [skill],
        methods: {
            deleteSkill() {
                const skillLabel = this.$el.children[0].childNodes[0].innerText;
                EventBus.$emit('delete-skill', skillLabel);
            }
        },
    }
</script>

<style>
    p {
        margin-top: 10px;
        font-weight: bold;
        font-size: 16px;
    }
    i {
        position: relative;
        left: 20px;
        font-size: 25px;
    }

</style>