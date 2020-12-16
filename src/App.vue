<template>
    <div id="app">
        <Header />
        <router-view/>
    </div>
</template>

<script>
import Header from './components/Header'
export default {
    name: 'App',
    components: {
        Header
    }
}
</script>

<style>
    html {
        box-sizing: border-box;
        font-size: 16px;
    }
    *, *:before, *:after {
        box-sizing: inherit;
    }
    body, h1, h2, h3, h4, h5, h6, p, ol, ul {
        margin-bottom: 10px;
        padding: 0;
        font-weight: normal;
    }
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
    }

    #nav a {
        font-weight: bold;
        color: #42b983;
    }
    .home,
    #nav {
        padding: 20px;
        margin: 0 auto;
        max-width: 992px;
    }
    .table {
        margin: 20px auto;
        width: 100%;
    }
    thead {
        text-align: left;
        background-color: #f2f2f2;
    }
    thead th {
        padding: 4px;
    }
    tbody tr:hover {
        background-color: #f1f1f1;
    }
    tbody tr td:last-of-type {
        text-align: center;
    }
    h1 {
        font-size: 1.3rem;

    }
    article h1,
    article h2 {
        font-size: 1.2rem;
        font-weight: 700;
    }
    ol, ul {
        list-style: none;
    }
    img {
        max-width: 100%;
        height: auto;
    }
    .btn {
        text-transform: uppercase;
        cursor: pointer;
    }
    .btn-details {
        font-size: 0.8rem;
    }
    .btn-sort {
        display: inline-block;
        padding: 4px 8px;
        border: none;
        outline: none;
        margin-right: 4px;
        border-radius: 2px;
        background: #42b983;
        text-transform: none;
        text-decoration: none;
        color: #ffffff;
        font-size: 1rem;
        text-align: center;
        -webkit-appearance: none;
        -moz-appearance: none;
    }
    .btn:focus {
        outline: 1px solid cadetblue;
        outline-offset: 1px;
    }
</style>
