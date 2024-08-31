# index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>By Buckley - Innovative Digital Teaching Resources</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/ScrollToPlugin.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/ScrollMagic.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/plugins/animation.gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/kute.js/2.2.4/kute.min.js"></script>
    <style>
        /* Hide scrollbar for all browsers */
        html, body {
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        html::-webkit-scrollbar, body::-webkit-scrollbar {
            display: none;
        }
        body {
            background-color: #1a1c20;
            color: #ffffff;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        .progress-container {
            position: fixed;
            top: 0;
            right: 0;
            width: 5px;
            height: 100%;
            background-color: rgba(255, 255, 255, 0.2);
            z-index: 1000;
        }
        .progress-bar {
            width: 100%;
            background-color: #4299e1;
            height: 0;
            transition: height 0.1s ease;
        }
        .sticky-index {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            background-color: rgba(0, 0, 0, 0.8);
            padding: 10px 20px;
            display: none;
            text-align: center;
            transition: background-color 0.5s ease;
        }
        .sticky-index a {
            display: inline-block;
            color: white;
            text-decoration: none;
            margin: 0 15px;
            font-size: 16px;
            transition: color 0.3s ease;
        }
        .sticky-index a:hover {
            color: #4299e1;
        }
        .section {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem;
            background-attachment: fixed;
            background-position: center;
            background-repeat: no-repeat;
            background-size: 200% 200%;
            animation: gradientShift 15s ease infinite;
        }
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        #welcome { background-image: linear-gradient(45deg, #0f1114, #1a1c20, #0f1114); }
        #about { background-image: linear-gradient(45deg, #1a1c20, #23262d, #1a1c20); }
        #resources { background-image: linear-gradient(45deg, #23262d, #2c3039, #23262d); }
        #ai { background-image: linear-gradient(45deg, #2c3039, #353946, #2c3039); }
        #unit-designs { background-image: linear-gradient(45deg, #353946, #3e4252, #353946); }
        #robotics { background-image: linear-gradient(45deg, #3e4252, #474c5f, #3e4252); }
        #vr-ar { background-image: linear-gradient(45deg, #474c5f, #50566b, #474c5f); }
        h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
        }
        h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }
        p {
            font-size: 1.5rem;
            max-width: 600px;
        }
        .reveal-svg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .morph-container {
            position: relative;
            width: 300px;
            height: 300px;
            margin-top: 2rem;
        }
        .cta-button {
            display: inline-block;
            margin-top: 2rem;
            padding: 1rem 2rem;
            background-color: #4299e1;
            color: #ffffff;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: background-color 0.3s ease;
        }
        .cta-button:hover {
            background-color: #3182ce;
        }
        .video-container {
            position: relative;
            width: 80%;
            max-width: 600px;
            margin: 2rem auto;
        }
        .video-frame {
            position: absolute;
            top: -10px;
            left: -10px;
            width: calc(100% + 20px);
            height: calc(100% + 20px);
            z-index: 1;
        }
        .video-player {
            position: relative;
            width: 100%;
            height: 0;
            padding-bottom: 56.25%; /* 16:9 aspect ratio */
            z-index: 2;
        }
        .video-player iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        #vr-ar {
    background-image: linear-gradient(45deg, #2d1b4e, #1a0f2e, #3d2b5f, #2d1b4e);
    background-size: 400% 400%;
    animation: gradientShift 15s ease infinite;
    flex-direction: row; /* Ensure horizontal layout */
    justify-content: space-between;
    align-items: center;
    padding: 4rem;
}

.vr-ar-content {
    flex: 0 0 60%;
    max-width: 60%;
    text-align: left;
    padding-right: 4rem;
}

