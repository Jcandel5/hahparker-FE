<template>
    <div class="headerContainer">
        <b-container class="header">
      <div class="col-md">
        <h2>22651 E Aurora Parkway Suite A-1</h2>
        <h2>Aurora, CO 80016</h2>
        <h2>720-870-8387</h2>
        <br>
        <p class="text">At Heritage Animal Hospital, we believe in gaining the trust of client and patient alike. We use the latest
          technology and provide the best treatment for your pet. Whether on two legs or four, everyone is treated like
          family.</p>
        <br>
        <p class="text">You’ll see a list of our services in the menu above. Feel free to browse around and ask any questions
          by clicking the Contact Us above. We look forward to offering unparalleled service and medical care.</p>
      </div>
    </b-container>
    </div>
</template>

<script>
export default {
name: "Header"
}
</script>

<style>
.header{
  background-color: white;
  border: 5px solid black;
  border-radius: 15px;
}
p{
  font-family: 'Lato', sans-serif;
}
.col-md{
   border-radius: 15px;
}
.text{
  color:black;
}
</style>
