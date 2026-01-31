# 🍽️ Restaurant Review Analysis with IBM Granite 
Capstone Project – Hacktiv8 x IBM SkillsBuild | by Davina Icasia

---

## 📌 PROJECT OVERVIEW 

### 🎯 Project Objective 
1. Automatically analyze restaurant customer reviews using the IBM Granite Large Language Model (LLM).
2. Classify each review into sentiment categories: Positive, Negative, or Mixed.
3. Identify key aspects frequently mentioned by customers, such as food, service, price, and cleanliness.
4. Generate summarized insights and actionable suggestions to help restaurant owners enhance customer experience.

### 🧠 Background 

In today’s digital era, online restaurant reviews from any platforms play a crucial role in shaping public perception and customer purchasing decisions. These reviews contain not only expressions of customer satisfaction but also valuable insights regarding service quality, food, pricing, and cleanliness directly from the customer’s perspective. However, the unstructured nature and massive volume of these reviews make it difficult for business owners and analysts to extract insights effectively and objectively. This calls for an AI driven approach to automate the analysis of sentiment and extract key themes from customer feedback.

### ❗ Specific Problems
1. Customer reviews are unstructured, written in diverse natural language formats that are difficult to process using conventional techniques.
2. Manual sentiment identification is time consuming and subject to human bias.
3. Important aspects are often implicit, embedded in long and complex sentences, requiring advanced NLP models to extract them effectively.
4. Lack of structured insights from the reviews makes it hard for restaurant owners to make data driven decisions.

### ⚙️ Approach 
1. Data Cleaning
2. Prompt Engineering with IBM Granite (Classification and Summarization)
3. Model Used: Granite-3.3-8B-Instruct by IBM, accessed via Replicate API.

---

## 📊 DATASET DESCRIPTION 
1. Total columns: 2 columns
- Review
- Liked
2. Total rows: 1000 rows
3. Link Kaggle: https://www.kaggle.com/datasets/vigneshwarsofficial/reviews?resource=download

---

## 🔢 ANALYSIS PROCESS 

### 🧹 Data Cleaning 
1. Check for Missing Values 

This loop goes through each column in the dataset. It prints the number of missing (null) values for each column. 

2. Detect and Remove Duplicate Rows

This line checks how many duplicate rows exist in the dataset. After that, this command removes all duplicate rows from the dataset. Then, the duplicate check is run again to confirm that all duplicates have been successfully removed.

3. Clean Unnecessary Characters in Text

To standardize the text, multiple whitespace characters are replaced with a single space using regex (\s+), and any leading or trailing spaces are removed using .strip(). After cleaning the text, the dataset is saved as a new file named Dataset_Bersih_RestaurantReview.csv for further analysis.

"Data cleaning ensures the dataset is consistent and reliable by handling missing values, removing duplicates, and standardizing text making it ready for accurate analysis."

### 🧪 Lab 1 
1. Instalation and Setup
   
Required libraries are installed and the IBM Granite model is set up via Replicate to enable LLM based analysis. 

2. Load Clean Dataset

The cleaned dataset is then loaded to prepare for sentiment classification and summarization

3. Select 3 Random Reviews

This code selects three random non null reviews from the dataset to ensure clean input for analysis. Each review is then formatted with a numbered label and joined with line breaks, preparing it for use in the prompt sent to the language model.

4. Generating Basic & Refined Prompts

The model is prompted to classify reviews by sentiment, with the refined prompt also extracting key aspects like food, service, price, and cleanliness.

5. Generating Multitask Prompt

The multitask prompt asks the model to classify sentiment and identify key aspects in a structured two step format.

6. Generating Formatted Prompt

The formatted prompt instructs the model to classify sentiment and extract aspects using a clear, structured output format for easier interpretation.

7. Select 8 Random Reviews

Eight random non null reviews are selected and formatted as bullet points to prepare input for the next analysis step.

8. Generating Structured Prompt

A structured prompt is used to generate a summarized analysis of the reviews, including key feedback, overall sentiment, and suggestions for improvement

"These steps (1-8) aim to prepare the environment and test various prompt formats to optimize sentiment and aspect extraction using the IBM Granite model."

### 🧪 Lab 2 🧪 
1. Select 5 Random Reviews
   
Five random non null reviews are selected from the dataset and formatted with bullet points and newline characters to prepare them for prompt input.

2. Generating Classification Prompt

This prompt instructs the model to classify each restaurant review by sentiment and identify key aspects such as food, service, price, and cleanliness.

3. Generating Summarization Prompt

A summarization prompt is designed to extract key feedback, overall sentiment, and improvement suggestions from the selected restaurant reviews.

4. Setting Default Parameters

A set of default generation parameters is defined to control the model’s response behavior, including token limits, sampling strategy, and repetition penalty.

5. Exploring Parameter Sets

Multiple parameter sets are defined to experiment with different model generation behaviors and observe how output quality changes with variations in sampling and token limits.

6. Run Classification Prompt with Different Parameters

The classification prompt is run using each parameter set to compare how different configurations affect the model’s sentiment and aspect classification output.

7. Run Summarization Prompt with Different Parameters

The summarization prompt is executed with each parameter set to observe how different settings affect the quality and depth of the model’s summary output.

