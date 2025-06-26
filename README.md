# Project Overview
The project is built with the goal of automating the control and protection of parking areas in households, boarding houses, or small residential areas, by applying Artificial Intelligence (AI) combined with low-cost hardware devices.

The system uses Raspberry Pi 4 as the control center, connecting to many devices such as cameras, Arduino microcontrollers, sensors, lights and motors. The three main AI functions include:

✅ 1. Face recognition - Automatic door opening
Using the face_recognition library with the ResNet-34 backbone model to extract facial embedding and compare.

To ensure high accuracy, valid users need to provide 5-10 facial images in good and clear lighting conditions.

When the camera recognizes a valid person, the system will activate the automatic door opening mechanism via servo or stepper motor.

✅ 2. Human Detection - Intrusion Warning
Applying the YOLOv8n model, which has been fine-tuned on real data collected in parking areas with low light conditions (night, low light, etc.).

Images are manually collected from surveillance cameras, then labeled using the Roboflow tool to prepare for the model retraining process.

When detecting people moving abnormally in the area outside of allowed hours, the system will send a warning and can record video/turn on/off warning lights.

✅ 3. Voice recognition – Device control
The system supports voice control through the VOSK offline voice recognition model, using the available Vietnamese package.

Users can give commands in Vietnamese to turn on/off lights, doors, sirens, or perform basic tasks without using their hands.

# Client:
## React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```

# Server:
## Set up back-end

b1: cd ../pbl5/be

b2: python -m venv .venv

b3: .venv\Scripts\Activate.ps1

b4: python -m pip install --upgrade pip

b5: pip install -r requirements.txt

## run server

fastapi dev main.py
