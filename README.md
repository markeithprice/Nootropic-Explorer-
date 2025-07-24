<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nootropics and Brands Explorer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --base-font-size: 16px; /* Control base font size for zoom */
        }
        html {
            font-size: var(--base-font-size);
        }
        body {
            font-family: 'Inter', sans-serif;
            padding-top: 4.5rem; /* Offset for fixed header */
        }
        /* Custom scrollbar for better aesthetics */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        ::-webkit-scrollbar-thumb {
            background: #888;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #555;
        }
        .modal-content {
            max-height: 85vh;
        }
        .prose h3 {
            margin-bottom: 0.5rem;
            font-weight: 600;
        }
        .prose ul {
            list-style-position: inside;
        }
        .prose .precaution-box {
            background-color: #fffbeb;
            border-left: 4px solid #facc15;
            padding: 1rem;
            border-radius: 0.5rem;
            margin-top: 1rem;
        }
        /* Styling for the settings toggle */
        .toggle-checkbox:checked {
            right: 0;
            border-color: #4f46e5;
        }
        .toggle-checkbox:checked + .toggle-label {
            background-color: #4f46e5;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <!-- Settings Menu Bar -->
    <header class="bg-white/80 backdrop-blur-lg shadow-md fixed top-0 left-0 right-0 z-20">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="text-xl font-bold text-indigo-600">Nootropics Explorer</div>
                <div class="flex items-center space-x-4">
                    <!-- Voice-over Toggle -->
                    <div class="flex items-center space-x-2">
                         <svg id="voice-icon" class="h-6 w-6 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.536 8.464a5 5 0 010 7.072m2.828-9.9a9 9 0 010 12.728M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z" />
                        </svg>
                        <div class="relative inline-block w-10 mr-2 align-middle select-none transition duration-200 ease-in">
                            <input type="checkbox" name="toggle" id="voiceToggle" class="toggle-checkbox absolute block w-6 h-6 rounded-full bg-white border-4 appearance-none cursor-pointer"/>
                            <label for="voiceToggle" class="toggle-label block overflow-hidden h-6 rounded-full bg-gray-300 cursor-pointer"></label>
                        </div>
                    </div>
                     <!-- Zoom Controls -->
                    <div class="flex items-center space-x-1 bg-gray-100 rounded-full p-1">
                        <button id="zoom-out" title="Zoom Out" class="p-1.5 rounded-full hover:bg-gray-200 transition">
                            <svg class="h-5 w-5 text-gray-600" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 12H4" /></svg>
                        </button>
                        <button id="zoom-reset" title="Reset Zoom" class="p-1.5 rounded-full hover:bg-gray-200 transition">
                             <svg class="h-5 w-5 text-gray-600" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" /><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z" /></svg>
                        </button>
                        <button id="zoom-in" title="Zoom In" class="p-1.5 rounded-full hover:bg-gray-200 transition">
                            <svg class="h-5 w-5 text-gray-600" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" /></svg>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Container -->
    <div class="container mx-auto p-4 sm:p-6 lg:p-8">

        <!-- Header -->
        <header class="text-center mb-8">
            <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-gray-900">Explore Nootropics</h1>
            <p class="mt-2 text-lg sm:text-xl text-indigo-500 font-semibold">By Heart Motivation</p>
            <p class="mt-2 text-md sm:text-lg text-gray-600">Discover nootropics, their benefits, and the brands that use them.</p>
        </header>

        <!-- Search Bar -->
        <div class="mb-8 max-w-2xl mx-auto">
            <div class="relative">
                <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
                    <svg class="h-5 w-5 text-gray-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd" d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z" clip-rule="evenodd" />
                    </svg>
                </div>
                <input type="text" id="searchInput"
                    class="block w-full pl-12 pr-4 py-3 border border-gray-300 rounded-full leading-5 bg-white placeholder-gray-500 focus:outline-none focus:placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm transition duration-150 ease-in-out"
                    placeholder="Search for a nootropic (e.g., Lion's Mane)">
            </div>
        </div>

        <!-- Nootropics Grid -->
        <main id="nootropicsGrid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
            <!-- Nootropic cards will be inserted here by JavaScript -->
        </main>
        
        <!-- Not Found Message -->
        <div id="notFoundMessage" class="text-center py-12 hidden">
            <h3 class="text-xl font-semibold text-gray-700">No Nootropics Found</h3>
            <p class="text-gray-500 mt-2">Try adjusting your search.</p>
        </div>

    </div>

    <!-- Modal -->
    <div id="infoModal" class="fixed inset-0 bg-gray-800 bg-opacity-75 flex items-center justify-center p-4 hidden z-50 transition-opacity duration-300">
        <div class="bg-white rounded-2xl shadow-xl w-full max-w-2xl transform transition-all duration-300 scale-95 opacity-0" id="modal-panel">
            <div class="p-6 relative">
                <button id="closeModal" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 transition">
                    <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                    </svg>
                </button>
                <div id="modalContent" class="pr-2 overflow-y-auto modal-content prose max-w-none">
                    <!-- Modal content will be dynamically inserted here -->
                </div>
            </div>
        </div>
    </div>


    <script>
        // --- DATA ---
        const nootropicsData = [
            {
                name: "Alpha-GPC",
                description: "Alpha-GPC (Alpha-glycerophosphocholine) is a natural choline compound found in the brain. It is a precursor to the neurotransmitter acetylcholine, which is involved in memory and learning.",
                benefits: ["May improve memory and learning functions.", "Supports cognitive function, especially in older adults.", "May enhance power output in athletes."],
                precautions: "Generally well-tolerated, but can cause side effects like heartburn, headache, or dizziness in some individuals. Consult a doctor if you are pregnant, nursing, or have a medical condition.",
                brands: [
                    { name: "Alpha BRAIN (Onnit)", url: "https://www.onnit.com/alphabrain/" },
                    { name: "Gorilla Mind", url: "https://gorillamind.com/" },
                    { name: "MADMONQ", url: "https://www.madmonq.gg/" },
                    { name: "Wild Society Nutrition", url: "https://wildsocietynutrition.com/" },
                    { name: "Double Wood Supplements", url: "https://doublewoodsupplements.com/" }
                ]
            },
            {
                name: "Ashwagandha",
                description: "An ancient medicinal herb classified as an adaptogen, meaning it can help your body manage stress. It's one of the most important herbs in Ayurveda.",
                benefits: ["Reduces stress and anxiety.", "May improve brain function, including memory.", "Can boost testosterone and increase fertility in men.", "May increase muscle mass and strength."],
                precautions: "Generally safe for most people. Not recommended for pregnant or breastfeeding women. People with autoimmune diseases should consult a doctor.",
                brands: [
                    { name: "Thesis", url: "https://takethesis.com/" },
                    { name: "Revive MD", url: "https://www.revivesups.com/" },
                    { name: "Sneak", url: "https://sneakenergy.com/" },
                    { name: "Heights", url: "https://www.yourheights.com/" },
                    { name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" }
                ]
            },
            {
                name: "Bacopa Monnieri",
                description: "A staple herb in traditional Ayurvedic medicine, primarily used to enhance cognitive functions.",
                benefits: ["Improves memory, attention, and the ability to process information.", "Contains powerful antioxidants.", "May reduce anxiety and stress.", "May help reduce ADHD symptoms."],
                precautions: "Can cause digestive issues like nausea and stomach cramps. It's advisable to take it with food. Consult a healthcare provider before use.",
                brands: [
                    { name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" },
                    { name: "Irwin Naturals", url: "https://irwinnaturals.com/" },
                    { name: "Himalaya", url: "https://himalayawellness.in/" },
                    { name: "Swanson", url: "https://www.swansonvitamins.com/" },
                    { name: "Nootropics Depot", url: "https://nootropicsdepot.com/" }
                ]
            },
            {
                name: "Caffeine",
                description: "A natural stimulant that works by stimulating the brain and central nervous system, helping you stay alert.",
                benefits: ["Improves alertness and concentration.", "Can enhance physical performance.", "May boost mood and protect against certain diseases."],
                precautions: "High doses can lead to anxiety, restlessness, and sleep problems. Regular high intake can lead to tolerance. Not recommended for individuals with heart conditions.",
                brands: [
                    { name: "C4 Energy", url: "https://cellucor.com/pages/c4-energy" },
                    { name: "GHOST ENERGY", url: "https://www.ghostlifestyle.com/pages/energy" },
                    { name: "Alani Nu", url: "https://www.alaninu.com/" },
                    { name: "Sneak", url: "https://sneakenergy.com/" },
                    { name: "Brite", url: "https://britedrinks.com/" }
                ]
            },
            {
                name: "Lion's Mane",
                description: "A type of medicinal mushroom containing health-promoting substances that may protect against dementia, reduce mild symptoms of anxiety and depression and help repair nerve damage.",
                benefits: ["Stimulates the growth of brain cells (neurogenesis).", "May help relieve mild symptoms of depression and anxiety.", "Protects against ulcers in the digestive tract.", "Reduces the risk of heart disease."],
                precautions: "Very safe with no proven side effects, but individuals with mushroom allergies should avoid it. As with any supplement, it's best to consult with a healthcare professional.",
                brands: [
                    { name: "Fungies", url: "https://eatfungies.com/" },
                    { name: "Host Defense", url: "https://hostdefense.com/" },
                    { name: "Real Mushrooms", url: "https://www.realmushrooms.com/" },
                    { name: "Four Sigmatic", url: "https://us.foursigmatic.com/" },
                    { name: "Om Mushroom Superfood", url: "https://ommushrooms.com/" }
                ]
            },
            {
                name: "L-Theanine",
                description: "An amino acid found primarily in green and black tea. It's known for its ability to promote relaxation without drowsiness. When paired with caffeine, it can create a state of calm focus.",
                benefits: ["Reduces stress and anxiety without causing sedation.", "Improves focus and attention, especially when combined with caffeine.", "May improve sleep quality.", "Can enhance immune system function."],
                precautions: "Extremely safe with no known serious side effects. It is generally well-tolerated. Consult a healthcare provider if you are taking medication for blood pressure.",
                brands: [
                    { name: "Irwin Naturals", url: "https://irwinnaturals.com/" },
                    { name: "Brite", url: "https://britedrinks.com/" },
                    { name: "Wild Society Nutrition", url: "https://wildsocietynutrition.com/" },
                    { name: "Thesis", url: "https://takethesis.com/" },
                    { name: "Sports Research", url: "https://sportsresearch.com/" }
                ]
            },
            {
                name: "Citicoline",
                description: "A brain nutrient that supports mental energy, focus, and attention. It is a naturally occurring compound that is a precursor to phosphatidylcholine, a key component of brain cell membranes.",
                benefits: ["Enhances memory and brain function.", "Supports the health of brain cells.", "May improve focus and mental energy."],
                precautions: "Generally considered safe and well-tolerated. Some may experience digestive upset. Consult a doctor before use if pregnant or nursing.",
                brands: [
                    { name: "Cognizin", url: "https://cognizin.com/" },
                    { name: "Jarrow Formulas", url: "https://jarrow.com/" },
                    { name: "NOW Foods", url: "https://www.nowfoods.com/" },
                    { name: "Mind Lab Pro", url: "https://www.mindlabpro.com/" },
                    { name: "Double Wood Supplements", url: "https://doublewoodsupplements.com/" }
                ]
            },
            {
                name: "Creatine",
                description: "An organic acid that helps supply energy to cells, particularly muscle and brain cells. While known for physical performance, it also has significant cognitive benefits.",
                benefits: ["Improves short-term memory and reasoning skills, especially in vegetarians.", "Enhances brain energy metabolism.", "May help fight neurodegenerative diseases."],
                precautions: "Can cause water retention and digestive issues. It is crucial to stay well-hydrated. Those with kidney issues should avoid it.",
                brands: [
                    { name: "Klean Athlete", url: "https://www.kleanathlete.com/" },
                    { name: "Optimum Nutrition", url: "https://www.optimumnutrition.com/" },
                    { name: "Myprotein", url: "https://us.myprotein.com/" },
                    { name: "Thorne", url: "https://www.thorne.com/" },
                    { name: "BulkSupplements.com", url: "https://www.bulksupplements.com/" }
                ]
            },
            {
                name: "Ginkgo Biloba",
                description: "An herbal supplement derived from one of the oldest living tree species. It's widely used for its potential to improve cognitive function and circulation.",
                benefits: ["May improve memory and thinking in some people.", "Can help with anxiety.", "Supports eye health and vision.", "Improves blood flow to the brain."],
                precautions: "Can interact with blood thinners and other medications. May cause side effects like headache, dizziness, or upset stomach.",
                brands: [
                    { name: "Nature's Bounty", url: "https://www.naturesbounty.com/" },
                    { name: "Pure Encapsulations", url: "https://www.pureencapsulations.com/" },
                    { name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" },
                    { name: "Doctor's Best", url: "https://www.drbvitamins.com/" },
                    { name: "Source Naturals", url: "https://www.sourcenaturals.com/" }
                ]
            },
            {
                name: "Rhodiola Rosea",
                description: "An adaptogenic herb that grows in cold, mountainous regions of Europe and Asia. It has long been used in traditional medicine to combat fatigue and enhance physical performance.",
                benefits: ["Fights fatigue and reduces feelings of burnout.", "Can improve symptoms of depression.", "Enhances brain function and concentration.", "Helps the body adapt to physical and mental stress."],
                precautions: "Generally safe, but may cause dizziness, dry mouth, or excessive saliva production. Avoid if you have an autoimmune disease without consulting a doctor.",
                brands: [
                    { name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" },
                    { name: "NOW Foods", url: "https://www.nowfoods.com/" },
                    { name: "Thorne", url: "https://www.thorne.com/" },
                    { name: "Nature's Way", url: "https://www.naturesway.com/" },
                    { name: "Swedish Herbal Institute", url: "https://www.shi.se/en/" }
                ]
            },
            { name: "Panax Ginseng", description: "Also known as Asian ginseng, it's a traditional herb renowned for its ability to boost energy and support brain health.", benefits: ["May improve brain functions like memory, behavior, and mood.", "Fights tiredness and increases energy levels.", "Strengthens the immune system."], precautions: "Can interfere with sleep (insomnia) and may affect blood pressure and blood sugar. Should not be taken for long periods.", brands: [{ name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "Solgar", url: "https://www.solgar.com/" }, { name: "KGC (Korea Ginseng Corp)", url: "https://www.kgcus.com/" }, { name: "Auragin", url: "https://auragin.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }] },
            { name: "Phosphatidylserine", description: "A fatty substance called a phospholipid. It covers and protects the cells in your brain and carries messages between them. It plays a key role in keeping your mind and memory sharp.", benefits: ["Supports memory and cognitive capacity.", "May help with age-related cognitive decline.", "Can improve symptoms of ADHD.", "Helps reduce stress by lowering cortisol levels."], precautions: "Generally safe. High doses might cause insomnia or stomach upset. Consult a doctor if you are on blood thinners.", brands: [{ name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Double Wood Supplements", url: "https://doublewoodsupplements.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }] },
            { name: "Huperzine A", description: "A substance purified from a plant called Chinese club moss. It works by improving the levels of neurotransmitters in the brain.", benefits: ["Enhances memory and learning.", "Used for Alzheimer's disease and age-related memory impairment.", "Protects nerve cells against damage."], precautions: "Should be cycled (e.g., take for a few weeks, then a break) to avoid side effects like nausea or sweating. Not for long-term daily use.", brands: [{ name: "Source Naturals", url: "https://www.sourcenaturals.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Double Wood Supplements", url: "https://doublewoodsupplements.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Absorb Health", url: "https://www.absorbyourhealth.com/" }] },
            { name: "Vinpocetine", description: "A synthetic compound derived from the periwinkle plant. It is reported to have cerebral blood-flow enhancing and neuroprotective effects.", benefits: ["Increases blood flow to the brain.", "May improve memory and cognitive performance.", "Has antioxidant and anti-inflammatory properties in the brain."], precautions: "Can cause flushing, headache, or dizziness. Should be avoided by people with bleeding disorders or low blood pressure. Not recommended for pregnant women.", brands: [{ name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Source Naturals", url: "https://www.sourcenaturals.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }] },
            { name: "Omega-3 Fatty Acids (Fish Oil)", description: "Essential fats that are crucial for brain health. The main omega-3s are EPA and DHA, which are building blocks of brain cell membranes.", benefits: ["Supports learning, memory, and overall cognitive function.", "May help fight depression and anxiety.", "Crucial for brain development and maintenance."], precautions: "Generally very safe. High doses might thin the blood, so consult a doctor if taking blood thinners. Choose high-quality, purified supplements to avoid contaminants.", brands: [{ name: "Nordic Naturals", url: "https://www.nordic.com/" }, { name: "Carlson Labs", url: "https://carlsonlabs.com/" }, { name: "Wiley's Finest", url: "https://www.wileysfinest.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Sports Research", url: "https://sportsresearch.com/" }] },
            { name: "N-Acetyl L-Tyrosine (NALT)", description: "An acetylated form of the amino acid L-Tyrosine. It is a precursor to several important neurotransmitters, including dopamine and norepinephrine, which are crucial for focus and mood.", benefits: ["Enhances cognitive flexibility and working memory, especially under stress.", "Improves focus and concentration.", "Can improve mood and reduce stress."], precautions: "Generally safe. Can interfere with thyroid medication and MAOI antidepressants. Avoid if you have hyperthyroidism or Graves' disease.", brands: [{ name: "Jym Supplement Science", url: "https://jymsupplementscience.com/" }, { name: "Myprotein", url: "https://us.myprotein.com/" }, { name: "BulkSupplements.com", url: "https://www.bulksupplements.com/" }, { name: "Nootropics Depot", url: "https://nootropicsdepot.com/" }, { name: "Gorilla Mind", url: "https://gorillamind.com/" }] },
            { name: "Uridine Monophosphate", description: "A nucleotide that is one of the four basic components of RNA. It is thought to support brain health by promoting the synthesis of cell membranes and boosting dopamine levels.", benefits: ["May improve memory and learning.", "Can enhance mood and motivation.", "Supports synaptic plasticity (the connections between brain cells)."], precautions: "Generally well-tolerated. Long-term effects of high-dose supplementation are not well-studied. It's best to start with a low dose.", brands: [{ name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Double Wood Supplements", url: "https://doublewoodsupplements.com/" }, { name: "Nootropics Depot", url: "https://nootropicsdepot.com/" }, { name: "LiftMode", url: "https://liftmode.com/" }, { name: "Cerebro", url: "https://www.cerebro.com/" }] },
            { name: "Magnesium (L-Threonate)", description: "A form of magnesium that is particularly effective at crossing the blood-brain barrier. It plays a vital role in brain plasticity, which is fundamental for learning and memory.", benefits: ["May improve short-term and long-term memory.", "Can enhance learning abilities.", "Supports overall brain health and may reduce age-related cognitive decline."], precautions: "Generally safe. Excessive intake of any magnesium form can lead to digestive issues. Consult a doctor if you have kidney problems.", brands: [{ name: "Magtein", url: "https://www.magtein.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }] },
            { name: "Cordyceps", description: "A genus of parasitic fungi that grows on the larvae of insects. In traditional Chinese medicine, it's used to treat fatigue, sickness, and low sex drive.", benefits: ["Boosts exercise performance by improving oxygen uptake.", "Has anti-aging properties.", "May help manage Type 2 diabetes.", "Supports heart health."], precautions: "Generally safe. May interact with blood-thinning and diabetes medications. Those with autoimmune conditions should be cautious.", brands: [{ name: "Four Sigmatic", url: "https://us.foursigmatic.com/" }, { name: "Real Mushrooms", url: "https://www.realmushrooms.com/" }, { name: "Host Defense", url: "https://hostdefense.com/" }, { name: "Om Mushroom Superfood", url: "https://ommushrooms.com/" }, { name: "Sun Potion", url: "https://www.sunpotion.com/" }] },
            { name: "Reishi Mushroom", description: "A fungus that grows in various hot and humid locations in Asia. Known as the 'mushroom of immortality,' it's used to enhance the immune system, reduce stress, and improve sleep.", benefits: ["Boosts the immune system.", "Can help fight fatigue and depression.", "Supports heart health and blood sugar control.", "Has antioxidant properties."], precautions: "Generally well-tolerated but can cause dizziness or digestive upset. People with bleeding disorders or low blood pressure should consult a doctor.", brands: [{ name: "Four Sigmatic", url: "https://us.foursigmatic.com/" }, { name: "Real Mushrooms", url: "https://www.realmushrooms.com/" }, { name: "Host Defense", url: "https://hostdefense.com/" }, { name: "Teeccino", url: "https://teeccino.com/" }, { name: "Terrasoul Superfoods", url: "https://www.terrasoul.com/" }] },
            { name: "Chaga Mushroom", description: "A type of fungus that grows mainly on the bark of birch trees in cold climates. It is packed with antioxidants and has been used for centuries to boost immunity and overall health.", benefits: ["Rich in antioxidants, fighting free radicals and inflammation.", "Supports the immune system.", "May lower cholesterol and blood sugar levels."], precautions: "May interact with blood-thinning and diabetes medications. High in oxalates, which can be problematic for those with kidney issues.", brands: [{ name: "Four Sigmatic", url: "https://us.foursigmatic.com/" }, { name: "Vimergy", url: "https://vimergy.com/" }, { name: "Sun Potion", url: "https://www.sunpotion.com/" }, { name: "Wild Foods", url: "https://www.wildfoods.co/" }, { name: "Sayan", url: "https://www.sayanchaga.com/" }] },
            { name: "Gotu Kola", description: "A culinary vegetable and medicinal herb in the parsley family, often called the 'herb of longevity.' It's used in traditional medicine to boost brainpower and heal skin issues.", benefits: ["May improve cognitive function and memory.", "Can help reduce anxiety and stress.", "Improves circulation.", "Helps heal wounds and minimize scarring."], precautions: "Generally safe, but can cause skin allergy when applied topically. High doses may cause nausea. Should not be used by pregnant women.", brands: [{ name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Organic India", url: "https://shop.organicindiausa.com/" }, { name: "Banyan Botanicals", url: "https://www.banyanbotanicals.com/" }] },
            { name: "Curcumin", description: "The main active ingredient in turmeric. It has powerful anti-inflammatory effects and is a very strong antioxidant.", benefits: ["Potent anti-inflammatory and antioxidant effects.", "May improve brain function and lower the risk of brain diseases.", "Can help prevent and perhaps even treat cancer.", "May improve symptoms of depression and arthritis."], precautions: "Poorly absorbed, so it's best taken with black pepper (piperine). High doses can cause digestive issues. Consult a doctor if you have gallbladder problems.", brands: [{ name: "Theracurmin", url: "https://theracurmin.com/" }, { name: "Bio-Kult", url: "https://www.bio-kult.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }, { name: "Solgar", url: "https://www.solgar.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }] },
            { name: "Saffron", description: "A spice derived from the flower of Crocus sativus. It's known for its powerful antioxidant properties and has been used to enhance mood, libido, and memory.", benefits: ["A powerful antioxidant.", "May improve mood and treat depressive symptoms.", "Can reduce appetite and aid weight loss.", "May improve memory in adults with Alzheimer's disease."], precautions: "Generally safe in culinary amounts. High doses can be toxic. Pregnant women should avoid high-dose supplements.", brands: [{ name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "California Gold Nutrition", url: "https://www.californiagoldnutrition.com/" }, { name: "Zaran Saffron", url: "https://www.zaransaffron.com/" }, { name: "Golden Saffron", url: "https://www.goldensaffron.com/" }] },
            { name: "Acetyl-L-Carnitine (ALCAR)", description: "An acetylated form of the amino acid L-carnitine. It helps the body produce energy and is important for heart and brain function, muscle movement, and many other body processes.", benefits: ["May benefit brain function and reduce age-related cognitive decline.", "Can improve mood and reduce fatigue.", "Supports nerve health."], precautions: "Generally safe. Can cause side effects such as stomach upset, nausea, and a 'fishy' body odor. Interact with thyroid hormones.", brands: [{ name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Thorne", url: "https://www.thorne.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }, { name: "BulkSupplements.com", url: "https://www.bulksupplements.com/" }] },
            { name: "Taurine", description: "An amino acid that occurs naturally in your body. It is particularly concentrated in your brain, eyes, heart, and muscles. It's considered a conditional amino acid.", benefits: ["Supports nerve growth.", "May help fight brain aging.", "Calms the nervous system, potentially reducing anxiety.", "Important for vision and heart health."], precautions: "Generally very safe with no known side effects when supplemented appropriately. Consult a doctor if you have kidney issues.", brands: [{ name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "BulkSupplements.com", url: "https://www.bulksupplements.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Thorne", url: "https://www.thorne.com/" }] },
            { name: "Kava", description: "An herb that's native to the South Pacific islands. Its root is used to produce a drink with sedative, anesthetic, and euphoriant properties.", benefits: ["Effectively reduces anxiety.", "Promotes relaxation and may improve sleep.", "Can produce a sense of calm and well-being."], precautions: "Can cause liver damage with heavy, long-term use. Should not be mixed with alcohol or certain medications. Use should be discussed with a healthcare professional.", brands: [{ name: "Leilo", url: "https://lelo.com/" }, { name: "Kava Haven", url: "https://kavahaven.com/" }, { name: "Kalm with Kava", url: "https://kalmwithkava.com/" }, { name: "Kona Kava Farm", url: "https://konakavafarm.com/" }, { name: "Wakacon", url: "https://wakacon.com/" }] },
            { name: "Mucuna Pruriens (L-Dopa)", description: "A tropical legume native to Africa and tropical Asia and widely naturalized and cultivated. It contains high levels of L-dopa, a precursor to the neurotransmitter dopamine.", benefits: ["Natural source of L-dopa, which can boost dopamine levels.", "May improve mood, focus, and motivation.", "Used in the management of Parkinson's disease.", "Can support male fertility and libido."], precautions: "Can cause nausea, abdominal bloating, and insomnia. Should not be taken with MAOI antidepressants or if you have a history of melanoma.", brands: [{ name: "The Genius Brand", url: "https://thegeniusbrand.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Banyan Botanicals", url: "https://www.banyanbotanicals.com/" }, { name: "Organic India", url: "https://shop.organicindiausa.com/" }] },
            { name: "Artichoke Extract (Luteolin)", description: "Derived from the artichoke plant, this extract is rich in cynarin and luteolin. Luteolin is a natural inhibitor of the PDE4 enzyme, which is linked to cognitive function.", benefits: ["Inhibits PDE4, which may enhance memory, wakefulness, and neuroprotection.", "Often paired with Forskolin to synergistically increase cAMP levels.", "Supports liver health and digestion."], precautions: "Generally safe. People with allergies to ragweed and related plants may have an allergic reaction. Consult a doctor if you have bile duct obstruction.", brands: [{ name: "Natural Stacks", url: "https://www.naturalstacks.com/" }, { name: "Double Wood Supplements", url: "https://doublewoodsupplements.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Solaray", url: "https://solaray.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }] },
            { name: "Coleus Forskohlii (Forskolin)", description: "An herb used in traditional Ayurvedic medicine. The active ingredient, forskolin, works on muscles in the heart and in the walls of the blood vessels. It increases an enzyme called cyclic AMP (cAMP).", benefits: ["Increases cellular levels of cAMP, which is associated with improved learning, memory, and mental stamina.", "Often paired with Artichoke Extract.", "May aid in weight loss and muscle building."], precautions: "Can lower blood pressure, so it should be avoided by those with low blood pressure. May increase stomach acid levels.", brands: [{ name: "Natural Stacks", url: "https://www.naturalstacks.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "Paradise Herbs", url: "https://paradiseherbs.com/" }] },
            { name: "Theacrine", description: "A naturally occurring chemical that is similar to caffeine. It's found in different types of tea and coffee, as well as in the seeds of the Herrania and Theocrama plant species.", benefits: ["Provides long-lasting energy without the jitteriness or crash of caffeine.", "Improves mood, focus, and motivation.", "Does not seem to lead to tolerance as quickly as caffeine."], precautions: "Generally safe. Less is known about it than caffeine, so it's best to use it in moderation. Avoid taking with other stimulants.", brands: [{ name: "TeaCrine", url: "https://www.compoundsolutions.com/teacrine.html" }, { name: "Jym Supplement Science", url: "https://jymsupplementscience.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Primaforce", url: "https://primaforce.com/" }, { name: "Kaged", url: "https://www.kaged.com/" }] },
            { name: "Schisandra Berry", description: "The fruit of a climbing vine, used in traditional Chinese medicine. It's an adaptogen with five distinct flavors (sweet, sour, salty, bitter, pungent) corresponding to the five elements.", benefits: ["Helps the body resist the effects of anxiety and stress.", "Increases endurance, accuracy, and working capacity.", "Supports liver function and may protect against liver damage."], precautions: "Generally safe. Avoid if pregnant. May cause stomach upset in some individuals.", brands: [{ name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "Dragon Herbs", url: "https://www.dragonherbs.com/" }, { name: "Sun Potion", url: "https://www.sunpotion.com/" }, { name: "Herb Pharm", url: "https://www.herb-pharm.com/" }] },
            { name: "Maritime Pine Bark Extract (Pycnogenol)", description: "A patented extract from the bark of the French maritime pine tree. It is a potent blend of antioxidants.", benefits: ["Improves blood flow, which can enhance cognitive function and attention.", "Powerful antioxidant and anti-inflammatory.", "May improve symptoms of ADHD.", "Supports skin and cardiovascular health."], precautions: "Generally safe. May cause dizziness or stomach issues. Can interact with immunosuppressants and diabetes medication.", brands: [{ name: "Pycnogenol", url: "https://www.pycnogenol.com/" }, { name: "Healthy Origins", url: "https://healthyorigins.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Solgar", url: "https://www.solgar.com/" }] },
            { name: "Cat's Claw (Uncaria tomentosa)", description: "A tropical vine that gets its name from its hooked thorns. It's used in traditional medicine to treat a wide range of health problems, particularly inflammation and immune issues.", benefits: ["Supports the immune system.", "Has potent anti-inflammatory effects.", "Contains antioxidants that help fight free radicals.", "May help repair DNA."], precautions: "Should be avoided by pregnant women and those with autoimmune disorders or leukemia. Can interfere with certain medications.", brands: [{ name: "Onnit", url: "https://www.onnit.com/" }, { name: "Raintree", url: "https://www.rain-tree.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }] },
            { name: "Oat Straw (Avena sativa)", description: "Derived from green oats, it has been used for centuries to support brain health, relieve stress, and increase energy levels.", benefits: ["May boost brain function in older adults.", "Can improve attention and concentration.", "Has a calming effect and can reduce anxiety.", "Supports heart health."], precautions: "Very safe and well-tolerated. Individuals with celiac disease or gluten sensitivity should ensure the product is certified gluten-free.", brands: [{ name: "Onnit", url: "https://www.onnit.com/" }, { name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" }, { name: "Starwest Botanicals", url: "https://www.starwest-botanicals.com/" }, { name: "Mountain Rose Herbs", url: "https://mountainroseherbs.com/" }, { name: "Frontier Co-op", url: "https://www.frontiercoop.com/" }] },
            { name: "Rosemary", description: "A fragrant evergreen herb native to the Mediterranean. It is used as a culinary condiment, to make bodily perfumes, and for its potential health benefits.", benefits: ["The aroma may improve concentration, performance, and mood.", "Contains antioxidants and anti-inflammatory compounds.", "May help protect the brain from damage."], precautions: "Safe in culinary amounts. Very large quantities can cause side effects. Essential oil should not be ingested.", brands: [{ name: "Simply Organic", url: "https://www.simplyorganic.com/" }, { name: "McCormick", url: "https://www.mccormick.com/" }, { name: "Traditional Medicinals", url: "https://www.traditionalmedicinals.com/" }, { name: "Herb Pharm", url: "https://www.herb-pharm.com/" }, { name: "Aura Cacia", url: "https://www.auracacia.com/" }] },
            { name: "Sage", description: "A staple herb in various cuisines around the world. It also has a long history of use in alternative and traditional medicine. It is believed to have memory-enhancing properties.", benefits: ["May improve memory and information processing.", "Rich in antioxidants and anti-inflammatory compounds.", "Supports oral health.", "May lower 'bad' LDL cholesterol."], precautions: "Safe in culinary amounts. Some varieties contain thujone, a compound that can be toxic in high doses. Avoid large supplemental doses.", brands: [{ name: "Simply Organic", url: "https://www.simplyorganic.com/" }, { name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "Mountain Rose Herbs", url: "https://mountainroseherbs.com/" }] },
            { name: "Turmeric", description: "A common spice that comes from the root of Curcuma longa. It contains the chemical curcumin, which is often used to color foods and cosmetics. It's a cornerstone of Ayurvedic medicine.", benefits: ["Contains curcumin, a substance with powerful anti-inflammatory and antioxidant properties.", "May improve memory and attention.", "Can help fight age-related decrease in brain function."], precautions: "Generally safe. Curcumin is poorly absorbed without black pepper (piperine). High doses may cause digestive issues.", brands: [{ name: "MegaFood", url: "https://www.megafood.com/" }, { name: "New Chapter", url: "https://www.newchapter.com/" }, { name: "Garden of Life", url: "https://www.gardenoflife.com/" }, { name: "Qunol", url: "https://www.qunol.com/" }, { name: "Nature's Nutrition", url: "https://naturesnutrition.net/" }] },
            { name: "Green Tea Extract (EGCG)", description: "A supplement derived from the green tea plant (Camellia sinensis). It is rich in antioxidants called catechins, particularly epigallocatechin gallate (EGCG).", benefits: ["EGCG and L-theanine work together to improve focus and calm alertness.", "Rich in antioxidants that protect brain cells.", "May improve memory and attention.", "Supports heart and metabolic health."], precautions: "Generally safe. Concentrated extracts can cause liver issues in rare cases, especially when taken on an empty stomach. Stick to recommended doses.", brands: [{ name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "BulkSupplements.com", url: "https://www.bulksupplements.com/" }, { name: "Ito En", url: "https://www.itoen.com/" }] },
            { name: "Nicotinamide Riboside (NR)", description: "A form of vitamin B3. It is converted by your body into nicotinamide adenine dinucleotide (NAD+), a coenzyme that is vital for metabolism and cellular processes.", benefits: ["Boosts NAD+ levels, which decline with age.", "May help fight brain aging by supporting cellular energy production.", "Supports healthy aging in general."], precautions: "Generally safe and well-tolerated. Mild side effects like nausea can occur. Long-term effects are still being studied.", brands: [{ name: "Tru Niagen", url: "https://www.truniagen.com/" }, { name: "Elysium Health", url: "https://www.elysiumhealth.com/" }, { name: "Thorne", url: "https://www.thorne.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }] },
            { name: "Pterostilbene", description: "A compound found in blueberries and grapes. It is chemically similar to resveratrol but is more easily absorbed and utilized by the body.", benefits: ["A powerful antioxidant and anti-inflammatory agent.", "May improve cognition and protect against age-related cognitive decline.", "Supports healthy blood sugar and cholesterol levels."], precautions: "Generally safe. May lower blood sugar, so diabetics should monitor levels closely. Not much is known about long-term use.", brands: [{ name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Double Wood Supplements", url: "https://doublewoodsupplements.com/" }, { name: "Thorne", url: "https://www.thorne.com/" }, { name: "Source Naturals", url: "https://www.sourcenaturals.com/" }] },
            { name: "Alpha Lipoic Acid (ALA)", description: "An antioxidant made by the body. It is found in every cell, where it helps turn glucose into energy. Antioxidants attack 'free radicals,' waste products created when the body turns food into energy.", benefits: ["A universal antioxidant, working in both water and fatty tissues.", "May protect brain and nerve tissue from damage.", "Can improve memory in some animal models.", "Helps with blood sugar control."], precautions: "Generally safe. May lower blood sugar levels, so people with diabetes should be cautious. Can interfere with thyroid treatments.", brands: [{ name: "Doctor's Best", url: "https://www.drbvitamins.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }] },
            { name: "Coenzyme Q10 (CoQ10)", description: "A compound that helps generate energy in your cells. Your body produces it naturally, but its production tends to decrease with age. It is stored in the mitochondria of your cells.", benefits: ["Essential for cellular energy production.", "Acts as a powerful antioxidant, protecting brain cells.", "May help prevent migraines.", "Supports heart health."], precautions: "Generally safe with few side effects. Can cause mild insomnia or digestive upset. Interacts with blood thinners and blood pressure medication.", brands: [{ name: "Qunol", url: "https://www.qunol.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }, { name: "Nature Made", url: "https://www.naturemade.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }] },
            { name: "Vitamin B6", description: "A water-soluble vitamin that is naturally present in many foods. It is vital for normal brain development and for keeping the nervous system and immune system healthy.", benefits: ["Crucial for creating neurotransmitters like serotonin and dopamine.", "May improve mood and reduce symptoms of depression.", "Can promote brain health and reduce Alzheimer's risk."], precautions: "Safe at recommended doses. Very high, long-term doses can cause severe nerve damage. Stick to the recommended dietary allowance unless advised by a doctor.", brands: [{ name: "Solgar", url: "https://www.solgar.com/" }, { name: "Nature's Bounty", url: "https://www.naturesbounty.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "GNC", url: "https://www.gnc.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }] },
            { name: "Vitamin B12", description: "An essential vitamin that your body needs but cannot produce. It's found naturally in animal products and is crucial for nerve function and the formation of DNA and red blood cells.", benefits: ["Supports the normal function of your nerve cells.", "May improve memory, especially in older adults.", "Can give you an energy boost.", "May improve mood and symptoms of depression."], precautions: "Very safe, even at high doses, as the body excretes what it doesn't use. Deficiencies are common in vegetarians, vegans, and older adults.", brands: [{ name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Garden of Life", url: "https://www.gardenoflife.com/" }, { name: "Solgar", url: "https://www.solgar.com/" }, { name: "Nature Made", url: "https://www.naturemade.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }] },
            { name: "Vitamin D", description: "Known as the 'sunshine vitamin,' it's a fat-soluble vitamin that is produced when UV rays from sunlight strike the skin. It has many roles in the body, including supporting brain health.", benefits: ["Plays a role in attention and executive function.", "May help improve mood.", "Crucial for bone health and immune function."], precautions: "Deficiency is very common. Toxicity is rare but can occur with mega-doses. It's best to get levels tested to determine appropriate dosage.", brands: [{ name: "Nordic Naturals", url: "https://www.nordic.com/" }, { name: "Carlson Labs", url: "https://carlsonlabs.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }, { name: "Sports Research", url: "https://sportsresearch.com/" }] },
            { name: "Zinc", description: "An essential mineral that is naturally present in some foods. Zinc is vital for immune function, wound healing, and the synthesis of DNA and proteins. It also plays a key role in brain function.", benefits: ["Essential for neurotransmitter function.", "Plays a role in memory and learning.", "Supports immune health.", "Important for mood regulation."], precautions: "High doses can interfere with copper absorption and cause nausea. It's best to stick to recommended daily amounts unless advised otherwise.", brands: [{ name: "Thorne", url: "https://www.thorne.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }, { name: "Life Extension", url: "https://www.lifeextension.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }] },
            { name: "Lemon Balm", description: "A lemon-scented herb that comes from the same family as mint. It is native to Europe, North Africa, and West Asia, but it's grown all over the world. It's traditionally used to improve mood and cognitive function.", benefits: ["Can reduce stress and anxiety.", "May help ease insomnia and other sleep disorders.", "Improves cognitive performance and mood.", "Soothes symptoms of indigestion."], precautions: "Generally safe. May cause mild side effects like headache or nausea. Can cause sleepiness, so be careful when driving.", brands: [{ name: "Traditional Medicinals", url: "https://www.traditionalmedicinals.com/" }, { name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "Swanson", url: "https://www.swansonvitamins.com/" }, { name: "Herb Pharm", url: "https://www.herb-pharm.com/" }] },
            { name: "Valerian Root", description: "An herb native to Europe and Asia. The root has been used since ancient Greek and Roman times as a medicinal herb, primarily for sleep disorders and anxiety.", benefits: ["Helps improve sleep quality without producing a 'hangover' effect.", "Can reduce anxiety and promote feelings of calmness.", "May reduce hyperactive behaviors in some children."], precautions: "Can cause headache, dizziness, and stomach upset. It's best not to take it with alcohol or other sedatives. Long-term safety is unknown.", brands: [{ name: "Gaia Herbs", url: "https://www.gaiaherbs.com/" }, { name: "Nature's Way", url: "https://www.naturesway.com/" }, { name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Solgar", url: "https://www.solgar.com/" }, { name: "Herb Pharm", url: "https://www.herb-pharm.com/" }] },
            { name: "5-HTP", description: "5-Hydroxytryptophan is an amino acid that your body naturally produces. Your body uses it to produce serotonin, a chemical messenger that sends signals between your nerve cells.", benefits: ["May help increase serotonin levels, which can improve mood.", "Can help with depression, anxiety, and sleep disorders.", "May aid in weight loss by increasing feelings of fullness."], precautions: "Can cause nausea and digestive issues. Should not be taken with antidepressants (SSRIs) as it can lead to a dangerous condition called serotonin syndrome.", brands: [{ name: "NOW Foods", url: "https://www.nowfoods.com/" }, { name: "Natrol", url: "https://www.natrol.com/" }, { name: "Doctor's Best", url: "https://www.drbvitamins.com/" }, { name: "Source Naturals", url: "https://www.sourcenaturals.com/" }, { name: "Jarrow Formulas", url: "https://jarrow.com/" }] }
        ];

        // --- DOM ELEMENTS ---
        const grid = document.getElementById('nootropicsGrid');
        const searchInput = document.getElementById('searchInput');
        const notFoundMessage = document.getElementById('notFoundMessage');
        const modal = document.getElementById('infoModal');
        const modalPanel = document.getElementById('modal-panel');
        const modalContent = document.getElementById('modalContent');
        const closeModalBtn = document.getElementById('closeModal');
        const voiceToggle = document.getElementById('voiceToggle');
        const voiceIcon = document.getElementById('voice-icon');
        const zoomInBtn = document.getElementById('zoom-in');
        const zoomOutBtn = document.getElementById('zoom-out');
        const zoomResetBtn = document.getElementById('zoom-reset');

        // --- SETTINGS STATE ---
        let isVoiceOverEnabled = false;
        let currentFontSize = 16; // Base font size in pixels

        // --- FUNCTIONS ---

        /**
         * Renders the nootropic cards to the grid.
         * @param {Array} nootropics - The array of nootropic objects to display.
         */
        function displayNootropics(nootropics) {
            grid.innerHTML = ''; // Clear existing grid content
            if (nootropics.length === 0) {
                notFoundMessage.classList.remove('hidden');
            } else {
                notFoundMessage.classList.add('hidden');
            }
            nootropics.forEach(nootropic => {
                const card = document.createElement('div');
                card.className = 'bg-white rounded-xl shadow-lg hover:shadow-2xl transition-all duration-300 cursor-pointer overflow-hidden transform hover:-translate-y-1.5';
                card.innerHTML = `
                    <div class="p-6">
                        <h3 class="text-lg font-semibold text-gray-900 truncate">${nootropic.name}</h3>
                        <p class="text-sm text-gray-500 mt-2 line-clamp-2">${nootropic.description}</p>
                    </div>
                    <div class="px-6 pb-4">
                        <span class="inline-block bg-indigo-100 text-indigo-800 text-xs font-medium px-2.5 py-1 rounded-full">View Details</span>
                    </div>
                `;
                card.addEventListener('click', () => openModal(nootropic));
                grid.appendChild(card);
            });
        }

        /**
         * Opens the modal and displays the details for a selected nootropic.
         * @param {Object} nootropic - The selected nootropic object.
         */
        function openModal(nootropic) {
            modalContent.innerHTML = `
                <h2 class="text-3xl font-bold text-gray-900 mb-4">${nootropic.name}</h2>
                <p class="text-gray-600 mb-6">${nootropic.description}</p>
                
                <div class="space-y-6">
                    <div>
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">Potential Benefits</h3>
                        <ul class="list-disc list-inside space-y-1 text-gray-700">
                            ${nootropic.benefits.map(benefit => `<li>${benefit}</li>`).join('')}
                        </ul>
                    </div>
                    
                    <div>
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">Precautions & Side Effects</h3>
                        <div class="precaution-box">
                            <p class="text-yellow-800">${nootropic.precautions}</p>
                        </div>
                    </div>

                    <div>
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">Found In These Brands</h3>
                        <div class="flex flex-wrap gap-3">
                            ${nootropic.brands.map(brand => `
                                <a href="${brand.url}" target="_blank" rel="noopener noreferrer" class="bg-gray-100 text-gray-800 hover:bg-gray-200 transition-colors duration-200 font-medium px-4 py-2 rounded-lg text-sm">
                                    ${brand.name} &rarr;
                                </a>
                            `).join('')}
                        </div>
                    </div>
                </div>
            `;
            modal.classList.remove('hidden');
            setTimeout(() => {
                modalPanel.classList.remove('scale-95', 'opacity-0');
            }, 10);

            if (isVoiceOverEnabled) {
                speakNootropicInfo(nootropic);
            }
        }

        /**
         * Closes the info modal and stops any speech.
         */
        function closeModal() {
            window.speechSynthesis.cancel(); // Stop any active speech
            modalPanel.classList.add('scale-95', 'opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300);
        }
        
        /**
         * Uses the Web Speech API to read out the nootropic information.
         * @param {Object} nootropic - The nootropic object to speak about.
         */
        function speakNootropicInfo(nootropic) {
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel(); // Cancel any previous speech

                const textToSpeak = `
                    ${nootropic.name}.
                    Description: ${nootropic.description}.
                    Potential Benefits: ${nootropic.benefits.join(', ')}.
                    Precautions: ${nootropic.precautions}.
                `;
                
                const utterance = new SpeechSynthesisUtterance(textToSpeak);
                utterance.lang = 'en-US';
                window.speechSynthesis.speak(utterance);
            } else {
                console.log("Sorry, your browser does not support text-to-speech.");
            }
        }

        /**
         * Updates the root font size to zoom the page content.
         */
        function updateZoom() {
            document.documentElement.style.fontSize = `${currentFontSize}px`;
        }

        // --- EVENT LISTENERS ---

        // Search input listener
        searchInput.addEventListener('input', (e) => {
            const searchTerm = e.target.value.toLowerCase();
            const filteredNootropics = nootropicsData.filter(n => 
                n.name.toLowerCase().includes(searchTerm) || 
                n.description.toLowerCase().includes(searchTerm)
            );
            displayNootropics(filteredNootropics);
        });

        // Modal close listeners
        closeModalBtn.addEventListener('click', closeModal);
        modal.addEventListener('click', (e) => {
            if (e.target === modal) {
                closeModal();
            }
        });
        
        // Close modal with Escape key
        window.addEventListener('keydown', (e) => {
            if (e.key === 'Escape' && !modal.classList.contains('hidden')) {
                closeModal();
            }
        });

        // Settings listeners
        voiceToggle.addEventListener('change', (e) => {
            isVoiceOverEnabled = e.target.checked;
            if (!isVoiceOverEnabled) {
                window.speechSynthesis.cancel(); // Stop speech if toggled off
            }
            voiceIcon.classList.toggle('text-gray-400', !isVoiceOverEnabled);
            voiceIcon.classList.toggle('text-indigo-600', isVoiceOverEnabled);
        });

        zoomInBtn.addEventListener('click', () => {
            currentFontSize = Math.min(24, currentFontSize + 1); // Max font size 24px
            updateZoom();
        });

        zoomOutBtn.addEventListener('click', () => {
            currentFontSize = Math.max(12, currentFontSize - 1); // Min font size 12px
            updateZoom();
        });

        zoomResetBtn.addEventListener('click', () => {
            currentFontSize = 16; // Reset to base
            updateZoom();
        });


        // --- INITIALIZATION ---
        displayNootropics(nootropicsData);

    </script>
</body>
</html>
