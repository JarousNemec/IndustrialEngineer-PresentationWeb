<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import Section from "./Section.svelte";
</script>

<Meta
        title="Example/Section"
        component={Section}
/>

<Template let:args>
    <Section/>
</Template>


<Story
        name="Primary"
/>