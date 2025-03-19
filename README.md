![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Chatbot

## Getting Started

Follow the instructions provided in the notebook.

Read the instructions for each cell and provide your answers. Make sure to test your answers in each cell and save. Jupyter Notebook should automatically save your work progress. But it's a good idea to periodically save your work manually just in case.

## Deliverables

- Downloaded notebook with your responses to each of the exercises.


## Submission

- Upon completion, add your deliverables to git. 
- Then commit git and push your branch to the remote.
- Make a pull request and paste the PR link in the submission field in the Student Portal.

## Report: Analyzing GPT's Responses for Flight Ticket Booking in JSON Format
1. Introduction
This report evaluates the performance of GPT in generating structured JSON summaries for flight ticket bookings. Three different prompt variations were tested to determine how well GPT maintains accuracy, consistency, and completeness in its responses. The objective was to assess whether GPT correctly followed the instructions, avoided hallucinations, and provided structured output aligned with real-world flight booking systems.

2. Analysis of Responses
2.1. Accuracy and Consistency
Each generated JSON response contained essential details such as passenger name, passport number, departure and destination cities, flight schedule, airline details, ticket class, and additional services. However, there were noticeable inconsistencies in formatting and missing details across different responses:

First Response: The structure was well-organized, including nested sections for the passenger, flight details, and additional services. However, the price format used a string ("$1500") instead of a numerical value, which may not be ideal for data processing.
Second Response: This version included an "age" field for the passenger, which was not requested, suggesting GPT added unnecessary information. Additionally, the "route" was formatted as a string instead of separate "departure_city" and "destination_city" fields, making it less structured.
Third Response: This response omitted passenger details entirely, focusing only on flight information. The "seat_number" field was included, which was not in the original prompt, indicating hallucination or deviation from instructions.
2.2. Completeness and Missing Details
While most responses contained the required information, some variations showed missing elements:

The third response lacked passenger information, making it incomplete for a ticket booking system.
Some responses used different naming conventions (e.g., "flight_details" vs. "flight" vs. "departure"), affecting consistency.
The pricing structure varied between responses, with some including "addons" like extra baggage pricing and others omitting such details.
2.3. Hallucinations and Unnecessary Additions
GPT sometimes added extra fields that were not explicitly requested, such as:

"seat_number" in the third response.
"age" field for the passenger in the second response.
"priority_boarding" as an addon, which was not part of the prompt.
These hallucinations suggest that GPT infers information rather than strictly following instructions, which can be problematic in structured data generation.

3. Key Learnings
Through this exercise, the following key insights were gained:

Precision in prompt design matters: More detailed and structured prompts result in more accurate JSON outputs.
GPT can introduce inconsistencies: Even with similar prompts, responses varied in naming conventions and data structure.
Strict format enforcement is necessary: When using GPT for structured data, validation mechanisms are needed to detect hallucinations or missing fields.
GPT is not deterministic: Even with a low temperature setting (temperature=0), variations in output still occurred, indicating some level of inherent randomness.
4. Conclusion
While GPT performed reasonably well in generating structured JSON flight ticket bookings, inconsistencies and hallucinations highlight the need for stricter prompt control and post-processing validation. For real-world applications, predefined schemas and additional constraints should be implemented to ensure reliable data generation.

<br>


