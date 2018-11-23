<template>
    <div>
        <h2>Contact Details</h2>
        First Name: <h3>{{contact.firstName}}</h3>
        Last Name: <p>{{contact.lastName}}</p>
        Email: <p>{{contact.email}}</p>
       
    
    </div>
</template>

<script>

export default {
    props: ['contact'],
   
};
</script>
