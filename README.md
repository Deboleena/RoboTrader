🤖 Robo Trader: AI-
Driven Investment Orchestration
Overview
The Robo Trader is a sophisticated multi-agent system built using Gemini models to automate the
investment decision-making and trade execution process. It performs real-time financial research,
analyzes earnings data, and applies expert reasoning to generate a clear investment signal
(BUY,
HOLD
, or SELL
)
. If a positive signal is generated, the system proceeds to automatically place a mock
trade order with a simulated brokerage API.
This project demonstrates a practical application of AI agents for high-stakes, multi-step workflows,
ensuring transparent and auditable decision-making for automated trading.
✨ Features
Multi-Agent Architecture: Utilizes specialized agents (Research,
down complex tasks.
Decision, Execution) to break
Real-Time Financial Analysis: Agents perform deep dives into company fundamentals, earnings,
and market sentiment (via Google Search grounding
)
.
Automated Decision-
HOLD)
based on aggregated data.
Making: Generates an explicit investment recommendation (e.g.
,
BUY,
Mock Trade Execution: Integrates a custom tool
(
API interactions for placing orders.
c
mo
k_
uy_sto
c
b
k_order) to simulate real-world
Reproducibility:
iteration.
Developed in a Jupyter Notebook/Kaggle environment for easy testing and
📐 Architecture and Workflow
The system is orchestrated through a root agent that enforces a sequential, controlled workflow,
ensuring the investment decision is grounded in research before any trade is attempted.
Agent Name Function Tools Used
Root Agent Orchestrates the entire workflow: Research → Decision →
Execution.
N/A
Parallel
Research
Team
(Implied: ParallelAgent) Gathers current events, earnings
reports, analyst sentiment, and financial health data for
the target company.
Google Search
Grounding
)
(Real-time
https://gemini.google.com/app/97b526cb23aa67a1 1/3
11/26/25, 11:10 AM Google Gemini
Decision-
Making Agent
(Implied: SequentialAgent) Synthesizes all gathered
research into a final, actionable investment
recommendation (BUY/HOLD/SELL
)
.
N/A
Execution
Agent
Manages the final trade process. Calls the external API
function based on the Decision Agent's output.
c
mo
k_
uy_sto
c
k_order()
b
🛠 Setup and Installation
This project is built using Python and the Google AI Agent Development Kit (
A
multi-agent pattern using the google-genai SDK
)
.
DK
)
framework
(or similar
Prerequisites
1. Python 3.10+
2. Gemini API Key: Obtain an API key from Google AI Studio.
1.
Environment Setup
It is highly recommended to run this project in the Kaggle Notebook environment where it was
developed, as the execution steps and data handling are optimized for that environment.
Alternatively, for local execution:
# 1. Clone the repository
git clone [https://githu
.c
b
om/your-username/ro
b
o-trader.git](https://githu
b
cd ro
o-trader
.c
om/your-us
b
# 2. Install dependen
cies (Requires a framework like google-adk or other agent li
b
# Example (if using c
ommon ADK structure):
# pip install google-adk numpy pandas
s)
# 3. Set API Key
export GEMINI_API_KEY="YOUR_API_KEY_HERE"
2. Running the Notebook
Execute the provided Jupyter Notebook
(
dm-capstone-project-ro
otrader.ipyn
b
b
) cell-by-cell.
🚀 Example Run: Amazon.com, Inc.
The following is an example of the execution flow when targeting Amazon.com, Inc. (
A
MZN
)
:
1. Input:
c
ompany = '
Amazon.c
om, In
c.'
2. Decision Agent Output: The agent analyzes strong financial results, positive analyst sentiment,
and promising future guidance, concluding: A
BUY recommendation is warranted.
https://gemini.google.com/app/97b526cb23aa67a1 2/3
11/26/25, 11:10 AM Google Gemini
3. Execution Agent Action: The Execution Agent receives the BUY tool.
signal and calls the mock trading
--- Sending Mo
c
k Order Request ---
URL: [https://api.schwa
api.c
b
om/v1/acc
Payload (Partial): {
"orderType"
:
"MARKET",
"session"
:
"NORMAL",
"duration"
:
"DAY",
"orderLegCollection"
: [
{
ounts/12345678/orders](https://api.schwa
b
api.c
om/
"instruction"
:
"BUY",
"quantity"
: 10,
"instrument"
: {
"sym
ol"
:
"
AMZN",
b
"assetType"
:
"EQUITY"
}
}
]
}
ExecutionAgent > I have placed a mo
c
k
uy order for 10 shares of AMZN. The order has
b
e
b
🛑 Disclaimer
This is a mock implementation for educational and demonstration purposes only. It uses simulated
https://gemini.google.com/app/97b526cb23aa67a1 3/3
