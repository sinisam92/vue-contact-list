<template>
    <div>
        <h3>Contact List</h3>
        <table border="1">
            <thead>
                <th>Key</th>
                <th>Name</th>
                <th>Email</th>
            </thead>
            <tbody>
                <tr v-for="(contact, index) in contactsList" :key="index">
                    <td>{{index + 1}}</td>
                    <td>
                    <router-link :to="{name: 'contact-details', params: {id: contact.id}}" >
                        {{contact.firstName + ' ' + contact.lastName}}
                    </router-link>
                    </td>
                    <td>{{contact.email}}</td>
                    
                        <button class="btn btn-danger" @click="removeContact(contact)" >Remove</button>
                    
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
export default {
    props: ['contactsList'],
    methods: {
       removeContact(contact) {
                let index = this.contactsList.indexOf(contact);
                this.contactsList.splice(index, 1);  
            }
   }
    
};
</script>

