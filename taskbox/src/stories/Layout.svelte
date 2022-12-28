<script>
    import Section from "./Section.svelte";
    import Header from "./Header.svelte";
    import Footer from "./Footer.svelte";
</script>


<centerlayout >
    <Header />
    <div class="grid-container">
        <Section section_name="About"/>
        <Section section_name="Features" />
        <Section section_name="Media"/>
        <Footer text_left="@2023 Jaroslav Němec - All rights reserved" text_right="franta.vomacka@gmail.com" />
    </div>

</centerlayout>

<style>
    .grid-container {
        display: flex;
        flex-direction: column;
        row-gap: 10px;

        width: 800px;
        margin: 0 auto;

        background-color: tan;
    }

    /* On screens that are 992px or less, set the background color to blue */
    @media screen and (max-width: 992px) {
        .grid-container {
            background-color: blue;
        }
    }

    /* On screens that are 600px or less, set the background color to olive */
    @media screen and (max-width: 600px) {
        .grid-container {
            background-color: olive;
        }
    }


</style>