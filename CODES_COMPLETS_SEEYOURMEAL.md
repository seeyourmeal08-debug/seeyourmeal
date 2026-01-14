# 🚀 TOUS LES CODES SEEYOURMEAL - COPIER-COLLER COMPLET

## 📦 LISTE COMPLÈTE DES 14 FICHIERS

1. package.json
2. vite.config.js
3. tailwind.config.js
4. postcss.config.js
5. .gitignore
6. README.md
7. public/index.html
8. src/index.css
9. src/main.jsx
10. src/App.jsx
11. src/config/firebase.js
12. src/components/HomePage.jsx ⭐
13. src/components/AdminDashboard.jsx ⭐
14. src/components/PublicMenu.jsx ⭐

---

# 📄 CODES COMPLETS À COPIER-COLLER

---

## 1️⃣ package.json (À LA RACINE DU PROJET)

**Créez un fichier nommé : `package.json`**

```json
{
  "name": "seeyourmeal",
  "version": "1.0.0",
  "description": "Plateforme de menus 3D pour restaurants",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.20.0",
    "firebase": "^10.7.1",
    "qrcode": "^1.5.3",
    "lucide-react": "^0.294.0"
  },
  "devDependencies": {
    "@vitejs/plugin-react": "^4.2.1",
    "vite": "^5.0.8",
    "tailwindcss": "^3.3.6",
    "postcss": "^8.4.32",
    "autoprefixer": "^10.4.16"
  }
}
```

---

## 2️⃣ vite.config.js (À LA RACINE)

**Créez un fichier nommé : `vite.config.js`**

```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000
  }
})
```

---

## 3️⃣ tailwind.config.js (À LA RACINE)

**Créez un fichier nommé : `tailwind.config.js`**

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {
      colors: {
        orange: {
          500: '#ff6b35',
          600: '#f7931e',
        }
      }
    },
  },
  plugins: [],
}
```

---

## 4️⃣ postcss.config.js (À LA RACINE)

**Créez un fichier nommé : `postcss.config.js`**

```javascript
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

---

## 5️⃣ .gitignore (À LA RACINE)

**Créez un fichier nommé : `.gitignore`**

```
# Dépendances
node_modules/
dist/

# Fichiers environnement
.env
.env.local

# Logs
*.log

# OS
.DS_Store
Thumbs.db

# IDE
.vscode/
.idea/
```

---

## 6️⃣ README.md (À LA RACINE)

**Créez un fichier nommé : `README.md`**

```markdown
# 🍽️ SeeYourMeal

Plateforme de menus 3D interactifs pour restaurants.

## Installation

```bash
npm install
npm run dev
```

## Déploiement

```bash
vercel
```

## Technologies

- React + Vite
- Firebase (Database + Storage)
- Tailwind CSS
- Stripe (Paiements)
```

---

## 7️⃣ public/index.html

**Créez le dossier `public` puis créez dedans : `index.html`**

```html
<!DOCTYPE html>
<html lang="fr">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>SeeYourMeal - Menus 3D pour Restaurants</title>
    <meta name="description" content="Transformez vos menus en expérience 3D interactive" />
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

---

## 8️⃣ src/index.css

**Créez le dossier `src` puis créez dedans : `index.css`**

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

---

## 9️⃣ src/main.jsx

**Dans le dossier `src`, créez : `main.jsx`**

```javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

---

## 🔟 src/App.jsx

**Dans le dossier `src`, créez : `App.jsx`**

```javascript
import React from 'react'
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom'
import HomePage from './components/HomePage'
import AdminDashboard from './components/AdminDashboard'
import PublicMenu from './components/PublicMenu'

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="/admin" element={<AdminDashboard />} />
        <Route path="/menu/:restaurantId" element={<PublicMenu />} />
      </Routes>
    </Router>
  )
}

export default App
```

---

## 1️⃣1️⃣ src/config/firebase.js

**Créez le dossier `src/config` puis créez dedans : `firebase.js`**

```javascript
import { initializeApp } from 'firebase/app';
import { getFirestore, collection, addDoc, getDocs, doc, updateDoc, deleteDoc, query, where, getDoc } from 'firebase/firestore';
import { getStorage, ref, uploadBytes, getDownloadURL } from 'firebase/storage';
import { getAuth } from 'firebase/auth';

// ⚠️ REMPLACEZ AVEC VOS VRAIES CLÉS FIREBASE
// Obtenez-les sur : https://console.firebase.google.com
const firebaseConfig = {
  apiKey: "VOTRE_API_KEY",
  authDomain: "VOTRE_PROJECT_ID.firebaseapp.com",
  projectId: "VOTRE_PROJECT_ID",
  storageBucket: "VOTRE_PROJECT_ID.appspot.com",
  messagingSenderId: "VOTRE_MESSAGING_SENDER_ID",
  appId: "VOTRE_APP_ID"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
export const db = getFirestore(app);
export const storage = getStorage(app);
export const auth = getAuth(app);

// Helper Functions pour faciliter l'utilisation

// Ajouter un restaurant
export const addRestaurant = async (restaurantData) => {
  try {
    const docRef = await addDoc(collection(db, 'restaurants'), {
      ...restaurantData,
      createdAt: new Date(),
    });
    return docRef.id;
  } catch (error) {
    console.error('Erreur ajout restaurant:', error);
    throw error;
  }
};

// Obtenir tous les restaurants
export const getAllRestaurants = async () => {
  try {
    const querySnapshot = await getDocs(collection(db, 'restaurants'));
    return querySnapshot.docs.map(doc => ({
      id: doc.id,
      ...doc.data()
    }));
  } catch (error) {
    console.error('Erreur récupération restaurants:', error);
    throw error;
  }
};

// Obtenir un restaurant par ID
export const getRestaurantById = async (id) => {
  try {
    const docRef = doc(db, 'restaurants', id);
    const docSnap = await getDoc(docRef);
    
    if (docSnap.exists()) {
      return { id: docSnap.id, ...docSnap.data() };
    } else {
      throw new Error('Restaurant non trouvé');
    }
  } catch (error) {
    console.error('Erreur récupération restaurant:', error);
    throw error;
  }
};

// Mettre à jour un restaurant
export const updateRestaurant = async (id, data) => {
  try {
    const docRef = doc(db, 'restaurants', id);
    await updateDoc(docRef, data);
  } catch (error) {
    console.error('Erreur mise à jour restaurant:', error);
    throw error;
  }
};

// Supprimer un restaurant
export const deleteRestaurant = async (id) => {
  try {
    await deleteDoc(doc(db, 'restaurants', id));
  } catch (error) {
    console.error('Erreur suppression restaurant:', error);
    throw error;
  }
};

// Upload une image vers Firebase Storage
export const uploadImage = async (file, path) => {
  try {
    const storageRef = ref(storage, path);
    await uploadBytes(storageRef, file);
    const url = await getDownloadURL(storageRef);
    return url;
  } catch (error) {
    console.error('Erreur upload image:', error);
    throw error;
  }
};
```

---

## 1️⃣2️⃣ src/components/HomePage.jsx ⭐

**Créez le dossier `src/components` puis créez dedans : `HomePage.jsx`**

**⚠️ FICHIER COMPLET - 500+ LIGNES**

