**Praktikum**

1. PHP dasar

   Tampilan VS Code

   ![gambar](https://github.com/syahbarudin/Lab7Web/assets/146621192/9823b176-c7b1-46fd-8217-3dd7370c3210)

   Tampilan Website

   ![gambar](https://github.com/syahbarudin/Lab7Web/assets/146621192/c33f8f33-a61a-498c-925c-42fc9ccf3578)

3. Variable PHP

   Tampilan VS Code

   ![gambar](https://github.com/syahbarudin/Lab7Web/assets/146621192/2a3fb497-1f7e-4f7d-858d-480fcf3e252a)

   Tampilan Website

   ![gambar](https://github.com/syahbarudin/Lab7Web/assets/146621192/ada30d86-53f5-4de9-9068-269f47e4801e)

4. Membuat form input

   Tampilan VS Code

   ![gambar](https://github.com/syahbarudin/Lab7Web/assets/146621192/7324e691-5156-44ed-b96e-7bab8e1dcafa)

   Tampilan Website

   ![gambar](https://github.com/syahbarudin/Lab7Web/assets/146621192/53131338-bcc3-48b3-8363-8b83cb6aefeb)


**_Tugas membuat form_**

       <!DOCTYPE html>
       <html>
        <head>
         <title>Form Input PHP</title>
         <style>
         body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
         }

        form {
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f8f8f8;
        }

        label {
            display: block;
            margin-bottom: 8px;
        }

        input,
        select {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            box-sizing: border-box;
        }

        input[type="submit"] {
            background-color: #4caf50;
            color: white;
            cursor: pointer;
        }
        .container {
            text-align: center;
        }

        form, .output {
            text-align: center;
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }
    </style>
    </head>
    <body>
    <div class=container>
    <h2>Form Input</h2>
    <form method="post" action="">
    <label for="nama">Nama:</label>
    <input type="text" name="nama" required><br>

    <label for="tanggal_lahir">Tanggal Lahir:</label>
    <input type="date" name="tanggal_lahir" required><br>

    <label for="pekerjaan">Pekerjaan:</label>
    <select name="pekerjaan" required>
        <option value="Programmer">Programmer</option>
        <option value="Designer">Designer</option>
        <option value="Marketing">Marketing</option>
        <option value="Manager">Manager</option>
    </select><br>

    <input type="submit" value="Submit">
    </form></div>
    <?php

    function hitungUmur($tanggal_lahir) {
       $tgl_lahir = new DateTime($tanggal_lahir);
       $sekarang = new DateTime('today');
       $umur = $sekarang->diff($tgl_lahir)->y;
       return $umur;
    }

    function hitungGaji($pekerjaan) {
       switch ($pekerjaan) {
        case 'Programmer':
            return 'Rp 10.000.000,-';
        case 'Designer':
            return 'Rp 8.000.000,-';
        case 'Marketing':
            return 'Rp 5.000.000,-';
        case 'Manager':
            return 'Rp 15.000.000,-';
        default:
            return 'Gaji tidak diketahui';
       }
    }   


    if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    
    $nama = $_POST['nama'];
    $tanggal_lahir = $_POST['tanggal_lahir'];
    $pekerjaan = $_POST['pekerjaan'];

    $umur = hitungUmur($tanggal_lahir);

    $gaji = hitungGaji($pekerjaan);

    echo "<div class='output'>";
    echo "<h2>Hasil Input:</h2>";
    echo "<p>Nama: $nama</p>";
    echo "<p>Tanggal Lahir: $tanggal_lahir</p>";
    echo "<p>Umur: $umur tahun</p>";
    echo "<p>Pekerjaan: $pekerjaan</p>";
    echo "<p>Gaji: $gaji</p>";
    echo "</div>";
    }
    ?>
    </body>
    </html>

Hasilnya

![gambar](https://github.com/syahbarudin/Lab7Web/assets/146621192/0d0f0827-5bae-4935-8d94-2591a0c14321)

