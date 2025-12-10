<script>
    import { Trophy, ArrowRight } from 'lucide-svelte';
    
    // Data for different streams
    const data = {
        'Engineering': [
            { rank: 1, name: 'IIT Madras', city: 'Chennai', cutoff: 'JEE Adv: 148', fees: '₹ 8-10 L' },
            { rank: 2, name: 'IIT Delhi', city: 'New Delhi', cutoff: 'JEE Adv: 118', fees: '₹ 8-9 L' },
            { rank: 3, name: 'IIT Bombay', city: 'Mumbai', cutoff: 'JEE Adv: 67', fees: '₹ 8-10 L' },
            { rank: 4, name: 'IIT Kanpur', city: 'Kanpur', cutoff: 'JEE Adv: 215', fees: '₹ 8.5 L' },
            { rank: 5, name: 'IIT Kharagpur', city: 'Kharagpur', cutoff: 'JEE Adv: 250', fees: '₹ 10 L' },
            { rank: 6, name: 'IIT Roorkee', city: 'Roorkee', cutoff: 'JEE Adv: 400', fees: '₹ 9 L' },
            { rank: 7, name: 'IIT Guwahati', city: 'Guwahati', cutoff: 'JEE Adv: 600', fees: '₹ 9 L' },
            { rank: 8, name: 'IIT Hyderabad', city: 'Hyderabad', cutoff: 'JEE Adv: 600+', fees: '₹ 9 L' },
            { rank: 9, name: 'NIT Trichy', city: 'Trichy', cutoff: 'JEE Main: 4500', fees: '₹ 5 L' },
            { rank: 10, name: 'Jadavpur Univ', city: 'Kolkata', cutoff: 'WBJEE: 100', fees: '₹ 20 K' },
        ],
        'Management': [
            { rank: 1, name: 'IIM Ahmedabad', city: 'Ahmedabad', cutoff: 'CAT: 99.6%ile', fees: '₹ 25 L' },
            { rank: 2, name: 'IIM Bangalore', city: 'Bangalore', cutoff: 'CAT: 99.5%ile', fees: '₹ 24.5 L' },
            { rank: 3, name: 'IIM Calcutta', city: 'Kolkata', cutoff: 'CAT: 99.4%ile', fees: '₹ 27 L' },
            { rank: 4, name: 'IIM Lucknow', city: 'Lucknow', cutoff: 'CAT: 98%ile', fees: '₹ 20 L' },
            { rank: 5, name: 'FMS Delhi', city: 'Delhi', cutoff: 'CAT: 99%ile', fees: '₹ 2 L' },
            { rank: 6, name: 'XLRI', city: 'Jamshedpur', cutoff: 'XAT: 96%ile', fees: '₹ 24 L' },
            { rank: 7, name: 'IIM Kozhikode', city: 'Kozhikode', cutoff: 'CAT: 98%ile', fees: '₹ 20.5 L' },
            { rank: 8, name: 'IIM Indore', city: 'Indore', cutoff: 'CAT: 98%ile', fees: '₹ 21 L' },
            { rank: 9, name: 'SPJIMR', city: 'Mumbai', cutoff: 'CAT: 98%ile', fees: '₹ 22 L' },
            { rank: 10, name: 'IIFT', city: 'Delhi', cutoff: 'CAT: 97%ile', fees: '₹ 21 L' },
        ],
        'Medical': [
            { rank: 1, name: 'AIIMS Delhi', city: 'New Delhi', cutoff: 'NEET: 710+', fees: '₹ 6 K' },
            { rank: 2, name: 'PGIMER', city: 'Chandigarh', cutoff: 'INI-CET', fees: '₹ 5 K' },
            { rank: 3, name: 'CMC Vellore', city: 'Vellore', cutoff: 'NEET: 650+', fees: '₹ 50 K' },
            { rank: 4, name: 'NIMHANS', city: 'Bangalore', cutoff: 'INI-CET', fees: '₹ 10 K' },
            { rank: 5, name: 'JIPMER', city: 'Puducherry', cutoff: 'NEET: 690+', fees: '₹ 12 K' },
            { rank: 6, name: 'Amrita Vishwa', city: 'Coimbatore', cutoff: 'NEET: 500+', fees: '₹ 18 L' },
            { rank: 7, name: 'SGPGI', city: 'Lucknow', cutoff: 'NEET PG', fees: '₹ 50 K' },
            { rank: 8, name: 'BHU (IMS)', city: 'Varanasi', cutoff: 'NEET: 680+', fees: '₹ 30 K' },
            { rank: 9, name: 'KMC Manipal', city: 'Manipal', cutoff: 'NEET: 580+', fees: '₹ 14 L' },
            { rank: 10, name: 'Madras Med', city: 'Chennai', cutoff: 'NEET: 650+', fees: '₹ 20 K' },
        ]
    };

    let activeTab = 'Engineering';
</script>

<div class="bg-white rounded-xl shadow-lg border border-gray-100 overflow-hidden">
    <div class="flex border-b border-gray-100">
        {#each Object.keys(data) as tab}
            <button 
                class="flex-1 py-4 text-sm font-semibold transition-colors {activeTab === tab ? 'bg-orange-50 text-orange-600 border-b-2 border-orange-500' : 'text-gray-600 hover:bg-gray-50'}"
                on:click={() => activeTab = tab}
            >
                {tab}
            </button>
        {/each}
    </div>

    <div class="overflow-x-auto">
        <table class="w-full text-left border-collapse">
            <thead>
                <tr class="bg-gray-50 text-gray-500 text-xs uppercase tracking-wider">
                    <th class="p-4">Rank</th>
                    <th class="p-4">College</th>
                    <th class="p-4 hidden sm:table-cell">Cutoff (Est)</th>
                    <th class="p-4 hidden sm:table-cell">Fees</th>
                    <th class="p-4">Action</th>
                </tr>
            </thead>
            <tbody class="divide-y divide-gray-100 text-sm">
                {#each data[activeTab] as college}
                    <tr class="hover:bg-orange-50/30 transition group">
                        <td class="p-4 font-bold text-gray-400 group-hover:text-orange-500">#{college.rank}</td>
                        <td class="p-4">
                            <div class="font-bold text-gray-800">{college.name}</div>
                            <div class="text-xs text-gray-500">{college.city}</div>
                        </td>
                        <td class="p-4 hidden sm:table-cell text-gray-600 font-medium bg-gray-50/50 rounded">{college.cutoff}</td>
                        <td class="p-4 hidden sm:table-cell text-green-600 font-bold">{college.fees}</td>
                        <td class="p-4">
                            <button class="text-orange-500 hover:bg-orange-100 p-2 rounded-full transition">
                                <ArrowRight size={18} />
                            </button>
                        </td>
                    </tr>
                {/each}
            </tbody>
        </table>
    </div>
</div>
