import streamlit as st

st.set_page_config(
    page_title="For You ❤️",
    page_icon="💌",
    layout="centered",
    initial_sidebar_state="collapsed"
)

# Clean look - hide Streamlit menu and footer
hide_style = """
    <style>
        #MainMenu {visibility: hidden;}
        footer {visibility: hidden;}
        header {visibility: hidden;}
        .stApp {
            background: linear-gradient(180deg, #fce7f3, #fdf2f8);
        }
    </style>
"""
st.markdown(hide_style, unsafe_allow_html=True)

# Full HTML + CSS + JS for the beautiful envelope + flip card (mobile friendly)
html_code = """
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>For You ❤️</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css">
    <script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400&display=swap');
        
        body { font-family: 'Poppins', sans-serif; background: linear-gradient(to bottom, #fce7f3, #fdf2f8); }
        .title-font { font-family: 'Playfair Display', serif; }

        .envelope {
            width: 320px;
            height: 220px;
            margin: 40px auto;
            position: relative;
            cursor: pointer;
            filter: drop-shadow(0 20px 25px rgba(0,0,0,0.15));
        }
        .envelope .back {
            position: absolute;
            width: 100%;
            height: 100%;
            background: #f8d7e8;
            border-radius: 12px;
        }
        .envelope .flap {
            position: absolute;
            width: 100%;
            height: 55%;
            background: #f8d7e8;
            top: 0;
            border-radius: 12px 12px 0 0;
            transform-origin: top;
            transition: transform 0.9s cubic-bezier(0.6, 0, 0.4, 1);
            z-index: 3;
            box-shadow: 0 8px 15px rgba(0,0,0,0.2);
        }
        .envelope.open .flap {
            transform: rotateX(-165deg);
        }
        .envelope .card {
            position: absolute;
            width: 92%;
            height: 82%;
            background: white;
            top: 11%;
            left: 4%;
            border-radius: 14px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.18);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 1.1s cubic-bezier(0.34, 1.56, 0.64, 1);
            z-index: 2;
        }
        .envelope.open .card {
            transform: translateY(-95px) scale(1.08);
        }

        .heart {
            position: absolute;
            font-size: 28px;
            animation: floatHeart 4.5s ease-in-out forwards;
            z-index: 10;
            pointer-events: none;
        }
        @keyframes floatHeart {
            0% { transform: translateY(100px) rotate(0deg); opacity: 0; }
            30% { opacity: 1; }
            100% { transform: translateY(-500px) rotate(720deg); opacity: 0; }
        }
    </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4">
    <div class="max-w-md w-full">

        <!-- Envelope -->
        <div id="envelope-screen" class="text-center">
            <div id="envelope" class="envelope" onclick="openEnvelope()">
                <div class="back"></div>
                <div class="flap"></div>
                <div class="card">
                    <div class="text-center">
                        <div class="text-7xl mb-4">💌</div>
                        <p class="text-pink-600 text-xl font-light">Tap to open my heart for you...</p>
                    </div>
                </div>
            </div>
            <p class="mt-10 text-pink-500 text-lg">A little surprise made just for you ❤️</p>
        </div>

        <!-- Card with swipeable pages -->
        <div id="card-screen" class="hidden flex-col items-center">
            <audio id="loveSong" preload="auto">
                <source src="https://www.dropbox.com/scl/fi/hbzvkjyu89xxqvyh65qbl/WhatsApp-Audio-2026-04-21-at-00.37.27.mpeg?rlkey=fqi951dsmqod8cicfvb33c4as&st=prbnenc3&dl=1" type="audio/mpeg">
            </audio>

            <div class="bg-white rounded-3xl shadow-2xl p-8 w-full max-w-[340px]">
                <div class="text-center mb-8">
                    <h1 class="title-font text-4xl text-pink-600">To: <span id="her-name">Her Name</span> ❤️</h1>
                    <p class="text-pink-400 mt-1">From Max • April 2026</p>
                </div>

                <div class="swiper mySwiper" id="swiper">
                    <div class="swiper-wrapper" id="slides"></div>
                    <div class="swiper-pagination mt-6"></div>
                </div>
            </div>

            <button onclick="window.location.reload()" 
                    class="mt-8 text-pink-400 hover:text-pink-600 text-sm flex items-center gap-2">
                ❤️ Open the envelope again
            </button>
        </div>
    </div>

    <script>
        const pages = [
            {title: "1", text: "Uhhhhhh 💕"},
            {title: "2", text: "I.... Mereko nahi samajh rha kya likhu"},
            {title: "3", text: "Aap cute ho"},
            {title: "4", text: "Aap gussana bhi cute hai"},
            {title: "5", text: "Mana raha hu dekho ✨"},
            {title: "6", text: "Ye line likhna zyada hard hai yr baaki se"},
            {title: "7", text: "I love you"},
            {title: "8", text: "Kissi le lo virtually ❤️"}
        ];

        function createSlides() {
            const container = document.getElementById("slides");
            container.innerHTML = "";
            pages.forEach(p => {
                const slide = document.createElement("div");
                slide.className = "swiper-slide flex flex-col items-center justify-center text-center min-h-[260px] px-4";
                slide.innerHTML = `
                    <div class="text-6xl mb-6">💖</div>
                    <h2 class="title-font text-2xl text-pink-700 mb-4">${p.title}</h2>
                    <p class="text-gray-700 leading-relaxed text-[17px]">${p.text}</p>
                `;
                container.appendChild(slide);
            });
        }

        function openEnvelope() {
            document.getElementById("envelope").classList.add("open");

            setTimeout(() => {
                document.getElementById("envelope-screen").classList.add("hidden");
                const cardScreen = document.getElementById("card-screen");
                cardScreen.classList.remove("hidden");
                cardScreen.classList.add("flex");

                // Play the song
                const song = document.getElementById("loveSong");
                song.play().catch(() => {});

                // Create pages and start swiper
                createSlides();
                new Swiper("#swiper", {
                    effect: "flip",
                    grabCursor: true,
                    pagination: { el: ".swiper-pagination", clickable: true },
                    loop: false
                });

                // Floating hearts
                for (let i = 0; i < 30; i++) {
                    setTimeout(() => {
                        const heart = document.createElement("div");
                        heart.className = "heart";
                        heart.textContent = "❤️";
                        heart.style.left = Math.random() * 100 + "vw";
                        heart.style.animationDuration = (3 + Math.random() * 3) + "s";
                        document.body.appendChild(heart);
                        setTimeout(() => heart.remove(), 8000);
                    }, i * 70);
                }
            }, 700);
        }

        // Replace these with your real info
        window.onload = () => {
            document.getElementById("Sneha").textContent = "Sneha Chudail";   // ← CHANGE TO HER NAME
        };
    </script>
</body>
</html>
"""

st.components.v1.html(html_code, height=820, scrolling=False)

st.caption("💌 Made with so much love — just for you")
