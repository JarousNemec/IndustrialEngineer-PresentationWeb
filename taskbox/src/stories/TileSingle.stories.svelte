<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import TileSingle from "./TileSingle.svelte";
</script>

<Meta
        title="Example/Tile/Single"
        component={TileSingle}
/>

<Template let:args>
    <TileSingle {...args}/>
</Template>


<Story
        name="Primary"
        args={{
            text: "Each block with object destructing",
  }}
/>
