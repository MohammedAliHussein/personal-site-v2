<script>
    import HeaderTitle from "../components/HeaderTitle.svelte";
    import HeaderSubTitle from "../components/HeaderSubTitle.svelte";
    import HeaderDownArrow from "../components/HeaderDownArrow.svelte";
</script>

<div class="header">
    <HeaderTitle title={"Hi, I'm [Mo]"}/>
    <HeaderSubTitle subTitle={"Aspiring software engineer"}/>
    <HeaderDownArrow/>
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