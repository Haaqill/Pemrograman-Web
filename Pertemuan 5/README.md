# Source Code Pertemuan 5

### Form Registerasi
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Form registerasi</title>

        <style>
            body {
                font-family: Arial, Helvetica, sans-serif;
                margin: 0;
                padding: 0;
                display: flex;
                justify-content: center;
                align-items: center ;
                height: 100vh;
            }

            
            .main {
                background-color: #fff;
                border-radius: 15px;
                box-shadow: 0 0 20px rgba(0,0,0,0.2);
                padding: 20px;
                width: 500px;
            }
            
            .main h2 {
                color: blue;
                margin-bottom: 20px;
            }

            label {
                display: block;
                margin-bottom: 5px;
                color: #555;
                font-weight: bold;
            }

            input[type="text"],input[type="number"]{
                width: 100%;
                margin-bottom: 15px;
                padding: 10px;
                box-sizing: border-box;
                border: 1px solid #ddd;
                border-radius: 5px;
            }

            button[type="submit"] {
                padding: 15px;
                border-radius: 10px;
                border: none;
                background-color: blue;
                color: white;
                cursor: pointer;
                width: 100%;
                font-size: 16px;
            }
            
            .suggestions {
                border: 1px solid #ccc;
                max-height: 150px;
                overflow-y: auto;
                position: absolute;
                background: white;
                width: 200px;
            }

            .suggestions div {
                padding: 8px;
                cursor: pointer;
            }

            .suggestions div:hover {
                background: #eee;
            }
        </style>
    </head>
    <body>
        <div class="main">
            <h2>Registeration Form</h2>
            <form action=""> 
                <label for="nama">Nama:</label>
                <input type="text" id="nama" name="nama" required/>

                <label for="nim">NIM:</label>
                <input type="number" id="nim" name="nim" required/>
                
                <label for="matkul">Mata kuliah:</label>
                <input type="text" id="matkul" name="matkul"required/>
                <div id="suggestion" class="suggestion"></div>                   
                <script type="text/javascript">
                    const matkul = ["Pemrograman Web","Pemrograman Berbasis Objek", "Jaringan Komputer", "Teori Graf", 
                    "Matematika Diskrit", "Konsep Pengembangan Perangkat Lunak", "Konsep Kecerdasan Artifisial"];
                    
                    const input_mk = document.getElementById("matkul");
                    const suggestion_mk = document.getElementById("suggestion");
                    
                    input_mk.addEventListener("input", () => {
                        const query = input_mk.value.toLowerCase();
                        suggestionBox.innerHTML = "";
                        
                        if (query) {
                            const filtered = matkul.filter(f => f.toLowerCase().includes(query));
                            filtered.forEach(f => {
                                const div = document.createElement("div");
                                div.textContent = f;
                                div.addEventListener("click", () => {
                                    input_mk.value = f;
                                    suggestionBox.innerHTML = "";
                                });
                                suggestionBox.appendChild(div);
                            });
                        }
                    })
                </script>

                <label for="dosen">Nama dosen</label>
                <input type="text" id="dosen" name="dosen" required/>
                <div id="suggestion" class="suggestion"></div>
                <script type="text/javascript">
                    const dosen = ["Pak Fajar", "Pak Baskoro", "Pak Irfan", "Pak Aldinata", "Pak Roy", "Bu Sarwo", "Pak Rully"];
                    
                    const input_dosen = document.getElementById("dosen");
                    const suggestionBox = document.getElementById("suggestion");
                    
                    input_dosen.addEventListener("input", () => {
                        const query = input_dosen.value.toLowerCase();
                        suggestionBox.innerHTML = "";
                        
                        if (query) {
                            const filtered = dosen.filter(f => f.toLowerCase().includes(query));
                            filtered.forEach(f => {
                                const div = document.createElement("div");
                                div.textContent = f;
                                div.addEventListener("click", () => {
                                    input_dosen.value = f;
                                    suggestionBox.innerHTML = "";
                                });
                                suggestionBox.appendChild(div);
                            });
                        }
                    })
                </script>

                
                <button type="submit">Submit</button>
            </form>
        </div>
    </body>
