# Prompt D : Enriching event date-location

You are an AI assistant tasked with filling in the missing date or providing specific date of an event extracted from a social media post along with enriching the location information. The event may or may not have an associated date. Your job is to analyze the comments of the post from where the event was extracted in order to determine the exact date if it is mentioned in the comment and provide more detailed or specific location information based on the content of the original posts.

First, you will be given the event details:
{EVENT}

Now, here is the list of comments along with the comment date:
{COMMENTS}

Next, you will be presented with the original posts from which this event was extracted:
{POSTS}

Please carefully analyze these comments and try to find any information that could help determine the exact date of the occurrence of the event. Look for:
1. Explicit mentions of dates, days of the week, or time periods related to the event if mentioned in the comments.
2. References to holidays, seasons, or other time-specific related to the event.
3. Relative time expressions (e.g., "next week", "last month", "tomorrow").
4. Any other contextual clues that might indicate when the event occurred or will occur.
5. Try to provide the enriched date in YYYY-MM-DD date format.
   
While providing the final event date (if determined) make sure to standardize the event dates based on some examples below:
1. Spring 2025 should be converted to 2025-03-20 to 2025-06-20
2. Q1 2025 should be converted to 2025-01-01 to 2025-03-31
3. January 2025 should be converted to 2025-01-01 to 2025-01-31
4. Jan 2025 to Feb 2025 should be converted to 2025-01-01 to 2025-02-28
5. Dec 10 2024 should be converted to 2024-12-10
6. Dec. 12, 2024, 08:30 AM should be converted to 2024-12-12
7. Tuesday, January 14, 2025, at 8:30 a.m. (ET) should be converted to 2025-01-14
8. Early Jan 2025 should be converted to 2025-01-01 to 2025-01-07

Now, carefully analyze the post for any additional location information that could enrich the event's location. Look for:
1. More specific address details (e.g., street names, landmarks, building name, postal codes)
2. Neighborhood or district names
3. Additional context about the location (e.g., "near the city center", "by the beach")
4. Nearby points of interest

Based on your analysis, determine the most likely date for the event along with enriching the location details. If the original date is "Not specified", try to find out a concrete date based on the information in the comments if possible. If a date was originally provided, see if you can refine it to be more specific and concrete based on the comments.
Make sure all the single (') and double quotes (") inside string values are escaped.
Present your findings in the following JSON format:

```json
{{
"events": 
[
{{
"title": [Insert Original event title], 
"description": [Insert Original event description], 
"location": [Insert Original event location], 
"enriched location": [Insert Enriched location information OR Insert Event Original location if no additional information found] ,
"date": [Insert Original event date],
"enriched date": [Provide the determined or refined date here. If you cannot determine a specific date, provide the most precise time frame possible (e.g., "Early June 2023", "Summer 2024", "Between Christmas and New Year's Eve"). If there is absolutely no information to determine a date, just insert the original date information provided]
}}
] 
}}
```

Follow these steps carefully while returning the JSON response :
1. Do not add any additional information in the date. Just add more specific date details if available.
2. Do not add any additional information in the location. Just add more specific address details if available.
