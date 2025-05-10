You are tasked with determining the exact date or most likely occurrence of an event based on the given information. Follow these steps carefully:
1. First, review the event title and event description:
   a. Event Name: {event_name}
   b. Event description: {event_description}
        
2. Now, examine the following list of snippets, their corresponding dates, and the link of the snippet. These snippets are obtained from web search results related to the event:
   {web_results}
    
3. Analyze the snippets to determine the event date:
   a. Look for explicit mentions of the event date in the snippet text.
   b. If no explicit date is mentioned, try to infer the event date based on the snippet date and context.
   c. Pay special attention to snippets that closely match the event title or description.
   d. Consider the chronological order of snippets if multiple relevant dates are found.    
   e. For periodic events that occur regularly throughout the year, try to determine the latest upcoming event date in the future.
       
4. If multiple dates are present for the same event and its difficult to determine the exact date then just return the latest date of occurrence of the event. For example:
   a. A event with multiple occurrence dates such as Nov 19 2024, Nov 15 2024, Nov 18 2024, Dec 10 2024 should return Dec 10 2024
   b. A event with multiple occurrence dates such as Jan 2024, Feb 2024 should return Feb 2024
   c. A event with multiple occurrence dates such as Q1 2024 and Q4 2024 should return 2024-10-01 to 2024-12-31
        
5. While providing the final event date (if determined) make sure to standardize the event dates based on some examples below:
   a. Spring 2025 should be converted to 2025-03-20 to 2025-06-20
   b. Q1 2025 should be converted to 2025-01-01 to 2025-03-31
   c. January 2025 should be converted to 2025-01-01 to 2025-01-31
   d. Jan 2025 to Feb 2025 should be converted to 2025-01-01 to 2025-02-28
   e. Dec 10 2024 should be converted to 2024-12-10
   f. Dec. 12, 2024, 08:30 AM should be converted to 2024-12-12
   g. Tuesday, January 14, 2025, at 8:30 a.m. (ET) should be converted to 2025-01-14
   h. Early Jan 2025 should be converted to 2025-01-01 to 2025-01-07
        
Present your findings in the following JSON format if the event date can be determined from websearch results snippet:
```json
{{
"Determined Date": [Insert the most likely date for the event if determined OR "Not specified" if the event date cannot be determined],
"snippet link": [Insert the snippet link corresponding to the snippet that was used to determine the event date if it is available OR "Not specified" if the snippet link is blank. If multiple snippets were used to determine the event date then provide the snippet links as a string of links separated by a comma delimeter.]
}}
```
