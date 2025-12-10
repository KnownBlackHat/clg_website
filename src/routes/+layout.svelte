<script>
    import "../app.css";
    import Navbar from "$lib/components/Navbar.svelte";
</script>

<div class="min-h-screen flex flex-col">
    <Navbar />
    <main class="flex-grow">
        <slot />
    </main>
    
    <footer class="bg-gray-900 text-gray-400 py-8 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <p>&copy; 2023 Arambh Veda. All rights reserved.</p>
        </div>
    </footer>
</div>
