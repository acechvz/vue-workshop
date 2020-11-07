<template>
    <div>
        <h3>How to fetch data and update template! yeii</h3>
        <div class="container-fluid">
            <div class="row">
                <div class="col-md-6">
                    <List :items="users" title="Users List" :handleClick="selectUser" />
                </div>
                <div class="col-md-6">
                    <h4>User Selected</h4>
                    <!-- Mostrar la info del usuario seleccionado
                        peeero solo cuando selectedUser traiga algo de info -->
                    <div class="media" v-if="Object.keys(selectedUser).length > 0">
                        <div class="media-left">
                            <a href="#">
                            <img height="50" class="media-object" src="https://www.gravatar.com/avatar/205e460b479e2e5b48aec07710c08d50?s=200" alt="...">
                            </a>
                        </div>
                        <div class="media-body" style="padding-left: 15px">
                            <h4 class="media-heading">{{ selectedUser.name }}</h4>
                            <div>
                                <small>{{ selectedUser.username }}</small>
                                <ul>
                                    <li>{{ selectedUser.email }}</li>
                                    <li>{{ selectedUser.phone }}</li>
                                    <li>{{ selectedUser.website }}</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <button class="btn-info" @click="getUsersData">
            Get data!
        </button>
    </div>
</template>

<script>
import List from '../../components/List';

export default {
    components: {
        List
    },
    data() {
        return {
           users: [],
           selectedUser: {},
        }
    },
    methods: {
        getUsersData() {
           alert('Ready to fetch :D');
            //    fetch por default hace peticion GET
           fetch('https://jsonplaceholder.typicode.com/users')
            .then((response) => response.json())
            .then(data => {
                this.users = data;
            })
            .catch(() => {
                alert('Imposible cargar info de usuarios :(')
            })
        },
        selectUser(user) {
            this.selectedUser = user;
            console.log(user);
        }
    }
}
</script>

<style>

</style>