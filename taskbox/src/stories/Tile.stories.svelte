<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import Tile from "./Tile.svelte";
</script>

<Meta
        title="Example/Tile"
        component={Tile}
/>

<Template let:args>
    <Tile {...args}/>
</Template>


<Story
        name="Primary"
        args={{
            text: "Each block with object destructing",
            image: "Super image",
  }}
/>
