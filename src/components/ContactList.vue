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
                <tr v-for="(contact, index) in contacts" :key="index">
                    <td>{{index + 1}}</td>
                    <td>{{contact.firstName}}</td>
                    <td>{{contact.lastName}}</td>
                    <td>{{contact.email}}</td>
                    <td>
                        <button class="btn btn-danger" @click="removeContact(contact)" >Remove</button>
                    </td>
                </tr>
            </tbody>
        </table>
     <h2>Add contact</h2>
        <form @submit.prevent="addContact">
            <label>First Name</label><br>
            <input v-model="newContact.firstName" type="text" placeholde="First Name"><br>
              <label>Last Name</label><br>
            <input v-model="newContact.lastName" type="text"  placeholde="Last Name"><br>
              <label>Email</label><br>
            <input v-model="newContact.email" type="text"  placeholde="Email"><br>
            <button type="submit">ADD CONTACT</button>
        </form>

    </div>
    
</template>

<script>
    export default {
        data() {
            return {
                newContact: {
                    firstName: '',
                    lastName: '',
                    email: ''
                },
                contacts: [
                    {firstName: 'John', lastName: 'Doe', email: 'john@example.com'},
                    {firstName: 'Jane', lastName: 'Doe', email: 'jane@example.com'},
                    {firstName: 'Jack', lastName: 'Doe', email: 'jack@example.com'},
                    {firstName: 'Sinisa', lastName: 'Doe', email: 'sinisa@example.com'},
                    {firstName: 'Jasnima', lastName: 'Doe', email: 'jasmina@example.com'}
                ],
                
            };
        },
        methods: {
            addContact() {
                this.contacts.push(this.newContact);
                this.newContact = {};
        
            },
            removeContact(contact) {
                let index = this.contacts.indexOf(contact);
                this.contacts.splice(index, 1);
                console.log(index);
                
            }
        }
    };

</script>

