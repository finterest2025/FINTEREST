You will a given a list of semantically similar events. The events are extracted from the social media posts like Twitter or X. You will also be given a list of posts that were used to extract the events and a date.
Here is the list of similar events:

{events_list}

Here is the list of posts that were used to extract the events:

{posts_list}

Your task is to carefully look at the similar events in the list and extract the title, description, date, location. Follow the below steps while extracting the unique event details:
  1. Provide a Title and Description For the Event - Title should be not more than a phrase and supply detail about that event through a 1-2 sentence description and make sure that any specific actors, entities, and any other relevant tangible details are mentioned in the description as well. The description should specifically mention both the actor and action of the event if it is present to make the description more specific and not generic.
  2. Use post text to call out specific dates, For example, "next week's product launch" is vague, because we don't know exactly what day "next week" refers to. We'd like to use context clues like the date of the post to be able to figure out a better time range.
  3. A detail title should be provided using the context from the posts and it should have tangible and concrete information in it as much as possible. Avoid providing too vague title to the events.

While providing the final event date (if determined) make sure to standardize the event date based on some examples below:
1. Spring 2025 should be converted to 2025-03-20 to 2025-06-20
2. Q1 2025 should be converted to 2025-01-01 to 2025-03-31
3. January 2025 should be converted to 2025-01-01 to 2025-01-31
4. Jan 2025 to Feb 2025 should be converted to 2025-01-01 to 2025-02-28
5. Dec 10 2024 should be converted to 2024-12-10
6. Dec. 12, 2024, 08:30 AM should be converted to 2024-12-12
7. Tuesday, January 14, 2025, at 8:30 a.m. (ET) should be converted to 2025-01-14
8. Early Jan 2025 should be converted to 2025-01-01 to 2025-01-07

Extract a title, description of the event, location, and date from the similar event list in the following JSON format.
```json
{{
"events": 
[{{"title": ..., "description": ..., "location": ..., "date": ...}}] 
}}
```
