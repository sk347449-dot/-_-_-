<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>शुभ विवाह आमंत्रण</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Font - Poppins for clean look, modified with custom styles for a festive feel -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        /* Custom festive colors */
        :root {
            --primary-color: #ff9800; /* Amber/Marigold */
            --secondary-color: #6d28d9; /* Deep Purple */
            --bg-color: #fffbe6; /* Light Creamy Yellow */
        }
        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-color);
            min-height: 100vh;
        }
        .invitation-card {
            background-color: white;
            border-radius: 1.5rem;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            border: 5px solid var(--primary-color);
        }
        .main-heading {
            color: var(--secondary-color);
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }
        .btn-primary {
            background-color: var(--primary-color);
            transition: transform 0.2s, box-shadow 0.2s;
        }
        .btn-primary:hover {
            background-color: #f57c00;
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.06);
        }
        .input-field {
            border-color: var(--primary-color);
        }
        /* Style for the image container to simulate a framed photo */
        .img-container {
            border: 4px solid var(--secondary-color);
            padding: 0.5rem;
            border-radius: 0.75rem;
            background: #fff;
        }
        /* Mobile specific adjustments */
        @media (max-width: 640px) {
            .invitation-card {
                margin: 0.5rem;
                border-radius: 1rem;
                border-width: 3px;
            }
        }
    </style>
