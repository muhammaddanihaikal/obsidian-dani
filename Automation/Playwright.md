- 1-Pengenalan
    - Materi
        
        # 🎭 Playwright - Hari 1
        
        # Pengenalan Playwright
        
        ---
        
        # 🎯 Tujuan
        
        Pada materi ini kita akan mengenal Playwright, memahami alasan mengapa banyak perusahaan mulai beralih dari Selenium, serta memahami konsep dasar sebelum mulai menulis automation test.
        
        ---
        
        # 📖 Apa itu Playwright?
        
        Playwright adalah framework automation browser yang dikembangkan oleh **Microsoft** untuk melakukan pengujian aplikasi web secara otomatis.
        
        Playwright memungkinkan kita mengontrol browser menggunakan kode, sehingga aktivitas yang biasanya dilakukan secara manual seperti:
        
        - Membuka browser
        - Mengunjungi website
        - Mengisi form
        - Menekan tombol
        - Memastikan hasil
        
        dapat dilakukan secara otomatis.
        
        Framework ini mendukung beberapa browser populer seperti:
        
        - Chromium (Chrome, Edge, Brave, Opera)
        - Firefox
        - WebKit (Safari Engine)
        
        Selain itu, Playwright juga mendukung beberapa bahasa pemrograman, seperti:
        
        - Python
        - JavaScript
        - TypeScript
        - Java
        - .NET
        
        ---
        
        # ⚔️ Selenium vs Playwright
        
        ## Selenium
        
        ```
        Python
           ↓
        Selenium
           ↓
        ChromeDriver
           ↓
        Browser
        ```
        
        Pada Selenium, komunikasi dengan browser dilakukan melalui **browser driver** seperti ChromeDriver atau GeckoDriver.
        
        Karena menggunakan driver terpisah, terkadang muncul masalah seperti:
        
        - Driver tidak cocok dengan versi browser.
        - Harus meng-update driver secara manual.
        - Lebih banyak konfigurasi.
        
        ---
        
        ## Playwright
        
        ```
        Python
           ↓
        Playwright
           ↓
        Browser
        ```
        
        Playwright menggunakan pendekatan yang lebih modern.
        
        Library Playwright dapat berkomunikasi langsung dengan browser menggunakan protokol yang sudah disediakan browser modern.
        
        Karena itu Playwright menjadi:
        
        - Lebih cepat.
        - Lebih stabil.
        - Tidak perlu mengelola ChromeDriver secara manual.
        
        ---
        
        # ⭐ Mengapa Banyak Perusahaan Menggunakan Playwright?
        
        Beberapa alasan utamanya adalah:
        
        ## 🚀 Auto Waiting
        
        Playwright akan menunggu element siap digunakan secara otomatis.
        
        Contoh:
        
        ```python
        page.click("button")
        ```
        
        Jika tombol belum siap, Playwright akan menunggu beberapa saat sebelum melakukan klik.
        
        Hal ini membuat test lebih stabil tanpa perlu sering menggunakan:
        
        ```python
        time.sleep()
        ```
        
        ---
        
        ## 🌍 Mendukung Banyak Browser
        
        Satu script dapat dijalankan pada beberapa browser:
        
        - Chromium
        - Firefox
        - WebKit
        
        Tanpa perlu mengubah kode automation.
        
        ---
        
        ## 👻 Headless Mode
        
        Browser dapat berjalan tanpa membuka tampilan (background).
        
        Mode ini sering digunakan pada:
        
        - CI/CD
        - Jenkins
        - GitHub Actions
        - Azure DevOps
        
        Karena lebih cepat dan hemat resource.
        
        ---
        
        ## ⚡ Performa Cepat
        
        Playwright memiliki performa yang lebih baik dibandingkan banyak framework automation sebelumnya karena menggunakan komunikasi yang lebih modern dengan browser.
        
        ---
        
        ## 💻 Multi Language Support
        
        Playwright tersedia dalam berbagai bahasa pemrograman sehingga konsep yang dipelajari tetap dapat digunakan meskipun nantinya berpindah bahasa.
        
        ---
        
        # 🔄 Flow Automation Playwright
        
        Hampir semua automation Playwright memiliki alur seperti berikut:
        
        ```
        Open Browser
              ↓
        Open Website
              ↓
        Find Element
              ↓
        Interaction
              ↓
        Assertion
              ↓
        Close Browser
        ```
        
        Walaupun project menjadi semakin besar, alur dasarnya hampir selalu sama.
        
        Yang berubah hanyalah detail implementasinya.
        
        ---
        
        # 📚 Istilah Penting
        
        ## 🌐 Browser
        
        Browser yang dikontrol oleh Playwright.
        
        Contohnya:
        
        - Chrome
        - Firefox
        - Edge
        - WebKit
        
        ---
        
        ## 👤 Context
        
        Context adalah **profil browser sementara**.
        
        Di dalam Context tersimpan data seperti:
        
        - Cookies
        - Session
        - Local Storage
        
        Setiap Context memiliki data yang terpisah sehingga dapat digunakan untuk mensimulasikan beberapa user yang login secara bersamaan.
        
        ---
        
        ## 📄 Page
        
        Page adalah tab browser.
        
        Satu Context dapat memiliki satu atau lebih Page.
        
        ---
        
        ## 🎯 Locator
        
        Locator digunakan untuk menemukan element pada halaman web.
        
        Contohnya:
        
        - Tombol Login
        - Input Username
        - Checkbox
        - Link
        
        Locator akan dipelajari lebih dalam pada materi berikutnya.
        
        ---
        
        ## 🖱️ Action
        
        Action adalah interaksi yang dilakukan terhadap element.
        
        Contohnya:
        
        - click()
        - fill()
        - hover()
        - check()
        
        ---
        
        ## ✅ Assertion
        
        Assertion digunakan untuk memastikan hasil sesuai dengan yang diharapkan.
        
        Contoh:
        
        - Halaman berhasil terbuka.
        - Text muncul.
        - Button terlihat.
        - URL berubah.
        
        ---
        
        # 💡 Analogi Browser, Context, dan Page
        
        ```
        Browser
        │
        ├── Context A
        │      ├── Page 1
        │      └── Page 2
        │
        └── Context B
               ├── Page 1
               └── Page 2
        ```
        
        Bayangkan seperti sebuah perpustakaan.
        
        - 🏢 Browser = Gedung perpustakaan
        - 🚪 Context = Ruang baca
        - 📖 Page = Buku yang sedang dibaca
        
        Setiap ruang baca memiliki barangnya sendiri (cookies, session, local storage), sehingga aktivitas di satu ruang tidak memengaruhi ruang lainnya.
        
        ---
        
        # 🧪 First Test
        
        Setelah Playwright berhasil diinstall, kita membuat test pertama:
        
        ```python
        from playwright.sync_api import sync_playwright
        
        def test_open_browser():
            with sync_playwright() as p:
                browser = p.chromium.launch(headless=False)
                page = browser.new_page()
        
                page.goto("<https://example.com>")
        
                browser.close()
        ```
        
        Test tersebut melakukan langkah berikut:
        
        1. Membuka Playwright.
        2. Menjalankan browser Chromium.
        3. Membuka tab baru.
        4. Mengunjungi website.
        5. Menutup browser.
        
        ---
        
        # ⭐ Best Practice
        
        - Gunakan **Sync API** ketika baru belajar Playwright.
        - Gunakan `with sync_playwright()` agar resource otomatis dibersihkan.
        - Gunakan `headless=False` saat belajar agar proses automation terlihat.
        - Setelah project masuk CI/CD, biasanya menggunakan `headless=True`.
        
        ---
        
        # 📝 Ringkasan
        
        - Playwright adalah framework automation browser buatan Microsoft.
        - Playwright menggunakan komunikasi modern sehingga tidak memerlukan ChromeDriver seperti Selenium.
        - Memiliki Auto Waiting yang membuat test lebih stabil.
        - Flow dasar automation adalah:
            - Open Browser
            - Open Website
            - Find Element
            - Interaction
            - Assertion
            - Close Browser
        - Struktur dasar Playwright terdiri dari Browser → Context → Page.
        
        ---
        
        # ⭐ Yang Harus Diingat
        
        - Playwright tidak hanya menggantikan Selenium, tetapi membawa pendekatan automation yang lebih modern.
        - Auto Waiting merupakan salah satu fitur paling penting yang membuat Playwright lebih stabil.
        - Browser, Context, dan Page adalah fondasi utama yang akan terus digunakan pada materi berikutnya.
        - Hampir seluruh automation Playwright merupakan pengembangan dari flow dasar yang telah dipelajari pada Hari 1.
    - Challenge
        
        # 🧠 Challenge - Playwright Hari 1
        
        ---
        
        # 🟢 Challenge 1
        
        ## ❓ Pertanyaan
        
        Mengapa Playwright dianggap lebih stabil dibanding Selenium?
        
        ✍️ Jawaban:
        
        ```
        - Playwright berkomunikasi langsung dengan browser menggunakan protokol modern.
        - Tidak memerlukan ChromeDriver seperti Selenium.
        - Memiliki Auto Waiting, sehingga banyak error karena elemen belum siap bisa dihindari.
        ```
        
        ---
        
        # 🟢 Challenge 2
        
        ## ❓ Susun Flow Automation berikut
        
        - Assertion
        - Open Browser
        - Close Browser
        - Open Website
        - Find Element
        - Interaction
        
        ✍️ Jawaban:
        
        ```
        1. Open Browser
        2. Open Website
        3. Find Element
        4. Interaction
        5. Assertion
        6. Close Browser
        ```
        
        ---
        
        # 🟢 Challenge 3
        
        ## ❓ Jelaskan dengan bahasamu sendiri
        
        Apa perbedaan antara:
        
        - Browser
        - Context
        - Page
        
        ✍️ Jawaban:
        
        ```
        1. Browser
        Aplikasi browser yang dikontrol Playwright.
        
        2. Context
        Profil browser sementara yang memiliki cookies, session, local storage, dan cache sendiri.
        
        3. Page
        Tab browser di dalam Context.
        ```
        
        ---
        
        # 🎯 Tujuan Challenge
        
        Setelah menyelesaikan challenge ini kamu diharapkan mampu:
        
        - ✅ Menjelaskan apa itu Playwright.
        - ✅ Memahami flow automation.
        - ✅ Memahami hubungan Browser, Context, dan Page.
