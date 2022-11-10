<template>
    <div id="demo">
        <v-container class="my-2">
            <v-row class="filters">
                <v-col cols="13" sm="6">
                    <v-toolbar class="toolbar">
                        <v-select :items="items" label="Entry Type"></v-select>
                    </v-toolbar>
                </v-col>
                <v-col cols="13" sm="6">
                    <v-toolbar class="toolbar">
                        <v-text-field hide-details prepend-icon="mdi-magnify" single-line></v-text-field>

                        <v-btn icon>
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
                        <th class="table__heading">woid</th>
                        <th class="table__heading">Name</th>
                        <th class="table__heading">Client's Name</th>
                        <th class="table__heading">Client's Cell No.</th>
                        <th class="table__heading">Address</th>
                        <th class="table__heading">Icons</th>
                    </tr>
                    <tr class="table__row" v-for="wo in wos" :key="wo.woid">
                        <td class="table__content" data-heading="woid">
                            {{ wo.woid }}
                        </td>
                        <td class="table__content" data-heading="Name">{{ wo.workersName }}</td>
                        <td class="table__content" data-heading="Client's Name">
                            {{ wo.clientsName }}
                        </td>
                        <td class="table__content" data-heading="Client's Cell No.">
                            {{ wo.contact }}
                        </td>
                        <td class="table__content" id="image" data-heading="Address">
                            {{ wo.address }}
                        </td>
                        <td class="table__content icons" data-heading="Icons">
                            <v-icon> mdi-pencil</v-icon>
                            <v-icon> mdi-trash-can</v-icon>
                            <router-link :to="{ name: 'SingleWO', params: { id: wo.woid } }" class="router-link">
                                <v-icon> mdi-information-outline</v-icon>
                            </router-link>

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
            wos: [
                { woid: 1, workersName: 'Jared Isaacs', clientsName: 'Gail Isaacs', contact: '0720515069', address: '21 Caledon Close' },
                { woid: 2, workersName: 'Abigail Jacobs', clientsName: 'Emile Van Wyk', contact: '0824740433', address: '124 Fishermans walk' }
            ]
        }
    }
}
</script>

<style scoped>

.v-application a {
    color: #1976d2;
    text-decoration: none !important;
}
.v-toolbar__content {
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
    border-bottom: solid 2px #FF8418 !important;
    
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
        border-bottom: 2px solid #FF8418;
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
    width: 50%;
    margin-top: 1%;
    margin-bottom: 2%;
    border-bottom-right-radius: 10px;
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