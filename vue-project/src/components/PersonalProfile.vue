<script>
</script>

<template>
    <header>
        <nav>
            <ul class="navbar">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About Me</a></li>
                <li><a href="#education">Education & Achievements</a></li>
                <li><a href="#experience">IT Experience</a></li>
                <li><a href="#hobbies">Hobbies & Interests</a></li>
                <li><a href="#goals">Goals & Dreams</a></li>
                <li><a href="#gallery">Photo Gallery</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home" class="section">
            <h1>Kon'nichiwa, my name is Tracie</h1>
            <p>I am from BSIT-MI231</p>
            <p>Currently pursuing a Bachelor of Science in Information Technology at Asia Pacific College, Makati City, Philippines.</p>
        </section>

        <section id="about" class="section">
            <h2>About Me</h2>
            <p>I am Tracie Cañas Tomon. Currently in my second year of pursuing a Bachelor of Science in Information Technology, with a specialization in Mobile and Internet Technology. People call me Trace, Tres or Trai. Some of my relatives call me Budang, like the Buddha, because I looked like the Buddha when I was born. Any shade of blue is my fave color. I like keeping things neat and tidy. Depending on my mood, I can be a bit of an introvert or an extrovert. I am committed to becoming a skilled IT professional, driven by my passion for technology and continuous learning.</p>
        </section>

        <section id="education" class="section">
            <h2>Education & Achievements</h2>
            <h3>College</h3>
            <p><strong>Asia Pacific College</strong><br>Bachelor of Science in Information Technology with specialization in Mobile and Internet Technology<br>August 2023 - Present<br>Dean's Lister AY 2023-2024<br>Class Representative (SoCIT Leads) 2023 - Present<br>Member of Microsoft Community (MSC) 2023 - Present</p>
            <p><strong>Southern Leyte State University</strong><br>Bachelor of Secondary Education major in General Science<br>August 2019 - 2021</p>

            <h3>Senior High School</h3>
            <p><strong>Saint Thomas Aquinas College</strong><br>Academic Track: Accountancy, Business, and Management<br>June 2017 - March 2019<br>Associate Editor-in-Chief of The TORCH (School Publication)<br>ABM Achiever<br>Graduated with High Honors</p>

            <h3>Junior High School</h3>
            <p><strong>Libas National High School</strong><br>Grade 9 - 10<br>SY 2015 - 2017<br>SSC President (2016-2017)<br>Completed Junior High as Class Valedictorian</p>
            <p><strong>Cesar C. Tan Memorial National High School</strong><br>Grade 7 - 8<br>SY 2013 - 2015<br>Consistent honor student</p>
        </section>

        <section id="experience" class="section">
            <h2>IT Experience</h2>
            <ul>
                <li>🚀 Designed the user interface for a mobile application project using Android Studio</li>
                <li>🎨 Created captivating interfaces and delightful user experiences for websites and mobile apps in a UI/UX Design and Programming course</li>
                <li>💻 Developed a detailed ERD in MySQL for a local shoe restoration business</li>
                <li>🛠️ Gained hands-on experience coding in Python and Java during the first year</li>
                <li>📞 Assisted customers with basic troubleshooting on their devices as a customer service representative</li>
            </ul>
        </section>

        <section id="hobbies" class="section">
            <h2>Hobbies & Interests</h2>
            <ul>
                <li>🎬 Diving into the world of entertainment with English movies, TV shows, Korean and Chinese dramas, and anime movies and series</li>
                <li>📚 Getting lost in the pages of manga and novels, with a special fondness for Paulo Coelho's masterpieces like The Alchemist</li>
                <li>🎤 Singing my heart out during karaoke sessions in my free time</li>
                <li>📺 Absorbing knowledge from documentaries about history, murder, and real-life crime stories</li>
                <li>🌟 Being captivated by people’s life stories, achievements, and experiences</li>
                <li>🧹 Finding joy in cleaning and organizing my stuff and room</li>
            </ul>
        </section>

        <section id="goals" class="section">
            <h2>Goals & Dreams</h2>
            <ul>
                <li>🎓 My ultimate goal is to graduate from this course by 2027, ideally with Latin honors, despite my unconventional journey.</li>
                <li>🌟 I aspire to secure a well-paying job with a healthy working environment. I aim to leverage my skills to make meaningful contributions in the IT field, financially support my family, and repay those who have helped me.</li>
                <li>📚 I am committed to continuous learning, collaborating with people worldwide, and developing solutions to modern problems to grow my IT career.</li>
                <li>🤝 I aspire to aid the less fortunate, honor my parents' sacrifices, and eventually gain recognition for my achievements.</li>
                <li>🏡 I don’t seek luxury, but a decent, comfortable life where I have everything I need.</li>
                <li>🌍 As an avid anime fan, I dream of traveling to anime landmarks and attending concerts of my favorite K-pop group, 2NE1, and artists like Bruno Mars.</li>
                <li>✈️ I also dream of traveling the world with my family and loved ones. These ambitions drive my dedication to study and strive for success.</li>
            </ul>
        </section>

        <section id="gallery" class="section">
            <h2>Photo Gallery</h2>
            <div class="gallery-container">
                <div class="gallery">
                    <img src="photo1.jpg" alt="Gallery Photo 1">
                </div>
                <div class="gallery">
                    <img src="photo2.jpg" alt="Gallery Photo 2">
                </div>
                <div class="gallery">
                    <img src="photo3.jpg" alt="Gallery Photo 3">
                </div>
            </div>
        </section>
    </main>

    <footer>
        <p>© 2025 Tracie Cañas Tomon. All rights reserved.</p>
    </footer>
</template>

<style>

body {
    font-family: "Proxima Nova Medium", sans-serif;
    margin: 0;
    padding: 0;
    background-color: #AFDBF5;
    color: #ffffff;
    line-height: 1.6;
}

a {
    text-decoration: none;
    color: #ADD8E6;
    transition: color 0.3s ease;
}

a:hover {
    color: #ffffff;
}

ul {
    list-style-type: none;
    padding: 0;
}

h1, h2, h3 {
    margin-top: 0;
}


header {
    background-color: #1F305E;
    padding: 20px;
    text-align: center;
}

.navbar {
    display: flex;
    justify-content: center;
    gap: 15px;
    padding: 0;
}

.navbar li {
    list-style: none;
}

.navbar a {
    font-size: 16px;
    padding: 10px 15px;
    border-radius: 5px;
    background-color: #3A5BA0;
    transition: background-color 0.3s ease;
}

.navbar a:hover {
    background-color: #5C7BBC;
}

.section {
    margin: 20px;
    padding: 20px;
    background-color: #1F305E;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.section h1, .section h2 {
    text-align: center;
    color: #FFD700;
}

footer {
    text-align: center;
    padding: 15px;
    background-color: #1F305E;
    position: relative;
    bottom: 0;
    width: 100%;
}
</style>
