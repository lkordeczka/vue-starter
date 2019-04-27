
<template>
        <div>
                <p> Zalogowany jako {{email}}</p>
                <div>
                        <ol>
                                <li v-for="meeting in meetings">
                                        {{ meeting }}
                                </li> 
                        </ol>
                </div>
                <button @click="$emit('logout')">Wyloguj</button>                
        </div>
</template>

<script>
        export default {
                props: ['email'],
                data(){return                         {
                                meetings: [
                                        'MWO',
                                        'TO',
                                        'INNE'
                                ]
                        }

                }
        }
</script>