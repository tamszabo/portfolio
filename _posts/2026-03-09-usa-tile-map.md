---
layout: post
title: "How to Build a USA Tile Map in Tableau (Where Every State Gets Equal Space)"
date: 2026-03-09
image: /assets/images/5-usa-tilemap.png
categories: [DataViz, Data Analysis]
description: "Rhode Island is 425x smaller than Alaska — but does that make it less important to your analysis? Here's how to build a tile map in Tableau where every state gets equal visual weight."
author: Tamas Szabo
---

# 🗺️ The Problem With Standard US Maps

If you've ever put US state data on a geographic map in Tableau, you already know the frustration. Alaska dominates the top-left corner. Texas and California eat up most of the visual real estate. And Rhode Island, Connecticut, Delaware — states that might be *critical* to your analysis — are practically invisible.

The standard choropleth map is geographically accurate, but analytically misleading. It encodes area as importance, when what you actually care about is the *data value* in each state.

The solution is a **tile map** — a grid layout where every state gets an equal-sized cell, positioned to loosely mirror the actual geography of the US. Same spatial intuition, zero distortion.

Here's exactly how I build mine in Tableau.

---

## 🧠 The Core Idea

Instead of plotting states on a real map, we assign each state an **x (Column) and y (Row) coordinate** in a grid. Tableau then plots them as a scatter chart, and we use shapes or square marks to fill each cell.

The result: a layout that *feels* geographically familiar — the Northeast is still top-right, the Southeast is still bottom-right, Alaska sits in the top-left — but every state occupies identical space. Rhode Island is just as visible as Texas.

This technique gives you something a standard map never can: **full creative control**. You can assign any shape, color, size, or label to each state cell, and you can reposition individual states simply by changing a coordinate value.

---

## ⚙️ Step 1: The Four Calculated Fields

You need four calculations. Create each one in Tableau via **Analysis > Create Calculated Field**.

---

### Calculation 1 — State Name

This is your anchor field. If your data source already has a `State` field with full state names, you can use that directly. If not, create this mapping from whatever identifier you have (abbreviation, FIPS code, etc.). The key requirement is that the names match exactly across all four calculations.

<details class="bg-[#252525]/50 rounded-xl border border-[#2a2a2a] p-4 my-6">
<summary class="cursor-pointer font-bold text-[#4a8e91] hover:text-[#6aacaf] list-none flex justify-between items-center">
    <span>▶ State Name — Full CASE WHEN</span>
    <button id="copy-name-btn" onclick="copyCode('nameCode', 'copy-name-btn', event)" class="text-xs bg-[#3c6e71]/20 hover:bg-[#3c6e71]/40 text-[#6aacaf] px-3 py-1 rounded-lg transition-all">Copy Code</button>
</summary>
<div class="mt-4 overflow-x-auto">
<pre id="nameCode" class="text-sm text-[#d9d9d9] font-mono leading-relaxed bg-[#252525] p-4 rounded-lg border border-[#3c6e71]/50">CASE [State ABR]
WHEN 'AK' THEN 'Alaska'
WHEN 'AL' THEN 'Alabama'
WHEN 'AR' THEN 'Arkansas'
WHEN 'AZ' THEN 'Arizona'
WHEN 'CA' THEN 'California'
WHEN 'CO' THEN 'Colorado'
WHEN 'CT' THEN 'Connecticut'
WHEN 'DC' THEN 'District of Columbia'
WHEN 'DE' THEN 'Delaware'
WHEN 'FL' THEN 'Florida'
WHEN 'GA' THEN 'Georgia'
WHEN 'HI' THEN 'Hawaii'
WHEN 'IA' THEN 'Iowa'
WHEN 'ID' THEN 'Idaho'
WHEN 'IL' THEN 'Illinois'
WHEN 'IN' THEN 'Indiana'
WHEN 'KS' THEN 'Kansas'
WHEN 'KY' THEN 'Kentucky'
WHEN 'LA' THEN 'Louisiana'
WHEN 'MA' THEN 'Massachusetts'
WHEN 'MD' THEN 'Maryland'
WHEN 'ME' THEN 'Maine'
WHEN 'MI' THEN 'Michigan'
WHEN 'MN' THEN 'Minnesota'
WHEN 'MO' THEN 'Missouri'
WHEN 'MS' THEN 'Mississippi'
WHEN 'MT' THEN 'Montana'
WHEN 'NC' THEN 'North Carolina'
WHEN 'ND' THEN 'North Dakota'
WHEN 'NE' THEN 'Nebraska'
WHEN 'NH' THEN 'New Hampshire'
WHEN 'NJ' THEN 'New Jersey'
WHEN 'NM' THEN 'New Mexico'
WHEN 'NV' THEN 'Nevada'
WHEN 'NY' THEN 'New York'
WHEN 'OH' THEN 'Ohio'
WHEN 'OK' THEN 'Oklahoma'
WHEN 'OR' THEN 'Oregon'
WHEN 'PA' THEN 'Pennsylvania'
WHEN 'RI' THEN 'Rhode Island'
WHEN 'SC' THEN 'South Carolina'
WHEN 'SD' THEN 'South Dakota'
WHEN 'TN' THEN 'Tennessee'
WHEN 'TX' THEN 'Texas'
WHEN 'UT' THEN 'Utah'
WHEN 'VA' THEN 'Virginia'
WHEN 'VT' THEN 'Vermont'
WHEN 'WA' THEN 'Washington'
WHEN 'WI' THEN 'Wisconsin'
WHEN 'WV' THEN 'West Virginia'
WHEN 'WY' THEN 'Wyoming'
END</pre>
</div>
</details>

