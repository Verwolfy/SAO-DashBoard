**SAO-DashBoard:**

Il s'agit d'une application de type Single Page Application (SPA) contenue dans un fichier unique (HTML/CSS/JS). Elle fait office de tableau de bord décisionnel (BI) orienté finance/opérations pour l'industrie cimentière (CPA, Clinker, Vrac, etc.).

Stack Technique : Vanilla JavaScript (ES6+), Tailwind CSS (via CDN), Plotly.js pour la data visualisation, PapaParse pour l'ingestion CSV, et l'API Google Gemini pour l'IA générative.

Pattern : Le code utilise un pattern de "State Management" fait maison (objets State et UI) qui imite des architectures plus complexes (comme Redux ou Vuex), ce qui est adapté pour une application de cette taille sans framework.

Gestion de l'État (State Management) : La séparation claire entre les données brutes (State.raw), les données filtrées (State.filtered), et l'interface utilisateur (UI) est une excellente pratique en Vanilla JS.

Flexibilité d'Ingestion : L'utilisation de PapaParse combinée à un "hack" de l'URL Google Sheets (/export?format=csv) et à une zone de Drag & Drop est très ingénieuse et pragmatique pour le client final.

UI/UX Moderne : L'implémentation du Dark Mode, des "Glass panels" (Glassmorphism), et la configuration personnalisée de Tailwind donnent un rendu très professionnel et corporate.

Programmation Défensive (Parsing) : La fonction getColRobust utilise du "fuzzy matching" pour trouver les colonnes de production. Cela montre que le développeur sait que les données sources (fichiers Excel/CSV humains) sont souvent sujettes à des fautes de frappe.

Robustesse des appels API : L'implémentation de la fonction fetchWithRetry avec un backoff exponentiel pour l'API Gemini est une pratique d'ingénierie senior, évitant que l'appli ne crashe à la moindre micro-coupure réseau.
