# PublicApp.github.io
<!-- Archivo corregido para MediTrack.apk -->
homeView.classList.add('view-hidden-left');
detailView.classList.remove('view-hidden-right');
detailView.classList.add('view-active');
window.scrollTo({ top: 0, behavior: 'smooth' });
}


function goBack() {
detailView.classList.remove('view-active');
detailView.classList.add('view-hidden-right');
homeView.classList.remove('view-hidden-left');
homeView.classList.add('view-active');
}


function startDownload() {
if (isDownloading) return;
const btn = document.getElementById('install-btn');
const link = document.getElementById('download-link');
const progressContainer = document.getElementById('download-progress');
const progressFill = document.getElementById('progress-fill');
isDownloading = true;


btn.disabled = true;
btn.innerHTML = '<span class="text-gray-500">Pendiente...</span>';
btn.classList.remove('bg-[#01875f]');
btn.classList.add('bg-gray-100', 'border', 'border-gray-300');


setTimeout(() => { link.click(); }, 500);


progressContainer.style.display = 'block';
let width = 0;
const interval = setInterval(() => {
if (width >= 100) {
clearInterval(interval);
finishDownload();
} else {
width += Math.random() * 8 + 2;
if (width > 100) width = 100;
progressFill.style.width = width + '%';
btn.innerHTML = `<span class="text-xs text-[#01875f] font-bold">${Math.round(width)}% de 28 MB</span>`;
}
}, 150);


function finishDownload() {
progressContainer.style.display = 'none';
progressFill.style.width = '0%';
btn.innerHTML = '<i class="fa-solid fa-circle-check mr-2"></i> Abrir';
btn.classList.remove('bg-gray-100');
btn.classList.add('bg-[#01875f]', 'text-white');
btn.disabled = false;
btn.onclick = () => showToast('La aplicación se está abriendo...');
showToast('✓ Descarga completada: MediTrack.apk');
isDownloading = false;
}
}


function showToast(msg) {
const toast = document.getElementById('toast');
toast.textContent = msg;
toast.classList.add('show');
setTimeout(() => toast.classList.remove('show'), 3500);
}
</script>
</body>
</html>