.vr-ar-image {
    flex: 0 0 40%;
    max-width: 40%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.vr-ar-image-container {
    position: relative;
    width: 100%;
    max-width: 400px;
}

.vr-ar-image-background {
    position: absolute;
    top: 10px;
    left: 10px;
    width: calc(100% - 20px);
    height: calc(100% - 20px);
    background-color: #a855f7;
    border-radius: 2rem;
    border-bottom-right-radius: 8rem;
    transform: perspective(1000px) rotateY(-15deg);
    transition: transform 0.3s ease-in-out;
}

.vr-ar-image-container:hover .vr-ar-image-background {
    transform: perspective(1000px) rotateY(0deg);
}

.vr-ar-image img {
    position: relative;
    width: 100%;
    height: auto;
    border-radius: 1.5rem;
    border-bottom-right-radius: 7rem;
    display: block;
}

.vr-ar-title {
    font-size: 4rem;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 1rem;
    background: linear-gradient(45deg, #d8b4fe, #a855f7);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.vr-ar-description {
    font-size: 1.5rem;
    font-weight: 300;
    margin-bottom: 2rem;
    color: #e2e8f0;
    max-width: 600px;
}

.vr-ar-button {
    display: inline-block;
    padding: 1rem 2rem;
    background-color: #a855f7;
    color: #ffffff;
    text-decoration: none;
    border-radius: 5px;
    font-weight: 600;
    transition: background-color 0.3s ease, transform 0.3s ease;
}

.vr-ar-button:hover {
    background-color: #9333ea;
    transform: translateY(-3px);
}
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');

        body {
            font-family: 'Poppins', sans-serif;
            background-color: #1a1c20;
            color: #ffffff;
            margin: 0;
            padding: 0;
        }
    </style>
</head>
<body>
    <div class="progress-container">
        <div class="progress-bar"></div>
    </div>

    <div class="sticky-index">
        <a href="#welcome">Welcome</a>
        <a href="#about">About Me</a>
        <a href="#resources">21st Century Resources</a>
        <a href="#ai">AI</a>
        <a href="#unit-designs">Unit Designs</a>
        <a href="#robotics">Robotics</a>
        <a href="#vr-ar">VR and AR</a>
    </div>

    <section id="welcome" class="section">
        <h1>Welcome</h1>
        <p>Innovative Digital Teaching Resources</p>
    </section>

    <section id="about" class="section">
        <div class="content">
            <h2>About Me</h2>
            <p>Learn about my journey in educational innovation.</p>
        </div>
        <div class="image-container">
            <img src="<img placeholder>" alt="About Me">
        </div>
    </section>

    <section id="resources" class="section">
        <div class="content">
            <h2>21st Century Resources</h2>
            <p>Explore cutting-edge educational tools and methodologies.</p>
        </div>
        <div class="video-container">
            <svg class="video-frame" viewBox="0 0 120 120" preserveAspectRatio="none">
                <rect x="0" y="0" width="120" height="120" fill="none" stroke="#4299e1" stroke-width="2"/>
                <rect x="5" y="5" width="110" height="110" fill="none" stroke="#4299e1" stroke-width="2"/>
                <rect x="10" y="10" width="100" height="100" fill="none" stroke="#4299e1" stroke-width="2"/>
            </svg>
            <div class="video-player">
                <iframe src="https://i.imgur.com/your_video_id.mp4" frameborder="0" allowfullscreen autoplay loop muted></iframe>
            </div>
        </div>
    </section>

    <section id="ai" class="section">
        <div class="content">
            <h2>AI in Education</h2>
            <p>Discover how artificial intelligence is transforming learning.</p>
        </div>
        <div class="morph-container">
            <svg width="300" height="300" viewBox="0 0 300 300">
                <path id="morphPath" d="M150,0 L300,150 L150,300 L0,150 Z" fill="#353946"/>
            </svg>
        </div>
    </section>

    <section id="unit-designs" class="section">
        <h2>Unit Designs</h2>
        <p>Innovative curriculum planning for the modern classroom.</p>
        <a href="#" class="cta-button">Explore Units</a>
    </section>

    <section id="robotics" class="section">
        <h2>Robotics</h2>
        <p>Engaging students with hands-on robotics projects.</p>
        <div class="image-container">
            <img src="<img placeholder>" alt="Robotics in Education">
        </div>
    </section>

    <section id="vr-ar" class="section">
        <div class="vr-ar-content">
            <h2 class="vr-ar-title">Innovate<br>and Elevate</h2>
            <p class="vr-ar-description">Lorem ipsum.</p>
            <a href="#" class="vr-ar-button">Explore more.</a>
        </div>
        <div class="vr-ar-image">
            <div class="vr-ar-image-container">
                <div class="vr-ar-image-background"></div>
                <img src="images/vrheadset.png" alt="VR Headset">
            </div>
        </div>
    </section>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const controller = new ScrollMagic.Controller();
            const progressBar = document.querySelector('.progress-bar');
            const stickyIndex = document.querySelector('.sticky-index');
            const welcomeSection = document.getElementById('welcome');
            const sections = document.querySelectorAll('.section');

            // Vertical Scroll Progress Indicator
            window.addEventListener('scroll', () => {
                const scrollPosition = window.pageYOffset;
                const documentHeight = document.documentElement.scrollHeight - window.innerHeight;
                const scrollPercentage = (scrollPosition / documentHeight) * 100;
                progressBar.style.height = scrollPercentage + '%';

                // Show/hide sticky index based on scroll position
                if (scrollPosition > welcomeSection.offsetHeight / 2) {
                    stickyIndex.style.display = 'block';
                } else {
                    stickyIndex.style.display = 'none';
                }

                // Update sticky index background color based on current section
                sections.forEach((section, index) => {
                    const rect = section.getBoundingClientRect();
                    if (rect.top <= 50 && rect.bottom > 50) {
                        const progress = (scrollPosition - section.offsetTop) / section.offsetHeight;
                        const startColor = getComputedStyle(section).backgroundImage.match(/rgb\(.*?\)/g)[0];
                        const endColor = getComputedStyle(sections[index + 1 < sections.length ? index + 1 : index]).backgroundImage.match(/rgb\(.*?\)/g)[0];
                        stickyIndex.style.backgroundColor = lerpColor(startColor, endColor, progress);
                    }
                });
            });

            // Smooth scrolling for anchor links
            document.querySelectorAll('.sticky-index a').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    gsap.to(window, {duration: 1, scrollTo: targetId, ease: "power2.inOut"});
                });
            });

            // About Me: Scale Animation
            new ScrollMagic.Scene({
                triggerElement: "#about",
                duration: "200%",
                triggerHook: 1
            })
            .setTween(gsap.timeline()
                .fromTo("#about .content", 
                    {scale: 0.5, opacity: 0},
                    {scale: 1, opacity: 1, ease: "power1.inOut", duration: 0.5}
                )
                .to("#about .content", 
                    {scale: 0.5, opacity: 0, ease: "power1.inOut", duration: 0.5},
                    "+=0.5"
                )
            )
            .addTo(controller);

            const resourcesTimeline = anime.timeline({
                easing: 'easeOutExpo',
                duration: 1000,
                autoplay: false
            });

            resourcesTimeline
                .add({
                    targets: '#resources .content',
                    translateX: ['100%', '0%'],
                    opacity: [0, 1]
                })
                .add({
                    targets: '.video-frame',
                    strokeDashoffset: [anime.setDashoffset, 0],
                    duration: 1500,
                }, '-=500')
                .add({
                    targets: '.video-player',
                    opacity: [0, 1],
                    duration: 500
                }, '-=500');

            new ScrollMagic.Scene({
                triggerElement: "#resources",
                triggerHook: 0.7
            })
            .on('enter', () => resourcesTimeline.play())
            .addTo(controller);

            // Resources: SVG Reveal Animation
            let revealTween = gsap.to(".reveal-svg path", {
                duration: 1,
                attr: { d: "M0,0 Q500,300 1000,0 L1000,300 Q500,300 0,300 Z" },
                ease: "power2.inOut"
            });

            new ScrollMagic.Scene({
                triggerElement: "#resources",
                duration: "100%",
                triggerHook: 0.5
            })
            .setTween(revealTween)
            .addTo(controller);

            // AI: SVG Morph Animation
            let morphTween = KUTE.to('#morphPath', {
                path: 'M150,0 C150,100 250,100 250,200 S150,300 150,300 S50,250 50,200 S150,100 150,0',
                easing: 'easingCubicInOut',
                duration: 2000
            });

            new ScrollMagic.Scene({
                triggerElement: "#ai",
                triggerHook: 0.5
            })
            .on('enter', function() {
                morphTween.start();
            })
            .addTo(controller);

            // Text Fade-in Animation
            document.querySelectorAll('.section .content').forEach(element => {
                new ScrollMagic.Scene({
                    triggerElement: element,
                    triggerHook: 0.8
                })
                .setTween(gsap.fromTo(element, 
                    {opacity: 0, y: 50},
                    {opacity: 1, y: 0, duration: 0.5}
                ))
                .addTo(controller);
            });

            // Reduced scroll snapping
            let isScrolling = false;
            let scrollTimeout;

            window.addEventListener('wheel', (e) => {
                clearTimeout(scrollTimeout);
                if (!isScrolling) {
                    const currentSection = [...sections].findIndex(section => 
                        section.getBoundingClientRect().top <= 50 && section.getBoundingClientRect().bottom > 50
                    );
                    const targetSection = e.deltaY > 0 ? 
                        Math.min(currentSection + 1, sections.length - 1) : 
                        Math.max(currentSection - 1, 0);
                    
                    if (targetSection !== currentSection) {
                        isScrolling = true;
                        gsap.to(window, {
                            duration: 1,
                            scrollTo: sections[targetSection],
                            ease: "power2.inOut",
                            onComplete: () => {
                                isScrolling = false;
                            }
                        });
                    }
                }
                scrollTimeout = setTimeout(() => {
                    isScrolling = false;
                }, 50);
            }, {passive: false});

            // Helper function to interpolate between two colors
            function lerpColor(a, b, amount) {
                const parseColor = (color) => color.match(/\d+/g).map(Number);
                const ah = parseColor(a);
                const bh = parseColor(b);
                const rh = Math.round(ah[0] + (bh[0] - ah[0]) * amount);
                const gh = Math.round(ah[1] + (bh[1] - ah[1]) * amount);
                const bl = Math.round(ah[2] + (bh[2] - ah[2]) * amount);
                return `rgba(${rh},${gh},${bl},0.8)`;
            }

            function updateStickyIndexColor() {
                const scrollPosition = window.pageYOffset;
                sections.forEach((section, index) => {
                    const rect = section.getBoundingClientRect();
                    if (rect.top <= 50 && rect.bottom > 50) {
                        const progress = (scrollPosition - section.offsetTop) / section.offsetHeight;
                        const startColor = getComputedStyle(section).backgroundImage.match(/rgb\(.*?\)/g)[0];
                        const endColor = getComputedStyle(sections[index + 1 < sections.length ? index + 1 : index]).backgroundImage.match(/rgb\(.*?\)/g)[0];
                        stickyIndex.style.backgroundColor = lerpColor(startColor, endColor, progress);
                    }
                });}

