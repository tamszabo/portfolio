---
layout: default
title: Resume
permalink: /cv/
---

<style>
@media print {
    /* 1. Hide Web UI */
    nav, footer, button {
        display: none !important;
    }

    /* 2. Reset to Light Theme for Printing */
    @page {
        margin: 1.5cm; /* Standard professional margin */
    }

    body, html, main, .max-w-5xl {
        background: white !important;
        color: #1e293b !important; /* Slate-800 for maximum readability */
        margin: 0 !important;
        padding: 0 !important;
        width: 100% !important;
    }

    /* 3. Adjust Typography for white paper */
    h1, h2, h3 {
        color: #0f172a !important; /* Darker Slate for headings */
    }
    
    .text-indigo-500, .text-indigo-400 {
        color: #4f46e5 !important; /* Solid Indigo-600 for contrast */
    }

    .text-slate-400, .text-slate-500 {
        color: #475569 !important; /* Slate-600 for subtext */
    }

    /* 4. Ensure Logos look crisp */
    .absolute.left-0 {
        border: 1px solid #e2e8f0 !important;
        background: white !important;
    }

    /* 5. Clean up the Layout */
    .border-b {
        border-bottom: 1px solid #e2e8f0 !important;
    }

    .relative {
        page-break-inside: avoid !important;
        margin-bottom: 2rem !important;
    }
}
</style>

<div class="flex justify-between items-center mb-10 pb-4 border-b border-slate-800">
    <h1 class="text-3xl font-black text-white uppercase tracking-tighter">
        Tamas <span class="text-indigo-500">Szabo</span>
    </h1>
    <button onclick="window.print()" class="text-xs font-bold uppercase tracking-widest text-slate-500 hover:text-indigo-400 transition border border-slate-800 px-4 py-2 rounded-lg">
        Print to PDF 📄
    </button>
</div>

<section class="mb-12">
    <div class="flex flex-col md:flex-row md:justify-between md:items-center gap-4 mb-6">
        <h2 class="text-xl font-bold text-white">Senior Data Analyst</h2>
        <div class="flex gap-4 text-xs text-slate-500 font-mono">
            <span>📍 Frankfurt am Main, DE</span>
            <span>✉️ prostaw@gmail.com</span>
        </div>
    </div>
    <p class="text-slate-400 leading-relaxed italic border-l-2 border-indigo-500 pl-4">
        Senior Data Analyst with over 8 years of experience driving executive decision-making within international corporate environments. Proven track record of translating complex datasets into actionable business insights for C-level stakeholders across multiple European markets. Expert in bridging the gap between Business and IT through strategic KPI frameworks and cross-functional leadership.
    </p>
</section>

