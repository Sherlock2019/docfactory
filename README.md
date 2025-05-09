🚀 RFP Modular Builder – Getting Started Guide


🧩 What is it?
RFP Modular Builder is a Terraform-inspired documentation tool that lets you:

Generate custom RFP responses using reusable content modules

Edit and preview each section in a friendly GUI

Auto-fill content using a customer input .txt file

Export everything into a Word doc using your own company template

🛠️ 1. Installation
✅ Prerequisites

Python 3.8+

Git

Streamlit

LibreOffice (optional, for docx preview/export)

🐧 Install (WSL or Linux/macOS):

git clone https://github.com/Sherlock2019/rfp-modular-builder.git
cd rfp-modular-builder
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

▶️ 2. Launch the App

make gui
If make isn't installed:

streamlit run streamlit_app.py
Then open http://localhost:8501 in your browser.

📋 3. Using the App
Step-by-Step:
Upload your .docx template
→ Must contain placeholders like [[EXECUTIVE_SUMMARY]]

(Optional) Upload customer_inputs.txt
→ Format: key = "value" pairs

Choose modules
→ Select which sections to include (e.g., EXECUTIVE_SUMMARY, TECHNICAL_ARCHITECTURE)

Edit content
→ Each module appears as a text box — auto-filled if customer_inputs.txt was uploaded

Generate your RFP document
→ Click “Generate Document” to download a .docx with all placeholders filled

📂 4. Folder Structure

rfp-modular-builder/
├── modules/
│   └── EXECUTIVE_SUMMARY/
│       └── main.txt
│   └── TECHNICAL_ARCHITECTURE/
│       └── main.txt
├── streamlit_app.py
├── Makefile
├── customer_inputs_sample.txt
└── requirements.txt

✍️ 5. Customization
Add your own modules:
Create a folder inside modules/ with a main.txt file.

Define your own placeholders:
Use ${variable_name} inside main.txt to map from customer_inputs.txt

Use any Word Template:
Just ensure it includes [[MODULE_NAME]] placeholders

💬 Example Placeholders
In main.txt:


Welcome ${customer_name}, we're excited to help you meet your goals of ${business_goals}.
In customer_inputs.txt:

customer_name = "Telco ABC"
business_goals = "Build a national private cloud"
🧠 Tips
You can save edited module content back to disk using the “💾 Save” button.

Works offline and doesn’t send data to the cloud.

Ideal for consulting, proposal writing, presales, and technical solutioning teams.