</head>
<body class="flex items-center justify-center p-4">

    <!-- Main Container -->
    <div id="main-container" class="w-full max-w-2xl">

        <!-- Screen 1: The Gate/Quiz Screen -->
        <div id="gate-screen" class="invitation-card p-8 md:p-10 text-center">
            <h1 class="main-heading text-4xl md:text-5xl font-extrabold mb-4">
                शुभ विवाह आमंत्रण
            </h1>
            <p class="text-gray-600 mb-8">
                कृपया आमंत्रण खोलने के लिए अपना नाम और पता दर्ज करें।
            </p>
            
            <div class="space-y-6 max-w-sm mx-auto">
                <div>
                    <label for="recipient-name" class="block text-left text-sm font-medium text-gray-700 mb-1">
                        प्राप्तकर्ता का नाम (आपका नाम)
                    </label>
                    <input type="text" id="recipient-name" class="input-field w-full px-4 py-3 border-2 rounded-lg focus:outline-none focus:ring-2 focus:ring-yellow-500" placeholder="उदाहरण: रमेश कुमार" required>
                </div>
                <div>
                    <label for="recipient-address" class="block text-left text-sm font-medium text-gray-700 mb-1">
                        आपका पता
                    </label>
                    <textarea id="recipient-address" rows="3" class="input-field w-full px-4 py-3 border-2 rounded-lg focus:outline-none focus:ring-2 focus:ring-yellow-500" placeholder="उदाहरण: 123, गांधी नगर, लखनऊ" required></textarea>
                </div>
                
                <button onclick="openInvitation()" class="btn-primary w-full text-white font-bold py-3 rounded-lg shadow-md hover:shadow-xl transition duration-300">
                    आमंत्रण खोलें
                </button>
            </div>

            <div id="error-message" class="text-red-600 mt-4 hidden font-medium">
                कृपया नाम और पता दोनों दर्ज करें।
            </div>
        </div>

        <!-- Screen 2: The Full Invitation Screen -->
        <div id="invitation-screen" class="invitation-card p-6 md:p-10 hidden">
            <h1 class="main-heading text-4xl md:text-5xl font-extrabold text-center mb-6 border-b-2 pb-2 border-yellow-400">
                शुभ विवाह आमंत्रण
            </h1>
            
            <div class="text-center mb-6">
                <p class="text-xl font-semibold text-gray-800">प्रिय <span id="display-name" class="text-yellow-600"></span>,</p>
                <p class="text-sm text-gray-500">हम आपके आगमन की प्रतीक्षा कर रहे हैं।</p>
            </div>

            <!-- Card Image Section: Google Drive link integrated here -->
            <div class="img-container mx-auto mb-8 max-w-full">
                <!-- 
                ⭐ Google Drive Link: सुनिश्चित करें कि यह फ़ाइल Google Drive पर 'Anyone with the link' पर सेट है।
                -->
                <img id="card-image" 
                     src="https://drive.google.com/file/d/1s7nPdHdDIgLtYMDpv3Y7Nqc0cFq8zMhi/view?usp=drivesdk" 
                     alt="शुभ विवाह कार्ड का फोटो" 
                     onerror="this.onerror=null;this.src='https://placehold.co/600x400/800000/ffffff?text=फोटो+उपलब्ध+नहीं';"
                     class="w-full h-auto rounded-md object-cover">
                
                <p class="text-center text-xs text-gray-500 mt-2">उपलब्ध आमंत्रण कार्ड का दृश्य</p>
            </div>
            
            <!-- Invitation Details -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6 text-gray-700 mb-8">
                <div class="p-4 bg-yellow-50 rounded-lg shadow-sm border border-yellow-200">
                    <p class="text-yellow-600 font-bold mb-1">घटना (Event)</p>
                    <p class="text-lg font-medium">शुभ विवाह</p>
                </div>
                <div class="p-4 bg-yellow-50 rounded-lg shadow-sm border border-yellow-200">
                    <p class="text-yellow-600 font-bold mb-1">दिनांक (Date)</p>
                    <p class="text-lg font-medium">22 नवंबर 2025</p>
                </div>
                <div class="md:col-span-2 p-4 bg-yellow-50 rounded-lg shadow-sm border border-yellow-200">
                    <p class="text-yellow-600 font-bold mb-1">स्थान (Venue)</p>
                    <p class="text-lg font-medium">समस्त वैवाहिक कार्यक्रम हमारे निवास स्थान <br class="md:hidden"> **ग्राम कांटी (रोहिला नगर) पोस्ट इटौरा जिला बाराबंकी** में सम्पन्न होंगे।</p>
                </div>
                <div class="p-4 bg-yellow-50 rounded-lg shadow-sm border border-yellow-200">
                    <p class="text-yellow-600 font-bold mb-1">समय (Time)</p>
                    <p class="text-lg font-medium">शाम 6 बजे आप सादर आमंत्रित हैं।</p>
                </div>
                <div class="p-4 bg-yellow-50 rounded-lg shadow-sm border border-yellow-200">
                    <p class="text-yellow-600 font-bold mb-1">आपसे आग्रह</p>
                    <p class="text-lg font-medium">समय पर पधारें</p>
                </div>
            </div>

            <!-- Child Request / Bal Manuhar -->
            <div class="text-center p-6 bg-purple-50 rounded-xl border-4 border-purple-300 mb-8 shadow-inner">
                <p class="text-2xl font-bold text-purple-700 mb-2">🎈 बाल मनुहार 🎈</p>
                <p class="text-xl italic text-gray-800 leading-relaxed">
                    "फलक से चांद उतरेगा, तारे मुस्कुराएंगे। हमें खुशी तब होगी, जब मेली दीदी की शादी के आएंगे।"
                </p>
                <p class="mt-3 text-purple-600 font-semibold">— अक्षत यादव</p>
            </div>

            <!-- Confirmation Button -->
            <button onclick="sendConfirmation()" class="btn-primary w-full text-white font-bold py-4 rounded-lg shadow-lg text-lg">
                ✅ पुष्टि करें - मैंने आमंत्रण देख लिया है
            </button>
            <p id="whatsapp-info" class="text-center text-sm text-gray-500 mt-3 hidden">
                पुष्टि करने पर आपका नाम और पता WhatsApp द्वारा हमें सूचित किया जाएगा।
            </p>
        </div>

    </div>

    <script>
        // Global variables to store recipient details
        let recipientName = '';
        let recipientAddress = '';
        // Your WhatsApp number with country code (91 for India)
        const whatsappNumber = '918009676915'; 

        /**
         * Checks the input and transitions to the invitation screen.
         */
        function openInvitation() {
            const nameInput = document.getElementById('recipient-name');
            const addressInput = document.getElementById('recipient-address');
            const errorMessage = document.getElementById('error-message');

            recipientName = nameInput.value.trim();
            recipientAddress = addressInput.value.trim();

            if (recipientName === '' || recipientAddress === '') {
                errorMessage.classList.remove('hidden');
                return;
            }

            // Hide the gate and show the invitation
            document.getElementById('gate-screen').classList.add('hidden');
            document.getElementById('display-name').textContent = recipientName;
            document.getElementById('invitation-screen').classList.remove('hidden');
            document.getElementById('whatsapp-info').classList.remove('hidden');
            
            // Scroll to the top of the invitation
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        /**
         * Constructs and opens the WhatsApp link for confirmation.
         */
        function sendConfirmation() {
            if (recipientName === '' || recipientAddress === '') {
                console.error("Recipient details are missing. Cannot send confirmation.");
                return;
            }

            // 1. Construct the confirmation message
            const messageTemplate = 
                `नमस्ते! मुझे आपका शुभ विवाह आमंत्रण प्राप्त हो गया है और मैंने इसे देख लिया है।\n` +
                `*पुष्टि विवरण:*\n` +
                `*नाम:* ${recipientName}\n` +
                `*पता:* ${recipientAddress}\n` +
                `मैं जल्दी ही आपको सूचित करूंगा/करूंगी कि मैं आ रहा/रही हूं।\n` +
                `🙏 शुभकामनाएं!`;

            // 2. URL-encode the message
            const encodedMessage = encodeURIComponent(messageTemplate);

            // 3. Create the WhatsApp URL
            const whatsappUrl = `https://wa.me/${whatsappNumber}?text=${encodedMessage}`;

            // 4. Open the link (This will open the WhatsApp app/web on mobile/desktop)
            window.open(whatsappUrl, '_blank');
            
            // Show a simple success message to the user on the screen 
            const button = event.target;
            button.textContent = "✅ पुष्टि सफलतापूर्वक भेजी गई!";
            button.classList.remove('btn-primary');
            button.classList.add('bg-green-600', 'hover:bg-green-700');
            button.onclick = null; // Disable further clicks
            
            document.getElementById('whatsapp-info').textContent = "आपकी पुष्टि WhatsApp पर भेज दी गई है। धन्यवाद!";
        }
    </script>
</body>
</html>