<section class="space-y-12">
    <h2 class="text-xs font-black uppercase tracking-[0.2em] text-indigo-500 mb-8">Professional Experience</h2>
    <div class="relative pl-14">
        <div class="absolute left-0 top-1 w-12 h-12 bg-white rounded-md overflow-hidden border border-slate-700 shadow-sm flex items-center justify-center">
            <img src="{{ '/assets/logos/hyundai-logo.jpg' | relative_url }}" alt="Hyundai" class="max-w-full max-h-full object-contain">
        </div>
        <div class="flex flex-col md:flex-row md:justify-between md:items-baseline mb-1">
            <h3 class="text-lg font-bold text-white">Hyundai Motor Europe</h3>
            <span class="text-sm font-mono text-slate-500">10/2023 — 07/2025</span>
        </div>
        <p class="text-indigo-400 text-sm font-semibold mb-3 italic">Senior Data Analyst | Frankfurt am Main, Germany</p>
        <ul class="list-disc list-outside ml-4 space-y-2 text-slate-400 text-sm">
            <li><strong>Executive Insights:</strong> Engineered a comprehensive C-suite sales funnel report by creating a unified data model from SAP, Siebel, and GA4 datasets.</li>
            <li><strong>Infrastructure Optimization:</strong> Orchestrated and executed a Tableau Server migration and upgrade, resulting in a significant increase in processing speeds and dashboard responsiveness.</li>
            <li><strong>Data Literacy Leadership:</strong> Launched and led a Tableau mentorship program across the organization, successfully increasing data literacy and self-service analytics capabilities for regional teams.</li>
            <li><strong>Stakeholder Management:</strong> Partnered with C-level leaders to reduce time-to-insight for regional performance reviews by 30%.</li>
        </ul>
    </div>
    <div class="relative pl-14">
        <div class="absolute left-0 top-1 w-12 h-12 bg-white rounded-md overflow-hidden border border-slate-700 shadow-sm flex items-center justify-center">
            <img src="{{ '/assets/logos/hcltech-logo.jpg' | relative_url }}" alt="Starschema" class="max-w-full max-h-full object-contain">
        </div>
        <div class="flex flex-col md:flex-row md:justify-between md:items-baseline mb-1">
            <h3 class="text-lg font-bold text-white">Starschema</h3>
            <span class="text-sm font-mono text-slate-500">12/2019 — 09/2023</span>
        </div>
        <p class="text-indigo-400 text-sm font-semibold mb-3 italic">Data Analyst | Budapest, Hungary</p>
        <ul class="list-disc list-outside ml-4 space-y-2 text-slate-400 text-sm">
            <li><strong>Fortune 500 Consultancy:</strong> Acted as a consultant for global giants including <strong>Apple, GE, and BlackRock</strong>, performing rapid environment assessments and delivering high-impact business insights under tight deadlines.</li>
            <li><strong>Strategic Sales Support:</strong> Served as the lead designer for a high-stakes sports analytics proof of concept (POC) for NFL and Soccer teams; the initiative directly resulted in securing the Los Angeles Rams as a marquee client.</li>
            <li><strong>KPI Standardization:</strong> Defined and implemented global KPI frameworks, ensuring 100% transparency in management metrics across international teams.</li>
            <li><strong>Workshop Facilitation:</strong> Educated non-technical stakeholders through targeted workshops, improving data understanding and reporting quality.</li>
        </ul>
    </div>
    <div class="relative pl-14">
        <div class="absolute left-0 top-1 w-12 h-12 bg-white rounded-md overflow-hidden border border-slate-700 shadow-sm flex items-center justify-center">
            <img src="{{ '/assets/logos/intrum-logo.jpg' | relative_url }}" alt="Intrum" class="max-w-full max-h-full object-contain">
        </div>
        <div class="flex flex-col md:flex-row md:justify-between md:items-baseline mb-1">
            <h3 class="text-lg font-bold text-white">Intrum</h3>
            <span class="text-sm font-mono text-slate-500">07/2017 — 11/2019</span>
        </div>
        <p class="text-indigo-400 text-sm font-semibold mb-3 italic">Business Intelligence Analyst | Budapest, Hungary</p>
        <ul class="list-disc list-outside ml-4 space-y-2 text-slate-400 text-sm">
            <li><strong>Strategic Business Pivot:</strong> Collaborated with the controlling team to conduct a deep-dive cost analysis that identified non-profitable operations, directly leading to the strategic discontinuation of a major business line.</li>
            <li><strong>Executive Education:</strong> Developed a suite of executive-level reports and mentored C-suite stakeholders on business intelligence best practices to drive data-driven decision-making.</li>
            <li><strong>Infrastructure Growth:</strong> Contributed to the architecture of a centralized analytics infrastructure for faster regional data access.</li>
        </ul>
    </div>
    <div class="relative pl-14">
        <div class="absolute left-0 top-1 w-12 h-12 bg-white rounded-md overflow-hidden border border-slate-700 shadow-sm flex items-center justify-center">
            <img src="{{ '/assets/logos/raiffeisen-bank-logo.jpg' | relative_url }}" alt="Raiffeisen" class="max-w-full max-h-full object-contain">
        </div>
        <div class="flex flex-col md:flex-row md:justify-between md:items-baseline mb-1">
            <h3 class="text-lg font-bold text-white">Raiffeisen Bank</h3>
            <span class="text-sm font-mono text-slate-500">01/2017 — 06/2017</span>
        </div>
        <p class="text-indigo-400 text-sm font-semibold mb-3 italic">Fraud Risk Analyst Trainee | Budapest, Hungary</p>
        <ul class="list-disc list-outside ml-4 space-y-2 text-slate-400 text-sm">
            <li><strong>Process Automation:</strong> Developed an automated Excel-based verification tool for the fraud team to validate customer IDs, significantly reducing manual verification errors and improving departmental efficiency.</li>
        </ul>
    </div>
</section>

<div class="grid grid-cols-1 md:grid-cols-2 gap-12 mt-20 pt-10 border-t border-slate-800">
    <section>
        <h2 class="text-xs font-black uppercase tracking-[0.2em] text-indigo-500 mb-6">Technical Skills</h2>
        <div class="space-y-4">
            <div>
                <h4 class="text-white text-sm font-bold mb-1 text-indigo-300">Data Visualization</h4>
                <p class="text-slate-400 text-sm">Tableau (Certified), Power BI, QlikSense</p>
            </div>
            <div>
                <h4 class="text-white text-sm font-bold mb-1 text-indigo-300">Data Analysis</h4>
                <p class="text-slate-400 text-sm">SQL, Advanced Excel, KPI Framework Development</p>
            </div>
	    <div>
                <h4 class="text-white text-sm font-bold mb-1 text-indigo-300">Soft Skills</h4>
                <p class="text-slate-400 text-sm">Stakeholder Management, Mentoring, Cross-functional Collaboration, Workshop Facilitation</p>
            </div>
            <div>
                <h4 class="text-white text-sm font-bold mb-1 text-indigo-300">Languages</h4>
                <p class="text-slate-400 text-sm">Hungarian (Native), English (Fluent - C1), German (Basic - A2)</p>
            </div>
        </div>
    </section>
    <section class="space-y-8">
        <div>
            <h2 class="text-xs font-black uppercase tracking-[0.2em] text-indigo-500 mb-4">Education</h2>
            <h3 class="text-white font-bold text-sm">BSc in Mathematics</h3>
            <p class="text-slate-500 text-xs italic">Eötvös Loránd University | 2016</p>
        </div>
        <div>
            <h2 class="text-xs font-black uppercase tracking-[0.2em] text-indigo-500 mb-4">Certificates</h2>
            <div class="flex items-center gap-3 bg-slate-900/50 p-3 rounded-lg border border-slate-800">
                <img src="{{ '/assets/logos/tableau-logo.png' | relative_url }}" class="w-8 h-8 object-contain" alt="Tableau">
                <p class="text-white font-bold text-xs uppercase tracking-tighter">Tableau Desktop Specialist</p>
            </div>
        </div>
    </section>
</div>






