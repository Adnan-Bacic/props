<template>
    <div id="navbar">
        <nav>
            {{ name }}
            {{ number }}
            <hr>

            

            </nav>
    </div>
</template>

<script>
export default {
    name: 'Navbar',

    props:['name', 'number'],

    data(){
        return{
            
        }
    }
}
</script>