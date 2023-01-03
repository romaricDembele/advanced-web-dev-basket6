<template>
    <table>
        <tr>
            <td @click="sortTableByRef" class="text-3xl font-bold underline">{{ gridColumns[0].value }}</td>
            <td @click="sortTableBySensors">{{ gridColumns[1].value }}</td>
        </tr>
        <tr>
            <td>{{ gridValues[0].ref }}</td>
            <td>{{ gridValues[0].name }}</td>
        </tr>
        <tr>
            <td>{{ gridValues[1].ref }}</td>
            <td>{{ gridValues[1].name }}</td>
        </tr>
        <tr>
            <td>{{ gridValues[2].ref }}</td>
            <td>{{ gridValues[2].name }}</td>
        </tr>
        <tr>
            <td>{{ gridValues[3].ref }}</td>
            <td>{{ gridValues[3].name }}</td>
        </tr>
    </table>
</template>

<script lang="ts">

    let data = {
        gridColumns: [
            { value: 'Ref', key: 1 },
            { value: 'Sensors', key: 2 }
        ],
        gridValues: [
            { ref: 'alpha', name: "New sensor" },
            { ref: 'beta', name: "Better" },
            { ref: 'omega', name: "Pollution" },
            { ref: 'upsilon', name: "Nano Part" }
        ],

    }

    export default {
        data (){
            return data;
        },
        computed: {

        },
        methods: {
            sortTableByRef(){
                this.gridValues.sort(function(a, b){
                    let x = a.ref.toLowerCase();
                    let y = b.ref.toLowerCase();
                    if (x < y) {return -1;}
                    if (x > y) {return 1;}
                    return 0;
                });
            },
            sortTableBySensors(){
                this.gridValues.sort(function(a, b){
                    let x = a.name.toLowerCase();
                    let y = b.name.toLowerCase();
                    if (x < y) {return -1;}
                    if (x > y) {return 1;}
                    return 0;
                });

            }

        },
    }
</script>