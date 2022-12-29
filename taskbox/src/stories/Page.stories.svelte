<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import Page from "./Page.svelte";
</script>

<Meta
        title="Example/Page"
        component={Page}
        argTypes={{
    name: { control: "text" },
    backgroundImage: { control: "text" }
  }}
/>

<Template let:args>
    <Page {...args}/>
</Template>

<Story
        name="Industrial Engineer Page"
        args={{
            name:"Industrial Engineer Page",
            backgroundImage: "./assets/images/bg-image.png"
  }}
/>
