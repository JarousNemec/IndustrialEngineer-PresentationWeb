<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import Footer from "./Footer.svelte";
</script>

<Meta
        title="Example/Footer"
        component={Footer}
/>

<Template let:args>
    <Footer {...args}/>
</Template>


<Story
        name="Primary"
        args={{
            text: "Each block with object destructing",
            image: "Super image",
  }}
/>