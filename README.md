DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Untuk Kamu ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{
    background:linear-gradient(135deg,#ff9a9e,#fad0c4);
    min-height:100vh;
    overflow:hidden;
}

.page{
    display:none
    min-height:100vh;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    text-align:center;
    padding:30px;
}

.active{
    display:flex;
}

.card{
    background:white;
    padding:30px;
    border-radius:25px;
    max-width:700px;
    box-shadow:0 10px 30px rgba(0,0,0,.2);
}

h1{
    margin-bottom:20px;
    color:#ff4d6d;
}

p{
    font-size:1.1rem;
    line-height:1.7;
}

.btn-area{
    margin-top:30px;
}

button{
    padding:12px 30px;
    border:none;
    border-radius:50px;
    cursor:pointer;
    font-size:18px;
    margin:10px;
    transition:.3s;
}

.yes{
    background:#ff4d6d;
    color:white;
}

.no{
    background:#666;
    color:white;
    position:absolute;
}

.gift{
    font-size:100px;
    animation:float 2s infinite alternate;
}

.bucket{
    font-size:90px;
    margin-top:10px;
}

img{
    width:280px;
    border-radius:20px;
    margin-top:20px;
    box-shadow:0 5px 20px rgba(0,0,0,.3);
}

@keyframes float{
    from{transform:translateY(0);}
    to{transform:translateY(-15px);}
}
</style>
</head>
<body>

<!-- PAGE 1 -->
<div class="page active" id="page1">
    <div class="card">
        <h1>Haii Cantikk ❤️</h1>

        <p>
            Sepertinya dah lama kita kenal.
            Udah 4 bulan kita kenal bahkan deket hehehehe.
            Sepertinya aku mau deh kasih status buat kita.
            Masakk sihh kamu ku gantung terus,
            jadi kamu mau ngga kita upgrade status kita?
        </p>

        <div class="btn-area">
            <button class="yes" onclick="nextPage(2)">Iya</button>
            <button class="no" id="no1">Tidak</button>
        </div>
    </div>
</div>

<!-- PAGE 2 -->
<div class="page" id="page2">
    <div class="card">
        <h1>💖 Will You Be My Girlfriend? 💖</h1>

        <div class="btn-area">
            <button class="yes" onclick="nextPage(3)">IYAAA</button>
            <button class="yes" onclick="nextPage(3)">Mauuu Banget</button>
            <button class="no" id="no2" style="font-size:10px;padding:5px 10px;">tidak</button>
        </div>
    </div>
</div>

<!-- PAGE 3 -->
<div class="page" id="page3">
    <div class="card">
        <h1>YEEEEY ❤️</h1>

        <p>
            Karena kamu sudah menerimanya nih ku kasih...
        </p>

        <div class="gift">❤️</div>
        <div class="bucket">💐</div>

        <h3 style="margin-top:20px;">
            Semoga kita bisa terus bersama yaa ✨
        </h3>

        <!-- FOTO KALIAN -->
        <img src="1000009141.jpg" alt="Foto Kita Berdua">
    </div>
</div>

<script>

function nextPage(page){
    document.querySelectorAll('.page').forEach(p=>{
        p.classList.remove('active');
    });

    document.getElementById('page'+page).classList.add('active');
}

function moveButton(btn){
    const maxX = window.innerWidth - btn.offsetWidth - 20;
    const maxY = window.innerHeight - btn.offsetHeight - 20;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    btn.style.left = x + 'px';
    btn.style.top = y + 'px';

    let size = parseFloat(getComputedStyle(btn).fontSize);
    if(size > 6){
        btn.style.fontSize = (size - 1) + 'px';
        btn.style.padding = '3px 6px';
    }
}

const no1 = document.getElementById("no1");
const no2 = document.getElementById("no2");

["mouseover","touchstart","click"].forEach(event=>{
    no1.addEventListener(event,function(e){
        e.preventDefault();
        moveButton(no1);
    });

    no2.addEventListener(event,function(e){
        e.preventDefault();
        moveButton(no2);
    });
});

moveButton(no1);
moveButton(no2);

</script>

</body>
</html>
