<template>
  <div >
    <form action="search" @submit="redirect">
        <div class="inline">

            <input id="searchBarInput" type="text" @focus="placeholder()" class="input" v-model="state.test">

            <button type="submit" @click="redirect" class="search-rpl-button">
                <rpl-text-icon
                    symbol="search"
                    color="primary"
                    placement="after"
                    size="m"
                    text=" "
                    form="search"
                    @click= submit
                />
            </button>

        </div>
    </form>
  </div>
</template>

<script>
    import { store } from '../main.js'
    import { RplTextIcon } from '@dpc-sdp/ripple-icon'

    export default {
        name: 'search-bar',
        components: {
            RplTextIcon
        },
        data() {
            return {
                state: store.state
            }
        },
        methods: {
            redirect() {
                this.$gtag.event('Search bar', {
                    'event_category': 'Alert',
                    'event_label': 'Search Bar Button Submit',
                    'value': true
                })
                this.$router.push('confidential').then(() => window.scrollTo(0, 800));
            }
        },
        mounted: function() {
            if(window.location.href.includes("confidential")) {
                document.getElementById("searchBarInput").placeholder = "confidential"
            } else if (window.location.href.includes("confidential")) {
                document.getElementById("searchBarInput").placeholder = "confidential"
            } else if (window.location.href.includes("confidential")) {
                document.getElementById("searchBarInput").placeholder = "confidential"
            } else {
                document.getElementById("searchBarInput").placeholder = "confidential"
            }
        }
    }
</script>

<style scoped>
    @import '../assets/productAndHomePages.css';
    label {
        width: 255px;
    }
    .search-rpl-button {
        border: transparent;
        background-color: white;
    }
    .search-rpl-button:hover {
        cursor: pointer;
    }
    input[type=text] {
        width: 86%;
        height: 40px;
        padding: 12px 20px;
        margin: 8px 0;
        box-sizing: border-box;
        /* border-radius: 25px; */
        outline: none;
    }

</style>