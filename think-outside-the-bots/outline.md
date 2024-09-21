- Introduction
- Surveying the room
  - How many of your have worked to implement something using "AI" at your company?
  - How many of you have plans or aspirations to?
- Popular examples of AI
- Thesis:
  - Successful AI adoption requires as human-first approach to design
- Human-Centric Design
  - Humans have goals and products help reach them
  - No human has the goal of interacting with a LLM-driven chatbot (unless they are investigating the technology)
  - Humans want to do something, accomplish something
- Technology-Centric Design
  - These are the limitations of the underlying technology which translate to the product
  - When you are a hammer, every problem looks like a nail
- TUI vs GUI
  - We've been through this revolution before
- MKBHD's Product vs Feature Distinction

---

High Level:

1. Introduction
2. Background
   1. Terminology
   2. Survey the room
   3. Brief history
3. The Problem: Technology-centric design
   1. No direction
   2. No context
   3. No resolution
4. The Solution: Human-centric design
   1. Target a resolution
   2. Build in context
   3. Design a direction
5. Examples
   1. Khanmigo Writing Coach
   2. Khanmigo Coeditor
   3. GitHub Copilot
   4. Adobe Firefly
   5. Apple Intelligence
6. Takeaways
   1. Chase the problem, not the solution
   2. Focus on the human user and their goals
   3. Embrace multiple model types and interaction modes

Slide v2: NOW IN GOOGLE SLIDES

Slides v1:

1. Thinking outside the bots: A Human-centric Approach to Model Interactions
2. Sean McPherson/Pittsburgh/Software Engineer
3. Building AI-powered learning experiences at Khan Academy
4. ---SECTION--- Background
5. AI vs Model
6. Survey time
7. How did we get here?
8. For decades, machine learning quietly solving problems
9. In 2022 ChatGPT bursts on the scene
10. Gold Rush: Eveyone is an AI company now
11. OpenAI/Microsoft/Google/Meta/Anthropic
12. Eveyone else is using their models or APIs
13. They all have their own chatbot
14. Chatbots are a bad UI (for most things)
15. But don't take my word for it
16. Chatbots are "the lazy solution... the obvious tip of the iceberg" (Appleton)
17. Chatbots "are not the future of interfaces." (Wattenberger)
18. Chatbots are not "going to revolutionize the world." (Henley)
19. ![Screenshots of articles referenced]
20. ---SECTION--- The Problem
21. #1 No direction/#2 No context/#3 No resolution
22. #1 No direction
23. "...how they should be used" (Wattenberger)
24. "The only clue..." (Wattenberger)
25. "Puts burden on user" (Henley)
26. Good design communicates to the user what is possible
27. A textbox says very little
28. #2 No context
29. There is no memory beyond `messages`\*
30. The chatbot doesn't know what you're doing
31. Users must "hack [context] into each of their questions" (Wattenberger)
32. "It puts all the burden on the user" (Henley)
33. ![Movie posters for _50 First Dates_ and _Groundhog Day_]
34. #3 No resolution
35. There is not result, no output
36. "...iteratively and incrementally explore the problem and solution space..." (Henley)
37. Chatbots make that difficult
38. "Difficult to see changes" (Wattenberger)
39. Imagine code review without inline/side-by-side diff
40. The Real Problem: Technology-centric design
41. We have let the solution shape the problem
42. When you have a hammer, every problem looks like a nail
43. ---SECTION--- The Solution
44. #1 No direction/#2 No context/#3 No resolution
45. #1 Target a resolution/#2 Build in context/#3 Design the direction
46. #1 Target a resolution
47. Every feature should have a clear output
48. What does the user need to accomplish?
49. #2 Build in context
50. What information gets the user to that resolution?
51. "feed the relevant context to the model behind the scenes and use that to preemptively suggest what I should do next." (Henley)
52. #3 Design the direction
53. Design with the user's goal at the forefront
54. For a writer, a document/For a dev, an editor/For an artist, a canvas
55. The Real Solution: Human-centered design
56. ---SECTION--- Examples
57. #1 Target a resolution/#2 Build in context/#3 Design the direction
58. Khan Academy's Khanmigo
59. Writing Coach
60. Coeditor
61. GitHub Copilot
62. Adobe Firefly
63. Apple Intelligence
64. ---SECTION--- Takeaway
65. Human-centric design
66. #1 Target a resolution/#2 Build in context/#3 Design the direction
67. Rand's _The Root Causes of Failure for Artificial Intelligence Projects and How They Can Succeed_
68. "Choose enduring problems" (Rand)
69. "Focus on the problem, not the technology" (Rand)
70. "No matter how impressive a new technology may appear, ultimately any technology—even AI—is simply a tool to be wielded rather than an end in and of itself." (Rand)
71. MKBHD
72. "AI is a feature, not a product"
73. Chase the problem, not the solution
74. Focus on the human user and their goals
75. Embrace multiple modal types and interaction modes

Slides v0:

1. Thinking outside the bots: A Human-centric Approach to Model Interactions
2. Sean McPherson/Pittsburgh/Software Engineer
3. Building AI-powered learning experiences at Khan Academy
4. Survey time
5. AI vs model
6. How did we get here?
7. For decades, machine learning quietly solving problems
8. In 2022 ChatGPT bursts on the scene
9. Gold Rush: Eveyone is an AI company now
10. OpenAI/Microsoft/Google/Meta/Anthropic
11. Eveyone else is using their models or APIs
12. Technology-centric Design
13. The current generation of AI products is technology-centric
14. Models work with chat, so we ship a chat bot
15. But should we?
16. _Why Chatbots Are Not the Future_ by Amelia Wattenberger
17. Text inputs have no affordances
18. Responses are isolated
19. "... the human is not longer in control of the outcome" AW
20. "No man's land" AW
21. _Language Model Sketchbook, or Why I Hate Chatbots_ by Maggie Appleton
22. "...the lazy solution" MA
23. _Natural Language is the Lazy User Interface_ by Austin Z. Henley
24. "not going to revolutionize the world" AZH
25. "all the burden on the user" AZH
26. "What to ask, where to ask it, how to ask it..." AZH
27. We've been through this before
28. Terminal v. GUI
29. When developers design, you get a textbox on a page
30. Screenshot of ChatGPT UI
31. A different way
32. Human-centric design
33. Good design is helping users accomplish goals
34. No one's goal is to chat with an AI
35. "A good user interface..." AZH
36. "A great user interface..." AZH
37. We need to support multiple modalities of interaction (AZH)
38. Models could run in the background (MA)
39. Models could prompt the human to think (MA)
40. Fulfilling user goals with models
41. AI the product vs AI the feature
42. MKBHD
43. AI isn't enough to make a product
44. AI makes a feature magical
45. Good examples
46. GitHub Copilot
47. Khanmigo Writing Coach
48. Adobe Firefly
49. Apple Intelligence
50. Successful AI products will have human-centric design
