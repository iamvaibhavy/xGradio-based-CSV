# xGradio-based CSV Question Answering and Visualization Application
This Python script creates a CSV Question Answering & Visualization App using Gradio, Pandas, Matplotlib, and Ollama (for LLM-based analysis). The app allows users to:

1. Upload a CSV file.
2. Ask a question about the data.
3. Select two columns to generate a plot.
4. Receive an answer from an LLM (Ollama) based on the data.
5. View a generated graph of the selected columns.


## Code Breakdown
### 1. Importing Libraries
gradio: Creates an interactive UI.
pandas: Handles CSV data.
matplotlib.pyplot: Generates plots.
ollama: Calls the LLM model for answering queries.
io: Helps read binary files.

<img width="1470" alt="Image" src="https://github.com/user-attachments/assets/3c615e5c-ee75-4b93-b34f-4b267e586f55" />

### 2.Function to Answer User Queries Using LLM
Takes a user question and the first five rows of the CSV.
Sends the data and question to Ollama’s LLM (llama3.1).
Handles errors in the API response.
Returns the model's response or an error message.

<img width="1470" alt="Image" src="https://github.com/user-attachments/assets/1c9b3f14-cf63-42c9-9a27-174e1723c610" />

### 3.Function to Generate a Graph
Checks if the selected columns exist in the CSV.
Creates a line plot (matplotlib).
Saves the plot as plot.png and returns the file path.

### 4.Function to Process CSV & Generate LLM Answer + Plot
1. Reads the uploaded CSV file.
2. Calls ask_llm() to get an answer based on the data.
3. Calls generate_plot() to create a graph.
4. Returns both the LLM response and the plot path.

<img width="1470" alt="Image" src="https://github.com/user-attachments/assets/816f67d3-2727-40ef-8925-ad8229de7197" />

### 5.Gradio UI Setup
A. Creates a Gradio interface with:
   1. File upload input (CSV).
   2. Text input for user questions.
   3. Text inputs for X and Y columns.
   4. A submit button to process the CSV.
   5. Textbox for LLM response.
   6. Image display for the generated graph.
B. Connects the submit button to the process_csv() function.

<img width="1470" alt="Image" src="https://github.com/user-attachments/assets/b14598f4-a2b0-4519-b451-46ddc4f64205" />

### 6. Running the App
Starts the Gradio app when the script is run.
Prints a local URL where the app is hosted (http://127.0.0.1:7860).



<img width="1470" alt="Image" src="https://github.com/user-attachments/assets/e7d17488-9aa1-4933-830f-d7fb75c92327" />

### Result of Running the Code
1. The app starts locally at http://127.0.0.1:7860.
2. Users can upload a CSV file, ask a question, and specify columns for visualization.
3. The app returns:
a. A text-based answer from the LLM (Ollama) based on the CSV.
b. A plot showing the relationship between the selected columns.



<img width="1470" alt="Image" src="https://github.com/user-attachments/assets/0290ca85-e406-4100-9033-d5867b910296" />



## Result Analysis
1. Outcome (When the App Runs Successfully)
a. The Gradio app starts at http://127.0.0.1:7860.
b. Users can upload a CSV file, ask a question, and specify columns for visualization.
c. The app returns:
   An LLM-generated response based on the CSV data.
   A line plot of the selected X and Y columns.

2. Issues & Crashes (Observed Behavior)
a. The app sometimes crashes, likely due to:
Large CSV files causing memory issues.
Ollama API failures (e.g., incorrect response format).
Invalid column names leading to missing data errors.
b. When it crashes, no output is generated, and the app may need a restart.


# Analysis :-

## Analysis 1:
### Insight 1: Higher price does not always mean higher value
The most expensive property ($13.3M) has fewer bedrooms (4) than other properties at similar price points ($12.2M).
This suggests that factors other than just the number of rooms—such as location or amenities—are influencing the price.

### Insight 2: Area and parking can be important factors in pricing
There is a strong correlation between property size and price.
Properties with more parking spots tend to have higher prices.

### Insight 3: Bathrooms may not be as important as other features
The correlation between the number of bathrooms and price is weaker compared to area size and parking.
Buyers may prioritize other amenities over additional bathrooms.

### Insight 4: Furnishing status can impact sales
Furnished properties tend to be slightly more expensive than semi-furnished ones.
Buyers may be willing to pay a premium for fully furnished homes due to added convenience.

### Insight 5: Basement and hot water heating are rare but valuable features
Only a few properties include basements or hot water heating, which may be highly desirable in colder climates.


## Analysis 2:
### Insight 1: Price is inversely proportional to area
Larger properties tend to be cheaper per square foot, suggesting that buyers might be prioritizing space over luxury.

### Insight 2: Most houses have 3-4 stories, but only half have hot water heating and air conditioning
Buyers seem willing to sacrifice certain luxury features in favor of affordability or space.

### Insight 3: Parking is a top priority for most buyers (80%)
Convenient parking availability significantly impacts desirability.

### Insight 4: Most houses are semi-furnished or furnished, but some buyers prefer unfurnished properties
There is a mix of buyer preferences, suggesting demand for both furnished and unfurnished options.

### Insight 5: The preferential area ("prefarea") is often mentioned alongside parking and furnishing status
Buyers consider the location along with amenities like parking and furnishing when making purchasing decisions.


