<template>
    <h1>The components</h1>

    <ButtonGroup :count=4>
        <template v-slot:button-0>
            <Button  @click="sm" type="button" label="Click me">button</Button>
        </template>
        <template v-slot:button-1>
            <Button link="/about" :externalLink="true" type="button" label="Click me">link</Button>
        </template>
        <template v-slot:button-2>
            <Button :disabled="true" variant="primary" type="button" label="Click me">button</Button>
        </template>
        <template v-slot:button-3>
            <Button variant="secondary" type="button" label="Click me">button</Button>
        </template>
    </ButtonGroup>
</template>

<script setup>

const sm = () => {
    alert('hi')
}
</script>

<style scoped lang='scss'>
*{
    margin-bottom: 10px;
}

.buttons{
    display: flex;
    align-items: center;

    *{
        margin: 0 10px;
    }
}
</style>