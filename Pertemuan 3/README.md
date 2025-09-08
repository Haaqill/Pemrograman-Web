# Source Code Pertemuan 3
### Tabel
```html
<!DOCTYPE html>
<html>
<body>
    <table border="1" bgcolor="white" align="center">
        <caption align="top"><b>Tabel Daftar Nilai Mahasiswa</b></caption>
        <tr bgcolor = "gray"><th rowspan="2">No</th><th rowspan="2">NPM</th><th rowspan="2">Nama</th><th colspan="2">Nilai</th></tr>
        <tr bgcolor = "gray"><th>UTS</th><th>UAS</th></tr>
        <tr>
            <td align="center" width="20">1</td>
            <td valign="middle" width="80" heigth="40">06.100.001</td>
            <td valing="middle" width="180" height="40">Amin A. Angkasa</td>
            <td align="center">70</td>
            <td align="center">80</td>
        </tr>
        <tr>
            <td align="center" width="20">2</td>
            <td valign="middle" width="80" heigth="40">06.100.002</td>
            <td valing="middle" width="180" height="40">Beni B. Bernardi</td>
            <td align="center">70</td>
            <td align="center">80</td>
        </tr>
    </table>


</body>
</html>
```

### Form
```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            body {
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
                color: #4caf50;
                margin-bottom: 20px;
            }

            label {
                display: block;
                margin-bottom: 5px;
                color: #555;
                font-weight: bold;
            }

            input[type="text"],input[type="email"],input[type="password"],select{
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
                background-color: #4caf50;
                color: "white";
                cursor: pointer;
                width: 100%;
                font-size: 16px;
            }
        </style>        
    </head>

    <body>
        <div class="main">
            <h2>Registeration Form</h2>
            <form action=""> 
                <label for="first">First Name:</label>
                <input type="text" id="first" name="first" required/>
                <label for="last">Last Name:</label>
                <input type="text" id="last" name="last" required/>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email"required/>
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required/>
                <label for="repassword">Re-type Password:</label>
                <input type="password" id="repassword" name="repassword" required/>
                <label for="mobile">Contact:</label>
                <input type="text" id="mobile" name="mobile" maxlength="10" required/>
                <label for="gender">Gender:</label>
                <select id="gender" name="gender" required>
                    <option value="male">Male</option>
                    <option value="female">Female</option>
                    <option value="other">Other</option>
                </select>
                <button type="submit">Submit</button>
            </form>
        </div>
    </body>
</html>
```

### Frame
```html
<!DOCTYPE html>
<html>
    <head>

    </head>
    <frameset rows="20%,5%,65%,10%">
        <frame name="menu" src="menu.html">
            <frame name="navbar" src="navbar.html">
                <frameset cols="25%,*">
                    <frame name="sidebar" src="sidebar.html">
                        <frame name="content" src="tabel.html">
                </frameset>
                <frame name="footer" src="footer.html">
    </frameset>

</html>
```
