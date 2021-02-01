<template>
    <v-row>
        <v-col v-for="(s, i) in separators" :key="i">
            <v-text-field
            suffix="/"
            :value="value[i]"
            :ref="'field'+i"
            :label="'field' + i"
            @input="sendValue"
            ></v-text-field>
        </v-col>
    </v-row>
</template>

<script>
export default {
    model: {
        prop: 'value',
        event: 'input',
    },
    props: {
        separators: {
            type: Number,
            default: 1,
        },
        value: {
            type: Array,
            default(){
                return new Array(this.separators);
            },
        }
    },
    methods: {
        sendValue(){
            let arr = [];
            for (let i = 0; i < this.separators; i++) {
                let input = this.$refs['field'+i][0].$el.querySelector('input');
                arr.push(input.value);
            }
            this.$emit('input', arr);
        }
    }
}
</script>