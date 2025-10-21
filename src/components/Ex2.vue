<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                newItem: '',
            }
            
        },
        methods: {
            addItems() {
                if (this.newItem.trim()) {
                    this.items.push(this.newItem.trim());
                    this.newItem = ''; // Clear input
                }
            },
            deleteItem(idx) {
                this.items.splice(idx, 1); // Remove item by index
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="(item, index) in items" :key="index">{{ item }}
            <button class="delete-btn" @click="deleteItem(index)">Delete</button>
        </li>
    </ul>
    
    <input v-model="newItem" type="text" placeholder="Enter item name">
    <button type="button" @click="addItems">add</button>
   
</template>
