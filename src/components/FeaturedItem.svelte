<script>
    import Lazy from 'svelte-lazy';
    import ImagePlaceholder from './ImagePlaceholder.svelte';
    import FaRegFolder from 'svelte-icons/fa/FaRegFolder.svelte'
    import FaRegFolderOpen from 'svelte-icons/fa/FaRegFolderOpen.svelte'
    import Hoverable from './Hoverable.svelte';

    export let data = {};
    export let flipped = false;
    $: projectLink = "/work/" + data.slug
</script>

<style>
    #coverImage {
        max-width: 650px;
    }

    #outer {
        margin-left: auto;
        margin-right: auto;
        width: 80%;
        display: flex;
        margin-bottom: 50px;
    }

    #inner {
        display: flex;
        flex-direction: column;
        margin-right: 25px;
        margin-left: 25px;
        flex-grow: 1;
        justify-content: flex-end;
    }

    .flipped {
        align-items: flex-end;
        text-align: end;
    }
    
    .reverseFlex {
        flex-direction: row-reverse;
    }

    p {
        max-width: 500px;
        font-size: 14px;
        color: #bfbfbf;
    }

    h1 {
        margin: 0;
    }

    .icon {
        width: 30px;
        height: 30px;
        margin-left: 10px;
    }

    .projectLink {
        display: flex;
        align-items: center;
        flex-direction: row;
        color: #bfbfbf;
    }

    .stackItem {
        margin-right: 5px;
        width: 20px;
        height: 20px;
    }

    .stackitemcontainer {
        margin-bottom: 10px;
    }

    @media only screen and (max-width: 1200px) {
      #outer {
          width: 100%;
          flex-wrap: wrap-reverse;
      }

      .flipped {
        flex-wrap: wrap;
      }

      #coverImage {
        max-width: 100%;
        }
    }
</style>

<div id="outer" class="{!flipped ? 'reverseFlex' : ''}">
    <div id="inner" class:flipped>
        <h1 class:flipped>{data.title}</h1>
        <p class:flipped>{data.shortdescription}</p>
        
        {#if data.stackitems.length > 0}
            <div class="darkBackground stackitemcontainer">
                {#each data.stackitems as stackitem (stackitem.id)}
                    <img class="stackItem" src={stackitem.logo.url} alt="stackitem logo" />
                {/each}
            </div>
        {/if}
        
        <Hoverable let:hovering={hovering}>
            <a href={projectLink}>
                <div class="projectLink">
                        <b>View Project</b>
                    <div class="icon">
                        {#if hovering}
                        <FaRegFolderOpen />
                        {:else}
                        <FaRegFolder/>
                        {/if}
                    </div>
                </div>
            </a>
        </Hoverable>
        
    </div>
    <Lazy 
    height={700} 
    placeholder={ImagePlaceholder}
    >
        <img id="coverImage"
        alt="cover"
        src={data.cover.url}
         />
    </Lazy>
</div>
