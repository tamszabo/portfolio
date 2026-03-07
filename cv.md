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
        Print to PDF
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

    <!-- Hyundai -->
    <div class="relative pl-14">
        <div class="absolute left-0 top-1 w-12 h-12 bg-white rounded-md overflow-hidden border border-slate-700 shadow-sm flex items-center justify-center">
            <img src="{{ '/assets/logos/hyundai-logo.png' | relative_url }}" alt="Hyundai" class="max-w-full max-h-full object-contain">
        </div>
        <div class="flex flex-col md:flex-row md:justify-between md:items-baseline mb-1">
            <h3 class="text-lg font-bold text-white">Hyundai Motor Europe</h3>
            <span class="text-sm font-mono text-slate-500">10/2023 — 07/2025</span>
        </div>
        <p class="text-indigo-400 text-sm font-semibold mb-3 italic">Senior Data Analyst | Frankfurt am Main, Germany</p>
        <ul class="list-disc list-outside ml-4 space-y-2 text-slate-400 text-sm">
            <li><strong>Executive Insights:</strong> Engineered a C-suite sales funnel report by unifying SAP, Siebel, and GA4 into a single data model — giving leadership a consolidated view of regional performance for the first time.</li>
            <li><strong>Infrastructure Optimization:</strong> Led a full Tableau Server migration serving 50–200 users across European markets, delivering measurably faster processing speeds and dashboard load times organization-wide.</li>
            <li><strong>Data Literacy Leadership:</strong> Launched and ran a Tableau mentorship program that scaled self-service analytics across regional teams, reducing ad-hoc analyst requests and empowering non-technical stakeholders.</li>
            <li><strong>Stakeholder Management:</strong> Partnered directly with C-level leaders to cut time-to-insight for regional performance reviews by 30%.</li>
        </ul>
    </div>

    <!-- Starschema -->
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
            <li><strong>Fortune 500 Consultancy:</strong> Delivered high-impact analytics engagements for <strong>Apple, GE, and BlackRock</strong> — conducting rapid environment assessments and producing executive-ready insights under tight client deadlines.</li>
            <li><strong>Strategic Sales Support:</strong> Led data and visualization design for a sports analytics POC targeting NFL and soccer teams; the engagement directly secured the <strong>Los Angeles Rams</strong> as a paying client.</li>
            <li><strong>KPI Standardization:</strong> Designed and implemented global KPI frameworks adopted across international teams, achieving 100% transparency in management metrics.</li>
            <li><strong>Workshop Facilitation:</strong> Delivered targeted data literacy workshops to non-technical stakeholders, raising reporting quality and reducing miscommunication between business and IT.</li>
        </ul>
    </div>

    <!-- Intrum -->
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
            <li><strong>Strategic Business Pivot:</strong> Partnered with the controlling team on a deep-dive cost analysis that identified a non-profitable business line — findings directly drove its discontinuation, contributing to a €0.5–2M cost impact.</li>
            <li><strong>Executive Education:</strong> Built and delivered a suite of executive-level BI reports; mentored C-suite stakeholders on data-driven decision-making best practices.</li>
            <li><strong>Infrastructure Growth:</strong> Contributed to the architecture of a centralized analytics infrastructure, accelerating data access for regional teams across multiple European markets.</li>
        </ul>
    </div>

    <!-- Raiffeisen -->
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
            <li><strong>Process Automation:</strong> Built an automated Excel-based customer ID verification tool for the fraud team, eliminating a manual, error-prone process and significantly improving departmental throughput and accuracy.</li>
        </ul>
    </div>
</section>

<div class="grid grid-cols-1 md:grid-cols-2 gap-12 mt-20 pt-10 border-t border-slate-800">
    <section>
        <h2 class="text-xs font-black uppercase tracking-[0.2em] text-indigo-500 mb-6">Technical Skills</h2>
        <div class="space-y-4">
            <div>
                <h4 class="text-white text-sm font-bold mb-1 text-indigo-300">Data Visualization</h4>
                <p class="text-slate-400 text-sm">Tableau <span class="text-indigo-400 font-semibold">(Desktop Specialist Certified)</span>, Power BI, QlikSense</p>
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
                <p class="text-slate-400 text-sm">Hungarian (Native), English (Fluent — C1), German (Beginner — A2)</p>
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


