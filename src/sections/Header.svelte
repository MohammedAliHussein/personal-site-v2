<script>
    import HeaderTitle from "../components/HeaderTitle.svelte";
    import HeaderSubTitle from "../components/HeaderSubTitle.svelte";
    import HeaderNavigation from "../components/HeaderNavigation.svelte";
</script>

<div class="header">
    <HeaderTitle/>
    <HeaderSubTitle/>
    <HeaderNavigation/>
</div>

<style>
    .header {
        width: 100%;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>