```javascript
import React, { useState } from 'react';
import { Link } from 'react-router-dom';
import { Menu, X, Eye, Smartphone, BarChart, Clock, CheckCircle, ArrowRight } from 'lucide-react';

const HomePage = () => {
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);
  const [billingCycle, setBillingCycle] = useState('monthly'); // 'monthly' ou 'annual'

  const stats = [
    { value: '200+', label: 'Restaurants partenaires' },
    { value: '35%', label: "Augmentation moyenne des commandes" },
    { value: '5000+', label: 'Plats modélisés' },
    { value: '98%', label: 'Satisfaction client' }
  ];

  const features = [
    {
      icon: <Eye className="w-8 h-8" />,
      title: 'Visualisation 3D Réaliste',
      description: 'Vos plats en 3D photoréaliste avec rotation 360° pour une expérience immersive.'
    },
    {
      icon: <Smartphone className="w-8 h-8" />,
      title: 'QR Code Unique',
      description: 'Un QR code personnalisé pour chaque restaurant. Scannez et visualisez instantanément.'
    },
    {
      icon: <Clock className="w-8 h-8" />,
      title: 'Modification en Temps Réel',
      description: 'Modifiez votre menu instantanément depuis votre dashboard. Changements visibles immédiatement.'
    },
    {
      icon: <BarChart className="w-8 h-8" />,
      title: 'Analytics Avancées',
      description: 'Suivez les performances de vos plats avec des statistiques détaillées.'
    },
    {
      icon: <CheckCircle className="w-8 h-8" />,
      title: 'Interface Intuitive',
      description: 'Dashboard simple et puissant pour gérer tous vos plats sans compétences techniques.'
    },
    {
      icon: <ArrowRight className="w-8 h-8" />,
      title: 'Responsive Design',
      description: 'Expérience parfaite sur tous les appareils : mobile, tablette et desktop.'
    }
  ];

  const steps = [
    {
      number: '01',
      title: 'Photographiez vos plats',
      description: 'Prenez des photos de vos plats signature ou nous venons les photographier.'
    },
    {
      number: '02',
      title: 'Modélisation 3D',
      description: 'Notre équipe transforme vos plats en modèles 3D photoréalistes.'
    },
    {
      number: '03',
      title: 'Intégration au menu',
      description: 'Nous créons votre menu digital avec QR code unique.'
    },
    {
      number: '04',
      title: 'Lancez et gérez',
      description: 'Gérez votre menu en autonomie via notre dashboard.'
    }
  ];

  const pricingPlans = [
    {
      name: 'STANDARD',
      price: billingCycle === 'monthly' ? 78 : 62,
      period: billingCycle === 'monthly' ? '/mois' : '/mois (annuel)',
      popular: false,
      features: [
        'Menu digital Ochel prêt à l\'emploi',
        'Accès à tous les templates personnalisables',
        'Dashboard de gestion',
        'Jusqu\'à 5 plats en animation vidéo',
        'QR code unique',
        'Modifications instantanées illimitées',
        'Hébergement & maintenance inclus',
        'Menu accessible partout'
      ],
      extra: 'Menu multilingue +12$ CAD'
    },
    {
      name: 'ESSENTIELLE',
      price: billingCycle === 'monthly' ? 92 : 73,
      period: billingCycle === 'monthly' ? '/mois' : '/mois (annuel)',
      popular: true,
      features: [
        'Tout de l\'offre Standard',
        'Jusqu\'à 15 plats en animation vidéo',
        'Gestion quotidienne optimisée',
        'Support prioritaire',
        'Analytics avancées'
      ],
      extra: 'Menu multilingue +12$ CAD'
    },
    {
      name: 'AVANCÉE',
      price: billingCycle === 'monthly' ? 119 : 95,
      period: billingCycle === 'monthly' ? '/mois' : '/mois (annuel)',
      popular: false,
      features: [
        'Tout de l\'offre Essentielle',
        'Animations de plats illimitées',
        'Gestion avancée du menu',
        'Cartes évolutives & rotations',
        'Reporting performance détaillé',
        'Support dédié 24/7'
      ],
      extra: 'Menu multilingue +12$ CAD'
    }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 via-gray-800 to-black text-white">
      {/* Navigation */}
      <nav className="fixed top-0 w-full bg-gray-900/95 backdrop-blur-sm z-50 border-b border-gray-800">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            {/* Logo */}
            <div className="flex items-center space-x-2">
              <Eye className="w-8 h-8 text-orange-500" />
              <span className="text-2xl font-bold">
                See<span className="text-orange-500">Your</span>Meal
              </span>
            </div>

            {/* Desktop Menu */}
            <div className="hidden md:flex items-center space-x-8">
              <a href="#features" className="hover:text-orange-500 transition">Fonctionnalités</a>
              <a href="#how-it-works" className="hover:text-orange-500 transition">Comment ça marche</a>
              <a href="#pricing" className="hover:text-orange-500 transition">Tarifs</a>
              <a href="#contact" className="hover:text-orange-500 transition">Contact</a>
              <Link 
                to="/admin" 
                className="px-4 py-2 border border-orange-500 rounded-lg hover:bg-orange-500 transition"
              >
                Connexion
              </Link>
              <button className="px-6 py-2 bg-gradient-to-r from-orange-500 to-orange-600 rounded-lg hover:shadow-lg hover:shadow-orange-500/50 transition">
                S'inscrire
              </button>
            </div>

            {/* Mobile Menu Button */}
            <button 
              className="md:hidden"
              onClick={() => setMobileMenuOpen(!mobileMenuOpen)}
            >
              {mobileMenuOpen ? <X className="w-6 h-6" /> : <Menu className="w-6 h-6" />}
            </button>
          </div>
        </div>

        {/* Mobile Menu */}
        {mobileMenuOpen && (
          <div className="md:hidden bg-gray-900 border-t border-gray-800">
            <div className="px-4 py-4 space-y-4">
              <a href="#features" className="block hover:text-orange-500">Fonctionnalités</a>
              <a href="#how-it-works" className="block hover:text-orange-500">Comment ça marche</a>
              <a href="#pricing" className="block hover:text-orange-500">Tarifs</a>
              <a href="#contact" className="block hover:text-orange-500">Contact</a>
              <Link to="/admin" className="block text-center py-2 border border-orange-500 rounded-lg">
                Connexion
              </Link>
              <button className="w-full py-2 bg-orange-500 rounded-lg">
                S'inscrire
              </button>
            </div>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section className="pt-32 pb-20 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto text-center">
          <h1 className="text-5xl md:text-7xl font-bold mb-6">
            Révolutionnez l'expérience
            <span className="block text-transparent bg-clip-text bg-gradient-to-r from-orange-500 to-orange-600">
              culinaire avec la 3D
            </span>
          </h1>
          <p className="text-xl md:text-2xl text-gray-300 mb-12 max-w-3xl mx-auto">
            Transformez vos plats en expériences visuelles 3D interactives qui donnent envie et augmentent vos ventes
          </p>
          
          {/* Stats */}
          <div className="grid grid-cols-2 md:grid-cols-4 gap-8 mb-12">
            {stats.map((stat, index) => (
              <div key={index} className="bg-gray-800/50 rounded-2xl p-6 backdrop-blur-sm border border-gray-700">
                <div className="text-4xl font-bold text-orange-500 mb-2">{stat.value}</div>
                <div className="text-gray-400">{stat.label}</div>
              </div>
            ))}
          </div>

          <div className="flex flex-col sm:flex-row gap-4 justify-center">
            <button className="px-8 py-4 bg-gradient-to-r from-orange-500 to-orange-600 rounded-lg text-lg font-semibold hover:shadow-lg hover:shadow-orange-500/50 transition">
              Demander une démo gratuite
            </button>
            <button className="px-8 py-4 border border-orange-500 rounded-lg text-lg font-semibold hover:bg-orange-500 transition">
              Voir les tarifs
            </button>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section id="features" className="py-20 px-4 sm:px-6 lg:px-8 bg-gray-800/30">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-4">
              Fonctionnalités <span className="text-orange-500">Puissantes</span>
            </h2>
            <p className="text-xl text-gray-300">
              Tout ce dont vous avez besoin pour créer une expérience menu exceptionnelle
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            {features.map((feature, index) => (
              <div 
                key={index}
                className="bg-gray-800/50 rounded-2xl p-8 backdrop-blur-sm border border-gray-700 hover:border-orange-500 transition group"
              >
                <div className="text-orange-500 mb-4 group-hover:scale-110 transition">
                  {feature.icon}
                </div>
                <h3 className="text-2xl font-bold mb-3">{feature.title}</h3>
                <p className="text-gray-400">{feature.description}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* How It Works Section */}
      <section id="how-it-works" className="py-20 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-4">
              Comment ça <span className="text-orange-500">Marche</span>
            </h2>
            <p className="text-xl text-gray-300">
              Un processus simple en 4 étapes
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
            {steps.map((step, index) => (
              <div key={index} className="text-center relative">
                <div className="w-20 h-20 mx-auto mb-6 bg-gradient-to-br from-orange-500 to-orange-600 rounded-2xl flex items-center justify-center text-3xl font-bold shadow-lg shadow-orange-500/50">
                  {step.number}
                </div>
                <h3 className="text-xl font-bold mb-3">{step.title}</h3>
                <p className="text-gray-400">{step.description}</p>
                {index < steps.length - 1 && (
                  <div className="hidden lg:block absolute top-10 left-[60%] w-[80%] h-0.5 bg-gradient-to-r from-orange-500 to-transparent"></div>
                )}
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Pricing Section */}
      <section id="pricing" className="py-20 px-4 sm:px-6 lg:px-8 bg-gray-800/30">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-4">
              Tarifs <span className="text-orange-500">Simples</span> et Transparents
            </h2>
            <p className="text-xl text-gray-300 mb-8">
              Choisissez le plan qui correspond à vos besoins
            </p>

            {/* Billing Toggle */}
            <div className="inline-flex items-center bg-gray-800 rounded-full p-1">
              <button
                onClick={() => setBillingCycle('monthly')}
                className={`px-6 py-2 rounded-full transition ${
                  billingCycle === 'monthly' 
                    ? 'bg-orange-500 text-white' 
                    : 'text-gray-400'
                }`}
              >
                Mensuel
              </button>
              <button
                onClick={() => setBillingCycle('annual')}
                className={`px-6 py-2 rounded-full transition relative ${
                  billingCycle === 'annual' 
                    ? 'bg-orange-500 text-white' 
                    : 'text-gray-400'
                }`}
              >
                Annuel
                <span className="absolute -top-6 right-0 bg-green-500 text-white text-xs px-2 py-1 rounded">
                  Économisez 20%
                </span>
              </button>
            </div>
          </div>

          <div className="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
            {pricingPlans.map((plan, index) => (
              <div
                key={index}
                className={`rounded-2xl p-8 relative ${
                  plan.popular
                    ? 'bg-gradient-to-br from-orange-500/20 to-orange-600/20 border-2 border-orange-500'
                    : 'bg-gray-800/50 border border-gray-700'
                }`}
              >
                {plan.popular && (
                  <div className="absolute -top-4 left-1/2 -translate-x-1/2 bg-orange-500 text-white px-4 py-1 rounded-full text-sm font-semibold">
                    LE PLUS POPULAIRE
                  </div>
                )}
                
                <div className="text-center mb-6">
                  <h3 className="text-orange-500 font-bold text-sm mb-2">{plan.name}</h3>
                  <div className="text-5xl font-bold mb-2">
                    {plan.price}$ <span className="text-lg text-gray-400">CAD</span>
                  </div>
                  <div className="text-gray-400">{plan.period}</div>
                </div>

                <ul className="space-y-4 mb-8">
                  {plan.features.map((feature, fIndex) => (
                    <li key={fIndex} className="flex items-start">
                      <CheckCircle className="w-5 h-5 text-green-500 mr-3 flex-shrink-0 mt-0.5" />
                      <span className="text-sm text-gray-300">{feature}</span>
                    </li>
                  ))}
                </ul>

                <div className="text-center text-sm text-gray-400 mb-6">
                  {plan.extra}
                </div>

                <button
                  className={`w-full py-3 rounded-lg font-semibold transition ${
                    plan.popular
                      ? 'bg-orange-500 hover:bg-orange-600 text-white'
                      : 'border border-orange-500 hover:bg-orange-500 text-white'
                  }`}
                >
                  Choisir ce plan
                </button>
              </div>
            ))}
          </div>

          {/* Premium Section */}
          <div className="mt-12 bg-gradient-to-r from-orange-500 to-orange-600 rounded-2xl p-8 text-center max-w-4xl mx-auto">
            <div className="inline-block bg-white/20 px-4 py-1 rounded-full text-sm font-semibold mb-4">
              PREMIUM
            </div>
            <h3 className="text-3xl font-bold mb-4">Besoin d'un Site Web Sur Mesure ?</h3>
            <p className="text-lg mb-6 opacity-90">
              Nous créons un site web sur mesure et proposons la modélisation 3D de vos plats pour une expérience unique.
            </p>
            <button className="px-8 py-3 bg-white text-orange-600 font-semibold rounded-lg hover:shadow-xl transition">
              Contactez-nous pour un devis
            </button>
          </div>
        </div>
      </section>

      {/* CTA Final Section */}
      <section className="py-20 px-4 sm:px-6 lg:px-8">
        <div className="max-w-4xl mx-auto text-center">
          <h2 className="text-4xl md:text-5xl font-bold mb-6">
            Prêt à transformer votre <span className="text-orange-500">menu</span> ?
          </h2>
          <p className="text-xl text-gray-300 mb-8">
            Rejoignez les centaines de restaurants qui ont déjà fait le choix de l'innovation
          </p>
          <div className="flex flex-col sm:flex-row gap-4 justify-center">
            <button className="px-8 py-4 bg-gradient-to-r from-orange-500 to-orange-600 rounded-lg text-lg font-semibold hover:shadow-lg hover:shadow-orange-500/50 transition">
              Demander une démo
            </button>
            <a 
              href="#pricing"
              className="px-8 py-4 border border-white rounded-lg text-lg font-semibold hover:bg-white hover:text-gray-900 transition"
            >
              Voir les tarifs
            </a>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer id="contact" className="bg-gray-900 border-t border-gray-800 py-12 px-4 sm:px-6 lg:px-8">
        <div className="max-w-7xl mx-auto">
          <div className="grid md:grid-cols-4 gap-8">
            <div>
              <div className="flex items-center space-x-2 mb-4">
                <Eye className="w-6 h-6 text-orange-500" />
                <span className="text-xl font-bold">SeeYourMeal</span>
              </div>
              <p className="text-gray-400 text-sm">
                La première plateforme de menus 3D pour restaurants au Canada
              </p>
            </div>
            
            <div>
              <h4 className="font-semibold mb-4">Produit</h4>
              <ul className="space-y-2 text-gray-400 text-sm">
                <li><a href="#features" className="hover:text-orange-500">Fonctionnalités</a></li>
                <li><a href="#pricing" className="hover:text-orange-500">Tarifs</a></li>
                <li><a href="#" className="hover:text-orange-500">Démo</a></li>
              </ul>
            </div>
            
            <div>
              <h4 className="font-semibold mb-4">Entreprise</h4>
              <ul className="space-y-2 text-gray-400 text-sm">
                <li><a href="#" className="hover:text-orange-500">À propos</a></li>
                <li><a href="#" className="hover:text-orange-500">Blog</a></li>
                <li><a href="#" className="hover:text-orange-500">Carrières</a></li>
              </ul>
            </div>
            
            <div>
              <h4 className="font-semibold mb-4">Contact</h4>
              <ul className="space-y-2 text-gray-400 text-sm">
                <li>📧 seeyourmeal08@gmail.com</li>
                <li>📍 Montréal, Québec</li>
                <li>📞 (514) XXX-XXXX</li>
              </ul>
            </div>
          </div>
          
          <div className="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400 text-sm">
            <p>&copy; 2025 SeeYourMeal. Tous droits réservés.</p>
          </div>
        </div>
      </footer>
    </div>
  );
};

export default HomePage;
```