---

### Calculation 2 — State Abbreviation

Used as the label inside each tile. Two-letter abbreviations keep tiles readable at any size.

<details class="bg-[#252525]/50 rounded-xl border border-[#2a2a2a] p-4 my-6">
<summary class="cursor-pointer font-bold text-[#4a8e91] hover:text-[#6aacaf] list-none flex justify-between items-center">
    <span>▶ State Abbreviation — Full CASE WHEN</span>
    <button id="copy-abbr-btn" onclick="copyCode('abbrCode', 'copy-abbr-btn', event)" class="text-xs bg-[#3c6e71]/20 hover:bg-[#3c6e71]/40 text-[#6aacaf] px-3 py-1 rounded-lg transition-all">Copy Code</button>
</summary>
<div class="mt-4 overflow-x-auto">
<pre id="abbrCode" class="text-sm text-[#d9d9d9] font-mono leading-relaxed bg-[#252525] p-4 rounded-lg border border-[#3c6e71]/50">CASE [State Name]
WHEN 'Alaska' THEN 'AK'
WHEN 'Alabama' THEN 'AL'
WHEN 'Arkansas' THEN 'AR'
WHEN 'Arizona' THEN 'AZ'
WHEN 'California' THEN 'CA'
WHEN 'Colorado' THEN 'CO'
WHEN 'Connecticut' THEN 'CT'
WHEN 'District of Columbia' THEN 'DC'
WHEN 'Delaware' THEN 'DE'
WHEN 'Florida' THEN 'FL'
WHEN 'Georgia' THEN 'GA'
WHEN 'Hawaii' THEN 'HI'
WHEN 'Iowa' THEN 'IA'
WHEN 'Idaho' THEN 'ID'
WHEN 'Illinois' THEN 'IL'
WHEN 'Indiana' THEN 'IN'
WHEN 'Kansas' THEN 'KS'
WHEN 'Kentucky' THEN 'KY'
WHEN 'Louisiana' THEN 'LA'
WHEN 'Massachusetts' THEN 'MA'
WHEN 'Maryland' THEN 'MD'
WHEN 'Maine' THEN 'ME'
WHEN 'Michigan' THEN 'MI'
WHEN 'Minnesota' THEN 'MN'
WHEN 'Missouri' THEN 'MO'
WHEN 'Mississippi' THEN 'MS'
WHEN 'Montana' THEN 'MT'
WHEN 'North Carolina' THEN 'NC'
WHEN 'North Dakota' THEN 'ND'
WHEN 'Nebraska' THEN 'NE'
WHEN 'New Hampshire' THEN 'NH'
WHEN 'New Jersey' THEN 'NJ'
WHEN 'New Mexico' THEN 'NM'
WHEN 'Nevada' THEN 'NV'
WHEN 'New York' THEN 'NY'
WHEN 'Ohio' THEN 'OH'
WHEN 'Oklahoma' THEN 'OK'
WHEN 'Oregon' THEN 'OR'
WHEN 'Pennsylvania' THEN 'PA'
WHEN 'Rhode Island' THEN 'RI'
WHEN 'South Carolina' THEN 'SC'
WHEN 'South Dakota' THEN 'SD'
WHEN 'Tennessee' THEN 'TN'
WHEN 'Texas' THEN 'TX'
WHEN 'Utah' THEN 'UT'
WHEN 'Virginia' THEN 'VA'
WHEN 'Vermont' THEN 'VT'
WHEN 'Washington' THEN 'WA'
WHEN 'Wisconsin' THEN 'WI'
WHEN 'West Virginia' THEN 'WV'
WHEN 'Wyoming' THEN 'WY'
END</pre>
</div>
</details>

