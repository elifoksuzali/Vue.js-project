<template>
    <div id="axios-get">
        <table class="table table-dark table-hover" id="tbl1">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Capital</th>
                    <th>Region</th>
                    <th>Flag</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="post of posts" :key="post.id">
                    <td>{{ post.name }}</td>
                    <td>{{ post.capital }}</td>
                    <td>{{ post.region }}</td>
                    <td><img style="width:32px;height:32px;" v-bind:src="post.flag" /> </td>
                </tr>
            </tbody>
        </table>
        <ul v-if="errors && errors.length">
            <li v-for="(error, index) of errors" :key="index">{{ index + 1 }} - {{ error.message }}</li>
        </ul>


    </div>
</template>



<script>
    import axios from "axios";
    export default {
        created() {
            this.getPosts();
        },
        data() {
            return {
                posts: [],
                errors: [],
                search: ''
                
            };
        },
        methods: {
            getPosts() {
                axios
                    .get("https://restcountries.eu/rest/v2/all")
                    .then(response => (this.posts = response.data))
                    .catch(error => {
                        this.errors.push(error);
                    });
            }
        }
    };
</script>
