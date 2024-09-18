# Reimagining AI: A Human-Centric Approach to Model Interactions

**Presentation details**

The explosion of large-language models in the past few years has turned everyone's attention to AI. OpenAI's ChatGPT has pioneered a new pattern for human-model interactions that other companies have been eager to follow. But is the chat-bot pattern the future of AI-powered products? In this talk, we'll analyze and critique current patterns of human-model interactions and consider a more human-centric future for AI.

**Target audience**

Employees from companies currently or considering developing AI-powered products and features.

**More information**

At Khan Academy, I have been working on activities that give students AI-powered feedback on long-form writing to encourage learning. We're using these LLMs in a novel way, and I believe that a more task-focused interactions are the future of human-model interactions. I plan to compare our product, GitHub's Copilot, and Adobe's Firefly, with standard chat bots to illustrate how human-centered tools are the future.

## AI Tools

- Apple Intelligence https://www.apple.com/apple-intelligence/
  - Writing Tools
  - ChatGPT Integration
- Adobe Firefly https://www.adobe.com/products/firefly.html
  - Generative Fill
- GitHub Copilot https://github.com/features/copilot
  - Suggestions
  - Explanations
  - Fix & Refactor

## Three main criticisms of chatbots

1. Place the burden of interaction on the user
   - Have no affordences (Wattenberger)
   - The burden to learn what works still lies with every single user (Wattenberger)
   - Puts all the burden on the user (Henley)
2. Re-active responses
   - Turn-based interaction paradigm (Appleton)
   - Burder is on the user to think of what, when, and how to ask and then make sense of the response (Henley)
   - There is now "flow" state if I'm stopping every few seconds to read a response (Wattenberger)
3. Difficult to use generated content
   - Difficult to find out what changed between responses (Wattenberger)

## Three improvements to chatbots

1. Model interactions that are tailored to a user's goal
   - Let's take the time to bake as much information into the interface as possible instead of making users hack it into each of their questions. (Wattenberger)
2. Pro-active responses
3. Content generation is the main interaction

## Resources

- _Meet Khanmigo Writing Coach_ by Khan Academy. https://blog.khanacademy.org/meet-khanmigo-writing-coach-helping-learners-become-better-writers/
- _Why Chatbots Are Not the Future_ by Amelia Wattenberger. https://wattenberger.com/thoughts/boo-chatbots
  - "chatbots are not the future of interfaces."
  - Text inputs have no affordances
    - "Good tools make it clear how they should be used. And more importantly, how they should not be used."
    - "The only clue we receive is that we should type characters into the textbox. The interface looks the same as a Google search box, a login form, and a credit card field."
    - "Of course, users can learn over time what prompts work well and which don't, but the burden to learn what works still lies with every single user. When it could instead be baked into the interface." #solution
  - Prompts are just a pile of context
    - "But pretty soon, we're going to get sick of typing all the time."
    - "Let's take the time to bake as much information into the interface as possible instead of making users hack it into each of their questions." #solution
  - Responses are isolated
    - "Even with this fairly short example, it's laborious to figure out what concretely has changed [between responses]. We're forced to scroll back and forth between responses, reading them line by line."
  - The implementation—evaluation loop
    - "When a painter is working, there are two distinct actions: up close, smooshing paint around on the canvas and stepping back to evaluate and plan. These two modes (implementing and evaluating) are present in any craft"
    - "Good tools let the user choose when to switch between implementation and evaluation."
    - "I ask a question (implement) and then I read a response (evaluate). There is no \"flow\" state if I'm stopping every few seconds to read a response. ... I have to wait long enough to lose the thread of what I was doing."
  - Avoid No man's land
    - "When I try these new products, I find myself transported into WALL-E. My brain turns off and I press the magic 🪄 button or mash the Tab key. And when I'm eventually jolted out of my zombie mode, I don't even really like what's been created."
    - "When a task requires mostly human input, the human is in control. They are the one making the key decisions and it's clear that they're ultimately responsible for the outcome."
    - "But once we offload the majority of the work to a machine, the human is no longer in control."
    - "There's a No man's land where the human is still required to make decisions, but they're not in control of the outcome."
    - "At the far end of the spectrum, users feel like machine operators: they're just pressing buttons and the machine is doing the work. There isn't much craft in operating a machine."
    - "I want to see more tools and fewer operated machines - we should be embracing our humanity instead of blindly improving efficiency. And that involves using our new AI technology in more deft ways than generating more content for humans to evaluate."
    - "Let's build tools that offer suggestions to help us gain clarity in our thinking, let us sculpt prose like clay by manipulating geometry in the latent space, and chain models under the hood to let us move objects (instead of pixels) in a video."
  - "we can add controls, information, and affordances to our chatbot interfaces to make them more usable." #solution
  - "I can't wait to see the field become more mature and for us to start building AI tools that embrace our human abilities."
