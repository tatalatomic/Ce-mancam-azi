<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ce Mâncăm Azi? - Smart Meal & Shopping</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap');
        body { font-family: 'Plus Jakarta Sans', sans-serif; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col justify-between max-w-md mx-auto shadow-2xl relative">

    <!-- Top Header -->
    <header class="bg-white px-6 py-4 border-b border-slate-100 flex justify-between items-center sticky top-0 z-10">
        <div>
            <h1 class="font-bold text-lg text-emerald-600 flex items-center gap-1">
                🍲 Ce Mâncăm Azi?
            </h1>
            <p class="text-xs text-slate-400">Familia ta | <span id="member-count">3</span> membri</p>
        </div>
        <button onclick="showScreen('family')" class="bg-emerald-50 text-emerald-700 px-3 py-1 rounded-full text-xs font-semibold hover:bg-emerald-100">
            ⚙️ Profil Familie
        </button>
    </header>

    <!-- TAB 1: ACASĂ -->
    <main id="screen-home" class="p-4 space-y-4 mb-20 overflow-y-auto">

        <!-- SOS Gătit -->
        <div class="bg-gradient-to-r from-amber-500 to-orange-500 rounded-2xl p-4 text-white shadow-lg shadow-orange-500/20 flex items-center justify-between cursor-pointer active:scale-95 transition-transform" onclick="alert('Se generează rețeta de urgență în 3 secunde pe baza ingredientelor din frigider!')">
            <div class="space-y-1">
                <span class="bg-white/20 text-xs px-2.5 py-0.5 rounded-full font-medium">Ora 18:00 - Criză de timp?</span>
                <h2 class="text-lg font-bold">SOS Gătit 🚨</h2>
                <p class="text-xs text-orange-100">Rețetă instant din ce ai în casă, fără bătăi de cap!</p>
            </div>
            <div class="bg-white text-orange-600 w-12 h-12 rounded-full flex items-center justify-center font-bold text-xl shadow-md">
                ⚡
            </div>
        </div>

        <!-- Hero -->
        <div class="bg-emerald-600 rounded-2xl p-5 text-white shadow-lg shadow-emerald-600/20 cursor-pointer active:scale-95 transition-transform" onclick="alert('Se deschide generatorul de rețete!')">
            <div class="flex justify-between items-start">
                <div>
                    <span class="bg-emerald-500/50 text-xs px-2.5 py-0.5 rounded-full font-medium">Meniu Inteligent</span>
                    <h2 class="text-xl font-bold mt-1">Ce gătesc azi? 🍳</h2>
                    <p class="text-xs text-emerald-100 mt-1">Alege rețeta perfectă pentru familia ta în câteva secunde.</p>
                </div>
                <span class="text-3xl">✨</span>
            </div>
        </div>

        <!-- Opțiuni -->
        <div class="grid grid-cols-1 gap-3">
            <div onclick="alert('Ai selectat: Ce am în frigider')" class="bg-white p-4 rounded-xl border border-slate-100 shadow-sm flex items-center gap-4 cursor-pointer hover:border-emerald-200">
                <div class="bg-blue-50 text-blue-600 p-3 rounded-xl text-xl">🧊</div>
                <div class="flex-1">
                    <h3 class="font-bold text-sm">Ce am în frigider</h3>
                    <p class="text-xs text-slate-400">Anti-risipă & economie maximă de bani</p>
                </div>
                <span class="text-slate-300">➔</span>
            </div>

            <div onclick="alert('Ai selectat: Pentru mine')" class="bg-white p-4 rounded-xl border border-slate-100 shadow-sm flex items-center gap-4 cursor-pointer hover:border-emerald-200">
                <div class="bg-purple-50 text-purple-600 p-3 rounded-xl text-xl">👤</div>
                <div class="flex-1">
                    <h3 class="font-bold text-sm">Pentru mine</h3>
                    <p class="text-xs text-slate-400">Dietă personalizată & masă rapidă</p>
                </div>
                <span class="text-slate-300">➔</span>
            </div>

            <div onclick="alert('Ai selectat: Pentru toată familia')" class="bg-white p-4 rounded-xl border border-slate-100 shadow-sm flex items-center gap-4 cursor-pointer hover:border-emerald-200">
                <div class="bg-amber-50 text-amber-600 p-3 rounded-xl text-xl">👨‍👩‍👧‍👦</div>
                <div class="flex-1">
                    <h3 class="font-bold text-sm">Pentru toată familia</h3>
                    <p class="text-xs text-slate-400">Gusturi împăcate & pachețel școală/serviciu</p>
                </div>
                <span class="text-slate-300">➔</span>
            </div>
        </div>

        <!-- Banner Cumpărături -->
        <div class="bg-slate-900 text-white p-4 rounded-xl flex items-center justify-between">
            <div class="space-y-0.5">
                <span class="text-xs text-emerald-400 font-semibold">Smart Shopping</span>
                <h4 class="font-bold text-sm">Lista de cumpărături</h4>
                <p class="text-xs text-slate-400">Fără cumpărături impulsive la piață!</p>
            </div>
            <button onclick="alert('Lista de cumpărături')" class="bg-emerald-500 text-white text-xs font-bold px-3 py-2 rounded-lg">
                Deschide 🛒
            </button>
        </div>
    </main>

    <!-- TAB 2: SETĂRI FAMILIE -->
    <main id="screen-family" class="p-4 space-y-4 mb-20 overflow-y-auto hidden">
        
        <div class="flex justify-between items-center mb-2">
            <div>
                <h2 class="text-lg font-bold text-slate-800">Profiluri Familie</h2>
                <p class="text-xs text-slate-400">Setează preferințele și restricțiile fiecăruia</p>
            </div>
            <button onclick="toggleAddMemberForm()" class="bg-emerald-600 text-white text-xs font-bold px-3 py-2 rounded-xl flex items-center gap-1 shadow-md shadow-emerald-600/20 active:scale-95 transition-transform">
                <span>+</span> Adaugă membru
            </button>
        </div>

        <!-- Formular Adăugare Membru (Ascuns inițial) -->
        <div id="add-member-form" class="bg-white p-4 rounded-2xl border-2 border-emerald-500 shadow-md space-y-3 hidden">
            <h3 class="font-bold text-sm text-emerald-700 flex items-center gap-1">
                👤 Membru Nou în Familie
            </h3>
            
            <div>
                <label class="text-xs font-semibold text-slate-500">1. Nume / Rol</label>
                <input type="text" id="input-name" placeholder="ex: Tata, Maria, Copil" class="w-full mt-1 p-2 border border-slate-200 rounded-lg text-sm focus:outline-none focus:border-emerald-500">
            </div>

            <div class="grid grid-cols-2 gap-2">
                <div>
                    <label class="text-xs font-semibold text-slate-500">2. Tip Membru</label>
                    <select id="input-type" class="w-full mt-1 p-2 border border-slate-200 rounded-lg text-sm bg-white">
                        <option value="Adult">Adult</option>
                        <option value="Copil">Copil</option>
                        <option value="Senior">Senior</option>
                    </select>
                </div>
                <div>
                    <label class="text-xs font-semibold text-slate-500">3. Obiectiv</label>
                    <select id="input-goal" class="w-full mt-1 p-2 border border-slate-200 rounded-lg text-sm bg-white">
                        <option value="Menținere">🥗 Menținere</option>
                        <option value="Slăbit">📉 Slăbit</option>
                        <option value="Masă musculară">💪 Energie/Masă</option>
                        <option value="Meniu Copii">🧒 Meniu Copii</option>
                    </select>
                </div>
            </div>

            <div>
                <label class="text-xs font-semibold text-slate-500">4. Alergii / Restricții Stricte</label>
                <input type="text" id="input-allergies" placeholder="ex: Fără lactoză, Fără nuci, Fără gluten" class="w-full mt-1 p-2 border border-slate-200 rounded-lg text-sm focus:outline-none focus:border-emerald-500">
            </div>

            <div>
                <label class="text-xs font-semibold text-slate-500">5. Gusturi & Preferințe</label>
                <input type="text" id="input-likes" placeholder="ex: Îi plac pastele, nu mănâncă ciuperci" class="w-full mt-1 p-2 border border-slate-200 rounded-lg text-sm focus:outline-none focus:border-emerald-500">
            </div>

            <div class="flex items-center gap-2 pt-1">
                <input type="checkbox" id="input-lunchbox" class="w-4 h-4 text-emerald-600 rounded">
                <label for="input-lunchbox" class="text-xs text-slate-600 font-medium">Necesită pachețel (școală/birou)</label>
            </div>

            <div class="flex gap-2 pt-2">
                <button onclick="saveMember()" class="flex-1 bg-emerald-600 text-white font-bold py-2 rounded-xl text-xs">Salvează Membru</button>
                <button onclick="toggleAddMemberForm()" class="bg-slate-100 text-slate-600 font-bold px-4 py-2 rounded-xl text-xs">Renunță</button>
            </div>
        </div>

        <!-- Lista Membrilor Existenti -->
        <div id="members-list" class="space-y-3">

            <!-- Card Membru 1 -->
            <div class="bg-white p-4 rounded-xl border border-slate-100 shadow-sm space-y-2">
                <div class="flex justify-between items-start">
                    <div class="flex items-center gap-2">
                        <span class="bg-blue-100 text-blue-700 p-2 rounded-lg text-sm">👨</span>
                        <div>
                            <h3 class="font-bold text-sm text-slate-800">Tata</h3>
                            <span class="text-[10px] bg-slate-100 text-slate-500 px-2 py-0.5 rounded-full">Adult • 💪 Masă musculară</span>
                        </div>
                    </div>
                    <span class="text-xs bg-amber-50 text-amber-600 px-2 py-1 rounded-md font-medium">💼 Pachețel Birou</span>
                </div>
                <div class="text-xs text-slate-500 border-t border-slate-50 pt-2 space-y-1">
                    <p><strong class="text-slate-700">Alergii:</strong> Niciuna</p>
                    <p><strong class="text-slate-700">Preferințe:</strong> Îi place carnea la grătar, fără mâncare picantă</p>
                </div>
            </div>

            <!-- Card Membru 2 -->
            <div class="bg-white p-4 rounded-xl border border-slate-100 shadow-sm space-y-2">
                <div class="flex justify-between items-start">
                    <div class="flex items-center gap-2">
                        <span class="bg-purple-100 text
                        