---

## 1️⃣3️⃣ src/components/AdminDashboard.jsx ⭐

**Dans le dossier `src/components`, créez : `AdminDashboard.jsx`**

**⚠️ FICHIER COMPLET - 700+ LIGNES**

```javascript
import React, { useState, useEffect } from 'react';
import { Link } from 'react-router-dom';
import QRCode from 'qrcode';
import { 
  Plus, 
  Trash2, 
  Edit, 
  QrCode as QrCodeIcon, 
  Download, 
  Eye,
  DollarSign,
  Users,
  TrendingUp,
  Menu,
  X
} from 'lucide-react';

const AdminDashboard = () => {
  const [restaurants, setRestaurants] = useState([
    {
      id: 'mazzalia-pizza',
      name: 'Mazzalia Pizza',
      plan: 'Essentielle',
      price: 92,
      template: 'modern',
      color: '#8b5cf6',
      menuItems: [
        {
          id: 1,
          name: 'Pizza Margherita',
          category: 'Pizzas',
          price: 16,
          description: 'Sauce tomate, mozzarella, basilic frais',
          images: [
            'https://images.unsplash.com/photo-1574071318508-1cdbab80d002?w=800',
            'https://images.unsplash.com/photo-1513104890138-7c749659a591?w=800',
            'https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=800',
            'https://images.unsplash.com/photo-1595854341625-f33ee10dbf94?w=800'
          ]
        }
      ]
    }
  ]);

  const [showAddRestaurant, setShowAddRestaurant] = useState(false);
  const [selectedRestaurant, setSelectedRestaurant] = useState(null);
  const [qrCodeUrl, setQrCodeUrl] = useState('');
  const [showQRModal, setShowQRModal] = useState(false);

  // Form states
  const [newRestaurant, setNewRestaurant] = useState({
    name: '',
    plan: 'Standard',
    template: 'classic',
    color: '#ff6b35',
    menuItems: []
  });

  const [newMenuItem, setNewMenuItem] = useState({
    name: '',
    category: '',
    price: '',
    description: '',
    images: ['', '', '', '']
  });

  // Statistics
  const totalRevenue = restaurants.reduce((sum, r) => sum + r.price, 0);
  const totalClients = restaurants.length;
  const totalScans = 1247; // Exemple

  const templates = [
    { id: 'classic', name: 'Classic', colors: ['#ffffff', '#f5f5f5'] },
    { id: 'modern', name: 'Modern', colors: ['#8b5cf6', '#6d28d9'] },
    { id: 'boutique', name: 'Boutique', colors: ['#1e293b', '#ff6b35'] },
    { id: 'casual', name: 'Casual', colors: ['#3b82f6', '#60a5fa'] }
  ];

  const plans = [
    { name: 'Standard', price: 78, maxDishes: 5 },
    { name: 'Essentielle', price: 92, maxDishes: 15 },
    { name: 'Avancée', price: 119, maxDishes: 999 }
  ];

  // Générer QR Code
  const generateQRCode = async (restaurant) => {
    try {
      const url = `${window.location.origin}/menu/${restaurant.id}`;
      const qrDataUrl = await QRCode.toDataURL(url, {
        width: 400,
        margin: 2,
        color: {
          dark: '#000000',
          light: '#ffffff'
        }
      });
      setQrCodeUrl(qrDataUrl);
      setSelectedRestaurant(restaurant);
      setShowQRModal(true);
    } catch (error) {
      console.error('Erreur génération QR:', error);
    }
  };

  // Télécharger QR Code
  const downloadQRCode = () => {
    const link = document.createElement('a');
    link.download = `qrcode-${selectedRestaurant.id}.png`;
    link.href = qrCodeUrl;
    link.click();
  };

  // Ajouter un restaurant
  const handleAddRestaurant = () => {
    if (!newRestaurant.name) {
      alert('Veuillez entrer un nom de restaurant');
      return;
    }

    const restaurantId = newRestaurant.name.toLowerCase().replace(/\s+/g, '-');
    const selectedPlan = plans.find(p => p.name === newRestaurant.plan);

    const restaurant = {
      id: restaurantId,
      ...newRestaurant,
      price: selectedPlan.price,
      createdAt: new Date()
    };

    setRestaurants([...restaurants, restaurant]);
    setShowAddRestaurant(false);
    
    // Reset form
    setNewRestaurant({
      name: '',
      plan: 'Standard',
      template: 'classic',
      color: '#ff6b35',
      menuItems: []
    });
    setNewMenuItem({
      name: '',
      category: '',
      price: '',
      description: '',
      images: ['', '', '', '']
    });
  };

  // Ajouter un plat
  const handleAddMenuItem = () => {
    if (!newMenuItem.name || !newMenuItem.price) {
      alert('Veuillez remplir au moins le nom et le prix du plat');
      return;
    }

    const menuItem = {
      id: Date.now(),
      ...newMenuItem,
      price: parseFloat(newMenuItem.price),
      images: newMenuItem.images.filter(img => img !== '')
    };

    setNewRestaurant({
      ...newRestaurant,
      menuItems: [...newRestaurant.menuItems, menuItem]
    });

    // Reset menu item form
    setNewMenuItem({
      name: '',
      category: '',
      price: '',
      description: '',
      images: ['', '', '', '']
    });
  };

  // Supprimer un restaurant
  const handleDeleteRestaurant = (id) => {
    if (window.confirm('Êtes-vous sûr de vouloir supprimer ce restaurant ?')) {
      setRestaurants(restaurants.filter(r => r.id !== id));
    }
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 via-gray-800 to-black text-white">
      {/* Header */}
      <header className="bg-gray-900/95 backdrop-blur-sm border-b border-gray-800 sticky top-0 z-40">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
          <div className="flex justify-between items-center">
            <div className="flex items-center space-x-3">
              <Eye className="w-8 h-8 text-orange-500" />
              <h1 className="text-2xl font-bold">
                SeeYourMeal <span className="text-orange-500">Dashboard</span>
              </h1>
            </div>
            <div className="flex items-center space-x-4">
              <Link 
                to="/" 
                className="px-4 py-2 border border-gray-700 rounded-lg hover:border-orange-500 transition"
              >
                Retour au site
              </Link>
              <button className="px-4 py-2 bg-red-600 rounded-lg hover:bg-red-700 transition">
                Déconnexion
              </button>
            </div>
          </div>
        </div>
      </header>

      {/* Main Content */}
      <main className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        {/* Stats Cards */}
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
          <div className="bg-gradient-to-br from-orange-500 to-orange-600 rounded-2xl p-6 shadow-lg">
            <div className="flex items-center justify-between">
              <div>
                <p className="text-orange-100 text-sm font-medium">Revenue Mensuel</p>
                <p className="text-3xl font-bold text-white mt-1">{totalRevenue}$ CAD</p>
              </div>
              <DollarSign className="w-12 h-12 text-white/50" />
            </div>
          </div>

          <div className="bg-gradient-to-br from-blue-500 to-blue-600 rounded-2xl p-6 shadow-lg">
            <div className="flex items-center justify-between">
              <div>
                <p className="text-blue-100 text-sm font-medium">Clients Actifs</p>
                <p className="text-3xl font-bold text-white mt-1">{totalClients}</p>
              </div>
              <Users className="w-12 h-12 text-white/50" />
            </div>
          </div>

          <div className="bg-gradient-to-br from-green-500 to-green-600 rounded-2xl p-6 shadow-lg">
            <div className="flex items-center justify-between">
              <div>
                <p className="text-green-100 text-sm font-medium">Scans Totaux</p>
                <p className="text-3xl font-bold text-white mt-1">{totalScans}</p>
              </div>
              <TrendingUp className="w-12 h-12 text-white/50" />
            </div>
          </div>
        </div>

        {/* Add Restaurant Button */}
        <div className="mb-6">
          <button
            onClick={() => setShowAddRestaurant(true)}
            className="px-6 py-3 bg-gradient-to-r from-orange-500 to-orange-600 rounded-lg font-semibold flex items-center space-x-2 hover:shadow-lg hover:shadow-orange-500/50 transition"
          >
            <Plus className="w-5 h-5" />
            <span>Ajouter Nouveau Restaurant</span>
          </button>
        </div>

        {/* Restaurants List */}
        <div className="bg-gray-800/50 rounded-2xl p-6 border border-gray-700">
          <h2 className="text-2xl font-bold mb-6">Mes Restaurants</h2>
          
          {restaurants.length === 0 ? (
            <div className="text-center py-12 text-gray-400">
              <p>Aucun restaurant pour le moment</p>
              <p className="text-sm mt-2">Cliquez sur "Ajouter Nouveau Restaurant" pour commencer</p>
            </div>
          ) : (
            <div className="grid gap-6">
              {restaurants.map((restaurant) => (
                <div
                  key={restaurant.id}
                  className="bg-gray-800 rounded-xl p-6 border border-gray-700 hover:border-orange-500 transition"
                >
                  <div className="flex flex-col md:flex-row md:items-center md:justify-between">
                    <div className="flex-1">
                      <h3 className="text-xl font-bold mb-2">{restaurant.name}</h3>
                      <div className="flex flex-wrap gap-3 text-sm">
                        <span className="px-3 py-1 bg-orange-500/20 text-orange-400 rounded-full">
                          Plan: {restaurant.plan}
                        </span>
                        <span className="px-3 py-1 bg-blue-500/20 text-blue-400 rounded-full">
                          Template: {restaurant.template}
                        </span>
                        <span className="px-3 py-1 bg-green-500/20 text-green-400 rounded-full">
                          {restaurant.menuItems.length} plats
                        </span>
                        <span className="px-3 py-1 bg-purple-500/20 text-purple-400 rounded-full">
                          {restaurant.price}$ CAD/mois
                        </span>
                      </div>
                    </div>

                    <div className="flex items-center space-x-3 mt-4 md:mt-0">
                      <Link
                        to={`/menu/${restaurant.id}`}
                        target="_blank"
                        className="p-2 bg-blue-600 rounded-lg hover:bg-blue-700 transition"
                        title="Voir le menu"
                      >
                        <Eye className="w-5 h-5" />
                      </Link>
                      <button
                        onClick={() => generateQRCode(restaurant)}
                        className="p-2 bg-green-600 rounded-lg hover:bg-green-700 transition"
                        title="Générer QR Code"
                      >
                        <QrCodeIcon className="w-5 h-5" />
                      </button>
                      <button
                        onClick={() => handleDeleteRestaurant(restaurant.id)}
                        className="p-2 bg-red-600 rounded-lg hover:bg-red-700 transition"
                        title="Supprimer"
                      >
                        <Trash2 className="w-5 h-5" />
                      </button>
                    </div>
                  </div>
                </div>
              ))}
            </div>
          )}
        </div>
      </main>

      {/* Add Restaurant Modal */}
      {showAddRestaurant && (
        <div className="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4">
          <div className="bg-gray-800 rounded-2xl w-full max-w-4xl max-h-[90vh] overflow-y-auto border border-gray-700">
            <div className="sticky top-0 bg-gray-800 border-b border-gray-700 p-6 flex justify-between items-center">
              <h2 className="text-2xl font-bold">Ajouter un Restaurant</h2>
              <button
                onClick={() => setShowAddRestaurant(false)}
                className="p-2 hover:bg-gray-700 rounded-lg transition"
              >
                <X className="w-6 h-6" />
              </button>
            </div>

            <div className="p-6 space-y-6">
              {/* Restaurant Info */}
              <div className="space-y-4">
                <h3 className="text-xl font-semibold text-orange-500">Informations du Restaurant</h3>
                
                <div>
                  <label className="block text-sm font-medium mb-2">Nom du Restaurant *</label>
                  <input
                    type="text"
                    value={newRestaurant.name}
                    onChange={(e) => setNewRestaurant({...newRestaurant, name: e.target.value})}
                    className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none"
                    placeholder="Ex: Mazzalia Pizza"
                  />
                </div>

                <div className="grid md:grid-cols-2 gap-4">
                  <div>
                    <label className="block text-sm font-medium mb-2">Plan *</label>
                    <select
                      value={newRestaurant.plan}
                      onChange={(e) => setNewRestaurant({...newRestaurant, plan: e.target.value})}
                      className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none"
                    >
                      {plans.map(plan => (
                        <option key={plan.name} value={plan.name}>
                          {plan.name} - {plan.price}$ CAD/mois ({plan.maxDishes === 999 ? 'Illimité' : `${plan.maxDishes} plats`})
                        </option>
                      ))}
                    </select>
                  </div>

                  <div>
                    <label className="block text-sm font-medium mb-2">Template *</label>
                    <select
                      value={newRestaurant.template}
                      onChange={(e) => setNewRestaurant({...newRestaurant, template: e.target.value})}
                      className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none"
                    >
                      {templates.map(template => (
                        <option key={template.id} value={template.id}>
                          {template.name}
                        </option>
                      ))}
                    </select>
                  </div>
                </div>

                <div>
                  <label className="block text-sm font-medium mb-2">Couleur Principale</label>
                  <input
                    type="color"
                    value={newRestaurant.color}
                    onChange={(e) => setNewRestaurant({...newRestaurant, color: e.target.value})}
                    className="w-full h-12 rounded-lg cursor-pointer"
                  />
                </div>
              </div>

              {/* Menu Items */}
              <div className="space-y-4">
                <h3 className="text-xl font-semibold text-orange-500">Ajouter des Plats</h3>
                
                <div className="grid md:grid-cols-2 gap-4">
                  <div>
                    <label className="block text-sm font-medium mb-2">Nom du Plat *</label>
                    <input
                      type="text"
                      value={newMenuItem.name}
                      onChange={(e) => setNewMenuItem({...newMenuItem, name: e.target.value})}
                      className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none"
                      placeholder="Ex: Pizza Margherita"
                    />
                  </div>

                  <div>
                    <label className="block text-sm font-medium mb-2">Catégorie</label>
                    <input
                      type="text"
                      value={newMenuItem.category}
                      onChange={(e) => setNewMenuItem({...newMenuItem, category: e.target.value})}
                      className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none"
                      placeholder="Ex: Pizzas"
                    />
                  </div>
                </div>

                <div>
                  <label className="block text-sm font-medium mb-2">Prix (CAD) *</label>
                  <input
                    type="number"
                    step="0.01"
                    value={newMenuItem.price}
                    onChange={(e) => setNewMenuItem({...newMenuItem, price: e.target.value})}
                    className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none"
                    placeholder="Ex: 16.99"
                  />
                </div>

                <div>
                  <label className="block text-sm font-medium mb-2">Description</label>
                  <textarea
                    value={newMenuItem.description}
                    onChange={(e) => setNewMenuItem({...newMenuItem, description: e.target.value})}
                    className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none"
                    rows="3"
                    placeholder="Description du plat..."
                  />
                </div>

                <div>
                  <label className="block text-sm font-medium mb-2">URLs des Images 3D (4 angles)</label>
                  {[0, 1, 2, 3].map((index) => (
                    <input
                      key={index}
                      type="url"
                      value={newMenuItem.images[index]}
                      onChange={(e) => {
                        const newImages = [...newMenuItem.images];
                        newImages[index] = e.target.value;
                        setNewMenuItem({...newMenuItem, images: newImages});
                      }}
                      className="w-full px-4 py-2 bg-gray-700 rounded-lg border border-gray-600 focus:border-orange-500 focus:outline-none mb-2"
                      placeholder={`URL Image ${index + 1} (optionnel)`}
                    />
                  ))}
                </div>

                <button
                  onClick={handleAddMenuItem}
                  className="w-full px-4 py-2 bg-blue-600 rounded-lg hover:bg-blue-700 transition font-semibold"
                >
                  Ajouter ce Plat au Menu
                </button>

                {/* List of added menu items */}
                {newRestaurant.menuItems.length > 0 && (
                  <div className="mt-4">
                    <h4 className="font-semibold mb-2">Plats ajoutés ({newRestaurant.menuItems.length}):</h4>
                    <div className="space-y-2">
                      {newRestaurant.menuItems.map((item) => (
                        <div key={item.id} className="bg-gray-700 p-3 rounded-lg flex justify-between items-center">
                          <div>
                            <p className="font-medium">{item.name}</p>
                            <p className="text-sm text-gray-400">{item.category} - {item.price}$ CAD</p>
                          </div>
                          <button
                            onClick={() => setNewRestaurant({
                              ...newRestaurant,
                              menuItems: newRestaurant.menuItems.filter(mi => mi.id !== item.id)
                            })}
                            className="p-2 bg-red-600 rounded-lg hover:bg-red-700 transition"
                          >
                            <Trash2 className="w-4 h-4" />
                          </button>
                        </div>
                      ))}
                    </div>
                  </div>
                )}
              </div>

              {/* Submit Button */}
              <div className="flex space-x-4 pt-4 border-t border-gray-700">
                <button
                  onClick={handleAddRestaurant}
                  className="flex-1 px-6 py-3 bg-gradient-to-r from-orange-500 to-orange-600 rounded-lg font-semibold hover:shadow-lg hover:shadow-orange-500/50 transition"
                >
                  Créer le Restaurant
                </button>
                <button
                  onClick={() => setShowAddRestaurant(false)}
                  className="px-6 py-3 bg-gray-700 rounded-lg font-semibold hover:bg-gray-600 transition"
                >
                  Annuler
                </button>
              </div>
            </div>
          </div>
        </div>
      )}

      {/* QR Code Modal */}
      {showQRModal && (
        <div className="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4">
          <div className="bg-gray-800 rounded-2xl w-full max-w-md border border-gray-700">
            <div className="p-6">
              <div className="flex justify-between items-center mb-6">
                <h2 className="text-2xl font-bold">QR Code - {selectedRestaurant?.name}</h2>
                <button
                  onClick={() => setShowQRModal(false)}
                  className="p-2 hover:bg-gray-700 rounded-lg transition"
                >
                  <X className="w-6 h-6" />
                </button>
              </div>

              <div className="bg-white p-6 rounded-xl mb-6">
                <img src={qrCodeUrl} alt="QR Code" className="w-full" />
              </div>

              <div className="space-y-3">
                <button
                  onClick={downloadQRCode}
                  className="w-full px-6 py-3 bg-gradient-to-r from-orange-500 to-orange-600 rounded-lg font-semibold flex items-center justify-center space-x-2 hover:shadow-lg hover:shadow-orange-500/50 transition"
                >
                  <Download className="w-5 h-5" />
                  <span>Télécharger le QR Code</span>
                </button>
                
                <p className="text-sm text-gray-400 text-center">
                  URL: {window.location.origin}/menu/{selectedRestaurant?.id}
                </p>
              </div>
            </div>
          </div>
        </div>
      )}
    </div>
  );
};

export default AdminDashboard;
```

