<script>
    import Section from "./Section.svelte";
    import Header from "./Header.svelte";
    import Footer from "./Footer.svelte";

    import {page_title} from "./assets/Layout_data.json";
    import {single_tile_data} from "./assets/Layout_data.json";
    import {advanced_tile_data} from "./assets/Layout_data.json";
    import {media_tile_data} from "./assets/Layout_data.json";
    import {header_buttons} from "./assets/Layout_data.json";
    import {footer_texts} from "./assets/Layout_data.json";

</script>
<div class="grid-container">
    <div class="grid-center">
        <Header title={page_title} buttons={header_buttons}/>
        <Section single_tile_data={single_tile_data} section_name="About"/>
        <Section advanced_tile_data={advanced_tile_data} section_name="Features"/>
        <Section media_tile_data={media_tile_data} section_name="Media"/>
        <Footer text_left={footer_texts.left} text_right={footer_texts.right}/>
    </div>
</div>


<style>
    .grid-center {
        grid-column: 2;
        background-color: var(--layout-bg);
    }

    @media screen and (max-width: 900px) {
        .grid-container {
        }
    }

    @media screen and (min-width: 900px) {
        .grid-container {
            display: grid;
            grid-template-columns: auto 900px auto;
        }
    }
</style>