- 2-Struktur Project
    - Materi
        
        # 📂 Playwright - Hari 1
        
        # Struktur Project Playwright
        
        ---
        
        # 🎯 Tujuan
        
        Sebelum membuat automation yang lebih kompleks, kita perlu memahami struktur project Playwright.
        
        Project automation yang baik tidak hanya berisi file test, tetapi juga dipisahkan berdasarkan fungsi agar mudah dibaca, dirawat, dan dikembangkan ketika jumlah test semakin banyak.
        
        ---
        
        # 📁 Struktur Project
        
        ```
        playwright/
        │
        ├── tests/
        ├── pages/
        ├── conftest.py
        ├── pytest.ini
        ├── pyproject.toml
        ├── README.md
        └── .venv/
        ```
        
        Mari kita bahas satu per satu.
        
        ---
        
        # 📁 tests/
        
        Folder ini digunakan untuk menyimpan semua file test.
        
        Contoh:
        
        ```
        tests/
        │
        ├── test_login.py
        ├── test_logout.py
        ├── test_profile.py
        ```
        
        Pytest akan otomatis mencari file yang memiliki nama seperti:
        
        ```
        test_*.py
        ```
        
        atau
        
        ```
        *_test.py
        ```
        
        Karena itu, penamaan file test sebaiknya mengikuti aturan tersebut.
        
        ### Fungsi
        
        - Menyimpan seluruh skenario pengujian.
        - Menjadi tempat Pytest mencari test yang akan dijalankan.
        
        ---
        
        # 📁 pages/
        
        Folder ini digunakan untuk menyimpan **Page Object Model (POM)**.
        
        Saat project masih kecil mungkin kita belum merasakan manfaatnya, tetapi ketika jumlah test mulai banyak, folder ini menjadi sangat penting.
        
        Misalnya tanpa POM:
        
        ```python
        page.locator("#username").fill("admin")
        page.locator("#password").fill("123456")
        page.locator("button").click()
        ```
        
        Kode tersebut bisa saja ditulis berulang kali di banyak file test.
        
        Dengan POM:
        
        ```python
        login_page.login("admin", "123456")
        ```
        
        Seluruh detail locator dan action disimpan di dalam folder `pages/`, sehingga test menjadi lebih bersih dan mudah dibaca.
        
        > Folder ini akan mulai kita gunakan saat mempelajari Page Object Model.
        
        ---
        
        # 📄 [conftest.py](http://conftest.py/)
        
        File ini digunakan untuk menyimpan **fixture** yang dapat dipakai oleh semua file test.
        
        Misalnya:
        
        - Browser
        - Context
        - Page
        - Login
        - Data test
        
        Daripada membuat fixture yang sama di setiap file, kita cukup membuatnya sekali di `conftest.py`.
        
        Dengan begitu seluruh test dapat menggunakannya kembali (reusable).
        
        ---
        
        # 📄 pytest.ini
        
        File ini digunakan untuk konfigurasi Pytest.
        
        Contohnya:
        
        - Register marker
        - Menentukan folder test
        - Konfigurasi Pytest lainnya
        
        Misalnya:
        
        ```
        [pytest]
        markers =
            smoke
            regression
        ```
        
        File ini membuat konfigurasi Pytest lebih rapi dan terpusat.
        
        ---
        
        # 📄 pyproject.toml
        
        Karena kita menggunakan **uv**, file ini menjadi pusat konfigurasi project.
        
        Di dalamnya terdapat:
        
        - Dependency
        - Development dependency
        - Konfigurasi tools
        - Informasi project
        
        Contoh:
        
        ```toml
        [dependency-groups]
        dev = [
            "pytest",
            "playwright"
        ]
        ```
        
        Saat menambahkan package menggunakan `uv add`, file ini akan diperbarui secara otomatis.
        
        ---
        
        # 📄 [README.md](http://readme.md/)
        
        README digunakan sebagai dokumentasi project.
        
        Biasanya berisi:
        
        - Penjelasan project
        - Cara install
        - Cara menjalankan test
        - Struktur project
        - Requirement
        
        README membantu anggota tim baru memahami project tanpa harus bertanya kepada developer lain.
        
        ---
        
        # 💡 Analogi
        
        Bayangkan project automation seperti sebuah kantor.
        
        ```
        🏢 Automation Project
        
        │
        
        ├── 📁 tests
        │      = Daftar pekerjaan
        
        ├── 📁 pages
        │      = Buku panduan kerja
        
        ├── 📄 conftest.py
        │      = Peralatan bersama
        
        ├── 📄 pytest.ini
        │      = Aturan kantor
        
        ├── 📄 pyproject.toml
        │      = Data administrasi
        
        └── 📄 README.md
               = Buku petunjuk
        ```
        
        Masing-masing memiliki tugasnya sendiri sehingga pekerjaan menjadi lebih teratur.
        
        ---
        
        # ⭐ Best Practice
        
        Gunakan nama folder:
        
        ```
        tests/
        ```
        
        bukan
        
        ```
        test/
        ```
        
        Karena hampir semua project Python menggunakan nama `tests/`.
        
        Selain lebih konsisten dengan dokumentasi Pytest, struktur ini juga lebih mudah dipahami oleh anggota tim lain.
        
        ---
        
        # 📝 Ringkasan
        
        - **tests/** → Menyimpan semua file test.
        - **pages/** → Menyimpan Page Object Model (POM).
        - [**conftest.py**](http://conftest.py/) → Menyimpan fixture yang dapat digunakan bersama.
        - **pytest.ini** → File konfigurasi Pytest.
        - **pyproject.toml** → Pusat konfigurasi project dan dependency.
        - [**README.md**](http://readme.md/) → Dokumentasi project.
        
        ---
        
        # ⭐ Yang Harus Diingat
        
        - Project automation yang baik dipisahkan berdasarkan tanggung jawab setiap file dan folder.
        - Jangan menaruh semua kode dalam satu file test.
        - Gunakan `tests/` sebagai folder utama untuk file test.
        - Folder `pages/` akan mulai digunakan saat mempelajari Page Object Model (POM).
        - `conftest.py` digunakan untuk menyimpan fixture yang dipakai bersama.
    - Challange
        
        # 🧠 Challenge - Playwright Hari 1 (Struktur Project)
        
        ---
        
        # 🟢 Challenge 1
        
        ## ❓ Pertanyaan
        
        Folder manakah yang digunakan untuk menyimpan semua file test?
        
        ✍️ Jawaban:
        
        ```
        folder untuk menyimpan semua file test adalah /test
        ```
        
        ---
        
        # 🟢 Challenge 2
        
        ## ❓ Pertanyaan
        
        Mengapa kita tidak menaruh semua locator langsung di dalam file test?
        
        ✍️ Jawaban:
        
        ```
        agar rapi dan enak untuk dimaintenance untuk pomnya, jadi ditaro di /page
        ```
        
        ---
        
        # 🟢 Challenge 3
        
        ## ❓ Pertanyaan
        
        Apa fungsi dari file berikut?
        
        - [conftest.py](http://conftest.py/)
        - pytest.ini
        - pyproject.toml
        - [README.md](http://readme.md/)
        
        ✍️ Jawaban:
        
        ```
        1. conftest.py -> untuk menyimpan semua fixture
        2. pytest.ini -> untuk menyimpan configurasi pytest
        3. pyproject.toml -> untuk menyimpan configurasi project
        4. README.md -> menyimpan catatan terkait project untuk public
        ```
        
        ---
        
        # 🟢 Challenge 4
        
        ## ❓ Pertanyaan
        
        Mengapa project automation dipisahkan menjadi beberapa folder, bukan semua file diletakkan dalam satu tempat?
        
        ✍️ Jawaban:
        
        ```
        supaya enak untuk development code dan maintenancenya
        ```
        
        ---
        
        # 🎯 Tujuan Challenge
        
        - Memahami struktur project Playwright.
        - Mengetahui fungsi setiap folder dan file.
        - Memahami alasan penggunaan struktur project yang rapi.