<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import Layout from "./Layout.svelte";
</script>

<Meta
        title="Example/Layout"
        component={Layout}
/>

<Template let:args>
    <Layout/>
</Template>


<Story
    name="Primary"
/>
