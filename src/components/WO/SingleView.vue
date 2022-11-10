<template>
    <div class="main_body">
        <v-row>
            <v-col>
                <div class="container_details">
                    <h1 class="titles" data-text="Client Details">Client Details</h1>
                    <br>
                    <v-row>
                        <v-col>Name</v-col>
                        <v-col>:</v-col>
                        <v-col></v-col>
                    </v-row>
                    <v-row>
                        <v-col>Email Address</v-col>
                        <v-col>:</v-col>
                        <v-col></v-col>
                    </v-row>
                    <v-row>
                        <v-col>Phone No</v-col>
                        <v-col>:</v-col>
                        <v-col></v-col>
                    </v-row>
                    <v-row>
                        <v-col>Extra</v-col>
                        <v-col>:</v-col>
                        <v-col></v-col>
                    </v-row>
                </div>
            </v-col>
            <v-col>
                <div class="container_details workers">
                    <h1 class="titles" data-text="Workers">Workers</h1>
                    <br>
                </div>
            </v-col>
        </v-row>
        <br>
        <v-row class="unity">
            <v-col class="container_details">
                <h1 class="titles" data-text="Address Details">Address Details</h1>
                <br>
                <v-row>
                    <v-col>Area</v-col>
                    <v-col>:</v-col>
                    <v-col></v-col>
                </v-row>
                <v-row>
                    <v-col>Address</v-col>
                    <v-col>:</v-col>
                    <v-col></v-col>
                </v-row>
            </v-col>
            <v-col class="container_details">
                <h1 class="titles" data-text="Work Status">Work Status</h1>
                <br>
                    <!-- <v-checkbox color="green" label="Done"></v-checkbox>
                    <v-checkbox color="yellow"  label="In Progress"></v-checkbox>
                    <v-checkbox color="red" label="Aborted"></v-checkbox> -->
            </v-col>
        </v-row>
        <br>
        <br>
        <v-row>
            <div class="container_details">
                <h1 class="titles" data-text="Additional Notes">Additional Notes</h1>
            </div>
        </v-row>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
/* .unity{
    padding: 50px 50px 50px 50px !important;
} */
.workers {
    height: 364.22px
}

.main_body {
    width: 110%;
}

.titles {
    position: relative;
    text-shadow: 0px 0px 10px;
    color: #FF8418 !important;
}

.titles::before {
    position: absolute;
    content: attr(data-text);
    text-shadow: 0px 0px 20px white !important;
    filter: blur(0px) brightness(1);
    animation: flicker 4s linear 1s infinite;
}

@keyframes flicker {
    0% {
        filter: blur(1px) brightness(1);
    }

    3% {
        filter: blur(1px) brightness(0);
    }

    6% {
        filter: blur(1px) brightness(0);
    }

    7% {
        filter: blur(1px) brightness(1);
    }

    8% {
        filter: blur(1px) brightness(0);
    }

    9% {
        filter: blur(1px) brightness(1);
    }

    10% {
        filter: blur(1px) brightness(0);
    }

    20% {
        filter: blur(1px) brightness(1);
    }

    50% {
        filter: blur(1px) brightness(1);
    }

    99% {
        filter: blur(1px) brightness(0);
    }

    100% {
        filter: blur(1px) brightness(1);
    }
}

.container_details {
    padding: 50px 50px 50px 50px !important;
    background-color: white;
}

@media(max-width:320px) {
    .container_details {
        padding: 20px 50px 10px 50px !important;
        background-color: white;
    }

    .main_body {
        background: linear-gradient(white, white);
        width: 110%;
    }

    .workers {
    height: 100%;
}
}
</style>