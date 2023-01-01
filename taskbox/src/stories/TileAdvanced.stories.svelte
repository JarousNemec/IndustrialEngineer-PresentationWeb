<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import TileAdvanced from "./TileAdvanced.svelte";
</script>

<Meta
        title="Example/Tile/Advanced"
        component={TileAdvanced}
/>

<Template let:args>
    <TileAdvanced {...args}/>
</Template>


<Story
        name="Even tile"
        args={{
            text: "Each block with object destructing",
            image: "./assets/images/coffee.png",
            even: true
  }}
/>


<Story
        name="Odd tile"
        args={{
            text: "Each block with object destructing",
            image: "./assets/images/coffee.png",
            even: false
  }}
/>