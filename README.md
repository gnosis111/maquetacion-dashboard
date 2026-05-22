<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard de Estadísticas - Checkpoint</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body class="bg-gray-100 font-sans text-gray-800 antialiased">

    <div class="flex h-screen overflow-hidden">
        
        <main class="flex-1 overflow-y-auto p-8">
            
            <div class="mb-8">
                <h1 class="text-3xl font-bold text-gray-900">Dashboard de Rendimiento</h1>
                <p class="text-gray-500 mt-1">Monitoreo en tiempo real de las métricas de tu aplicación.</p>
            </div>

            <div class="grid grid-cols-4 gap-6 mb-8">
                
                <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-sm font-medium text-gray-500 uppercase tracking-wider">Usuarios Activos</span>
                        <div class="p-2 bg-blue-50 text-blue-600 rounded-lg">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" /></svg>
                        </div>
                    </div>
                    <div class="flex items-baseline space-x-2">
                        <span class="text-2xl font-bold">14,820</span>
                        <span class="text-sm font-semibold text-green-600">+12%</span>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-sm font-medium text-gray-500 uppercase tracking-wider">Ingresos Totales</span>
                        <div class="p-2 bg-green-50 text-green-600 rounded-lg">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
                        </div>
                    </div>
                    <div class="flex items-baseline space-x-2">
                        <span class="text-2xl font-bold">$45,231</span>
                        <span class="text-sm font-semibold text-green-600">+8.4%</span>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-sm font-medium text-gray-500 uppercase tracking-wider">Tasa de Conversión</span>
                        <div class="p-2 bg-purple-50 text-purple-600 rounded-lg">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" /></svg>
                        </div>
                    </div>
                    <div class="flex items-baseline space-x-2">
                        <span class="text-2xl font-bold">3.24%</span>
                        <span class="text-sm font-semibold text-red-600">-1.5%</span>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-sm font-medium text-gray-500 uppercase tracking-wider">Sesiones Nuevas</span>
                        <div class="p-2 bg-orange-50 text-orange-600 rounded-lg">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>
                        </div>
                    </div>
                    <div class="flex items-baseline space-x-2">
                        <span class="text-2xl font-bold">2,430</span>
                        <span class="text-sm font-semibold text-green-600">+23%</span>
                    </div>
                </div>

            </div>

            <div class="grid grid-cols-2 gap-6">
                
                <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                    <div class="mb-4">
                        <h3 class="text-lg font-semibold text-gray-900">Historial de Ventas</h3>
                        <p class="text-sm text-gray-500">Desempeño financiero mensual</p>
                    </div>
                    <div class="relative h-64">
                        <canvas id="graficaLineas"></canvas>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                    <div class="mb-4">
                        <h3 class="text-lg font-semibold text-gray-900">Adquisición por Canal</h3>
                        <p class="text-sm text-gray-500">Origen de los nuevos usuarios</p>
                    </div>
                    <div class="relative h-64">
                        <canvas id="graficaBarras"></canvas>
                    </div>
                </div>

            </div>

        </main>
    </div>

    <script>
        // Gráfica de Líneas
        const ctxLineas = document.getElementById('graficaLineas').getContext('2d');
        new Chart(ctxLineas, {
            type: 'line',
            data: {
                labels: ['Ene', 'Feb', 'Mar', 'Abr', 'May', 'Jun'],
                datasets: [{
                    label: 'Ventas ($)',
                    data: [12000, 19000, 3000, 5000, 22000, 30000],
                    borderColor: 'rgb(59, 130, 246)',
                    backgroundColor: 'rgba(59, 130, 246, 0.1)',
                    borderWidth: 2,
                    fill: true,
                    tension: 0.4
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false
            }
        });

        // Gráfica de Barras
        const ctxBarras = document.getElementById('graficaBarras').getContext('2d');
        new Chart(ctxBarras, {
            type: 'bar',
            data: {
                labels: ['Orgánico', 'Referidos', 'Social', 'Anuncios'],
                datasets: [{
                    label: 'Usuarios',
                    data: [450, 200, 150, 320],
                    backgroundColor: [
                        'rgba(34, 197, 94, 0.8)',
                        'rgba(168, 85, 247, 0.8)',
                        'rgba(249, 115, 22, 0.8)',
                        'rgba(59, 130, 246, 0.8)'
                    ],
                    borderRadius: 6
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false
            }
        });
    </script>
</body>
</html>