---

### Calculation 3 — Column (X coordinate)

This places each state along the horizontal axis. The values range from 1 (far west) to 11 (far northeast), loosely mirroring real US geography.

<details class="bg-[#252525]/50 rounded-xl border border-[#2a2a2a] p-4 my-6">
<summary class="cursor-pointer font-bold text-[#4a8e91] hover:text-[#6aacaf] list-none flex justify-between items-center">
    <span>▶ Column — Full CASE WHEN</span>
    <button id="copy-col-btn" onclick="copyCode('colCode', 'copy-col-btn', event)" class="text-xs bg-[#3c6e71]/20 hover:bg-[#3c6e71]/40 text-[#6aacaf] px-3 py-1 rounded-lg transition-all">Copy Code</button>
</summary>
<div class="mt-4 overflow-x-auto">
<pre id="colCode" class="text-sm text-[#d9d9d9] font-mono leading-relaxed bg-[#252525] p-4 rounded-lg border border-[#3c6e71]/50">CASE [State Name]
WHEN 'Alaska' THEN 1
WHEN 'Alabama' THEN 7
WHEN 'Arkansas' THEN 5
WHEN 'Arizona' THEN 2
WHEN 'California' THEN 1
WHEN 'Colorado' THEN 3
WHEN 'Connecticut' THEN 10
WHEN 'District of Columbia' THEN 9
WHEN 'Delaware' THEN 10
WHEN 'Florida' THEN 9
WHEN 'Georgia' THEN 8
WHEN 'Hawaii' THEN 1
WHEN 'Iowa' THEN 5
WHEN 'Idaho' THEN 2
WHEN 'Illinois' THEN 6
WHEN 'Indiana' THEN 6
WHEN 'Kansas' THEN 4
WHEN 'Kentucky' THEN 6
WHEN 'Louisiana' THEN 5
WHEN 'Massachusetts' THEN 10
WHEN 'Maryland' THEN 9
WHEN 'Maine' THEN 11
WHEN 'Michigan' THEN 7
WHEN 'Minnesota' THEN 5
WHEN 'Missouri' THEN 5
WHEN 'Mississippi' THEN 6
WHEN 'Montana' THEN 3
WHEN 'North Carolina' THEN 7
WHEN 'North Dakota' THEN 4
WHEN 'Nebraska' THEN 4
WHEN 'New Hampshire' THEN 11
WHEN 'New Jersey' THEN 9
WHEN 'New Mexico' THEN 3
WHEN 'Nevada' THEN 2
WHEN 'New York' THEN 9
WHEN 'Ohio' THEN 7
WHEN 'Oklahoma' THEN 4
WHEN 'Oregon' THEN 1
WHEN 'Pennsylvania' THEN 8
WHEN 'Rhode Island' THEN 11
WHEN 'South Carolina' THEN 8
WHEN 'South Dakota' THEN 4
WHEN 'Tennessee' THEN 6
WHEN 'Texas' THEN 4
WHEN 'Utah' THEN 2
WHEN 'Virginia' THEN 8
WHEN 'Vermont' THEN 10
WHEN 'Washington' THEN 1
WHEN 'Wisconsin' THEN 6
WHEN 'West Virginia' THEN 7
WHEN 'Wyoming' THEN 3
END</pre>
</div>
</details>

---

### Calculation 4 — Row (Y coordinate)

This places each state along the vertical axis. Row 1 is the top (Alaska, Maine), Row 8 is the bottom (Hawaii, Florida, Texas).

