<script>
	import { Search, Monitor, PenTool, Stethoscope, Scale, Building2 } from 'lucide-svelte';
	import CollegeCard from '$lib/components/CollegeCard.svelte';

	// Mock Data
	const streams = [
		{ name: 'Engineering', icon: Monitor, count: '6000+ Colleges' },
		{ name: 'Management', icon: Building2, count: '4500+ Colleges' },
		{ name: 'Medical', icon: Stethoscope, count: '1200+ Colleges' },
		{ name: 'Design', icon: PenTool, count: '800+ Colleges' },
		{ name: 'Law', icon: Scale, count: '900+ Colleges' }
	];

	const colleges = [
		{
			name: 'Indian Institute of Technology (IIT)',
			location: 'Mumbai, Maharashtra',
			type: 'Government',
			rating: '9.8',
			fees: '₹ 2.15 Lakhs',
			exam: 'JEE Advanced',
			image: 'https://images.unsplash.com/photo-1562774053-701939374585?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80'
		},
		{
			name: 'Indian Institute of Management (IIM)',
			location: 'Bangalore, Karnataka',
			type: 'Public',
			rating: '9.6',
			fees: '₹ 24.50 Lakhs',
			exam: 'CAT',
			image: 'https://images.unsplash.com/photo-1541339907198-e08756dedf3f?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80'
		},
		{
			name: 'BITS Pilani',
			location: 'Pilani, Rajasthan',
			type: 'Private',
			rating: '9.3',
			fees: '₹ 5.40 Lakhs',
			exam: 'BITSAT',
			image: 'https://images.unsplash.com/photo-1592280771190-3e2e4d50325f?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80'
		},
        {
			name: 'Delhi University (DU)',
			location: 'New Delhi, Delhi',
			type: 'Central',
			rating: '9.1',
			fees: '₹ 15,000',
			exam: 'CUET',
			image: 'https://images.unsplash.com/photo-1523050854058-8df90110c9f1?ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80'
		}
	];
</script>

<section class="relative bg-gray-900 py-20 lg:py-32 overflow-hidden">
    <div class="absolute inset-0 z-0">
        <div class="absolute inset-0 bg-gradient-to-r from-orange-600 to-red-600 opacity-10"></div>
        <img src="https://images.unsplash.com/photo-1523240795612-9a054b0db644?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80" alt="Background" class="w-full h-full object-cover mix-blend-overlay opacity-40">
    </div>

	<div class="relative z-10 max-w-7xl mx-auto px-4 text-center">
		<h1 class="text-4xl md:text-6xl font-bold text-white mb-6">
			Find Your Dream College in <br/><span class="text-yellow-300">Arambh Veda</span>
		</h1>
		<p class="text-gray-100 text-lg mb-10 max-w-2xl mx-auto">
			Explore thousands of colleges, courses, exams, and reviews. Start your journey today with the best education portal.
		</p>

		<div class="max-w-3xl mx-auto bg-white p-2 rounded-full shadow-2xl flex items-center">
			<Search class="ml-4 text-gray-400" size={24} />
			<input
				type="text"
				placeholder="Search for colleges, exams, courses and more..."
				class="flex-1 p-3 text-gray-700 placeholder-gray-400 focus:outline-none rounded-full"
			/>
			<button class="bg-gray-900 text-white px-8 py-3 rounded-full font-semibold hover:bg-orange-600 transition">
				Search
			</button>
		</div>

        <div class="mt-6 flex flex-wrap justify-center gap-3">
            {#each ['B.Tech', 'MBA', 'MBBS', 'Design', 'Study Abroad'] as tag}
                <button class="px-4 py-1 rounded-full border border-white/30 text-white text-sm hover:bg-white hover:text-orange-600 transition backdrop-blur-sm">
                    {tag}
                </button>
            {/each}
        </div>
	</div>
</section>

<section class="py-12 bg-white border-b border-gray-100">
	<div class="max-w-7xl mx-auto px-4">
        <h2 class="text-2xl font-bold text-gray-800 mb-8">Select Your Study Goal</h2>
		<div class="grid grid-cols-2 md:grid-cols-5 gap-4">
			{#each streams as stream}
				<div class="flex flex-col items-center p-6 border border-gray-100 rounded-xl hover:shadow-lg hover:border-orange-200 cursor-pointer transition group">
					<div class="p-4 bg-gray-50 rounded-full mb-3 group-hover:bg-orange-100 transition">
						<svelte:component this={stream.icon} class="text-gray-600 group-hover:text-orange-600" size={28} />
					</div>
					<h3 class="font-bold text-gray-800">{stream.name}</h3>
					<p class="text-xs text-gray-500 mt-1">{stream.count}</p>
				</div>
			{/each}
		</div>
	</div>
</section>

<section class="py-16 bg-gray-50">
	<div class="max-w-7xl mx-auto px-4">
        <div class="flex justify-between items-end mb-10">
            <div>
                <h2 class="text-3xl font-bold text-gray-900">Top Collections</h2>
                <div class="h-1 w-20 bg-orange-500 mt-2 rounded-full"></div>
            </div>
            <a href="/" class="text-orange-600 font-semibold hover:underline">View All Colleges →</a>
        </div>
		
		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
			{#each colleges as college}
				<CollegeCard {college} />
			{/each}
		</div>
	</div>
</section>
