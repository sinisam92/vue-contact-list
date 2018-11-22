<template>
    <div>
        <h3>Contact List</h3>
        <table border="1">
            <thead>
                <th>Key</th>
                <th>First Name</th>
                <th>Last Name</th>
                <th>Email</th>
                
            </thead>
            <tbody>
                <tr v-for="(contact, index) in contactsList" :key="index">
                    <td>{{index + 1}}</td>
                    <td>
                    <router-link :to="{name: 'contact-details', params: {id: contact.id}}" >
                        {{contact.firstName}}
                    </router-link>
                    </td>
                    <td>
                    <router-link :to="{name: 'contact-details', params: {id: contact.id}}" >
                        {{contact.lastName}}
                    </router-link>
                    
                    <td>{{contact.email}}</td>
                    
                        <button class="btn btn-danger" @click="removeContact(contact)" >Remove</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
export default {
    props: ['contactsList']
};
</script>

