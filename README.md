# MODUS-EDUKASI-PEMANTAUAN-MANDIRI-
Modul edukasi diabetes terdiri dari 4 pilar: mengenal Diabetes Melitus tipe 1 dan 2 serta gejala hipo dan hiperglikemia; pengaturan nutrisi dengan metode piring makan Model T dan pembatasan gula; aktivitas fisik seperti jalan kaki 30 menit/hari; serta perawatan mandiri melalui penggunaan glukometer dan kepatuhan minum obat/insulin.
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aplikasi Pemantauan Mandiri Diabetes</title>
    <style>
        :root {
            --primary-color: #2c7be5;
            --bg-color: #f4f6f9;
            --text-dark: #333;
            --white: #ffffff;
        }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: var(--bg-color); margin: 0; color: var(--text-dark); }
        header { background: var(--primary-color); color: white; padding: 30px 20px; text-align: center; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        header h1 { margin: 0; font-size: 24px; }
        .container { max-width: 800px; margin: 20px auto; padding: 0 20px; }
        .card { background: var(--white); padding: 25px; margin-bottom: 20px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.05); }
        h2 { color: var(--primary-color); border-bottom: 2px solid #eee; padding-bottom: 10px; margin-top: 0; }
        label { font-weight: bold; display: block; margin-top: 15px; margin-bottom: 5px; }
        select, input { width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 6px; box-sizing: border-box; font-size: 16px; }
        button { background: var(--primary-color); color: white; border: none; padding: 15px 30px; border-radius: 8px; cursor: pointer; font-size: 18px; font-weight: bold; width: 100%; transition: 0.3s; }
        button:hover { background: #1a5dc9; transform: translateY(-2px); }
        .result-box { margin-top: 20px; padding: 20px; border-radius: 8px; display: none; }
        .status-baik { background: #d4edda; color: #155724; border-left: 5px solid #28a745; }
        .status-kurang { background: #fff3cd; color: #856404; border-left: 5px solid #ffc107; }
        .footer { text-align: center; font-size: 12px; color: #888; margin-top: 40px; padding-bottom: 20px; }
    </style>
</head>
<body>

<header>
    <h1>Edukasi Pemantauan Mandiri Diabetes</h1>
    <p>Kuesioner Kualitas Hidup (DQOL) & Manajemen Diri (DMSQ)</p>
</header>

<div class="container">
    <div class="card">
        <h2>1. Data Responden</h2>
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px;">
            <div>
                <label>Usia (Tahun)</label>
                <input type="number" id="usia" placeholder="Contoh: 45" />
            </div>
            <div>
                <label>Jenis Kelamin</label>
                <select id="jk">
                    <option>Laki-laki</option>
                    <option>Perempuan</option>
                </select>
            </div>
        </div>
        <label>Lama Menderita Diabetes (Tahun)</label>
        <input type="number" id="lama" placeholder="Contoh: 5" />
    </div>

    <div class="card">
        <h2>2. Kualitas Hidup (DQOL)</h2>
        <p><small><i>1 = Sangat Tidak Puas/Setuju | 5 = Sangat Puas/Setuju</i></small></p>
        
        <label>1. Kepuasan terhadap pengobatan saat ini</label>
        <select class="dqol"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>2. Kemampuan melakukan aktivitas fisik</label>
        <select class="dqol"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>3. Ketenangan pikiran terkait komplikasi</label>
        <select class="dqol"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>4. Kepuasan terhadap dukungan keluarga</label>
        <select class="dqol"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>5. Rasa percaya diri mengontrol gula darah</label>
        <select class="dqol"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>
    </div>

    <div class="card">
        <h2>3. Manajemen Diri (DMSQ)</h2>
        <p><small><i>1 = Tidak Pernah | 5 = Selalu</i></small></p>
        
        <label>1. Mengikuti pola makan (diet) sehat</label>
        <select class="dmsq"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>2. Melakukan aktivitas fisik/olahraga rutin</label>
        <select class="dmsq"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>3. Memeriksa kadar gula darah secara mandiri</label>
        <select class="dmsq"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>4. Mengonsumsi obat/insulin sesuai jadwal</label>
        <select class="dmsq"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>

        <label>5. Melakukan perawatan kaki diabetes</label>
        <select class="dmsq"><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5" selected>5</option></select>
    </div>

    <button onclick="hitung()">LIHAT HASIL ANALISIS</button>

    <div id="hasil-box" class="result-box">
        <h2 id="status-title">Hasil Analisis</h2>
        <p id="skor-detail"></p>
        <p id="saran-edukasi"></p>
    </div>

    <div class="footer">
        &copy; 2026 Diabetes Self-Management App. Instrumen diadaptasi dari DQOL dan DMSQ.
    </div>
</div>

<script>
function hitung() {
    // Ambil semua data input
    const dqolInputs = document.querySelectorAll('.dqol');
    const dmsqInputs = document.querySelectorAll('.dmsq');
    
    let totalDQOL = 0;
    let totalDMSQ = 0;

    dqolInputs.forEach(input => totalDQOL += parseInt(input.value));
    dmsqInputs.forEach(input => totalDMSQ += parseInt(input.value));

    // Logika Analisis (Skala 5-25)
    let kKualitas = (totalDQOL >= 20) ? "Sangat Baik" : (totalDQOL >= 15) ? "Cukup Baik" : "Kurang Baik";
    let kManajemen = (totalDMSQ >= 18) ? "Patuh" : "Perlu Ditingkatkan";

    // Tampilkan Hasil
    const box = document.getElementById('hasil-box');
    const detail = document.getElementById('skor-detail');
    const saran = document.getElementById('saran-edukasi');

    box.style.display = 'block';
    box.className = 'result-box ' + (totalDMSQ >= 18 ? 'status-baik' : 'status-kurang');

    detail.innerHTML = `
        <strong>Skor Kualitas Hidup:</strong> ${totalDQOL} / 25 (${kKualitas})<br>
        <strong>Skor Manajemen Mandiri:</strong> ${totalDMSQ} / 25 (${kManajemen})
    `;

    // Berikan saran berdasarkan skor
    if (totalDMSQ < 18) {
        saran.innerHTML = "<strong>Saran:</strong> Fokuskan pada kedisiplinan jadwal obat dan olahraga ringan 30 menit sehari untuk meningkatkan kualitas hidup Anda.";
    } else {
        saran.innerHTML = "<strong>Saran:</strong> Pertahankan gaya hidup Anda! Tetap rutin melakukan pemeriksaan gula darah berkala dan kontrol ke dokter.";
    }

    // Scroll otomatis ke hasil
    box.scrollIntoView({ behavior: 'smooth' });
}
</script>

</body>
</html>
