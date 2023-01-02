<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import Header from "./Header.svelte";

    let header_buttons = [
        {
            label: "Github",
            url: "https://github.com/JarousNemec/IndustrialEngineer-PresentationWeb"
        },
        {
            label: "Download",
            url: "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
        }
    ];

</script>

<Meta
        title="Example/Header"
        component={Header}
        argTypes={{
    title: { control: "text" },
    buttons: {control: "object"}
  }}
/>

<Template let:args>
    <Header {...args}/>
</Template>

<Story
        name="Industrial Header"
        args={{
    title: "Test header title",
    buttons: header_buttons
  }}
/>
