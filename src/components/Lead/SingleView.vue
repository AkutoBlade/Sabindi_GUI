<template>
    <div class="main_body">
        <v-row>
            <v-col>
                <div class="container_details">
                    <h1 class="titles" data-text="Personal Details">Personal Details</h1>
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
                <div class="container_details">
                    <v-row>
                        <v-col>Priority level</v-col>
                        <v-col>:</v-col>
                        <v-col></v-col>
                    </v-row>
                    <br>
                    <v-row>
                        <v-col>Interested</v-col>
                        <v-col>:</v-col>
                        <v-col></v-col>
                    </v-row>
                    <br>
                    <v-row>
                        <v-col>Brought</v-col>
                        <v-col>:</v-col>
                        <v-col></v-col>
                    </v-row>
                    <br>
                </div>
            </v-col>
        </v-row>
        <br>
        <v-row>
            <div class="container_details">
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
            </div>
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
.main_body{
    background:linear-gradient(black,orange,black,orange);
    width:110%;
}
.titles {
    position: relative;
    text-shadow: 0px 0px 10px;
    color: orange !important;
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
</style>