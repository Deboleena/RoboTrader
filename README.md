<!-----



Conversion time: 0.653 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs™ to Markdown version 2.0β1
* Wed Nov 26 2025 11:35:56 GMT-0800 (PST)
* Source doc: Untitled document
* Tables are currently converted to HTML tables.
----->



# **🤖 Robo Trader: AI-Driven Investment Orchestration**


## **Overview**

The **Robo Trader** is a sophisticated multi-agent system built using Gemini models to automate the investment decision-making and trade execution process. It performs real-time financial research, analyzes earnings data, and applies expert reasoning to generate a clear investment signal (BUY, HOLD, or SELL). If a positive signal is generated, the system proceeds to automatically place a mock trade order with a simulated brokerage API.

This project demonstrates a practical application of AI agents for high-stakes, multi-step workflows, ensuring transparent and auditable decision-making for automated trading.


## **✨ Features**



* **Multi-Agent Architecture:** Utilizes specialized agents (Research, Decision, Execution) to break down complex tasks.
* **Real-Time Financial Analysis:** Agents perform deep dives into company fundamentals, earnings, and market sentiment (via Google Search grounding).
* **Automated Decision-Making:** Generates an explicit investment recommendation (e.g., BUY, HOLD) based on aggregated data.
* **Mock Trade Execution:** Integrates a custom tool (`mock_buy_stock_order`) to simulate real-world API interactions for placing orders.
* **Reproducibility:** Developed in a Jupyter Notebook/Kaggle environment for easy testing and iteration.


## **📐 Architecture and Workflow**

The system is orchestrated through a root agent that enforces a sequential, controlled workflow, ensuring the investment decision is grounded in research before any trade is attempted.


<table>
  <tr>
   <td><strong>Agent Name</strong>
   </td>
   <td><strong>Function</strong>
   </td>
   <td><strong>Tools Used</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Root Agent</strong>
   </td>
   <td>Orchestrates the entire workflow: Research → Decision → Execution.
   </td>
   <td>N/A
   </td>
  </tr>
  <tr>
   <td><strong>Parallel Research Team</strong>
   </td>
   <td><strong>(Implied: ParallelAgent)</strong> Gathers current events, earnings reports, analyst sentiment, and financial health data for the target company.
   </td>
   <td>Google Search (Real-time Grounding)
   </td>
  </tr>
  <tr>
   <td><strong>Decision-Making Agent</strong>
   </td>
   <td><strong>(Implied: SequentialAgent)</strong> Synthesizes all gathered research into a final, actionable investment recommendation (BUY/HOLD/SELL).
   </td>
   <td>N/A
   </td>
  </tr>
  <tr>
   <td><strong>Execution Agent</strong>
   </td>
   <td>Manages the final trade process. Calls the external API function based on the Decision Agent's output
   </td>
   <td><code>mock_buy_stock_order()</code>
   </td>
  </tr>
</table>



## **🛠️ Setup and Installation**

This project is built using Python and the Google AI Agent Development Kit (ADK) framework (or similar multi-agent pattern using the `google-genai` SDK).


### **Prerequisites**



1. **Python 3.10+**
2. **Gemini API Key:** Obtain an API key from Google AI Studio.


### **1. Environment Setup**

It is highly recommended to run this project in the Kaggle Notebook environment where it was developed, as the execution steps and data handling are optimized for that environment.

Alternatively, for local execution:

# 1. Clone the repository

git clone [https://github.com/your-username/robo-trader.git](https://github.com/your-username/robo-trader.git)

cd robo-trader

# 2. Install dependencies (Requires a framework like google-adk or other agent libs)

# Example (if using common ADK structure):

# pip install google-adk numpy pandas

# 3. Set API Key

export GEMINI_API_KEY="YOUR_API_KEY_HERE"


### **2. Running the Notebook**

Execute the provided Jupyter Notebook (`dm-capstone-project-robotrader.ipynb`) cell-by-cell.


## **🚀 Example Run: Amazon.com, Inc.**

The following is an example of the execution flow when targeting **MyCompany **:



1. **Input:** <code>company = '</code>**MyCompany**`'`
2. **Decision Agent Output:** The agent analyzes strong financial results, positive analyst sentiment, and promising future guidance, concluding: **A BUY recommendation is warranted.**
3. **Execution Agent Action:** The Execution Agent receives the `BUY` signal and calls the mock trading tool.

--- Sending Mock Order Request ---

URL: [https://api.schwabapi.com/v1/accounts/12345678/orders]Payload (Partial): {

  "orderType": "MARKET",

  "session": "NORMAL",

  "duration": "DAY",

  "orderLegCollection": [

    {

      "instruction": "BUY",

      "quantity": 10,

      "instrument": {

        "symbol": "Company_Ticker Symbol",

        "assetType": "EQUITY"

      }

    }

  ]

}

ExecutionAgent > I have placed a mock buy order for 10 shares of **MyCompany**. The order has been placed as a MARKET BUY order and the order ID is 123456789.


## **🛑 Disclaimer**

**This is a mock implementation for educational and demonstration purposes only.** It uses simulated APIs and is not connected to any real brokerage or live trading system. **Do not use this code for real financial transactions.** All decisions and outputs are generated by an AI model and should not be considered financial advice.
