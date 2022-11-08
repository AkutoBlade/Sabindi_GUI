<template>
    <div id="demo">
        <v-container class="my-2">
            <v-row class="filters">
                <v-col cols="12" sm="6">
                    <v-toolbar class="toolbar" >
                    <v-select :items="items" label="Entry Type"></v-select>
                    </v-toolbar>
                </v-col>
                <v-col cols="12" sm="6">        
                <v-toolbar class="toolbar" >
                    <v-text-field hide-details prepend-icon="mdi-magnify" single-line></v-text-field>

                    <v-btn  icon>
                        <v-icon>mdi-plus</v-icon>
                    </v-btn>

                    <v-btn icon>
                        <v-icon>mdi-sort</v-icon>
                    </v-btn>
                    
                </v-toolbar>
            </v-col>
            </v-row>
        </v-container>
        <div class="decrease">
            <div class="table-responsive-vertical shadow-z-1">
                <!-- Table starts here -->
                <table class="table table-hover table-mc-light-blue">
                    <tr>
                        <th class="table__heading">lid</th>
                        <th class="table__heading">Lead Name</th>
                        <th class="table__heading">Entry Type</th>
                        <th class="table__heading">Contact No.</th>
                        <th class="table__heading">Email Address</th>
                        <th class="table__heading"></th>
                    </tr>
                    <tr class="table__row" v-for="lead in leads" :key="lead.lid">
                        <td class="table__content" data-heading="lid">
                            {{ lead.lid }}
                        </td>
                        <td class="table__content" data-heading="Lead Name">{{ lead.leadName }}</td>
                        <td class="table__content" data-heading="Entry Type">
                            {{ lead.entryType }}
                        </td>
                        <td class="table__content" data-heading="Contact No.">
                            {{ lead.contact }}
                        </td>
                        <td class="table__content" id="image" data-heading="Email Address">
                            {{ lead.emailAddress }}
                        </td>
                        <td class="table__content icons" data-heading="">
                            <v-icon> mdi-pencil</v-icon>
                            <v-icon> mdi-trash-can</v-icon>
                            <v-icon> mdi-information-outline</v-icon>
                        </td>
                        <!-- <EditModal :product="product" /> -->
                    </tr>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            items: ['Buyer', 'Seller', 'Looking to rent', 'Looking to out', 'Maintenance'],
            leads: [
                { lid: 1, leadName: 'Jared Isaacs', entryType: 'Seller', contact: '0720515069', emailAddress: 'rared.isaacs@gmail.com' },
                { lid: 2, leadName: 'Abigail Jacobs', entryType: 'Buyer', contact: '0824740433', emailAddress: 'abigail.jacobs@gmail.com' }
            ]
        }
    }
}
</script>

<style scoped>
.v-toolbar__content{
    background-color: white !important;
}
.sort {
    display: flex;
    justify-content: space-around;
}

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.filters {
    display: flex;
    justify-content: center;
    width: 50%;
}

.icons {
    display: flex;
    justify-content: space-around;
    padding-right: 2px;
}

.decrease {
    display: flex;
    justify-content: center;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    color: black;
    font-family: "Dosis", sans-serif;
    /* overflow-x: hidden; */
}

.table {
    margin-bottom: 2%;
}

body {
    font-weight: 400;
    font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
    background-color: #fafafa;
}

#box {
    display: flex;
}

/* button {
  align-self: center;
  position: absolute;
  left: 95%;
  gap: 10px;
  height: 50px;
  width: 80px;
  border-radius: 20px;
  border: 1px solid orange;
  background-color: white;
  color: orange;
  font-size: 12px;
  font-weight: bold;
  padding: 12px 12px;
  letter-spacing: 1px;
  text-transform: uppercase;
  box-shadow: 0px 0px 10px orange;
} */

td,
th {
    padding: 2px;
    padding: 0.5rem;
}

th {
    text-align: left;
    font-weight: 300;
    font-size: 20px;
    font-size: 1.25rem;
}

td {
    font-family: "Avenir Next", "Segoe UI", "Lucida Grande", sans-serif;
}

.table {
    width: 1600px;
    padding: 16px;
    padding: 1rem;
    box-shadow: 0vw 10px 10px rgba(0, 0, 0, 0.465)
}

.table__heading {
    border-bottom: solid 2px orange !important;
    border-top: solid 2px orange !important;
}

@media (max-width: 32rem) {
    .decrease {
        display: block;

    }

    .table__heading {
        display: none;
    }

    .table__content {
        display: block;
        padding: 0.5rem 0;
    }

    .table__row {
        margin: 0.25rem 1rem;
        padding: 0.5rem 0;
        display: block;
        border-bottom: 2px solid orange;
    }

    .table__content:before {
        content: attr(data-heading);
        display: inline-block;
        width: 5rem;
        margin-right: 1.2rem;
        color: #999;
        font-size: 0.75rem;
        font-weight: 700;
        font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", sans-serif;
        text-transform: uppercase;
        letter-spacing: 2px;
    }

    .table {
        width: 100%;
    }

    .filters {
        display: flex;
        justify-content: center;
        width: 100%;
    }

    .sort {

        position: absolute
    }

}

h1,
h4 {
    margin: 50px auto 50px auto;
    text-align: center;
}

@media (max-width:320px) {
    button {
        left: 70%;
    }
}
</style>