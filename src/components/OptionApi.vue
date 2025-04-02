<template>
    <div>
        <h1>{{ title }}</h1>
        <p>{{ content }}</p>
    </div>
</template>
<script>

export default{
    name: 'OptionApi',
    props: {
        title: {
            type: String,
            default: 'Default Title'
        },
        content: {
            type: String,
            default: 'Default Content'
        }
    },
    methods:{

    },
    setup(props) {
        return {
            props
        }
    },
    beforeMount() {
        console.log('beforeMount');
    },
    mounted() {
        console.log('mounted');
    },
}
</script>