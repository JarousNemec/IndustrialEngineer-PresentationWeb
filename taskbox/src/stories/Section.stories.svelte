<script>
    import {Meta, Template, Story} from "@storybook/addon-svelte-csf";
    import Section from "./Section.svelte";


    export let single_tile__data = [{
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA)\n' +
            'Director: Damien Chazelle\n' +
            'Awards: Academy Award for Best Sound Mixing'
    }, {text: 'h is one of the most powerful films that I have seen in a long time. The sheer emotion and power it is able to effectively convey is simply extraordinary. J.K Simmons Performance goes unrivalled by anyone else, and his character is just as well written as it is acted. Miles Teller is also great, and helps to amplify the chemistry between himself and Simmons.  2'}, {text: ' sacrifice will be part of your routine. You will likely have a mentor, teacher or coach whose job is to cultivate your skills while pushing you to new limits. This film questions whether the best approach is intimidation or society\'s current preferred method of nurturing. 3'}];
    export let advanced_tile__data = [{
        src: "./assets/images/coffee.png",
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA) 1'
    }, {
        src: "./assets/images/coffee.png",
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA) 2'
    }, {
        src: "./assets/images/coffee.png",
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA) ced_tile_data 3'
    }];
    export let media_tile__data = [{src: "./assets/images/coffee.png", media_type: 'img'},
        {src: "./assets/images/bg-image.png", media_type: 'img'}, {
            src: "./assets/images/coffee.png", media_type: 'img'
        }, {
            src: "./assets/images/coffee.png", media_type: 'movie',
        },];
</script>

<Meta
        title="Example/Section"
        component={Section}
        argTypes={{
            section_name: {control: "text"},
    single_tile_data: { control: "object" },
    advanced_tile_data: { control: "object" },
    media_tile_data: { control: "object" },
  }}
/>

<Template let:args>
    <Section {...args}/>
</Template>

<Story name="Single Data"
       args={{
    section_name: "Single Data",
    single_tile_data: single_tile__data,
  }}
/>
<Story name="Advanced Data"
       args={{
    section_name: "Advanced Data",
    advanced_tile_data: advanced_tile__data,
  }}
/>
<Story name="Media Tile Section"
       args={{
    section_name: "Media Tile Section",
    media_tile_data: media_tile__data,
  }}
/>