<script lang="ts">
import type { InfoBoxType } from "$components/general_components/general_components_types"
import Information from "$icons/Information.svelte"

export let infoBox: InfoBoxType

</script>

<div class="main">
    <div class="header">
        <div class="icon" style="font-size: {infoBox.icon.size}px; height: {infoBox.icon.size}px; color: {infoBox.icon.color};">
            <svelte:component this={ infoBox.icon.type } />
        </div>
        <div class="heading">
            {infoBox.heading}
        </div>
    </div>
    <div class="key-information">
        {#each infoBox.paragraphs as paragraph}
            <p>{paragraph}</p>
        {/each}
    </div>
</div>

<style lang="stylus">
.main
    border-radius 10px
    background-color #EFEFEF
    padding 20px
    margin 20px 0

.header
    display flex

.icon
    font-size 18px
    margin auto 0
    margin-right 10px

.heading
    font-size 18px
    font-weight 600
    margin auto 0

p
    margin 0
    padding 0
    margin-top 10px
    line-height 22px

</style>