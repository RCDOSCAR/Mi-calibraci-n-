<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calibración Profesional</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <style>
        body { font-family: sans-serif; background: #0f172a; color: white; padding: 20px; }
        .tab-content { display: none; }
        .active { display: block; }
        .card { background: #1e293b; padding: 20px; border-radius: 12px; margin-bottom: 20px; }
        input, select, button { width: 100%; padding: 14px; margin: 8px 0; border-radius: 8px; border: none; background: #334155; color: white; font-size: 16px; }
        button { background: #22c55e; color: #000; font-weight: bold; cursor: pointer; }
        .item-container { background: #334155; padding: 15px; border-radius: 10px; margin-bottom: 15px; border-left: 5px solid #22c55e; }
    </style>
</head>
<body>

<div style="display: flex; gap: 10px; margin-bottom: 20px;">
    <button onclick="showTab('add')">➕ Nueva</button>
    <button onclick="showTab('list')">📋 Lista</button>
</div>

<div id="add" class="tab-content active">
    <div class="card">
        <h2>Ingresar Herramienta</h2>
        <input type="text" id="nombre" placeholder="Nombre">
        <input type="date" id="fechaUltima">
        <input type="number" id="cantidad" placeholder="Periodo (ej: 5)">
        <select id="unidad"><option value="meses">Meses</option><option value="dias">Días</option></select>
        <button onclick="guardar()">Guardar y Proyectar</button>
    </div>
</div>

<div id="list" class="tab-content">
    <button style="background:#3b82f6; color:white" onclick="render()">🔄 Refrescar Datos</button>
    <button style="background:#ef4444; color:white; margin-top:10px" onclick="generarPDF()">📥 Exportar PDF</button>
    <div id="lista" style="margin-top:20px"></div>
</div>

<script>
    function showTab(id) {
        document.querySelectorAll('.tab-content').forEach(t => t.style.display = 'none');
        document.getElementById(id).style.display = 'block';
        if(id === 'list') render();
    }

    function guardar() {
        let datos = JSON.parse(localStorage.getItem('calibraciones')) || [];
        let nombre = document.getElementById('nombre').value;
        let fechaBase = new Date(document.getElementById('fechaUltima').value + 'T12:00:00');
        let cant = parseInt(document.getElementById('cantidad').value);
        let uni = document.getElementById('unidad').value;
        
        if(!nombre || isNaN(fechaBase.getTime()) || isNaN(cant)) return alert("Por favor llena todos los campos correctamente");

        let fechas = [];
        let f = new Date(fechaBase);
        
        // Calcular fechas proyectadas
        while (true) {
            if (uni === 'meses') f.setMonth(f.getMonth() + cant);
            else f.setDate(f.getDate() + cant);
            if (f.getFullYear() > 2026) break;

            let d = f.getDay();
            if (d === 6) f.setDate(f.getDate() + 2); // Sáb -> Lun
            else if (d === 0) f.setDate(f.getDate() + 1); // Dom -> Lun

            fechas.push(new Intl.DateTimeFormat('es-ES', {weekday: 'long', day: 'numeric', month: 'long', year: 'numeric'}).format(f));
        }

        datos.push({ nombre, fechas });
        localStorage.setItem('calibraciones', JSON.stringify(datos));
        
        // LIMPIEZA DE CAMPOS
        document.getElementById('nombre').value = '';
        document.getElementById('fechaUltima').value = '';
        document.getElementById('cantidad').value = '';
        
        alert("¡Guardado correctamente! Ve a la pestaña 'Lista' para ver los resultados.");
        showTab('list');
    }

    function render() {
        let datos = JSON.parse(localStorage.getItem('calibraciones')) || [];
        let lista = document.getElementById('lista');
        lista.innerHTML = datos.map((h, i) => `
            <div class="item-container">
                <h3 style="margin-top:0">${h.nombre}</h3>
                ${h.fechas.map(f => `<div style="margin-bottom:5px">✅ ${f}</div>`).join('')}
                <button onclick="eliminar(${i})" style="background:#dc2626; color:white; margin-top:15px">Eliminar Herramienta</button>
            </div>
        `).join('');
    }

    function eliminar(i) {
        let datos = JSON.parse(localStorage.getItem('calibraciones'));
        datos.splice(i, 1);
        localStorage.setItem('calibraciones', JSON.stringify(datos));
        render();
    }

    function generarPDF() {
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF();
        let datos = JSON.parse(localStorage.getItem('calibraciones'));
        doc.setFontSize(16);
        doc.text("Plan Anual de Calibracion 2026", 10, 10);
        let y = 20;
        datos.forEach(h => {
            doc.setFontSize(12);
            doc.text(h.nombre.toUpperCase(), 10, y);
            y += 7;
            h.fechas.forEach(f => { doc.text("- " + f, 15, y); y += 6; });
            y += 5;
        });
        doc.save("Reporte_Calibracion_2026.pdf");
    }
</script>
</body>
</html>