<details class="bg-[#252525]/50 rounded-xl border border-[#2a2a2a] p-4 my-6">
<summary class="cursor-pointer font-bold text-[#4a8e91] hover:text-[#6aacaf] list-none flex justify-between items-center">
    <span>▶ Row — Full CASE WHEN</span>
    <button id="copy-row-btn" onclick="copyCode('rowCode', 'copy-row-btn', event)" class="text-xs bg-[#3c6e71]/20 hover:bg-[#3c6e71]/40 text-[#6aacaf] px-3 py-1 rounded-lg border border-[#3c6e71]/50 transition-all">Copy Code</button>
</summary>
<div class="mt-4 overflow-x-auto">
<pre id="rowCode" class="text-sm text-[#d9d9d9] font-mono leading-relaxed bg-[#252525] p-4 rounded-lg border border-[#3c6e71]/50">CASE [State Name]
WHEN 'Alaska' THEN 1
WHEN 'Alabama' THEN 7
WHEN 'Arkansas' THEN 6
WHEN 'Arizona' THEN 6
WHEN 'California' THEN 5
WHEN 'Colorado' THEN 5
WHEN 'Connecticut' THEN 4
WHEN 'District of Columbia' THEN 6
WHEN 'Delaware' THEN 5
WHEN 'Florida' THEN 8
WHEN 'Georgia' THEN 7
WHEN 'Hawaii' THEN 8
WHEN 'Iowa' THEN 4
WHEN 'Idaho' THEN 3
WHEN 'Illinois' THEN 3
WHEN 'Indiana' THEN 4
WHEN 'Kansas' THEN 6
WHEN 'Kentucky' THEN 5
WHEN 'Louisiana' THEN 7
WHEN 'Massachusetts' THEN 3
WHEN 'Maryland' THEN 5
WHEN 'Maine' THEN 1
WHEN 'Michigan' THEN 3
WHEN 'Minnesota' THEN 3
WHEN 'Missouri' THEN 5
WHEN 'Mississippi' THEN 7
WHEN 'Montana' THEN 3
WHEN 'North Carolina' THEN 6
WHEN 'North Dakota' THEN 3
WHEN 'Nebraska' THEN 5
WHEN 'New Hampshire' THEN 2
WHEN 'New Jersey' THEN 4
WHEN 'New Mexico' THEN 6
WHEN 'Nevada' THEN 4
WHEN 'New York' THEN 3
WHEN 'Ohio' THEN 4
WHEN 'Oklahoma' THEN 7
WHEN 'Oregon' THEN 4
WHEN 'Pennsylvania' THEN 4
WHEN 'Rhode Island' THEN 4
WHEN 'South Carolina' THEN 6
WHEN 'South Dakota' THEN 4
WHEN 'Tennessee' THEN 6
WHEN 'Texas' THEN 8
WHEN 'Utah' THEN 5
WHEN 'Virginia' THEN 5
WHEN 'Vermont' THEN 2
WHEN 'Washington' THEN 3
WHEN 'Wisconsin' THEN 2
WHEN 'West Virginia' THEN 5
WHEN 'Wyoming' THEN 4
END</pre>
</div>
</details>

---

## 🛠 Step 2: Build the View

Once your four calculated fields are ready:

1. **Drag `Column` to Columns** and `Row` to Rows on the sheet
2. **Right-click both pills** and set them to **Dimension** — not Measure. This prevents Tableau from aggregating the coordinates
3. **Change the mark type to Square** — this gives each state an equal-sized filled tile
4. **Drag `State Abbreviation` to Label** — centre-align it so it sits in the middle of each square
5. **Drag your metric** (e.g. sales, jobs, whatever your data contains) **to Color**

<div class="p-6 bg-[#3c6e71]/5 border-l-4 border-[#3c6e71] rounded-r-2xl my-8">
    <h4 class="text-white font-bold mb-2">💡 Pro Tip: Hide the Headers</h4>
    <p class="text-[#b0bfc0] text-sm">Right-click the Column and Row axes and select <strong>Show Header</strong> to toggle them off. The numeric axis labels add nothing to the viz and hiding them gives you a much cleaner, more polished dashboard with no extra configuration needed.</p>
</div>

---