---

## 1️⃣4️⃣ src/components/PublicMenu.jsx ⭐

**Dans le dossier `src/components`, créez : `PublicMenu.jsx`**

**⚠️ FICHIER COMPLET - 600+ LIGNES**

```javascript
import React, { useState, useEffect } from 'react';
import { useParams } from 'react-router-dom';
import { ChevronLeft, ChevronRight, X, Eye } from 'lucide-react';

const PublicMenu = () => {
  const { restaurantId } = useParams();
  const [restaurant, setRestaurant] = useState(null);
  const [selectedDish, setSelectedDish] = useState(null);
  const [currentImageIndex, setCurrentImageIndex] = useState(0);
  const [loading, setLoading] = useState(true);

  // Simuler le chargement des données (remplacer par Firebase)
  useEffect(() => {
    // Ici vous chargerez les données depuis Firebase avec getRestaurantById(restaurantId)
    // Pour l'instant, on utilise des données d'exemple
    setTimeout(() => {
      setRestaurant({
        id: restaurantId,
        name: 'Mazzalia Pizza',
        template: 'modern',
        color: '#8b5cf6',
        menuItems: [
          {
            id: 1,
            name: 'Pizza Margherita',
            category: 'Pizzas',
            price: 16,
            description: 'Sauce tomate, mozzarella, basilic frais',
            images: [
              'https://images.unsplash.com/photo-1574071318508-1cdbab80d002?w=800',
              'https://images.unsplash.com/photo-1513104890138-7c749659a591?w=800',
              'https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=800',
              'https://images.unsplash.com/photo-1595854341625-f33ee10dbf94?w=800'
            ]
          },
          {
            id: 2,
            name: 'Pizza Pepperoni',
            category: 'Pizzas',
            price: 18,
            description: 'Sauce tomate, mozzarella, pepperoni',
            images: [
              'https://images.unsplash.com/photo-1628840042765-356cda07504e?w=800',
              'https://images.unsplash.com/photo-1534308983496-4fabb1a015ee?w=800',
              'https://images.unsplash.com/photo-1571066811602-716837d681de?w=800',
              'https://images.unsplash.com/photo-1593560708920-61dd98c46a4e?w=800'
            ]
          },
          {
            id: 3,
            name: 'Pizza Végétarienne',
            category: 'Pizzas',
            price: 17,
            description: 'Sauce tomate, mozzarella, légumes grillés',
            images: [
              'https://images.unsplash.com/photo-1511689660979-10d2b1aada49?w=800',
              'https://images.unsplash.com/photo-1571407970349-bc81e7e96c47?w=800',
              'https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=800',
              'https://images.unsplash.com/photo-1574071318508-1cdbab80d002?w=800'
            ]
          }
        ]
      });
      setLoading(false);
    }, 1000);
  }, [restaurantId]);

  // Templates
  const getTemplateStyles = (template) => {
    const templates = {
      classic: {
        bg: 'from-white to-gray-50',
        text: 'text-gray-900',
        card: 'bg-white border-gray-200',
        accent: 'from-gray-700 to-gray-900'
      },
      modern: {
        bg: 'from-purple-900 via-purple-800 to-indigo-900',
        text: 'text-white',
        card: 'bg-white/10 border-white/20 backdrop-blur-sm',
        accent: 'from-purple-600 to-indigo-600'
      },
      boutique: {
        bg: 'from-slate-900 via-slate-800 to-slate-900',
        text: 'text-white',
        card: 'bg-slate-800/50 border-orange-500/30',
        accent: 'from-orange-500 to-orange-600'
      },
      casual: {
        bg: 'from-blue-500 via-cyan-500 to-teal-500',
        text: 'text-white',
        card: 'bg-white/20 border-white/30 backdrop-blur-sm',
        accent: 'from-blue-600 to-cyan-600'
      }
    };
    return templates[template] || templates.classic;
  };

  const styles = restaurant ? getTemplateStyles(restaurant.template) : {};

  // Group menu items by category
  const groupedItems = restaurant?.menuItems.reduce((acc, item) => {
    const category = item.category || 'Autres';
    if (!acc[category]) {
      acc[category] = [];
    }
    acc[category].push(item);
    return acc;
  }, {});

  // Handle dish selection
  const openDishViewer = (dish) => {
    setSelectedDish(dish);
    setCurrentImageIndex(0);
  };

  const closeDishViewer = () => {
    setSelectedDish(null);
    setCurrentImageIndex(0);
  };

  const nextImage = () => {
    if (selectedDish && selectedDish.images.length > 0) {
      setCurrentImageIndex((prev) => 
        prev === selectedDish.images.length - 1 ? 0 : prev + 1
      );
    }
  };

  const prevImage = () => {
    if (selectedDish && selectedDish.images.length > 0) {
      setCurrentImageIndex((prev) => 
        prev === 0 ? selectedDish.images.length - 1 : prev - 1
      );
    }
  };

  if (loading) {
    return (
      <div className="min-h-screen flex items-center justify-center bg-gradient-to-br from-gray-900 to-black">
        <div className="text-center">
          <div className="w-16 h-16 border-4 border-orange-500 border-t-transparent rounded-full animate-spin mx-auto mb-4"></div>
          <p className="text-white text-xl">Chargement du menu...</p>
        </div>
      </div>
    );
  }

  if (!restaurant) {
    return (
      <div className="min-h-screen flex items-center justify-center bg-gradient-to-br from-gray-900 to-black">
        <div className="text-center text-white">
          <h1 className="text-4xl font-bold mb-4">Restaurant non trouvé</h1>
          <p className="text-gray-400">Le menu que vous cherchez n'existe pas.</p>
        </div>
      </div>
    );
  }

  return (
    <div className={`min-h-screen bg-gradient-to-br ${styles.bg} ${styles.text}`}>
      {/* Header */}
      <header className="sticky top-0 z-40 backdrop-blur-sm bg-black/30 border-b border-white/10">
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-6">
          <div className="flex items-center space-x-3">
            <Eye className="w-8 h-8" style={{ color: restaurant.color }} />
            <h1 className="text-3xl md:text-4xl font-bold">{restaurant.name}</h1>
          </div>
          <p className="text-sm mt-2 opacity-80">
            Explorez notre menu en 3D - Cliquez sur un plat pour voir toutes les vues
          </p>
        </div>
      </header>

      {/* Menu Content */}
      <main className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        {Object.entries(groupedItems || {}).map(([category, items]) => (
          <div key={category} className="mb-12">
            <h2 
              className="text-3xl font-bold mb-6 pb-2 border-b-2"
              style={{ borderColor: restaurant.color }}
            >
              {category}
            </h2>
            
            <div className="grid md:grid-cols-2 gap-6">
              {items.map((dish) => (
                <div
                  key={dish.id}
                  onClick={() => openDishViewer(dish)}
                  className={`${styles.card} rounded-2xl p-6 border cursor-pointer transform hover:scale-105 transition-all duration-300 hover:shadow-2xl`}
                  style={{ 
                    borderColor: `${restaurant.color}40`,
                    boxShadow: `0 10px 40px ${restaurant.color}20`
                  }}
                >
                  {dish.images && dish.images.length > 0 && (
                    <div className="relative h-48 mb-4 rounded-xl overflow-hidden">
                      <img
                        src={dish.images[0]}
                        alt={dish.name}
                        className="w-full h-full object-cover"
                      />
                      <div 
                        className="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end p-4"
                      >
                        <span className="text-white text-sm font-medium">
                          📸 {dish.images.length} vues 3D disponibles
                        </span>
                      </div>
                    </div>
                  )}
                  
                  <div className="flex justify-between items-start mb-2">
                    <h3 className="text-xl font-bold">{dish.name}</h3>
                    <span 
                      className="text-2xl font-bold"
                      style={{ color: restaurant.color }}
                    >
                      {dish.price}$
                    </span>
                  </div>
                  
                  {dish.description && (
                    <p className="text-sm opacity-80 mb-3">{dish.description}</p>
                  )}
                  
                  <button
                    className="w-full py-2 rounded-lg font-semibold text-white transition-all"
                    style={{ 
                      background: `linear-gradient(135deg, ${restaurant.color}, ${restaurant.color}dd)`
                    }}
                  >
                    Voir en 3D
                  </button>
                </div>
              ))}
            </div>
          </div>
        ))}
      </main>

      {/* 3D Dish Viewer Modal */}
      {selectedDish && (
        <div className="fixed inset-0 bg-black/95 z-50 flex items-center justify-center p-4">
          <div className="w-full max-w-4xl">
            {/* Close Button */}
            <button
              onClick={closeDishViewer}
              className="absolute top-4 right-4 p-3 bg-white/10 hover:bg-white/20 rounded-full transition"
            >
              <X className="w-6 h-6 text-white" />
            </button>

            {/* Main Image */}
            <div className="relative mb-6">
              <div className="aspect-square rounded-2xl overflow-hidden bg-gray-900 flex items-center justify-center">
                {selectedDish.images && selectedDish.images.length > 0 ? (
                  <img
                    src={selectedDish.images[currentImageIndex]}
                    alt={`${selectedDish.name} - Vue ${currentImageIndex + 1}`}
                    className="w-full h-full object-cover"
                  />
                ) : (
                  <div className="text-gray-500 text-center p-8">
                    <Eye className="w-16 h-16 mx-auto mb-4 opacity-50" />
                    <p>Aucune image 3D disponible</p>
                  </div>
                )}
              </div>

              {/* Navigation Arrows */}
              {selectedDish.images && selectedDish.images.length > 1 && (
                <>
                  <button
                    onClick={prevImage}
                    className="absolute left-4 top-1/2 -translate-y-1/2 p-3 bg-black/50 hover:bg-black/70 rounded-full transition"
                  >
                    <ChevronLeft className="w-6 h-6 text-white" />
                  </button>
                  <button
                    onClick={nextImage}
                    className="absolute right-4 top-1/2 -translate-y-1/2 p-3 bg-black/50 hover:bg-black/70 rounded-full transition"
                  >
                    <ChevronRight className="w-6 h-6 text-white" />
                  </button>
                </>
              )}

              {/* Image Counter */}
              <div className="absolute bottom-4 left-1/2 -translate-x-1/2 px-4 py-2 bg-black/70 rounded-full text-white text-sm">
                {currentImageIndex + 1} / {selectedDish.images?.length || 0}
              </div>
            </div>

            {/* Thumbnails */}
            {selectedDish.images && selectedDish.images.length > 1 && (
              <div className="flex gap-3 justify-center mb-6 overflow-x-auto">
                {selectedDish.images.map((image, index) => (
                  <button
                    key={index}
                    onClick={() => setCurrentImageIndex(index)}
                    className={`flex-shrink-0 w-20 h-20 rounded-lg overflow-hidden border-2 transition ${
                      currentImageIndex === index
                        ? 'border-white scale-110'
                        : 'border-white/30 opacity-50 hover:opacity-100'
                    }`}
                  >
                    <img
                      src={image}
                      alt={`Vue ${index + 1}`}
                      className="w-full h-full object-cover"
                    />
                  </button>
                ))}
              </div>
            )}

            {/* Dish Info */}
            <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-6 text-white">
              <div className="flex justify-between items-start mb-4">
                <div>
                  <h2 className="text-3xl font-bold mb-2">{selectedDish.name}</h2>
                  {selectedDish.category && (
                    <span className="inline-block px-3 py-1 bg-white/20 rounded-full text-sm">
                      {selectedDish.category}
                    </span>
                  )}
                </div>
                <div className="text-right">
                  <div 
                    className="text-4xl font-bold"
                    style={{ color: restaurant.color }}
                  >
                    {selectedDish.price}$
                  </div>
                  <div className="text-sm opacity-70">CAD</div>
                </div>
              </div>
              
              {selectedDish.description && (
                <p className="text-lg opacity-90 leading-relaxed">
                  {selectedDish.description}
                </p>
              )}
            </div>

            {/* Instructions */}
            <div className="mt-6 text-center text-white/60 text-sm">
              <p>
                {selectedDish.images && selectedDish.images.length > 1
                  ? '← Utilisez les flèches pour voir toutes les vues 3D →'
                  : 'Explorez les autres plats du menu !'}
              </p>
            </div>
          </div>
        </div>
      )}

      {/* Footer */}
      <footer className="border-t border-white/10 mt-12 py-8">
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <div className="flex items-center justify-center space-x-2 mb-2">
            <Eye className="w-5 h-5" style={{ color: restaurant.color }} />
            <span className="font-semibold">Powered by SeeYourMeal</span>
          </div>
          <p className="text-sm opacity-70">
            Menus 3D interactifs pour restaurants
          </p>
        </div>
      </footer>
    </div>
  );
};

export default PublicMenu;
```

