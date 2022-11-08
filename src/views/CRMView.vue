<template>
<div id="demo">
  <div class="table-responsive-vertical shadow-z-1">
  <!-- Table starts here -->
  <table id="table" class="table table-hover table-mc-light-blue">
      <thead>
        <tr>
          <th>lid</th>
          <th>Lead Name</th>
          <th>Entry Type</th>
          <th>Contact</th>
          <th>Email Address</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="lead in leads " :key="lead.lid">
          <td data-title="lid">{{lead.lid}}</td>
          <td data-title="Lead Name">{{lead.leadName}}</td>
          <td data-title="Entry Type">{{lead.entryType}} </td>
          <td data-title="Contact">{{lead.contact}}</td>
          <td data-title="Email Address">{{lead.emailAddress}}</td>
        </tr>  
      </tbody>
    </table>
  </div>
</div>
</template>

<script>
export default {
    data() {
    return {
      leads: [
        {lid: 1,leadName: 'Jared Isaacs', entryType:'Seller', contact: '0720515069', emailAddress: 'rared.isaacs@gmail.com' },
        {lid:2 ,leadName: 'Abigail Jacobs', entryType:'Buyer',contact: '0824740433', emailAddress: 'abigail.jacobs@gmail.com' }
      ]
    }
  }
}
</script>

<style scoped>
/* table {
  border: 1px solid #ccc;
  border-collapse: collapse;
  margin: 0;
  padding: 0;
  width: 100%;
  table-layout: fixed;
}

table caption {
  font-size: 1.5em;
  margin: .5em 0 .75em;
}

table tr {
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  padding: .35em;
}

table th,
table td {
  padding: .625em;
  text-align: center;
}

table th {
  font-size: .85em;
  letter-spacing: .1em;
  text-transform: uppercase;
}

@media screen and (max-width: 600px) {
  table {
    border: 0;
  }

  table caption {
    font-size: 1.3em;
  }
  
  table thead {
    border: none;
    clip: rect(0 0 0 0);
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
  }
  
  table tr {
    border-bottom: 3px solid #ddd;
    display: block;
    margin-bottom: .625em;
  }
  
  table td {
    border-bottom: 1px solid #ddd;
    display: block;
    font-size: .8em;
    text-align: right;
  }
  
  table td::before {

    content: attr(data-label);
    float: left;
    font-weight: bold;
    text-transform: uppercase;
  }
  
  table td:last-child {
    border-bottom: 0;
  }
}















body {
  font-family: "Open Sans", sans-serif;
  line-height: 1.25;
} */
</style>