<script>
    import "@fortawesome/fontawesome-free/css/all.css";
    import { Social } from "$lib/social";

    const icons = {
        TikTok: "fa-brands fa-tiktok",
        Instagram: "fa-brands fa-instagram",
        YouTube: "fa-brands fa-youtube",
        Facebook: "fa-brands fa-facebook",
        Spotify: "fa-brands fa-spotify",
        "Apple Music": "fa-brands fa-apple",
    };
</script>

<section class="w-full py-10">
    <div class="max-w-full mx-auto">
        <div
            class="bg-zinc-800 border border-yellow-500/20 rounded-xl shadow-lg p-6 sm:p-10 md:p-12"
        >
            <div class="text-center text-yellow-50">
                <h2 class="text-2xl sm:text-3xl font-bold text-yellow-400 mb-4">
                    Conecta conmigo
                </h2>
                <p class="text-sm sm:text-base text-gray-300 mb-8">
                    Sígueme en plataformas donde comparto mi música y contenido.
                </p>
            </div>

            <div class="flex flex-wrap justify-center gap-5 mb-10">
                {#each Social as social}
                    <a
                        href={social.link}
                        target="_blank"
                        rel="noopener noreferrer"
                        aria-label={social.name}
                        class="group w-12 h-12 flex items-center justify-center rounded-full bg-linear-to-r from-yellow-500/10 to-yellow-500/20 border border-yellow-500/10 hover:bg-yellow-500 transition-colors duration-300"
                    >
                        <i
                            class={`${icons[social.name]} text-lg text-yellow-400 group-hover:text-black transition-colors duration-300`}
                        ></i>
                    </a>
                {/each}
            </div>

            <div class="text-center text-sm sm:text-base text-gray-300">
                <p class="mb-2">Contacto</p>
                <a
                    href="mailto:axeljoshbusiness@gmail.com"
                    class="text-yellow-300 hover:text-yellow-400 transition-colors"
                >
                    axeljoshbusiness@gmail.com
                </a>
            </div>
        </div>
    </div>
</section>
