<script>
	import { Search, Monitor, PenTool, Stethoscope, Scale, Building2, MapPin, GraduationCap, BookOpen, Calendar, ArrowUpRight } from 'lucide-svelte';
	import RankTable from '$lib/components/RankTable.svelte';

    // Mock Data for new sections
    const programs = [
        { name: 'B.Tech', duration: '4 Years', type: 'Full Time' },
        { name: 'MBA', duration: '2 Years', type: 'Full Time' },
        { name: 'MBBS', duration: '5.5 Years', type: 'Medical' },
        { name: 'M.Tech', duration: '2 Years', type: 'Post Grad' },
        { name: 'BBA', duration: '3 Years', type: 'Undergrad' },
        { name: 'BCA', duration: '3 Years', type: 'Technology' },
    ];

    const studyPlaces = [
        { city: 'Bangalore', label: 'Tech Capital', bg: 'bg-blue-100 text-blue-600' },
        { city: 'Delhi', label: 'Education Hub', bg: 'bg-red-100 text-red-600' },
        { city: 'Mumbai', label: 'Finance & Arts', bg: 'bg-purple-100 text-purple-600' },
        { city: 'Pune', label: 'Oxford of East', bg: 'bg-indigo-100 text-indigo-600' },
        { city: 'Hyderabad', label: 'IT & Pharma', bg: 'bg-orange-100 text-orange-600' },
        { city: 'Chennai', label: 'Engineering', bg: 'bg-yellow-100 text-yellow-600' },
    ];

    const exams = [
        { name: 'JEE Main 2025', date: 'Jan 24 - Feb 1', type: 'Engineering' },
        { name: 'NEET UG 2025', date: 'May 4', type: 'Medical' },
        { name: 'CAT 2025', date: 'Nov 24', type: 'Management' },
        { name: 'GATE 2025', date: 'Feb 3-11', type: 'Tech PG' },
    ];
</script>

<section class="relative bg-gray-900 py-20 lg:py-28 overflow-hidden">
    <div class="absolute inset-0 z-0">
        <div class="absolute inset-0 bg-gradient-to-br from-gray-900 via-gray-900 to-orange-900 opacity-90"></div>
        <img src="https://images.unsplash.com/photo-1523050854058-8df90110c9f1" alt="Bg" class="w-full h-full object-cover mix-blend-overlay opacity-50">
    </div>
	<div class="relative z-10 max-w-7xl mx-auto px-4 text-center">
		<h1 class="text-4xl md:text-6xl font-bold text-white mb-6">
			Find Your Dream College in <br/><span class="text-orange-500">Arambh Veda</span>
		</h1>
        <p class="text-gray-300 mb-8 text-lg">Search over 12,000+ colleges, exams and courses.</p>
		<div class="max-w-3xl mx-auto bg-white p-2 rounded-full shadow-2xl flex items-center mb-6">
			<Search class="ml-4 text-gray-400" size={24} />
			<input type="text" placeholder="Search for colleges, exams, courses..." class="flex-1 p-3 text-gray-700 outline-none rounded-full" />
			<button class="bg-orange-500 text-white px-8 py-3 rounded-full font-bold hover:bg-orange-600 transition">Search</button>
		</div>
	</div>
</section>

