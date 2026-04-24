<script>
    import Biograph from "./modules/Biograph.svelte";
    import Contact from "./modules/Contact.svelte";
    import Header from "./modules/Header.svelte";
    import Releases from "./modules/Releases.svelte";
    import Footer from "./modules/Footer.svelte";
</script>

<main class="container mx-auto px-4 py-8">
    <Header />

    <Biograph />

    <span id="Releases">
        <Releases />
    </span>

    <Contact />
</main>
<Footer />