"These steps (1-7) aim to test how different parameter settings impact the quality of classification and summarization outputs using the IBM Granite model."

---

## 💡 INSIGHTS & FINDINGS 

### 🧪 Lab 1 
1. Generating Basic Prompt
   
The basic prompt correctly classified the reviews: 2 as positive and 1 as negative. The positive reviews show satisfaction and intent to return, while the negative review criticizes a specific server.

2. Generating Refined Prompt

The refined prompt not only classified sentiment but also identified aspects. One review was linked to the service aspect (negative), while the others were positive with no specific aspects mentioned, assumed to reflect overall satisfaction.

3. Generating Multitask Prompt

The multitask prompt accurately classified sentiments and identified service in the negative review, while the positive ones reflected general satisfaction without specific aspects.

4. Generating Formatted Prompt

The formatted prompt clearly links each sentiment to specific aspects, identifying service in the negative review and overall experience or intent to return in the positive ones.

5. Generating Structured Prompt

The structured prompt output highlights negative sentiment, mainly due to bland food, poor service, and cost cutting complaints. It suggests improving food flavor, staff professionalism, and customer experience details like packaging.

### 🧪 Lab 2 
1. Generating Classification Prompt
- Parameter Set 1
  
The prompt classified reviews accurately, with service as the main issue in negative reviews and food in positives. One review was mixed, leaning negative due to overall dissatisfaction.
- Parameter Set 2
  
The model consistently classified sentiments and aspects, with service again being the main issue in negative reviews and food praised in positives. The fifth review shows overall dissatisfaction, suggesting multiple problem areas despite lacking specific details.
- Parameter Set 3
  
The model gave consistent results, identifying service in negative reviews and food in positives. One review reflected overall dissatisfaction, though specific aspects like price or cleanliness weren’t mentioned.

2. Generating Summarization Prompt
- Parameter Set 1
  
The summary highlights positive feedback on food and service, especially the pulled pork, but also notes recurring complaints about slow water refills. Overall sentiment is mixed, and improvement suggestions focus on better service consistency and addressing refill delays.
- Parameter Set 2
  
The summary shows mixed sentiment, with praise for food quality, especially the pulled pork, but complaints about slow water refills and service inconsistency. Suggestions focus on improving attentiveness, maintaining food standards, and encouraging better service to support tipping.
- Parameter Set 3
     
The summary reflects mixed sentiment, with praise for food and service, but concerns about slow water refills and poor staff attentiveness. Suggestions include improving refill responsiveness, staff training, and addressing negative service perceptions to enhance customer experience.

### 🔍 Interpretation 
1. Service aspect is the most frequently criticized issue

Many negative reviews highlight problems with service, such as delayed water refills, lack of staff attentiveness, and unprofessional behavior.

Why is this important? Because service is a core part of the customer experience. Repeated complaints indicate the need for staff training and improvements in standard operating procedures to increase customer satisfaction.

2. Generating Structured Prompt

Positive reviews reflect customer satisfaction with the taste, presentation, and portion size of the food.

Why is this important? This represents a key strength of the restaurant. Maintaining consistent food quality is crucial for preserving reputation and encouraging customer loyalty.

3. Some reviews show mixed sentiment

Some customers enjoyed the food, but their overall experience was negative due to poor service.

Why is this important? It shows that customer satisfaction is influenced not only by food, but also by other factors such as service, price, and cleanliness. All aspects must be managed consistently to deliver a complete and positive dining experience.

### 📊 Visualization 

The visualization shows the result of sentiment classification on restaurant reviews using the IBM Granite model with a basic prompt approach. All reviews in the dataset were automatically analyzed and categorized into three sentiment labels: Positive, Negative, and Mixed. The outcome indicates that most reviews are almost evenly distributed between positive and negative, while mixed reviews are significantly fewer, suggesting that customer opinions are generally clear. This process provides a fast and objective way to understand overall customer perception.

---

## 📃 CONCLUSION & RECOMMENDATION 

### 📃 Conclusion 

Through a series of prompt engineering experiments using the IBM Granite model, this project demonstrated how sentiment classification and aspect extraction can be applied to restaurant reviews with varying levels of detail and structure.

- Lab 1 explored prompt formats (basic, refined, multitask, formatted, and structured) which progressively improved output clarity and aspect relevance.

- Lab 2 examined how different generation parameters (top_k, top_p, max_tokens) affect model performance, showing their impact on classification and summarization quality.

Additionally, a bar chart was generated to visualize the overall distribution of sentiment classifications (Positive, Negative, Mixed) using the basic prompt, providing a clear overview of customer sentiment across the dataset.

### ✅ Recommendation 

1. Improve service quality through better staff training and clear SOPs
2. Maintain and promote consistency in food quality
3. Conduct comprehensive monitoring of all service aspects not just food
   
🤖 AI SUPPORT EXPLANATION 🤖

In this project, AI specifically the IBM Granite large language model is used to automate restaurant review analysis through sentiment classification, aspect extraction, and summarization. By leveraging its natural language understanding capabilities, the model interprets unstructured review texts and provides structured insights on key aspects such as food, service, price, and cleanliness. Through prompt engineering and parameter tuning, IBM Granite can be guided to deliver both concise classifications and detailed summaries, making it adaptable to various analytical needs and offering actionable feedback for business improvement.
