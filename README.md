# BMO Local Agent (Version Française) 🤖
**Un agent IA haute-performance, 100% hors-ligne pour Raspberry Pi 5**

![Python](https://img.shields.io/badge/Python-3.11%2B-blue) ![Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi%205-red) ![Language](https://img.shields.io/badge/Language-Français-green)

Cette version améliorée du projet `be-more-agent` est optimisée pour le **Raspberry Pi 5 (16Go)**. Elle utilise les dernières technologies IA locales pour offrir une expérience fluide, intelligente et entièrement en français.

## 🚀 Améliorations de cette version

*   **Cerveau (LLM) :** Utilise **Qwen 3.5 2B** via Ollama. Ce modèle est plus performant pour le raisonnement et le français que les modèles 1B classiques.
*   **Voix Premium (TTS) :** Remplace Piper par **Kokoro-82M**. La qualité de synthèse vocale est exceptionnelle ("stade de l'art") avec un support natif du français.
*   **Conteneurisation :** Support complet de **Docker** et **Docker Compose** pour un déploiement simplifié.
*   **Localisation :** Prompts système et détection de langue configurés pour le français par défaut.

## ✨ Caractéristiques principales

*   **Vie privée totale :** 100% local, aucune donnée ne quitte votre appareil.
*   **Multimodal :** Capable de voir (via caméra) et d'entendre (via Whisper).
*   **Extensible :** Recherche web intégrée via DuckDuckGo.
*   **Visages réactifs :** Interface Tkinter avec animations synchronisées à la voix.

## 🛠️ Configuration requise

*   **Raspberry Pi 5** (16Go recommandés, 8Go minimum)
*   **Microphone USB** & **Haut-parleurs**
*   **Caméra Pi** (Optionnel, pour la vision)
*   **OS :** Raspberry Pi OS (64-bit)

---

## 📂 Structure du projet

```text
.
├── agent.py           # Cerveau de l'agent (Logique principale)
├── config.json        # Configuration (Modèles, Prompts, Caméra)
├── Dockerfile         # Image pour déploiement Docker
├── docker-compose.yml # Orchestration Docker
├── requirements.txt   # Dépendances Python
├── faces/             # Séquences d'images pour les expressions
└── sounds/            # Sons système (Thinking, Error, etc.)
```

---

## 🚀 Installation & Déploiement

### 1. Pré-requis (sur le Pi)
```bash
# Installation de Docker
curl -sSL https://get.docker.com | sh
sudo usermod -aG docker $USER

# Installation d'Ollama
curl -fsSL https://ollama.com/install.sh | sh
```

### 2. Cloner le projet
```bash
git clone https://github.com/SnowSnowChowChow/BMO_local_qwen3.5_2B-KOKORO-82M.git
cd BMO_local_qwen3.5_2B-KOKORO-82M
```

### 3. Télécharger les modèles
```bash
# Modèle LLM
ollama pull qwen3.5:2b

# Modèles TTS Kokoro
wget https://github.com/theodore-ganzh/kokoro-onnx/releases/download/v1.0/kokoro-v1.0.onnx
wget https://github.com/theodore-ganzh/kokoro-onnx/releases/download/v1.0/voices-v1.0.bin
```

### 4. Lancer l'agent
**Via Docker (Recommandé) :**
```bash
docker compose up --build
```

**Ou en local (Python) :**
```bash
pip install -r requirements.txt
python agent.py
```

---

## 🎨 Personnalisation

Éditez le fichier `config.json` pour modifier :
*   `system_prompt` : Changez la personnalité de BMO.
*   `voice_name` : Changez la voix de Kokoro (ex: `ff_siwis` pour le français).
*   `camera_rotation` : Ajustez l'orientation de la caméra (0, 90, 180, 270).

---

## 📄 Licence
Ce projet est sous licence MIT.

## ⚖️ Mentions Légales
**"BMO"** et **"Adventure Time"** sont des marques déposées de **Cartoon Network**. Ce projet est une création de fan à but éducatif.
