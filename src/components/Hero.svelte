<script>
    import MdArrowDownward from 'svelte-icons/md/MdArrowDownward.svelte'
</script>

<style>
    h1 {
        font-size: 2.5em;
    }

    p {
        font-size: 1.3em;
        color: #f5f2e8;
    }

    #main {
        margin-top: 45mm;
        text-align: center;
        width: 100%;
        align-items: center;
        justify-content: center;
    }

    #subtitle {
        margin-top: 160px;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
    }

    .icon {
        width: 30px;
        height: 30px;
        color: grey;
        margin-left: 10px;
        margin-right: 10px;
    }

    #subtitle > p {
        font-size: 1em;
    }

    .small {
        font-size: 15px;
        color: grey;
    }
</style>

<div id="main">
    <h1> Hi, i'm matt 👋 </h1>
    <p> I ❤️ web development </p>
    <p class="small"> (among other things) </p>

    <div id="subtitle">
        <div class="icon">
            <MdArrowDownward />
        </div>
        <p>because I know you're here to see what I can do</p>
        <div class="icon">
            <MdArrowDownward />
        </div>
    </div>
</div>