</html>
```

### Pencarian Kode Pos
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Pencarian kode pos</title>
        <style>
            body {
                font-family: Arial, Helvetica, sans-serif;
                margin: 0;
                padding: 0;
                display: flex;
                justify-content: center;
                align-items: center ;
                height: 100vh;
            }

            
            .main {
                background-color: #fff;
                border-radius: 15px;
                box-shadow: 0 0 20px rgba(0,0,0,0.2);
                padding: 20px;
                width: 500px;
            }

            label {
                display: block;
                margin-bottom: 5px;
                color: #555;
                font-weight: bold;
            }

            select{
                width: 100%;
                margin-bottom: 15px;
                padding: 10px;
                box-sizing: border-box;
                border: 1px solid #ddd;
                border-radius: 5px;
            }

            button{
                padding: 15px;
                border-radius: 10px;
                border: none;
                background-color: blue;
                color: white;
                cursor: pointer;
                width: 100%;
                font-size: 16px;
            }

            .modal {
                display: none;
                position: fixed;
                top: 0; left: 0; right: 0; bottom: 0;
                background: rgba(0,0,0,0.5);
                justify-content: center;
                align-items: center;
            }
            .modal-content {
                background: white;
                padding: 20px;
                border-radius: 8px;
                min-width: 300px;
            }
            .close {
                float: right;
                cursor: pointer;
                font-weight: bold;
            }
        </style>        
    </head>
    <body>
        <div class="main">

            <label for="provinsi">Provinsi</label>
            <select name="provinsi" id="provinsi">
                <option value=""></option>
                <option value="jatim">Jawa Timur</option>
                <option value="kaltim">Kalimantan Timur</option>
            </select>
            
            <label for="kotaKab">Kota/Kabupaten</label>
            <select name="kotaKab" id="kotaKab">
                <option value=""></option>
            </select>
            <script type="text/javascript">
                const options_kk = {
                    jatim: ["Ponorogo", "Surabaya"],
                    kaltim: ["Balikpapan", "Samarinda"]
                };

                const pilih_prov = document.getElementById("provinsi");
                const pilih_kotaKab = document.getElementById("kotaKab");

                pilih_prov.addEventListener("change", () => {
                    const prov = pilih_prov.value;

                    pilih_kotaKab.innerHTML = "<option value=''></option>";

                    if(prov && options_kk[prov]){
                        options_kk[prov].forEach( kk => {
                            const option = document.createElement("option");
                            option.value = kk;
                            option.textContent = kk;
                            pilih_kotaKab.appendChild(option);
                        });
                    }
                });
            </script>

            <label for="kecamatan">Kecamatan</label>
            <select name="kecamatan" id="kecamatan">
                <option value=""></option>
            </select>
            <script type="text/javascript">
                const options_kec = {
                    Ponorogo: ["Badegan", "Jenangan", "Kauman"],
                    Surabaya: ["Sukolilo", "Rungkut", "Mulyorejo"],
                    Balikpapan: ["Balikpapan Timur", "Balikpapan Barat", "Balikpapan Utara"],
                    Samarinda: ["Samarinda Ulu", "Samarinda Seberang", "Palaran"]
                };

                const pilih_kk = document.getElementById("kotaKab");
                const pilih_kec = document.getElementById("kecamatan");

                pilih_kk.addEventListener("change", () => {
                    const kk = pilih_kk.value;

                    pilih_kec.innerHTML = "<option value=''></option>";

                    if(kk && options_kec[kk]){
                        options_kec[kk].forEach( kec => {
                            const option = document.createElement("option");
                            option.value = kec;
                            option.textContent = kec;
                            pilih_kec.appendChild(option);
                        });
                    }
                });
            </script>
        
            <button id="submit">Submit</button>
            <div id="popup" class="modal">
                <div class="modal-content">
                    <span id="closeBtn" class="close">&times;</span>
                    <p id="popupText"></p>
                </div>
            </div>

            <script type="text/javascript">
                const info = {
                    "Samarinda Ulu": "Kode posnya adalah 75122 - 75128",
                    "Samarinda Seberang": "Kode posnya adalah 75131 - 75133",
                    Palaran: "Kode posnya adalah 75241 - 75253",
                    Sukolilo: "Kode posnya adalah 60111 - 60119",
                    Rungkut: "Kode posnya adalah 60293 - 60298",
                    Mulyorejo: "Kode posnya adalah 60112 - 60116",
                    Badegan: "Kode posnya adalah 63455",
                    Jenangan: "Kode posnya adalah 63492",
                    Kauman: "Kode posnya adalah 63451",
                    "Balikpapan Timur": "Kode posnya adalah 76116 - 76118",
                    "Balikpapan Barat": "Kode posnya adalah 76131 - 76134",
                    "Balikpapan Utara": "Kode posnya adalah 76125 - 76136"
                };

                const select = document.getElementById("kecamatan");
                const submitBtn = document.getElementById("submit");
                const popup = document.getElementById("popup");
                const popupText = document.getElementById("popupText");
                const closeBtn = document.getElementById("closeBtn");

                submitBtn.addEventListener("click", () => {
                    const choice = select.value;
                    if (choice && info[choice]) {
                        popupText.textContent = info[choice];
                        popup.style.display = "flex";
                    } else {
                        alert("Please select an item first!");
                    }
                    });

                    closeBtn.addEventListener("click", () => {
                        popup.style.display = "none";
                    });

                    window.addEventListener("click", (e) => {
                        if (e.target === popup) {
                            popup.style.display = "none";
                        }
                });
            </script>

        </div>
    </body>
</html>
```

