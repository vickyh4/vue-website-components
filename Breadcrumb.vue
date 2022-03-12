<template>
    <div>
        <rpl-breadcrumbs style="display:block" :crumbs="crumbs" />
    </div>
</template>

<script>
import RplBreadcrumbs from "@dpc-sdp/ripple-breadcrumbs";
export default {
    name: 'breadcrumb',
    components: {
        RplBreadcrumbs
    },
    computed: {
        crumbs: function() {
            function capitalize(str) {
                return str.charAt(0).toUpperCase() + str.slice(1);
            }
            function capitalizeStr(str) {
                return str.split('-').map(capitalize).join(' ');
            }
            const fullPath = this.$route.path;
            const tokenisedFullPath = fullPath.split("/");

            var CtokenisedFullPath = []
            var tokens = []
            for(var x = 0; x < tokenisedFullPath.length; x++){
                CtokenisedFullPath.push(tokenisedFullPath[x].charAt(0).toUpperCase()+tokenisedFullPath[x].slice(1));
            }
            CtokenisedFullPath = CtokenisedFullPath.filter(function (el) {
                return el != null;
            })
            if (CtokenisedFullPath.length == 2) {
                tokens = [
                    { text:"Home", url: "/"},
                    { text: `${capitalizeStr(CtokenisedFullPath[1])}`, url: `/${CtokenisedFullPath[1]}`},
                ];
            }
            else if (CtokenisedFullPath.length == 3){
                tokens = [
                    { text:"Home", url: "/"},
                    { text: `${capitalizeStr(CtokenisedFullPath[1])}`, url: `/${CtokenisedFullPath[1]}`},
                    { text: `${capitalizeStr(CtokenisedFullPath[2])}`, url: `/${tokenisedFullPath[1]}/${tokenisedFullPath[2]}`}
                ];
            }
            else if (CtokenisedFullPath.length == 4){
                tokens = [
                    { text:"Home", url: "/"},
                    { text: `${capitalizeStr(CtokenisedFullPath[1])}`, url: `/${CtokenisedFullPath[1]}`},
                    { text: `${capitalizeStr(CtokenisedFullPath[2])}`, url: `/${tokenisedFullPath[1]}/${tokenisedFullPath[2]}`},
                    { text: `${capitalizeStr(CtokenisedFullPath[3])}`, url: `/${tokenisedFullPath[1]}/${tokenisedFullPath[2]}/${tokenisedFullPath[3]}`}
                ];
            }
            else if (CtokenisedFullPath.length == 5){
                tokens = [
                    { text:"Home", url: "/"},
                    { text: `${capitalizeStr(CtokenisedFullPath[1])}`, url: `/${CtokenisedFullPath[1]}`},
                    { text: `${capitalizeStr(CtokenisedFullPath[2])}`, url: `/${tokenisedFullPath[1]}/${tokenisedFullPath[2]}`},
                    { text: `${capitalizeStr(CtokenisedFullPath[3])}`, url: `/${tokenisedFullPath[1]}/${tokenisedFullPath[2]}/${tokenisedFullPath[3]}`},
                    { text: `${capitalizeStr(CtokenisedFullPath[4])}`, url: `/${tokenisedFullPath[1]}/${tokenisedFullPath[2]}/${tokenisedFullPath[3]}/${capitalizeStr(CtokenisedFullPath[4])}`}
                ];
            }
            return tokens;
        }
    },
    methods: {
        changeLink() {
            this.$router.push({ path: this.mobilitySelected.value }, () => {});577896
        }
    }
}
</script>

<style>
    .rpl-breadcrumbs {
        padding-bottom: 0.6rem;
    }
</style>