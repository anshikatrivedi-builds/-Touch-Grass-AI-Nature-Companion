
# 🌿 Touch Grass — AI Nature Companion

> **Less scrolling. More exploring.**

A nature-focused web app inspired by the Hacktoberfest **"Touch Grass"** theme. It combines browser-based AI image classification with gardening suggestions and outdoor activity ideas to encourage people to spend more time outside.

![HTML](https://img.shields.io/badge/HTML5-Website-orange)
![CSS](https://img.shields.io/badge/CSS3-Responsive-blue)
![JavaScript](https://img.shields.io/badge/JavaScript-Interactive-yellow)
![AI](https://img.shields.io/badge/AI-Open%20Model-6a994e)

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Why Touch Grass?](#-why-touch-grass)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [How the AI Works](#-how-the-ai-works)
- [Getting Started](#-getting-started)
- [How to Use](#-how-to-use)
- [Project Structure](#-project-structure)
- [Privacy and Limitations](#-privacy-and-limitations)
- [Future Improvements](#-future-improvements)
- [Contributing](#-contributing)
- [Hacktoberfest Theme](#-hacktoberfest-theme)
- [License](#-license)
- [Acknowledgements](#-acknowledgements)

---

## 🌱 About the Project

**Touch Grass — AI Nature Companion** is a lightweight, responsive web application designed to make outdoor exploration more interesting.

Instead of encouraging people to spend even more time on screens, this project uses technology to inspire real-world activities. Users can try AI image classification with a nature photo, get a beginner-friendly planting idea, or generate a short outdoor mission.

The project is built using HTML, CSS, and JavaScript, making it easy for beginners to explore, understand, and improve.

## 🌍 Why "Touch Grass"?

"Touch grass" is an informal phrase meaning to step away from screens and reconnect with the real world.

This project encourages people to:

- Notice birds, plants, leaves, colours, and sounds.
- Try small gardening activities.
- Take a walk or spend mindful time outdoors.
- Use AI as a helper, not as a replacement for real-world experiences.

## ✨ Features

### 1. 🔎 Nature Lens — AI Image Classification

- Upload a photo from your device.
- Run an image-classification model in the browser.
- Display the top prediction and alternative labels.
- Show the model's prediction score.
- Preview or clear the selected image.

**Note:** The current model is a general-purpose image classifier, not a specialist plant or bird identification system. Its predictions may be incorrect.

### 2. 🌿 Garden Buddy — Planting Suggestions

Choose your climate, growing space, and preferred plant category.

The app provides beginner-friendly suggestions for:

- Herbs
- Leafy greens
- Flowers for pollinators
- Vegetables

These suggestions use predefined JavaScript rules and do not depend on live weather information.

### 3. 👟 Go Outside Generator — Outdoor Missions

Generate a small outdoor activity based on your available time and mood.

Available activity types include:

- **Calm:** Notice sounds, colours, textures, or clouds.
- **Curious:** Observe nature and discover new details.
- **Movement:** Take a safe walk or stretch gently.
- **Creative:** Try a nature colour hunt or sketch a fallen leaf.

### 4. 📱 Responsive Interface

- Nature-inspired colours and illustrations.
- Responsive layout for desktop and mobile devices.
- No account or sign-in required.
- Simple, lightweight frontend.

---

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Website structure |
| CSS3 | Styling and responsive layout |
| JavaScript | Interactive features |
| Transformers.js | Runs the image-classification pipeline in the browser |
| Xenova ViT model | Pretrained image-classification model |
| jsDelivr CDN | Loads the JavaScript library |

The basic project does not require Node.js, a database, or a custom backend.

## 🧠 How the AI Works

The Nature Lens feature uses Transformers.js to load the model:

`Xenova/vit-base-patch16-224`

The workflow is:

1. The user selects a photo.
2. The browser displays a local preview.
3. Transformers.js loads the AI model and required assets.
4. The model processes the image in the browser.
5. The website displays the top labels and their scores.

The first model load requires an internet connection because the library and model files are downloaded from external hosting.

Offline use is not guaranteed and depends on whether all required files have been cached.

### Why use an open model?

- **User control:** The selected image is processed in the browser instead of being uploaded to a custom application backend.
- **Learning:** Developers can inspect the code and experiment with compatible models.
- **Potential cost savings:** The current implementation does not call a paid custom inference API.
- **Offline potential:** Browser-based models may work offline after required assets are cached, but this prototype does not guarantee offline operation.

Always check the model card and dependency licences before redistribution or deployment.

---

## 🚀 Getting Started

### Requirements

- A modern browser such as Chrome, Edge, or Firefox.
- An internet connection for the initial AI model download.
- An image file to test the Nature Lens feature.

### Option 1: Open the HTML file

1. Download or clone this repository.
2. Locate `touch_grass_ai_nature_companion.html`.
3. Open it in your browser.
4. Choose a photo and click **Identify with AI** to test image classification.

The gardening and outdoor activity features work without downloading the AI model.

### Option 2: Run using Python

Open a terminal in the project folder and run:

```bash
python -m http.server 8000
```

On Windows, you can also try:

```bash
py -m http.server 8000
```

Open this URL in your browser:

```text
http://localhost:8000/touch_grass_ai_nature_companion.html
```

Press `Ctrl + C` in the terminal to stop the server.

No Ollama installation or custom AI backend is required for this version.

---

## 🧭 How to Use

### Nature Lens

1. Click **Choose a photo**.
2. Select an image.
3. Click **Identify with AI**.
4. Wait for the model to load.
5. Review the prediction and alternative labels.

### Garden Buddy

1. Select your general climate.
2. Choose your growing space.
3. Select a plant category.
4. Click **Suggest a planting idea**.
5. Check local growing guidance before planting.

### Go Outside Generator

1. Choose how much time you have.
2. Select your preferred mood.
3. Click **Give me an outdoor mission**.
4. Follow the suggested activity safely.

---

## 📁 Project Structure

```text
touch-grass/
├── touch_grass_ai_nature_companion.html
└── README.md
```

The HTML file contains the website markup, CSS styles, JavaScript interactions, and AI model-loading code.

## 🔐 Privacy and Limitations

### Privacy

- No account or sign-in is required.
- There is no custom application backend.
- The selected image is processed in the browser by the model code.
- The library and model are downloaded from external hosting, which may receive normal network request metadata.
- The project does not guarantee complete privacy or offline functionality.

### Limitations

- The model is a general image classifier, not a dedicated nature field guide.
- Prediction scores do not guarantee correctness.
- Gardening suggestions are not based on live weather or soil data.
- Outdoor missions come from a predefined list.
- Model downloads may take time and use bandwidth.

**Safety:** Never eat or handle an unknown plant or mushroom based only on an AI prediction. Verify identifications using trusted local sources or qualified experts.

---

## 🛠️ Future Improvements

- [ ] Add a specialist plant-identification model.
- [ ] Add a dedicated bird-identification feature.
- [ ] Improve AI loading progress and error handling.
- [ ] Test offline support and model caching.
- [ ] Add local weather and seasonal planting guidance.
- [ ] Improve accessibility and automated testing.
- [ ] Separate HTML, CSS, and JavaScript into different files.
- [ ] Add support for multiple languages.
- [ ] Test with real-world nature photos and document the results.

---

## 🤝 Contributing

Contributions, bug reports, suggestions, and documentation improvements are welcome!

### Beginner-friendly contributions

- Improve the mobile layout.
- Improve accessibility.
- Add outdoor missions.
- Improve gardening suggestions using reliable sources.
- Test image classification with different photos.
- Improve documentation and error messages.

### Contribution workflow

1. Fork this repository.
2. Clone your fork.
3. Create a new branch.
4. Make your changes.
5. Test the website.
6. Commit your changes.
7. Push the branch to your fork.
8. Open a pull request.

Example commands:

```bash
git clone <your-fork-url>
cd <repository-folder>
git checkout -b improve-nature-lens
git add .
git commit -m "Improve Nature Lens feedback"
git push origin improve-nature-lens
```

Replace the placeholder values with your actual repository details.

---

## 🌳 Hacktoberfest — Touch Grass

This project is inspired by the challenge to build with open-weight models or open-source AI in a way that helps people reconnect with the world outside their screens.

The idea is simple:

**Use the screen to get curious. Then go outside and explore.**

Touch Grass combines browser-based image classification with practical nature activities. Future improvements can make the project more accurate, useful, and accessible.

---

## 📄 License

No project licence has been selected yet.

Before publishing, choose a suitable licence for your own code and add a `LICENSE` file. Review the licences of the AI model, libraries, and other assets separately. Do not assume they are all covered by your project's licence.

---

## 🙌 Acknowledgements

- [Transformers.js](https://github.com/xenova/transformers.js) — browser-based machine learning.
- [Hugging Face](https://huggingface.co/) — model hosting and documentation.
- The open-source community — for making experimentation and learning accessible.
- The Hacktoberfest **Touch Grass** theme — for the inspiration.

---

**Built with curiosity and a little green energy. 🌱**
