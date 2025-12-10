<script>
	import { Search, Menu, User } from 'lucide-svelte';
</script>

<nav class="sticky top-0 z-50 bg-white border-b border-gray-200 shadow-sm">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="flex justify-between items-center h-16">
			<div class="flex-shrink-0 flex items-center gap-2">
                <div class="w-8 h-8 bg-orange-500 rounded flex items-center justify-center text-white font-bold">AV</div>
				<span class="text-2xl font-bold text-gray-900 tracking-tight">Arambh<span class="text-orange-500">Veda</span></span>
			</div>

			<div class="hidden md:flex space-x-8 text-sm font-medium text-gray-700">
				<a href="/" class="hover:text-orange-500 transition">Colleges</a>
				<a href="/" class="hover:text-orange-500 transition">Exams</a>
				<a href="/" class="hover:text-orange-500 transition">Courses</a>
				<a href="/" class="hover:text-orange-500 transition">Study Abroad</a>
				<a href="/" class="hover:text-orange-500 transition">Reviews</a>
			</div>

			<div class="flex items-center space-x-4">
				<button class="hidden md:block">
					<Search size={20} class="text-gray-500 hover:text-orange-500" />
				</button>
                <button class="flex items-center gap-2 px-4 py-2 bg-gray-900 text-white rounded-md text-sm font-medium hover:bg-orange-500 transition">
                    <User size={16} />
                    <span>Login</span>
                </button>
				<button class="md:hidden text-gray-600">
					<Menu size={24} />
				</button>
			</div>
		</div>
	</div>
</nav>
