<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import TileMedia from "./TileMedia.svelte";
</script>

<Meta
        title="Example/Tile/Media"
        component={TileMedia}
/>

<Template let:args>
    <TileMedia {...args}/>
</Template>


<Story
        name="Primary"
        args={{
            text: "Each block with object destructing",
            image: "Super image",
  }}
/>
