<template>
<div id='bottom-nav'>
    <nav class="nav nav-pills nav-fill fixed-bottom bg-light align-items-center" style='height: 70px;'>
        <div @click='home' id='home' class="nav-link">
            <i class='material-icons'>home</i>
        </div>
        <div @click='history' id='history' class="nav-link">
            <i class='material-icons'>history</i>
        </div>
        <div @click='payments' id='payments' class="nav-link">
            <i class='material-icons'>payments</i>
        </div>
        <div @click='sidenav' id='sidenav' class="nav-link">
            <i class='material-icons'>face</i>
        </div>
    </nav>
</div>
</template>

<script>
export default {
    name: 'BottomNav',
    created() {},
    mounted() {},
    methods: {
        home() {
            if (localStorage.getItem('isCompanion') === 'true' && localStorage.getItem('isClient') === 'false') {
                this.$router.push('/companionHome/orders').catch(() => {})
            } else {
                this.$router.push({
                    name: 'Home'
                }).catch(() => {})
            }
            document.querySelector('#home i').style.color = '#009ffa'
            document.querySelector('#payments i').style.color = 'rgba(0,0,0, .4)'
            document.querySelector('#history i').style.color = 'rgba(0,0,0, .4)'
            document.querySelector('#sidenav i').style.color = 'rgba(0,0,0, .4)'
        },
        history() {
            if (localStorage.getItem('isCompanion') === 'true' && localStorage.getItem('isClient') === 'false') {
                this.$router.push('/companion-history').catch(() => {})
            } else {
                this.$router.push('/history').catch(() => {})
            }
            document.querySelector('#home i').style.color = 'rgba(0,0,0, .4)'
            document.querySelector('#history i').style.color = '#009ffa'
            document.querySelector('#payments i').style.color = 'rgba(0,0,0, .4)'
            document.querySelector('#sidenav i').style.color = 'rgba(0,0,0, .4)'

        },
        payments() {
            this.$router.push('/payments').catch(() => {})
            document.querySelector('#home i').style.color = 'rgba(0,0,0, .4)'
            document.querySelector('#history i').style.color = 'rgba(0,0,0, .4'
            document.querySelector('#payments i').style.color = '#009ffa'
            document.querySelector('#sidenav i').style.color = 'rgba(0,0,0, .4)'
        },
        sidenav() {
            this.$router.push('/sidenav').catch(() => {})
            document.querySelector('#home i').style.color = 'rgba(0,0,0, .4)'
            document.querySelector('#history i').style.color = 'rgba(0,0,0, .4'
            document.querySelector('#payments i').style.color = 'rgba(0,0,0, .4)'
            document.querySelector('#sidenav i').style.color = '#009ffa'
        }
    }
}
</script>

<style lang="scss" scoped>
#bottom-nav {
    .nav-link {
        i {
            color: rgba(0, 0, 0, .4);
            font-size: 1.8rem;
        }

    }
}
</style>
