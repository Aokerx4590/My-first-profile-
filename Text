// Toggle Mobile Navigation Menu Drawer
const menuIcon = document.querySelector('#menu-icon');
const navbar = document.querySelector('.navbar');

menuIcon.onclick = () => {
    menuIcon.classList.toggle('bx-x'); // Toggle close 'X' icon
    navbar.classList.toggle('active'); // Slide in navbar
};

// Remove menu drawer when clicking a navigation link
document.querySelectorAll('.navbar a').forEach(link => {
    link.onclick = () => {
        menuIcon.classList.remove('bx-x');
        navbar.classList.remove('active');
    };
});

// Activate Sticky Header Navbar State on Scroll
const header = document.querySelector('.header');
const sections = document.querySelectorAll('section');
const navLinks = document.querySelectorAll('header nav a');

window.onscroll = () => {
    // 1. Sticky Header logic
    header.classList.toggle('sticky', window.scrollY > 100);

    // 2. Active Link logic based on scroll position
    sections.forEach(sec => {
        const top = window.scrollY;
        const offset = sec.offsetTop - 150;
        const height = sec.offsetHeight;
        const id = sec.getAttribute('id');

        if (top >= offset && top < offset + height) {
            navLinks.forEach(links => {
                links.classList.remove('active');
                document.querySelector('header nav a[href*=' + id + ']').classList.add('active');
            });
        }
    });
};

// Aditya's Typing Animation Engine Logic
const words = ["Web Developer.", "Class 12th Student.", "Tech Enthusiast."];
let wordIndex = 0;
let charIndex = 0;
let isDeleting = false;
const typingSpeed = 100;
const erasingSpeed = 50;
const delayBetweenWords = 2000; // Time word stays typed

const typingTarget = document.querySelector('.typing-text');

function typeEffect() {
    const currentWord = words[wordIndex];
    
    // Determine how much of the word is displayed
    if (isDeleting) {
        typingTarget.textContent = currentWord.substring(0, charIndex - 1);
        charIndex--;
    } else {
        typingTarget.textContent = currentWord.substring(0, charIndex + 1);
        charIndex++;
    }

    // Logic to switch between typing and deleting states
    if (!isDeleting && charIndex === currentWord.length) {
        // Word is finished, pause before deleting
        setTimeout(() => isDeleting = true, delayBetweenWords);
    } else if (isDeleting && charIndex === 0) {
        // Word is deleted, move to next word
        isDeleting = false;
        wordIndex = (wordIndex + 1) % words.length;
    }

    // Loop the typing effect with variable speeds
    setTimeout(typeEffect, isDeleting ? erasingSpeed : typingSpeed);
}

// Fire up typing animation on site load
if(typingTarget) {
    typeEffect();
}