## 🎨 Step 3: Why This Layout Beats a Standard Map

<div class="grid grid-cols-1 md:grid-cols-2 gap-6 my-8 not-prose">
    <div class="p-6 bg-[#2a2a2a]/40 border border-[#3c6e71] rounded-2xl">
        <h4 class="text-red-400 font-bold text-sm uppercase tracking-widest mb-3">Standard Choropleth Map</h4>
        <ul class="space-y-2 text-[#b0bfc0] text-sm">
            <li>❌ Alaska visually dominates (largest state by area)</li>
            <li>❌ Rhode Island near-invisible (0.4% of Alaska's size)</li>
            <li>❌ Color differences hard to spot on tiny states</li>
            <li>❌ Layout fixed — you can't reposition states</li>
        </ul>
    </div>
    <div class="p-6 bg-[#2a2a2a]/40 border border-[#3c6e71]/30 rounded-2xl">
        <h4 class="text-[#4a8e91] font-bold text-sm uppercase tracking-widest mb-3">Tile Map</h4>
        <ul class="space-y-2 text-[#b0bfc0] text-sm">
            <li>✅ Every state gets identical visual weight</li>
            <li>✅ Rhode Island as readable as Texas</li>
            <li>✅ Color, shape, and size all fully customizable per tile</li>
            <li>✅ Move any state by changing one coordinate value</li>
        </ul>
    </div>
</div>

The real power shows up in dense, data-heavy dashboards. When you need the viewer to compare all 50 states at once — not just spot which large states are red — a tile map does the job that a choropleth simply cannot.

---

## 📊 See It in Action

Here's a live example using this exact technique — US job demand data mapped across all 50 states with equal tile sizes:

<div class="not-prose my-10">
    <div class="aspect-video w-full rounded-2xl overflow-hidden border border-[#3c6e71] shadow-2xl">
        <iframe
            src="https://public.tableau.com/views/Themostin-demandjobsacrosstheU_S_/Themostin-demandjobsacrosstheU_S_?:language=en-US&:embed=y&:display_count=n&:origin=viz_share_link&:showVizHome=no"
            class="w-full h-full"
            frameborder="0"
            allowfullscreen>
        </iframe>
    </div>
    <p class="text-[#8a9a9b] text-xs text-center mt-3 font-mono">Interactive — hover over any state to see the data. <a href="https://public.tableau.com/app/profile/tamasszabo/viz/Themostin-demandjobsacrosstheU_S_/Themostin-demandjobsacrosstheU_S_" target="_blank" class="text-[#4a8e91] hover:underline">Open full screen on Tableau Public →</a></p>
</div>

---

## 🔑 The Key Insight

The tile map isn't just a design preference — it's an analytical decision. When your data has a value for every state and you need a viewer to make fair comparisons across all of them, equal-area representation is the *correct* choice. Geography should inform layout, not distort perception.

Saving the coordinates as calculated fields also means the grid travels with your workbook. Copy the four calculations into any new Tableau project and your tile map scaffold is ready in under a minute.

<div class="not-prose mt-12 p-8 bg-[#3c6e71]/5 border border-[#3c6e71]/20 rounded-3xl text-center space-y-4">
    <h3 class="text-white font-bold text-xl">Want to use this in your own workbook?</h3>
    <p class="text-[#b0bfc0] text-sm max-w-md mx-auto">All four calculations are in the collapsible blocks above — copy them directly into any Tableau project. If you build something with this technique, I'd love to see it.</p>
    <a href="/work-with-me/#contact" class="inline-block bg-[#3c6e71] hover:bg-[#4a8e91] text-white font-bold px-6 py-3 rounded-xl transition-all text-sm uppercase tracking-widest">
        Share Your Map →
    </a>
</div>

<script>
function copyCode(elementId, btnId, e) {
    e.preventDefault();
    var code = document.getElementById(elementId).innerText;
    navigator.clipboard.writeText(code).then(function() {
        var btn = document.getElementById(btnId);
        var original = btn.innerText;
        btn.innerText = '✓ Copied!';
        btn.classList.add('bg-[#3c6e71]/40', 'text-white');
        setTimeout(function() {
            btn.innerText = original;
            btn.classList.remove('bg-[#3c6e71]/40', 'text-white');
        }, 2000);
    });
}
</script>
