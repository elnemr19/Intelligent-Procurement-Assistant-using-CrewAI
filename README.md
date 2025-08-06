# 🛒 Intelligent Procurement Assistant using CrewAI

An AI-powered, multi-agent system for automating procurement research and reporting. This project streamlines the process of discovering, evaluating, and reporting on products (e.g., coffee machines) from multiple online e-commerce platforms using [CrewAI](https://github.com/crewAIInc/crewAI), [Tavily](https://www.tavily.com/), and [ScrapeGraph](https://scrapegraphai.com/). <br><br>



> ✅ Ideal for businesses like Rankyx seeking to make informed, data-driven procurement decisions with minimal manual work.



<img width="1015" height="365" alt="Capture" src="https://github.com/user-attachments/assets/2d04031f-08e0-4577-95a3-7a16748991fc" />



## 🚀 Features

- **🔍 Smart Search Query Generation**
  
     Generates high-intent, localized, and product-specific search queries to discover available products online.

- **🌐 Search Engine Integration (Tavily API)**
  
     Gathers real-time product listings from multiple websites using advanced search tools.

- **🧠 Intelligent Web Scraping (ScrapeGraph API)**
  
     Automatically extracts detailed product information from product pages.

- **📊 Automated Procurement Report (HTML)**
  
     Generates a professional, structured procurement report in HTML using Bootstrap, including comparisons, recommendations, and visuals.




## 🧠 Agents Overview

| Agent                                   | Role                 | Description                                                                              |
| --------------------------------------- | -------------------- | ---------------------------------------------------------------------------------------- |
| **A. SearchQueriesRecommendationAgent** | 🧾 Query Generator   | Crafts high-value, localized search queries based on company needs.                      |
| **B. SearchEngineAgent**                | 🔎 Search Executor   | Uses Tavily to fetch relevant product listings across e-commerce platforms.              |
| **C. ScrapingAgent**                    | 🧹 Product Extractor | Uses ScrapeGraph to scrape product pages and extract detailed specs and prices.          |
| **D. ProcurementReportAuthorAgent**     | 📝 Report Writer     | Generates a polished HTML report summarizing findings, comparisons, and recommendations. |


<br><br>


## 🛠️ Tech Stack & Tools

| Tool / Library              | Purpose                                       |
| --------------------------- | --------------------------------------------- |
| **CrewAI**                  | Orchestrates multi-agent workflow             |
| **TavilyClient**            | Real-time web search for product discovery    |
| **ScrapeGraph-Py**          | Structured data extraction from product pages |
| **Pydantic**                | Validates structured JSON output from agents  |
| **Google Colab + userdata** | Securely handles API keys and config          |
| **Bootstrap (via HTML)**    | Clean UI for procurement report               |





## 📦 Output Structure

`step_1_suggested_search_queries.json`: Generated search queries

`step_2_search_results.json`: Search results with title, URLs, and confidence scores

`step_3_search_results.json`: Structured product details (price, specs, image, etc.)

`step_4_procurement_report.html`: Final procurement report with recommendations





## 📂 Sample Use Case

```python
rankyx_crew.kickoff(
    inputs={
        "product_name": "coffee machine for the office",
        "websites_list": [
            "www.amazon.eg", 
            "www.jumia.com.eg", 
            "www.noon.com/egypt-en"
        ],
        "country_name": "Egypt",
        "no_keywords": 10,
        "language": "English",
        "score_th": 0.10,
        "top_recommendations_no": 10
    }
)
```


## 📑 Report Sections (Generated HTML)

1. Executive Summary

2. Introduction

3. Methodology

3. Findings (Comparisons, tables, and product charts)

4. Analysis

5. Recommendations

6. Conclusion

7. Appendices


## 🔐 Environment Variables (Colab/Userdata)

Ensure these environment variables are loaded before running:

```python
os.environ["GROQ_API_KEY"] = userdata.get('GROQ_API_KEY')
os.environ["AGENTOPS_API_KEY"] = userdata.get('AgentOps')
os.environ["GEMINI_API_KEY"] = userdata.get('GEMINI_API_KEY')
os.environ["TVLY_API_KEY"] = userdata.get('tvly-search')
```




## 🧠 Advanced Concepts Used

- `@tool` decorators for custom tools integration

- `StringKnowledgeSource` for contextual company information

- `Pydantic` classes for output validation

- `AgentOps` integration for agent session tracking (optional)




## 📈 Ideal Applications

- Procurement automation for SMBs and enterprises

- Market research and product comparison

- Competitive product intelligence

- E-commerce procurement analytics

