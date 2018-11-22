<template>
    <div>
        <ContactsTable :contactsList="contacts"/>
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
    <ContactDetails :contact="routeContact"/>
    </div>
    
</template>

<script>
import ContactsTable from './ContactsTable'
import ContactDetails from './ContactDetails'
    export default {
        components: {
            ContactsTable,
            ContactDetails
        },
        data() {
            return {
                newContact: {
                    firstName: '',
                    lastName: '',
                    email: ''
                },
                contacts: [
                    {id: 1, firstName: 'John', lastName: 'Doe', email: 'john@example.com'},
                    {id: 2, firstName: 'Jane', lastName: 'Doe', email: 'jane@example.com'},
                    {id: 3, firstName: 'Jack', lastName: 'Doe', email: 'jack@example.com'},
                    {id: 4, firstName: 'Sinisa', lastName: 'Doe', email: 'sinisa@example.com'},
                    {id: 5, firstName: 'Jasnima', lastName: 'Doe', email: 'jasmina@example.com'}
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
        },
        computed: {
            routeContact() {
                return this.contacts.find(contact => contact.id == this.$route.params.id)
            }
            
        }
    };

</script>

