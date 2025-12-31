<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Latihan Data Nilai Mahasiswa</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #dfe6eb;
            margin: 0;
            padding: 30px;
        }

        h1 {
            color: #444;
            margin-bottom: 20px;
        }

        .container {
            display: flex;
            gap: 20px;
        }

        .box {
            background: #dce6cc;
            padding: 20px;
            width: 50%;
            border: 1px solid #999;
        }

        .box h3 {
            text-align: center;
            margin-top: 0;
        }

        .line {
            border-top: 2px dashed #000;
            margin: 10px 0 15px;
        }

        label {
            display: inline-block;
            width: 130px;
            margin-bottom: 10px;
        }

        input[type="text"],
        input[type="number"] {
            width: 200px;
            padding: 5px;
        }

        .btn {
            margin-top: 10px;
        }

        button {
            padding: 5px 15px;
            margin-right: 5px;
            cursor: pointer;
        }

        .info {
            font-size: 14px;
            margin-top: 15px;
        }

        .output p {
            margin: 8px 0;
        }
    </style>
</head>
<body>

<h1>LATIHAN</h1>

<div class="container">

    <!-- INPUT -->
    <div class="box">
        <h3>DATA NILAI MAHASISWA</h3>
        <div class="line"></div>

        <label>Masukan NIM :</label>
        <input type="text" id="nim"><br>

        <label>Nama Mahasiswa :</label>
        <input type="text" id="nama"><br>

        <label>Nilai UTS :</label>
        <input type="number" id="uts"><br>

        <label>Nilai UAS :</label>
        <input type="number" id="uas"><br>

        <label>Nilai Tugas :</label>
        <input type="number" id="tugas"><br>

        <div class="btn">
            <button onclick="proses()">Proses</button>
            <button onclick="batal()">Batal</button>
        </div>

        <div class="line"></div>

        <div class="info">
            UTS : 30% &nbsp; UAS : 40% &nbsp; TUGAS : 30% <br>
            85 s/d 100 : A, 70 s/d 84 : B, 60 s/d 69 : C, 40 s/d 59 : D, &lt; 40 : E
        </div>
    </div>

    <!-- OUTPUT -->
    <div class="box output">
        <h3>DATA NILAI MAHASISWA</h3>
        <div class="line"></div>

        <p><b>NIM :</b> <span id="o_nim"></span></p>
        <p><b>Nama Mahasiswa :</b> <span id="o_nama"></span></p>
        <p><b>Nilai UTS :</b> <span id="o_uts"></span></p>
        <p><b>Nilai UAS :</b> <span id="o_uas"></span></p>
        <p><b>Nilai Tugas :</b> <span id="o_tugas"></span></p>
        <p><b>Index :</b> <span id="o_index"></span></p>

        <div class="line"></div>
    </div>

</div>

<script>
    function proses() {
        let nim = document.getElementById("nim").value;
        let nama = document.getElementById("nama").value;
        let uts = parseFloat(document.getElementById("uts").value);
        let uas = parseFloat(document.getElementById("uas").value);
        let tugas = parseFloat(document.getElementById("tugas").value);

        let nilaiAkhir = (uts * 0.3) + (uas * 0.4) + (tugas * 0.3);
        let index = "";

        if (nilaiAkhir >= 85) index = "A";
        else if (nilaiAkhir >= 70) index = "B";
        else if (nilaiAkhir >= 60) index = "C";
        else if (nilaiAkhir >= 40) index = "D";
        else index = "E";

        document.getElementById("o_nim").innerText = nim;
        document.getElementById("o_nama").innerText = nama;
        document.getElementById("o_uts").innerText = uts;
        document.getElementById("o_uas").innerText = uas;
        document.getElementById("o_tugas").innerText = tugas;
        document.getElementById("o_index").innerText = index;
    }

    function batal() {
        document.getElementById("nim").value = "";
        document.getElementById("nama").value = "";
        document.getElementById("uts").value = "";
        document.getElementById("uas").value = "";
        document.getElementById("tugas").value = "";

        document.getElementById("o_nim").innerText = "";
        document.getElementById("o_nama").innerText = "";
        document.getElementById("o_uts").innerText = "";
        document.getElementById("o_uas").innerText = "";
        document.getElementById("o_tugas").innerText = "";
        document.getElementById("o_index").innerText = "";
    }
</script>

</body>
</html>
