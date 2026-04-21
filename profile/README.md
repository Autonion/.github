# 🧅 Autonion Ecosystem

**Autonion** is a comprehensive, cross-device AI-powered automation ecosystem designed to seamlessly bridge your Android device, Desktop OS, and Web Browser. By leveraging on-device ML, local LLMs, and seamless LAN connectivity, Autonion provides intelligent, agentic automation without relying on cloud services.

## 🚀 Core Components

The ecosystem consists of four main modules that work in harmony:

### 1. 📱 [Automation Companion (Android App)](../Users/Guru/AndroidStudioProjects/AutomationCompanion/README.md)
The brain and primary interface of the ecosystem. It is an offline-first Android application that empowers users to create powerful automations natively on their phone.
* **Key Features:** Omni-Chatbot with Langchain and RAG, Gesture Recording & Playback, Flow Automation, Screen Understanding via ML Kit, Semantic Automation, and Hardware Remote capabilities.
* **Role:** Acts as the central command hub, processing natural language requests via local LLMs and routing them either to local Android execution or to the Desktop Agent.

### 2. 🖥️ [Autonion-Agent (Desktop Agent)](Autonion-Agent/README.md)
A Flutter-based desktop application serving as the communication hub for your desktop environment.
* **Key Features:** Zero-config mDNS discovery, local WebSocket Server bridge, bi-directional clipboard synchronization, Python-based native OS automation, and intelligent task routing.
* **Role:** Receives agentic action requests from the Android app. It intelligently routes web-related tasks to the browser extension and native desktop tasks to its embedded Python backend.

### 3. 🌐 [Autonion-Extension (Desktop Browser Extension)](Autonion-Extension/README.md)
An AI-powered browser automation extension for Chromium-based desktop browsers.
* **Key Features:** AI-driven DOM execution, seamless syncing with the Autonion ecosystem, and dedicated content scripts for interacting with LLM interfaces like ChatGPT and Gemini.
* **Role:** Executes the semantic automation plans inside the browser DOM (e.g., clicking, typing, navigating) as requested by the Autonion-Agent.

### 4. 📱🌐 [Autonion-Android-Extension (Mobile Browser Extension)](Autonion-Android-Extension/README.md)
A Lemur Browser companion extension for Android devices.
* **Key Features:** Semantic DOM snapshots extraction, local WebSocket relay, and LLM-driven execution within the mobile browser.
* **Role:** Acts as a bridge on the Android device itself to allow the Automation Companion app to execute complex web interactions within the mobile browser.

---

## 🔗 How They Work Together

1. **User Request:** You ask the **Automation Companion** (Android) via the Omni-Chatbot to perform a task (e.g., "Play my presentation on my PC" or "Log in to my email").
2. **AI Processing:** The app's local LLM (with RAG/Langchain support) understands the intent and generates an agentic plan.
3. **Task Routing:** 
   * If it's a mobile task, it executes locally (using Accessibility, ScreenML, or the **Autonion-Android-Extension**).
   * If it's a cross-device task, it communicates via local Wi-Fi to the **Autonion-Agent** (Desktop).
4. **Desktop Execution:** The **Autonion-Agent** receives the command.
   * Native tasks (e.g., opening PowerPoint, media controls) are handled by the embedded Python backend.
   * Web tasks are forwarded to the **Autonion-Extension** (Desktop Browser), which manipulates the DOM to complete the task.

## 🛠️ Tech Stack Highlights
- **Android App:** Kotlin, Jetpack Compose, Room, TFLite, ML Kit, Langchain.
- **Desktop Agent:** Flutter, Dart, Python, mDNS, WebSockets.
- **Browser Extensions:** JavaScript, Chrome Extension Manifest V3.

## 📄 Licensing
Autonion components are licensed under the PolyForm Noncommercial License 1.0.0, permitting personal, research, and educational use.