// Add scroll event listener for updating sticky index color
window.addEventListener('scroll', updateStickyIndexColor);

// Initial call to set the correct color
updateStickyIndexColor();

// Parallax effect for images
sections.forEach(section => {
    const img = section.querySelector('img');
    if (img) {
        new ScrollMagic.Scene({
            triggerElement: section,
            duration: '200%',
            triggerHook: 1
        })
        .setTween(gsap.to(img, {y: '20%', ease: 'none'}))
        .addTo(controller);
    }
});

// Animate CTA buttons
document.querySelectorAll('.cta-button').forEach(button => {
    button.addEventListener('mouseenter', () => {
        gsap.to(button, {scale: 1.1, duration: 0.3});
    });
    button.addEventListener('mouseleave', () => {
        gsap.to(button, {scale: 1, duration: 0.3});
    });
});

// Text reveal animation
sections.forEach(section => {
    const content = section.querySelector('.content');
    if (content) {
        const tl = gsap.timeline({paused: true});
        tl.from(content.children, {
            y: 50,
            opacity: 0,
            duration: 0.5,
            stagger: 0.2
        });

        new ScrollMagic.Scene({
            triggerElement: section,
            triggerHook: 0.7
        })
        .on('enter', () => tl.play())
        .on('leave', () => tl.reverse())
        .addTo(controller);
    }
});

