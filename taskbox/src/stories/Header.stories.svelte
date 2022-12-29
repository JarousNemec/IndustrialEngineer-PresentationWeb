<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import Header from "./Header.svelte";
</script>

<Meta
  title="Example/Header"
  component={Header}
  argTypes={{
    title: { control: "text" }
  }}
/>

<Template let:args>
  <Header {...args}/>
</Template>

<Story
  name="Industrial Header"
/>
