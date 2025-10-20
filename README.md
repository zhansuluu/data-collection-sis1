# 🎮 Free-to-Play Gaming Trends 📈

## 👩‍💻 Team
* Shakhizada Zhansulu 22B030568
* Myrzakhankyzy Arailym 22B030408

---

## 🎯 Project Overview

We chose the topic "Free-to-Play Gaming Trends" to better understand which free-to-play games are currently popular, which platforms they are most often released on, and how trends in this area have changed over time.

## 📊 Data Sources

We used the **FreeToGame API** (`https://www.freetogame.com/api/games`) as our primary data source. This API allowed us to obtain a comprehensive list of free-to-play games along with additional information such as genre, platform, release date, and publisher.

Additionally, to obtain information about currently popular games, we used **web scraping** 🕸️, collecting the 'Top Free Games' list from the Microsoft Store page (`https://www.microsoft.com/en-us/store/top-free/games/xbox`). This allowed us to compare data from the general API database with the current top-ranked games on one platform.

---

## 🛠️ Methodology

### 2. Data Cleaning and Preparation 🧹
In the "Data Cleaning and Preparation" section, we completed the following steps:

* First, we looked for the column that contains the game names. We checked all the columns to find the one with the data type “text”. 📝
* Then we cleaned these names: we created a new column called `title` and remove all the "noise" (everything inside square brackets), as well as any extra spaces at the beginning or end.
* After that, we kept only this clean `title` column, removed all empty rows using `.dropna()`, and most importantly, deleted all duplicates with `drop_duplicates()`, so we ended up with a list of only unique games. 💎
* Finally, for our analysis, we selected the first 50 games from this unique list using `.iloc[:50]`.

### 3. Data Comparison 🔄
Next, we compared two data sources (Microsoft Store and the FreeToGame API) to find games that appear in both lists.

* We used the `.merge()` method to match the game titles.
* To make the comparison accurate and ignore letter case (for example, `PUBG` vs `pubg`), we converted all titles from both sources to lowercase using `.str.lower()`.
* As a result, we found **11 exact matches** ✅; these are the games that exist in both the Microsoft Store and the API database.

---

## 💡 Key Insights

### 1. Genres (API) 🎭
> The visualization "Top Genres in F2G API (10)" shows that the F2P game market is completely dominated by one genre: **MMORPG**.

There are an unreal number of them - almost `160` games, and they are far ahead of all other genres. Even **Shooter** 🔫 games, which are in second place with around `108` games, are still far behind. And **Strategy** games (third place) are almost three times fewer than MMORPGs.

### 2. Platforms (API) 💻
> If we look at which platforms people use to play F2P games (based on this API), the conclusion is clear: almost all of the free games in this list are made for **PC (Windows)**.

There are a lot of them - almost `340` games. In second place are **browser games** 🌐, but there are way fewer of them (only `75`). So, in simple words, this API database is basically a list of PC games.

### 3. Releases by Year (API) 🗓️
> It turns out that in the 2000s, almost no F2P games were released. There were only about 5–10 games per year.

Starting from 2010, the number of new free games began to grow quickly and reached its peak in **2015** 🚀 with `37` releases. After 2015, the number went down, but it still stayed at a high level — around `15–20` games per year, which is way more than in the 2000s.

### 4. Matched Games (API + Web) 🤝
> The "Matched Games by Genre" chart clearly shows which games were found in both of our lists “Microsoft Store and the API”.

It turned out that out of the `11` matched games, **8 of them are Shooters** - that’s the huge majority. The other genres “Battle Royale”, “Action RPG”, and “Sports” appear only once each.

### 5. Top Words (Web Scraping) 💬
> The chart shows which words appear most often in the game titles from our Microsoft Store list.

The most common words are **"call"**, **"duty"**, and **"modern"** - each of them appears 4 times.

This happened because our list includes games like "Call of Duty: Modern Warfare II", "Call of Duty: Modern Warfare III", "Call of Duty: DMZ", and "Call of Duty: Warzone". So naturally, the words `call`, `duty`, and `modern` ended up at the top.

---

## 📄 Summary

During our work, we analyzed two data sources.

* **Microsoft Store dataset:** After cleaning the data, it contained **37 unique games**.
* **FreeToGame API database:** This dataset includes **416 games** in total.

From the API analysis, we found that the most popular genres are **MMORPG** (`158` games) and **Shooter** (`106` games). Among the top publishers, the leaders are **R2 Games** and **Valve**.
