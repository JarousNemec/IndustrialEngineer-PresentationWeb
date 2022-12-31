<script>
    import Section from "./Section.svelte";
    import Header from "./Header.svelte";
    import Footer from "./Footer.svelte";

    let single_tile_data = [{
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA)\n' +
            'Director: Damien Chazelle\n' +
            'Awards: Academy Award for Best Sound Mixing'
    }, {text: 'h is one of the most powerful films that I have seen in a long time. The sheer emotion and power it is able to effectively convey is simply extraordinary. J.K Simmons Performance goes unrivalled by anyone else, and his character is just as well written as it is acted. Miles Teller is also great, and helps to amplify the chemistry between himself and Simmons.  2'}, {text: ' sacrifice will be part of your routine. You will likely have a mentor, teacher or coach whose job is to cultivate your skills while pushing you to new limits. This film questions whether the best approach is intimidation or society\'s current preferred method of nurturing. 3'}];
    let advanced_tile_data = [{
        image: 1,
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA) 1'
    }, {
        image: 2,
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA) 2'
    }, {
        image: 3,
        text: 'Andrew enrols in a music conservatory to become a drummer. But he is mentored by Terence Fletcher, whose unconventional training methods push him beyond the boundaries of reason and sensibility.\n' +
            'Release date: 2014 (USA) ced_tile_data 3'
    }];
    let media_tile_data = [{media: 0, media_type: 'img'}, {media: 1, media_type: 'img'}, {
        media: 2,
        media_type: 'img'
    }, {
        media: 3,
        media_type: 'movie',
    },];

</script>
<div class="grid-container">
    <div class="grid-center">
        <Header/>
                <Section single_tile_data={single_tile_data} section_name="About"/>
                <Section advanced_tile_data={advanced_tile_data} section_name="Features"/>
                <Section media_tile_data={media_tile_data} section_name="Media"/>
                <Footer text_left="@2023 Jaroslav Němec - All rights reserved" text_right="franta.vomacka@gmail.com"/>
    </div>
</div>


<style>

    .grid-center {
        grid-column: 2;
        background-color: var(--layout-bg);
    }

    @media screen and (max-width: 800px) {
        .grid-container {
        }
    }

    @media screen and (min-width: 800px) {
        .grid-container {
            display: grid;
            grid-template-columns: auto 800px auto;
        }
    }


</style>