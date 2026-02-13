# 📊 Svelte + D3 Scatter Plot Visualization

An interactive data visualization project built using **Svelte** and **D3.js**.

This application renders **two different datasets simultaneously** and demonstrates reactive data visualization using SVG, dynamic scaling, and external API integration.

---

## 🌟 Live Visualization Preview

### 🐄 Cow Racing Dataset
<img width="852" height="539" alt="Cow Dataset" src="https://github.com/user-attachments/assets/e5266906-aab9-4809-8733-3e612a65acb5" />

### 🎮 Pokémon Dataset
<img width="833" height="489" alt="Pokemon Dataset" src="https://github.com/user-attachments/assets/ad3ee42e-8efe-49a0-b04c-d1bb5555de3d" />

---

## 🚀 Project Overview

This project includes:

- 📈 Two scatter plot visualizations displayed together
- 🔄 Dynamic axis selection for the first dataset
- 📱 Responsive SVG layout
- 🎨 Categorical color mapping
- 🌐 External API data fetching
- ⚡ Reactive updates using Svelte state

---

## 📌 Visualization 1: Cow Racing Dataset

A fictional dataset representing cow race performance metrics.

### Features:
- X-axis: Weight or Length
- Y-axis: Race Time or Position
- Color-coded by cow name
- Dynamic property switching
- Data loaded from external CSV

### Demonstrates:
- CSV parsing using D3
- Numeric transformation
- Dynamic scale generation
- Reactive axis updates
- Component-based visualization design

---

## 📌 Visualization 2: Pokémon Dataset

Real-world dataset fetched dynamically from **PokeAPI**.

### Features:
- X-axis: Weight
- Y-axis: Speed
- Color-coded by Pokémon type
- REST API integration
- JSON parsing and transformation

### Demonstrates:
- Asynchronous data fetching
- API data mapping
- Categorical color scaling
- Multiple dataset handling in a single app

---

## 🛠 Technologies Used

- **Svelte**
- **D3.js**
- **SVG**
- **JavaScript (ES6)**
- **PokeAPI**

---

## 🧠 Technical Concepts Applied

- Reactive state management (`$state`, `$derived`)
- D3 `scaleLinear` and `scaleOrdinal`
- Dynamic axis rendering
- Responsive SVG binding
- Component reusability
- Multi-dataset visualization architecture

---

## 🏗 Project Architecture

<img width="2267" height="1255" alt="Architecture" src="https://github.com/user-attachments/assets/006fc0f7-662c-4ecb-b773-9ba40dcf33e3" />

---

## ▶️ How to Run the Project

```bash
npm install
npm run dev
