# Free-to-Play Gaming Trends Analysis

**Authors:**

* **Shakhizada Zhansulu — 22B030568**
* **Myrzakhankyzy Arailym — 22B030408**

---

## 🎯 Project Goal

We chose the topic **"Free-to-Play Gaming Trends"** to analyze:

* Which **F2P games are currently popular**
* Which **platforms** they are most often released on
* How **trends have evolved over time**

---

## 📊 Data Sources

| Source                           | Description                                                                                     | Link                                                                                                                   |
| -------------------------------- | ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **FreeToGame API**               | Main dataset with full list of F2P games including genre, platform, release date, and publisher | [https://www.freetogame.com/api/games](https://www.freetogame.com/api/games)                                           |
| **Microsoft Store Web Scraping** | “Top Free Games” list scraped from Xbox Store to capture currently trending games               | [https://www.microsoft.com/en-us/store/top-free/games/xbox](https://www.microsoft.com/en-us/store/top-free/games/xbox) |

---

## 🧹 Data Cleaning & Preparation

1. Identified the column containing **game names** (text type).
2. Created a new `title` column and **removed noise**, including:

   * Text inside **square brackets**
   * Extra **leading and trailing spaces**
3. Kept only the clean title column.
4. Removed **empty rows** using `.dropna()`.
5. Removed **duplicates** using `.drop_duplicates()`.
6. Selected the **first 50 unique games** using `.iloc[:50]`.

---

## 🔗 Data Comparison (API vs Web Scraping)

To find games that appear in **both datasets**, we:

* Converted all titles to **lowercase** using `.str.lower()`.
* Used `.merge()` to match titles.

✅ **Result:** **11 exact matches** — these are games that exist **both** in the Microsoft Store top list and in the FreeToGame API.

---

## 📈 Key Insights

### 1. 🎮 Genres (API)

* The F2P market is **dominated by MMORPGs** — nearly **160 games**.
* **Shooter** is second with ~108 games.
* **Strategy** comes third but is **almost 3× smaller** than MMORPG.

---

### 2. 🖥️ Platforms (API)

| Platform         | Count      | Conclusion                |
| ---------------- | ---------- | ------------------------- |
| **PC (Windows)** | ~340 games | Almost the entire dataset |
| **Browser**      | ~75 games  | Minor share               |

👉 The API dataset is **mostly PC-focused**.

---

### 3. 📅 Releases Over Time

* **2000s:** Only **5–10 games/year**
* **2010–2015:** Sharp growth, **peak in 2015 (37 releases)**
* **After 2015:** Slight decline but stable at **15–20 games/year**

---

### 4. 🎯 Matched Games by Genre (API + Web)

Out of 11 matched games:

| Genre         | Count |
| ------------- | ----- |
| **Shooter**   | **8** |
| Battle Royale | 1     |
| Action RPG    | 1     |
| Sports        | 1     |

👉 **Shooters dominate the overlap** between “Most Popular” and “Most Common”.

---

### 5. 🏷️ Most Common Words in Titles (Web Scraping)

| Word       | Count | Reason                        |
| ---------- | ----- | ----------------------------- |
| **call**   | 4     | Part of “Call of Duty” series |
| **duty**   | 4     | Same                          |
| **modern** | 4     | From “Modern Warfare” titles  |

---

## 📌 Summary

| Dataset             | Total Games                    | Insights                                                  |
| ------------------- | ------------------------------ | --------------------------------------------------------- |
| **Microsoft Store** | 37 unique games after cleaning | Used to capture **current popularity trends**             |
| **FreeToGame API**  | 416 games                      | Used to analyze **genre, platform, and release patterns** |

* **Top Genres:** MMORPG (158), Shooter (106)
* **Top Publishers:** **R2 Games** and **Valve**

---

Let me know if you’d like:

✅ **Markdown with images/charts placeholders**
✅ **Badges / Table of Contents / Installation section**
✅ **Jupyter Notebook-style README with code blocks**

Would you like me to **add image embeds or code samples** to this README?

