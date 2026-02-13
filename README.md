# 📊 Svelte + D3 Scatter Plot Visualization

This project is built using **Svelte** and **D3.js** to create dynamic and interactive scatter plot visualizations.

The application renders two different datasets simultaneously and demonstrates reactive data visualization techniques using SVG.

<img width="852" height="539" alt="image" src="https://github.com/user-attachments/assets/e5266906-aab9-4809-8733-3e612a65acb5" />

<img width="833" height="489" alt="image" src="https://github.com/user-attachments/assets/ad3ee42e-8efe-49a0-b04c-d1bb5555de3d" />


---

## 🚀 Project Overview

This project contains:

- Two scatter plot visualizations displayed together
- Dynamic axis selection for the first dataset
- Responsive SVG layout
- Categorical color mapping
- External API integration

---

## 📌 Visualization 1: Cow Racing Dataset

The first scatter plot represents a fictional cow racing dataset.

### Features:
- X-axis: Weight or Length
- Y-axis: Race Time or Position
- Color-coded by cow name
- Dynamic property switching
- Data loaded from external CSV file

This visualization demonstrates:
- Data parsing
- Numeric transformation
- Dynamic scale generation
- Reactive axis updates

---

## 📌 Visualization 2: Pokémon Dataset

The second scatter plot uses real data fetched from the **PokeAPI**.

### Features:
- X-axis: Weight
- Y-axis: Speed
- Color-coded by Pokémon type
- Data fetched from REST API
- JSON parsing and transformation

This visualization demonstrates:
- API integration
- Asynchronous data fetching
- Data mapping
- Categorical color scaling

---

## 🛠 Technologies Used

- Svelte
- D3.js
- SVG
- JavaScript (ES6)
- PokeAPI

---

## 🧠 Concepts Demonstrated

- Reactive state management using Svelte
- D3 scaleLinear and scaleOrdinal
- Dynamic axis rendering
- Data transformation
- Multiple visualizations in a single page
- Responsive SVG width binding

---

## ▶️ How to Run the Project

```bash
npm install
npm run dev