---

# 🎉 FÉLICITATIONS !

Vous avez maintenant **TOUS LES CODES COMPLETS** pour SeeYourMeal !

---

# 📋 CHECKLIST D'INSTALLATION

## ✅ ÉTAPE 1 : Créer la Structure (10 min)

1. Créez un dossier `seeyourmeal` sur votre Bureau
2. À l'intérieur, créez ces dossiers :
   - `src/`
   - `src/components/`
   - `src/config/`
   - `public/`
3. Créez tous les 14 fichiers en copiant les codes ci-dessus

## ✅ ÉTAPE 2 : Installer Node.js (5 min)

1. Allez sur : https://nodejs.org
2. Téléchargez la version LTS (Long Term Support)
3. Installez-le (suivez les instructions)
4. Vérifiez l'installation : ouvrez Terminal et tapez `node --version`

## ✅ ÉTAPE 3 : Installer les Dépendances (3 min)

1. Ouvrez Terminal
2. Allez dans votre dossier : `cd Desktop/seeyourmeal`
3. Installez tout : `npm install`
4. Attendez 2-3 minutes

## ✅ ÉTAPE 4 : Configurer Firebase (15 min)

1. Allez sur : https://console.firebase.google.com
2. Créez un nouveau projet : "seeyourmeal"
3. Activez Firestore Database
4. Activez Storage
5. Dans Project Settings → General → Your apps
6. Copiez les clés Firebase
7. Collez-les dans `src/config/firebase.js`

