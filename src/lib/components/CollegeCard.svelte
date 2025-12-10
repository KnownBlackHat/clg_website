<script>
    import { MapPin, Star, Heart } from 'lucide-svelte';
    export let college;
</script>

<div class="group bg-white rounded-xl overflow-hidden border border-gray-200 hover:shadow-xl transition-all duration-300 relative">
    <div class="h-48 relative overflow-hidden">
        <img src={college.image} alt={college.name} class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
        <div class="absolute top-0 inset-x-0 h-full bg-gradient-to-t from-black/60 to-transparent"></div>
        
        <div class="absolute top-3 left-3 bg-white/90 backdrop-blur-sm px-2 py-1 rounded text-xs font-bold text-gray-800">
            {college.type}
        </div>
        <div class="absolute top-3 right-3 p-2 bg-white/20 backdrop-blur-md rounded-full text-white hover:bg-orange-500 transition cursor-pointer">
            <Heart size={16} />
        </div>

        <div class="absolute bottom-3 right-3 flex items-center gap-1 bg-orange-500 text-white px-2 py-1 rounded shadow-lg">
            <span class="font-bold text-sm">{college.rating}</span>
            <Star size={12} fill="white" />
        </div>
    </div>

    <div class="p-5">
        <h3 class="text-lg font-bold text-gray-900 leading-tight mb-1 group-hover:text-orange-500 transition">{college.name}</h3>
        <div class="flex items-center text-gray-500 text-xs mb-4">
            <MapPin size={12} class="mr-1" />
            {college.location}
        </div>

        <div class="grid grid-cols-2 gap-4 py-3 border-t border-b border-gray-100 mb-4">
            <div>
                <p class="text-orange-500 font-bold text-sm">{college.fees}</p>
                <p class="text-gray-400 text-xs">1st Year Fees</p>
            </div>
            <div>
                <p class="text-gray-800 font-bold text-sm truncate">{college.exam}</p>
                <p class="text-gray-400 text-xs">Exam Accepted</p>
            </div>
        </div>

        <div class="flex gap-2">
            <button class="flex-1 py-2 bg-orange-50 text-orange-600 font-semibold text-sm rounded hover:bg-orange-100 transition">Apply Now</button>
            <button class="flex-1 py-2 border border-orange-500 text-orange-500 font-semibold text-sm rounded hover:bg-orange-500 hover:text-white transition">Brochure</button>
        </div>
    </div>
</div>
