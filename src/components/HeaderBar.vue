<template lang="html">
    <nav class="header-bar">
        <div class="nav-wrapper">
            <a href="#/index" class="brand-logo"><img src="../assets/images/logo.png" alt="" width="156" /></a>
            <a href="#" data-activates="mobile-demo" class="button-collapse"><i class="material-icons">menu</i></a>
            <ul class="right hide-on-med-and-down">
                <li><a href="#/index">Home</a></li>
                <li><a href="#/zdm">Commodity</a></li>
                <li><a href="#/category">Category</a></li>
            </ul>
            <ul class="side-nav" id="mobile-demo" v-on:click="hideSideNav">
                <li><a href="#/index" class="side-logo"><img src="../assets/images/logo_side.png" alt="" width="100" /></a></li>
                <li><a href="#/index">首页</a></li>
                <li><a href="#/zdm">值得买</a></li>
                <li><a href="#/category">分类</a></li>
            </ul>
      </div>
  </nav>
</template>

<script>
export default {
    name: 'HeaderBar',

    data() {
        return {
            isStretch: true,
        };
    },
    computed: {},
    ready() {
        $(".button-collapse").sideNav({
          menuWidth: 160, // Default is 240
          edge: 'left', // Choose the horizontal origin
          closeOnClick: true // Closes side-nav on <a> clicks, useful for Angular/Meteor
        });
    },
    attached() {},
    methods: {
        hideSideNav: function() {
            $('.button-collapse').sideNav('hide');
        }
    },
    created() {

    },
    components: {}
};
</script>

<style lang="scss">
    @import "../assets/scss/variables.scss";
    .header-bar {
        height: auto !important;
        line-height: auto !important;
        background-color: $themeColor !important;
        padding: 15px;
        .nav-wrapper {
            overflow: hidden;
            .right a{
                font-size: 1.5rem;
            }
        }
        .side-logo {
            text-align: center;
            // height: 80px;
            background: #424242;
            // line-height: 80px;
            background-color: $bgColor;
            font-size: 1.5rem;
            border-bottom: 1px solid #ddd;
            &:hover {
            }
        }
        .side-nav {
            background-color: $bgColor;
            a {
                text-align: center;
                font-size: 1.5rem;
                // height: 100px;
                // line-height: 100px;

            }
            .side-logo {
            //   height: 60px;
              width: 100%;
              background-repeat: no-repeat;
              background-position: center;
              padding: 10px 0;
            }
        }
        .brand-logo, .side-logo {
            width: 156px;
            height: 60px;
            // background-image: url(../assets/images/logo.png);
        }
        .side-logo {
            // background-image: url(../assets/images/logo_side_1.png);
            margin: 0 auto;

        }
    }
</style>