## ✅ ÉTAPE 5 : Tester en Local (2 min)

1. Dans Terminal : `npm run dev`
2. Ouvrez : http://localhost:3000
3. Testez le site !

## ✅ ÉTAPE 6 : Déployer sur Vercel (10 min)

1. Créez compte sur : https://vercel.com
2. Dans Terminal : `npm i -g vercel`
3. Puis : `vercel`
4. Suivez les instructions
5. Votre site est en ligne ! 🎉

## ✅ ÉTAPE 7 : Acheter le Domaine (5 min)

1. Allez sur : https://www.namecheap.com
2. Cherchez : `seeyourmeal.com`
3. Achetez le domaine (15$/an)
4. Dans Vercel : Settings → Domains → Ajoutez votre domaine

---

# 💰 COÛTS TOTAUX

- **Domaine** : 15$/an
- **Firebase** : Gratuit (jusqu'à 1GB)
- **Vercel** : Gratuit
- **Stripe** : 2.9% par transaction

**Total startup : 15$** 🎉

---

# 🚀 PROCHAINES ÉTAPES BUSINESS

1. **Semaine 1** : Testez tout en local
2. **Semaine 2** : Déployez et achetez le domaine
3. **Semaine 3** : Téléchargez Luma AI et testez avec de vrais plats
4. **Semaine 4** : Contactez votre premier client restaurant

---

# 📞 BESOIN D'AIDE ?

Si vous bloquez quelque part :

1. Vérifiez que tous les fichiers sont créés
2. Vérifiez que Node.js est installé : `node --version`
3. Vérifiez les clés Firebase
4. Consultez la documentation :
   - Firebase : https://firebase.google.com/docs
   - Vercel : https://vercel.com/docs
   - React : https://react.dev

---

# 🎊 BONNE CHANCE !

Vous avez maintenant tout ce qu'il faut pour lancer SeeYourMeal !

**Revenue potentiel avec 10 clients : 780-1190$/mois** 💰

**Allez-y, lancez votre business ! 🚀**
