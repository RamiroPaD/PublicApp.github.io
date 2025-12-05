# PublicApp.github.io
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Google Play Store - Descargar MediTrack</title>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet" />


<style>
* { box-sizing: border-box; }
body { font-family: 'Roboto', sans-serif; background: #f0f2f5; margin: 0; padding: 0; }
.hide-scrollbar::-webkit-scrollbar { display: none; }
.hide-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
.mobile-container { max-width: 480px; margin: 0 auto; background: #fff; min-height: 100vh; position: relative; box-shadow: 0 0 20px rgba(0,0,0,0.1); overflow: hidden; }
@keyframes spin { to { transform: rotate(360deg); } }
.loading-spinner { border: 3px solid #e5e7eb; border-top: 3px solid #01875f; border-radius: 50%; width: 24px; height: 24px; animation: spin 1s linear infinite; }
.view-section { transition: transform 0.3s ease-in-out, opacity 0.3s; width: 100%; position: absolute; top: 0; left: 0; min-height: 100vh; background: #fff; z-index: 10; }
.view-hidden-right { transform: translateX(100%); opacity: 0; pointer-events: none; }
.view-hidden-left { transform: translateX(-100%); opacity: 0; pointer-events: none; }
.view-active { transform: translateX(0); opacity: 1; pointer-events: auto; position: relative; }
.progress-bar-container { width: 100%; height: 4px; background: #e0e0e0; position: absolute; top: 0; left: 0; display: none; z-index: 100; }
.progress-bar-fill { height: 100%; background-color: #01875f; width: 0%; transition: width 0.2s ease-out; }
.toast { position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%); background: rgba(31,41,55,0.95); color: #fff; padding: 12px 24px; border-radius: 24px; font-size: 14px; box-shadow: 0 4px 12px rgba(0,0,0,0.15); z-index: 1000; opacity: 0; transition: opacity 0.3s ease-in-out; pointer-events: none; }
.toast.show { opacity: 1; }
button:active { transform: scale(0.98); }
@media (max-width: 480px) { .mobile-container { max-width: 100%; } }
</style>
</head>


<body>
<div class="mobile-container">
<!-- HOME -->
<div id="home-view" class="view-section view-active pb-20">
<div class="sticky top-0 z-40 bg-white pt-3 pb-2 px-4 shadow-sm">
<div class="flex items-center bg-gray-100 rounded-full px-4 py-3 shadow-sm border border-gray-200">
<i class="fa-solid fa-bars text-gray-600 text-lg"></i>
<input type="text" placeholder="Buscar apps y juegos" class="bg-transparent border-none outline-none ml-4 flex-grow text-gray-700 text-sm" readonly />
<div class="w-7 h-7 rounded-full bg-purple-600 flex items-center justify-center text-white font-bold text-xs ml-2">A</div>
</div>
<div class="flex mt-3 space-x-6 overflow-x-auto hide-scrollbar border-b border-gray-100">
<button class="whitespace-nowrap pb-2 px-1 border-b-2 border-[#01875f] text-[#01875f] font-medium text-sm">Para ti</button>
<button class="whitespace-nowrap pb-2 px-1 text-gray-500 font-medium text-sm">Más populares</button>
<button class="whitespace-nowrap pb-2 px-1 text-gray-500 font-medium text-sm">Infantiles</button>
</div>
</div>


<div class="overflow-y-auto">
<div class="p-4 border-b border-gray-100 cursor-pointer" onclick="goToAppDetail()">
<div class="relative rounded-xl overflow-hidden shadow-lg h-48 bg-gray-800 group">
<div class="absolute inset-0 flex items-center justify-center bg-gradient-to-r from-green-800 to-teal-900">
<i class="fa-brands fa-android text-7xl text-white opacity-20 group-hover:scale-110 transition duration-500"></i>
</div>
<div class="absolute bottom-0 left-0 p-4 bg-gradient-to-t from-black/90 via-black/50 to-transparent w-full">
<h2 class="text-white font-bold text-xl mb-1">MediTrack - Versión Beta</h2>
<div class="flex items-center text-gray-300 text-xs mb-2"><span>Herramientas</span> • <span class="flex items-center ml-1"><i class="fa-solid fa-star text-[10px] mr-1"></i>5.0</span></div>
<span class="bg-[#01875f] text-white px-6 py-1.5 rounded-md font-medium text-sm shadow-md">Ver detalles</span>
</div>
</div>
</div>
</div>


<div class="fixed bottom-0 max-w-[480px] w-full bg-white border-t border-gray-200 flex justify-around items-center h-16 z-50" style="left: 50%; transform: translateX(-50%);">
<button class="flex flex-col items-center justify-center w-full h-full text-[#01875f]"><i class="fa-solid fa-gamepad text-xl mb-1"></i><span class="text-[10px] font-medium">Juegos</span></button>
<button class="flex flex-col items-center justify-center w-full h-full text-gray-400"><i class="fa-solid fa-layer-group text-xl mb-1"></i><span class="text-[10px] font-medium">Apps</span></button>