<section class="py-12 bg-gray-50 border-b border-gray-200">
    <div class="max-w-7xl mx-auto px-4">
        <h2 class="text-2xl font-bold text-gray-800 mb-6 flex items-center gap-2">
            <BookOpen class="text-orange-500" /> Explore Programs
        </h2>
        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
            {#each programs as prog}
                <div class="bg-white p-4 rounded-xl border border-gray-100 hover:shadow-md hover:border-orange-200 transition cursor-pointer group">
                    <h3 class="font-bold text-gray-800 group-hover:text-orange-500">{prog.name}</h3>
                    <p class="text-xs text-gray-500 mt-1">{prog.duration} • {prog.type}</p>
                </div>
            {/each}
        </div>
    </div>
</section>

<section class="py-16 bg-white">
    <div class="max-w-7xl mx-auto px-4">
        <div class="flex flex-col md:flex-row justify-between items-end mb-8">
            <div>
                <h2 class="text-3xl font-bold text-gray-900">Top 10 Colleges 2025</h2>
                <p class="text-gray-500 mt-2">Based on NIRF Ranking, Cutoffs & Placement Reports.</p>
            </div>
            <a href="/" class="text-orange-600 font-semibold hover:underline flex items-center gap-1">
                View Full Rankings <ArrowUpRight size={16}/>
            </a>
        </div>
        
        <RankTable />
    </div>
</section>

<section class="py-16 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4">
        <h2 class="text-3xl font-bold text-gray-900 mb-8 flex items-center gap-2">
            <MapPin class="text-orange-500" /> Top Study Places
        </h2>
        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
            {#each studyPlaces as place}
                <div class="bg-white rounded-xl p-6 text-center border border-gray-200 hover:-translate-y-1 transition duration-300 shadow-sm hover:shadow-lg cursor-pointer">
                    <div class="w-12 h-12 mx-auto rounded-full {place.bg} flex items-center justify-center mb-3 font-bold text-xl">
                        {place.city[0]}
                    </div>
                    <h3 class="font-bold text-gray-800">{place.city}</h3>
                    <span class="text-xs text-gray-400 font-medium uppercase mt-1 block">{place.label}</span>
                </div>
            {/each}
        </div>
    </div>
</section>

<section class="py-16 bg-white border-t border-gray-200">
    <div class="max-w-7xl mx-auto px-4">
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
            
            <div class="lg:col-span-2">
                <h2 class="text-2xl font-bold text-gray-900 mb-6 flex items-center gap-2">
                    <GraduationCap class="text-orange-500" /> Top Universities & Colleges
                </h2>
                <div class="grid md:grid-cols-2 gap-6">
                    <div class="bg-gray-50 p-6 rounded-xl border border-gray-100">
                        <h3 class="font-bold text-lg mb-4 text-gray-800 border-b border-gray-200 pb-2">Top Universities</h3>
                        <ul class="space-y-3">
                            {#each ['Delhi University (DU)', 'Jawaharlal Nehru University (JNU)', 'Anna University', 'Mumbai University', 'Banaras Hindu University (BHU)'] as uni}
                                <li class="flex items-center gap-2 text-sm text-gray-600 hover:text-orange-600 cursor-pointer">
                                    <div class="w-1.5 h-1.5 bg-orange-400 rounded-full"></div> {uni}
                                </li>
                            {/each}
                        </ul>
                    </div>
                    <div class="bg-gray-50 p-6 rounded-xl border border-gray-100">
                        <h3 class="font-bold text-lg mb-4 text-gray-800 border-b border-gray-200 pb-2">Top Colleges</h3>
                        <ul class="space-y-3">
                            {#each ['Miranda House, Delhi', 'St. Stephens, Delhi', 'Loyola College, Chennai', 'Presidency College, Chennai', 'St. Xaviers, Mumbai'] as col}
                                <li class="flex items-center gap-2 text-sm text-gray-600 hover:text-orange-600 cursor-pointer">
                                    <div class="w-1.5 h-1.5 bg-blue-400 rounded-full"></div> {col}
                                </li>
                            {/each}
                        </ul>
                    </div>
                </div>
            </div>

            <div class="lg:col-span-1">
                <div class="bg-orange-50 rounded-xl p-6 border border-orange-100">
                    <h2 class="text-xl font-bold text-gray-900 mb-6 flex items-center gap-2">
                        <Calendar class="text-orange-600" /> Top Exams 2025
                    </h2>
                    <div class="space-y-4">
                        {#each exams as exam}
                            <div class="bg-white p-4 rounded-lg shadow-sm border border-orange-100 flex justify-between items-center group cursor-pointer hover:shadow-md transition">
                                <div>
                                    <h4 class="font-bold text-gray-800 group-hover:text-orange-600">{exam.name}</h4>
                                    <p class="text-xs text-gray-500">{exam.type}</p>
                                </div>
                                <div class="text-right">
                                    <span class="block text-xs font-bold text-orange-500 bg-orange-100 px-2 py-1 rounded">
                                        {exam.date}
                                    </span>
                                </div>
                            </div>
                        {/each}
                        <button class="w-full mt-4 py-2 border border-orange-500 text-orange-600 font-semibold rounded text-sm hover:bg-orange-500 hover:text-white transition">
                            View All Exams
                        </button>
                    </div>
                </div>
            </div>

        </div>
    </div>
</section>
