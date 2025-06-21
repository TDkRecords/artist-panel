<script>
    import axel from "$lib/images/cv-profile.jpg";

    // Datos del artista
    const artista = {
        nombre: "Axel Josh",
        bio: `Mi pasión nació en 2017 con Music Maker Jam, una aplicación móvil para mezclar loops, y al año conseguí mi primera guitarra acústica—¡todavía la conservo! Desde entonces he explorado géneros como rock, rap, funk, soul, salsa y cumbia, creando fusiones únicas que definen mi sonido.
He colaborado con Dokzma en el tema “Pensándote” (2022), junto a participaciones con Young Frizz. Estos proyectos me impulsan a seguir tocando en bares, clubes y eventos, con la vista puesta en grandes escenarios.`,
        lanzamientos: [
            {
                titulo: "Pensándote (feat. Dokzma)",
                fecha: "2022-08-02",
                spotify:
                    "https://open.spotify.com/intl-es/album/6R47pvde2dSLwSo3Di0qmI?si=6dL4zKPQTdKX03eNHa8VHg",
                amazon: "https://music.amazon.com/albums/B0B75N39B7?marketplaceId=ART4WZ8MWBX2Y&musicTerritory=CO&ref=dm_sh_M1IXVi2b6n9ORkBhGscnKObWt",
            },
            {
                titulo: "Arcoíris",
                fecha: "2022-05-20",
                spotify:
                    "https://open.spotify.com/intl-es/album/1EzAlc9dNhTadL23hPikAE?si=2UThKphgQLaZmyh63mpSpA",
                amazon: "https://music.amazon.com/albums/B0B5CZKT4B?marketplaceId=ART4WZ8MWBX2Y&musicTerritory=CO&ref=dm_sh_KdOUQlBZKV5eRQplKy7rfQoJK",
            },
            {
                titulo: "El 110 de Ti",
                fecha: "2023-11-15",
                spotify:
                    "https://open.spotify.com/intl-es/album/4f2f4D0cxDHCWiZd0oPeT3?si=j5FFPNukQ6ugiYv9I2mYYA",
                amazon: "https://music.amazon.com/albums/B0CH985C78?marketplaceId=ART4WZ8MWBX2Y&musicTerritory=CO&ref=dm_sh_pmoI3tVNDTPgB2O70twLq6hlu",
            },
        ],
        redes: {
            instagram: "https://www.instagram.com/_axeljosh_/",
            spotify:
                "https://open.spotify.com/intl-es/artist/6ZsMyAQxU6u1sXkIpvJK1P?si=DQ-Z5GhVSV-29cSUSQGInA&nd=1&dlsi=a7c631c9f4494420",
            youtube: "https://www.youtube.com/@AxelJosh",
            twitter: "https://x.com/_axeljosh_",
        },
        correo: "tdk.prods.company@gmail.com",
        // URL a tu Press Kit (EPK) en PDF u otro recurso. Cámbiala a la ruta real donde subas tu PDF,
        // por ejemplo en /static/presskit/AxelJosh-EPK.pdf o almacenamiento externo:
        epkUrl: "/presskit/AxelJosh-EPK.pdf",
    };
</script>

<main class="container py-5">
    <!-- Hero -->
    <section
        class="hero-dark text-center py-5 rounded mb-5 d-flex justify-content-center align-items-center"
    >
        <div
            class="greeting d-flex flex-column justify-content-center align-items-center w-75 py-4 px-3 rounded-3"
        >
            <h1 class="display-4">{artista.nombre}</h1>
            <p class="lead">Músico · Productor · Creador</p>
            <a href="#lanzamientos" class="btn btn-outline-light btn-lg">
                <i class="fa fa-play fa-fw"></i> Escucha ahora
            </a>
        </div>
    </section>

    <!-- Sobre mí -->
    <section id="sobre-mi" class="mb-5 p-4 bg-body-tertiary rounded shadow-sm">
        <div class="row align-items-center">
            <div class="col-md-3 text-center mb-3 mb-md-0">
                <img
                    src={axel}
                    alt="Axel Josh"
                    class="img-fluid rounded-circle border"
                    style="max-width: 200px;"
                />
            </div>
            <div class="col-md-9">
                <h2 class="text-light-emphasis">Sobre mí</h2>
                <p class="text-secondary">{artista.bio}</p>
            </div>
        </div>
    </section>

    <!-- Lanzamientos -->
    <section id="lanzamientos" class="mb-5">
        <h2 class="mb-4 text-secondary">Mis lanzamientos</h2>
        <div class="row">
            {#each artista.lanzamientos as item}
                <div class="col-md-4 mb-4">
                    <div class="card bg-body-secondary border-0 shadow-sm">
                        <div class="card-body">
                            <h5 class="card-title text-light-emphasis">
                                {item.titulo}
                            </h5>
                            <p class="card-text">
                                <small class="text-muted">{item.fecha}</small>
                            </p>
                            <div class="d-flex gap-2">
                                <a
                                    target="_blank"
                                    href={item.spotify}
                                    class="btn btn-spotify"
                                >
                                    <i class="fab fa-spotify fa-fw"></i> Spotify
                                </a>
                                <a
                                    target="_blank"
                                    href={item.amazon}
                                    class="btn btn-amazon"
                                >
                                    <i class="fa fa-amazon fa-fw"></i> Amazon Music
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </section>

    <!-- Booking / EPK temporal -->
    <section id="shows" class="mb-5 text-center">
        <h2 class="text-light-emphasis">¿Quieres contratarme?</h2>
        <p class="text-secondary mb-3">
            ¿Quieres saber más sobre mi trabajo, ver material promocional o
            contratarme para un evento?
        </p>
        <a
            href="mailto:{artista.correo}?subject=Booking {encodeURIComponent(
                artista.nombre,
            )}"
            class="btn btn-outline-secondary"
        >
            <i class="fa fa-envelope fa-fw"></i> Contáctame directamente
        </a>
    </section>

    <!-- Redes y contacto -->
    <section id="contacto" class="text-center mb-5">
        <h2 class="text-secondary">Sígueme en redes</h2>
        <div class="mb-3">
            {#each Object.entries(artista.redes) as [key, link]}
                <a target="_blank" href={link} class="text-body mx-2">
                    <!-- links -->
                    <i class="fa fa-fw fa-{key} fa-2x"></i>
                </a>
            {/each}
        </div>
        <p>
            Contacto:
            <a
                target="_blank"
                href={"mailto:" + artista.correo}
                class="text-decoration-none">{artista.correo}</a
            >
        </p>
    </section>
</main>

<footer class="bg-body-secondary text-center py-3">
    <small class="text-secondary">
        © 2025 {artista.nombre} ·
        <a
            href="/politica-y-privacidad"
            class="text-decoration-none text-secondary"
            >Política de privacidad</a
        > · Creado con SvelteKit
    </small>
</footer>

<style>
    .card-epk {
        background-color: #2a2a3d;
        border: 1px solid #444;
    }
    .btn-epk {
        background-color: var(--bs-secondary);
        color: #1e1e2e;
        border-color: var(--bs-secondary);
    }
    .btn-epk:hover {
        background-color: #e0a84b;
        border-color: #e0a84b;
        color: #1e1e2e;
    }
    .btn-booking {
        background-color: transparent;
        color: var(--bs-secondary);
        border: 1px solid var(--bs-secondary);
    }
    .btn-booking:hover {
        background-color: var(--bs-secondary);
        color: #1e1e2e;
    }
</style>