// Particle background effect
const particleContainer = document.createElement('div');
particleContainer.style.position = 'fixed';
particleContainer.style.top = '0';
particleContainer.style.left = '0';
particleContainer.style.width = '100%';
particleContainer.style.height = '100%';
particleContainer.style.pointerEvents = 'none';
particleContainer.style.zIndex = '-1';
document.body.appendChild(particleContainer);

for (let i = 0; i < 50; i++) {
    const particle = document.createElement('div');
    particle.style.position = 'absolute';
    particle.style.width = '2px';
    particle.style.height = '2px';
    particle.style.background = 'rgba(255, 255, 255, 0.5)';
    particle.style.borderRadius = '50%';
    particleContainer.appendChild(particle);

    gsap.set(particle, {
        x: Math.random() * window.innerWidth,
        y: Math.random() * window.innerHeight
    });

    gsap.to(particle, {
        duration: Math.random() * 10 + 5,
        x: '+=' + (Math.random() * 100 - 50),
        y: '+=' + (Math.random() * 100 - 50),
        repeat: -1,
        yoyo: true,
        ease: 'sine.inOut'
    });
}
});
</script>
</body>
</html>
```

# .gitattributes

```
# Auto detect text files and perform LF normalization
* text=auto

```

# images\vrheadset.png

This is a binary file of the type: Image

# CSS\styles.css

```css
body {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
    background-color: #2d3748;
    color: #ffffff;
}

