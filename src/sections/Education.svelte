<script>
    import HeaderTitle from "../components/HeaderTitle.svelte";
    import HeaderSubTitle from "../components/HeaderSubTitle.svelte";
    import { fly, fade } from "svelte/transition";
    import { circOut } from "svelte/easing";
</script>

<div class="education">
    <HeaderTitle title={"Education"}/>
    <HeaderSubTitle subTitle={"Curtin University - Software Engineering (B Comp)"} />
    <h5>Course Weighted Average: 82%</h5> 
</div>

<style>
    .education {
        width: 100%;
        height: 50vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        font-size: 14px;
    }

    h5 {
        margin: 10px;
    }
</style>