- _Language Model Sketchbook, or Why I Hate Chatbots_ by Maggie Appleton. https://maggieappleton.com/lm-sketchbook
  - "We don't quite know what to do with language models yet. But we have some hunches."
  - "The primary interface everyone and their mother jumps to at this point is the chatbot. We are irreversibly anchored to this text-heavy, turn-based interface paradigm. And sure, it's a great solution in a lot of cases! It's flexible, familiar, and easy to implement."
  - "But it's also the lazy solution. It's only the obvious tip of the iceberg when it comes to exploring how we might interact with these strange new language model agents we've grown inside a neural net."
  - Iceberg graphic
  - Daemons
    - "Imagine the environment you're writing in has a few characters who hang out in the background and suggest ideas to you every now and then."
    - "These daemons have particular personalities – one plays devil's advocate, one says encouraging things and compliments your writing, one synthesises your ideas into more concise statements, one fetches evidence and research for you, one elaborates on points you haven't fully explained, etc."
    - "As you write, one of them might highlight a sentence and suggest a revision, or ask you to defend a claim. You can always ignore them if you like and the suggestion will fade."
    - Video & screenshots
  - Branches
    - "A lot of what we think of as “understanding an issue” often comes down to “What caused this?” and “What are the consequences of this?”. ... We usually get to the bottom of these questions through a mix of research and sitting alone trying to think hard about the issue at hand."
    - "It seems plausible language models would be good helpers in this department. They have plenty of latent knowledge and I've found they're quite good at suggesting reasonable cause-and-effect chains. As long as you double-check its suggestions and don't take them as gospel."
  - Epi
    - "Models can help in a bunch of small ways – rephrasing sentences, offering critiques of ideas, helping to find evidence for claims, generating possible research questions, and pointing out our assumptions."
    - "Epi uses the familiar right-click context menu to make these moves available in a simple writing context."
- _Natural language is the lazy user interface_ by Austin Z. Henley. https://austinhenley.com/blog/naturallanguageui.html
  - "ChatGPT has kicked off a frenzy. It is all anyone in the tech world is talking about it seems. Startups are popping up left and right. Big companies are rapidly releasing ChatGPT-like features integrated in their products."
  - "People are anticipating that large language models are going to revolutionize the world. / And maybe they will."
  - "But a chat bot won't."
  - "Expecting users to primarily interact with software in natural language is lazy. / It puts all the burden on the user to articulate good questions. What to ask, when to ask it, how to ask it, to make sense of the response, and then to repeat that many times."
  - "A good user interface let's me iteratively and incrementally explore the problem and solution space in a variety of ways. / A great user interface guides me and offers nudges."
  - "Couldn't a natural language interface help with that? / Certainly. / But not as the only option. Probably not even the main interface."
  - "The need to support multiple modalities isn't new—it just seems we are so awestruck by LLMs that new software features are launching that regress to a single modality."
  - "The potential of LLMs goes far beyond a natural language interface."
  - "For example, an application could feed the relevant context to the model behind the scenes and use that to preemptively suggest what I should do next."
- _AI the Product vs AI the Feature_ by MKBHD. https://youtu.be/sDIi95CqTiM
  - I think he's citing https://www.wired.com/story/gadget-lab-podcast-647/ but I couldn't find the direct quotes
  - "AI is a feature, not a product"
  - "You could even consider going to the ChatGPT website and using it there as 'AI as a product'"
  - "It's a different way of thinking about AI for the consumer, where it's just one of the features built into the thing that you use."
  - With Apple Intelligence, Apple is working on their own models that run on device and "building a ChatGPT wrapper into a lot of their OS"
  - "More people in the long run are going to end up using this AI stuff as a feature more than going to a standalone thing"
  - "I found it really hard to find any examples of the other way around happening"
- _The Root Causes of Failure for Artificial Intelligence Projects and How They Can Succeed_ by James Ryseff, Brandon De Bruhl, Sydne J. Newberry. Rand. https://www.rand.org/pubs/research_reports/RRA2680-1.html https://www.rand.org/content/dam/rand/pubs/research_reports/RRA2600/RRA2680-1/RAND_RRA2680-1.pdf
  - Conducted interviews of "with experienced AI practitioners in both industry and academia. During these interviews, we defined the failure of an AI project as a project that was perceived to be a failure by the organization. We included both technical failures and business failures within this definition." (4)
  - Under takeaways: "Third, in some cases, AI projects fail because the organization focuses more on using the latest and greatest technology than on solving real problems for its intended users." (2)
  - Under industry recommendations:
    - "Choose enduring problems: AI projects require time and patience to complete. Before they begin any AI project, leaders should be prepared to commit each product team to solving a specific problem for at least a year. If an AI project is not worth such a long-term commitment, it most likely is not worth committing to at all" (2)
    - "Focus on the problem, not the technology: Successful projects are laser-focused on the problem to be solved, not the technology used to solve it. Chasing the latest and greatest advances in AI for their own sake is one of the most frequent pathways to failure." (2)
  - "Experienced engineers told us that successful project teams kept a clear focus on the business problem to be solved instead of the technology that would be used to solve it." (14)
  - "Chasing the latest and greatest advances in AI for their own sake is one of the most frequent pathways to failure." (14)
  - "...select AI projects that are both a good fit for the technology and that solve a real problem for their intended user." (14)
  - "No matter how impressive a new technology may appear, ultimately any technology—even AI—is simply a tool to be wielded rather than an end in and of itself." (14)
- _The Design of Everyday Things_ by Don Norman
  - "An affordance is a relationship between the properties of an object and the capabilities of the [person] that determine just how the object could possibly be used." 11
  - "An affordance is not a property. An affordance is a relationshi. Whether an affordance exists depends upon the properties of both the object and the [person]." 11