.section {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2rem;
    position: relative;
    overflow: hidden;
}

h1 {
    font-size: 4rem;
    margin-bottom: 1rem;
}

h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
}

p {
    font-size: 1.2rem;
    max-width: 600px;
    margin: 0 auto;
}

.image-container {
    margin-top: 2rem;
    max-width: 80%;
}

.image-container img {
    width: 100%;
    height: auto;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.reveal-svg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.morph-container {
    margin-top: 2rem;
}

.cta-button {
    display: inline-block;
    margin-top: 2rem;
    padding: 1rem 2rem;
    background-color: #4299e1;
    color: #ffffff;
    text-decoration: none;
    border-radius: 5px;
    font-weight: bold;
    transition: background-color 0.3s ease;
}

.cta-button:hover {
    background-color: #3182ce;
}

.progress-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 5px;
    background-color: rgba(255, 255, 255, 0.2);
    z-index: 1000;
}

.progress-bar {
    height: 100%;
    background-color: #4299e1;
    width: 0;
    transition: width 0.1s ease;
}

html, body {
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        html::-webkit-scrollbar, body::-webkit-scrollbar {
            display: none;
        }
        body {
            background-color: #2d3748;
            color: #ffffff;
            font-family: Arial, sans-serif;
        }
        .progress-container {
            position: fixed;
            top: 0;
            right: 0;
            width: 5px;
            height: 100%;
            background-color: rgba(255, 255, 255, 0.2);
            z-index: 1000;
        }
        .progress-bar {
            width: 100%;
            background-color: #4299e1;
            height: 0;
            transition: height 0.1s ease;
        }
        .sticky-index {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            background-color: rgba(0, 0, 0, 0.8);
            padding: 10px 20px;
            display: none;
        }
        .sticky-index a {
            display: inline-block;
            color: white;
            text-decoration: none;
            margin: 0 15px;
            font-size: 16px;
            transition: color 0.3s ease;
        }
        .sticky-index a:hover {
            color: #4299e1;
        }
        .section {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem;
        }
        h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
        }
        p {
            font-size: 1.5rem;
            max-width: 600px;
        }
        
        
```

