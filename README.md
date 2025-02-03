# My Website Project
# -Rizwan-Rasheed-TestRepo
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Publications</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/alpinejs@2.8.2/dist/alpine.min.js" defer></script>
    <style>
        /* Floating Text Animation */
        .floating-text {
            animation: float 5s ease-in-out infinite;
        }

        @keyframes float {
            0% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0); }
        }

        /* Smooth Fade-in and Transitions */
        .fade-in {
            animation: fadeIn 2s ease-in-out forwards;
        }

        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        /* Smooth Hover Effects for Buttons */
        .hover-effect:hover {
            transform: scale(1.1);
            transition: transform 0.3s ease-in-out;
        }
    </style>
</head>
<body class="bg-gray-50 dark:bg-gray-800 transition-colors duration-300">

    <!-- Navbar -->
    <nav class="p-4 bg-blue-600 dark:bg-blue-800">
        <div class="flex justify-between items-center">
            <h1 class="text-white text-xl font-bold">My Publications</h1>
            <button id="theme-toggle" class="bg-gray-200 dark:bg-gray-700 p-2 rounded-full">
                <span class="text-gray-900 dark:text-gray-100">🌙</span>
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="text-center py-20 px-4">
        <h2 class="text-3xl text-gray-900 dark:text-white font-bold mb-4 fade-in">Welcome to My Personal Publications</h2>
        <p class="text-lg text-gray-700 dark:text-gray-300 fade-in">Here, I share my insights, research, and more!</p>
    </section>

    <!-- Floating Text -->
    <section class="flex justify-center mt-10">
        <h3 class="text-4xl font-bold text-blue-600 dark:text-blue-400 floating-text">Rizwan Rasheed</h3>
    </section>

    <!-- Publication List -->
    <section class="max-w-4xl mx-auto py-12">
        <h3 class="text-2xl text-gray-900 dark:text-white font-bold mb-6 fade-in">Recent Publications</h3>
        <div class="grid gap-6 grid-cols-1 sm:grid-cols-2 lg:grid-cols-3">
            <!-- Publication Card Example -->
            <div class="bg-white dark:bg-gray-700 p-4 rounded-lg shadow-lg transition-all duration-300 hover:shadow-xl">
                <h4 class="text-xl text-gray-800 dark:text-white font-semibold">Publication Title</h4>
                <p class="text-gray-600 dark:text-gray-300">Brief description of the publication.</p>
                <button class="mt-4 px-4 py-2 bg-blue-600 text-white rounded-full hover:bg-blue-700 hover-effect">Read More</button>
            </div>
        </div>
    </section>

    <!-- Contact Form Section -->
    <section class="bg-gray-100 dark:bg-gray-900 py-12">
        <div class="max-w-2xl mx-auto text-center">
            <h3 class="text-2xl text-gray-900 dark:text-white font-bold mb-6 fade-in">Get in Touch</h3>
            <form id="contact-form" class="space-y-4">
                <input type="text" id="name" placeholder="Your Name" class="w-full p-3 rounded-lg bg-white dark:bg-gray-800 border border-gray-300 dark:border-gray-600 text-gray-900 dark:text-white">
                <input type="email" id="email" placeholder="Your Email" class="w-full p-3 rounded-lg bg-white dark:bg-gray-800 border border-gray-300 dark:border-gray-600 text-gray-900 dark:text-white">
                <textarea id="message" placeholder="Your Message" class="w-full p-3 rounded-lg bg-white dark:bg-gray-800 border border-gray-300 dark:border-gray-600 text-gray-900 dark:text-white"></textarea>
                <button type="submit" class="w-full p-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700 hover-effect">Send Message</button>
            </form>
        </div>
    </section>

    <footer class="bg-blue-600 dark:bg-blue-800 text-white text-center py-4">
        <p>&copy; 2025 My Publications. All Rights Reserved.</p>
    </footer>

    <!-- Script for Dark Mode Toggle -->
    <script>
        const themeToggleButton = document.getElementById('theme-toggle');
        themeToggleButton.addEventListener('click', () => {
            document.body.classList.toggle('dark');
            themeToggleButton.querySelector('span').textContent = document.body.classList.contains('dark') ? '🌞' : '🌙';
        });

        // Form Handling (just a sample)
        const form = document.getElementById('contact-form');
        form.addEventListener('submit', function (event) {
            event.preventDefault();
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;

            // API integration (send data to backend)
            fetch('https://your-api-endpoint.com/contact', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({ name, email, message }),
            })
            .then(response => response.json())
            .then(data => {
                alert('Message sent successfully!');
                form.reset();
            })
            .catch(error => {
                alert('Error sending message!');
            });
        });
    </script>
</body>
</html>
