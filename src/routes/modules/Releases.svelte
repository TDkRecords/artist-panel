<script>
    import { Releases } from "$lib/releases.js";
    import "@fortawesome/fontawesome-free/css/all.css";
</script>

<section class="w-full py-10">
    <div class="max-w-full mx-auto">
        <h2
            class="text-3xl sm:text-4xl font-bold text-yellow-400 mb-10 text-center"
        >
            Ultimos Lanzamientos
        </h2>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            {#each Releases as release (release.name)}
                <div
                    class="bg-zinc-800 p-6 rounded-xl border border-yellow-500/20 hover:border-yellow-500/40 transition-all duration-300 hover:shadow-lg hover:shadow-yellow-500/10 group"
                >
                    <!-- Icono de música -->
                    <div class="mb-4 flex justify-center">
                        <div
                            class="w-16 h-16 bg-yellow-500/20 rounded-full flex items-center justify-center group-hover:bg-yellow-500/30 transition-colors"
                        >
                            <i class="fas fa-music text-yellow-400 text-2xl"
                            ></i>
                        </div>
                    </div>

                    <!-- Nombre del release -->
                    <h3
                        class="text-xl font-bold text-yellow-50 text-center mb-2 group-hover:text-yellow-200 transition-colors"
                    >
                        {release.name}
                    </h3>

                    <!-- Fecha -->
                    <p class="text-sm text-gray-400 text-center mb-6">
                        <i class="fas fa-calendar text-yellow-500/60 mr-2"></i>
                        {new Date(release.date).toLocaleDateString("es-ES", {
                            year: "numeric",
                            month: "long",
                            day: "numeric",
                        })}
                    </p>

                    <!-- Botones de plataformas -->
                    <div class="flex gap-3 flex-col sm:flex-row">
                        <a
                            href={release.spotify}
                            target="_blank"
                            rel="noopener noreferrer"
                            class="flex-1 bg-green-600 hover:bg-green-500 text-white px-4 py-2 rounded-lg font-medium transition-colors text-center flex items-center justify-center gap-2 text-sm"
                        >
                            <i class="fab fa-spotify"></i>
                            Spotify
                        </a>
                        <a
                            href={release.amazon}
                            target="_blank"
                            rel="noopener noreferrer"
                            class="flex-1 bg-yellow-600 hover:bg-yellow-500 text-black px-4 py-2 rounded-lg font-medium transition-colors text-center flex items-center justify-center gap-2 text-sm"
                        >
                            <i class="fab fa-amazon"></i>
                            Amazon
                        </a>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</section>