### List Dropdown Dinamis
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Dynamic Drop Down Menu</title>
        <style>
            body {
                font-family: Arial, Helvetica, sans-serif;
                margin: 0;
                padding: 0;
                display: flex;
                justify-content: center;
                align-items: center ;
                height: 100vh;
            }

            
            .main {
                background-color: #fff;
                border-radius: 15px;
                box-shadow: 0 0 20px rgba(0,0,0,0.2);
                padding: 20px;
                width: 500px;
            }
            
            .main h2 {
                color: blue;
                margin-bottom: 20px;
            }

            label {
                display: block;
                margin-bottom: 5px;
                color: #555;
                font-weight: bold;
            }

            select{
                width: 100%;
                margin-bottom: 15px;
                padding: 10px;
                box-sizing: border-box;
                border: 1px solid #ddd;
                border-radius: 5px;
            }

        </style>        
    </head>

    <body>
        <div class="main">
            <h2>Dynamic Drop Down List</h2>
            <label for="jenis">Jenis produk</label>
            <select name="jenis" id="jenis">
                <option value="">-- Pilih jenis produk --</option>
                <option value="desktop">Desktop</option>
                <option value="laptop">Laptop</option>
                <option value="smartphone">Smartphone</option>
            </select>

            <label for="merk">Merk produk</label>
            <select name="merk" id="merk">
                <option value="">-- Pilih merk produk --</option>
            </select>

            <script type="text/javascript">
                const options = {
                    desktop: ["Apple", "Asus", "Dell", "Lenovo", "MSI", "Xiaomi"],
                    laptop: ["Asus", "Lenovo", "Acer", "HP", "Dell", "MSI"],
                    smartphone: ["Asus", "Samsung", "Iphone", "Vivo", "Oppo", "Xiaomi"]
                };

                const pilihJenis = document.getElementById("jenis");
                const pilihMerk = document.getElementById("merk");

                pilihJenis.addEventListener("change", () => {
                    const jenis = pilihJenis.value;

                    pilihMerk.innerHTML = "<option value=''>-- Pilih merk produk --</option>"; 
                    if(jenis && options[jenis]){
                        options[jenis].forEach(merk => {
                            const option = document.createElement("option");
                            option.value = merk;
                            option.textContent = merk;
                            pilihMerk.appendChild(option);
                        });
                    }
                });
            </script>
        </div>
    </body>
</html>
```
