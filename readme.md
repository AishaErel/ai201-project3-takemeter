**Labels**:
Label 1- Analysis: Posts that use statistics, game footage, historical comparisons, or detailed reasoning to support a basketball argument.
Examples: 1- Why Nikola Jokic is the most impactful offensive player in the NBA: an analysis using lineup and efficiency data. 2- "Film breakdown of how the Celtics defended pick-and-roll actions in the playoffs."

Label 2: News: Posts whose primary purpose is reporting factual information, transactions, injuries, quotes, or announcements.
Examples:1-"The NBA announces next season's salary cap projections." 2- "Shams: Damian Lillard expected to miss 6–8 weeks with a calf injury"

Label 3- Opinion: Posts expressing a subjective claim or ranking without substantial supporting evidence.
Examples: 1- "Prime Westbrook was better than prime Harden." 2-"The Nuggets had one of the easiest championship paths in NBA history."

The hardest boundary is Analysis vs. Opinion. Many r/nba posts contain both a subjective claim and some supporting evidence. To ensure consistency, I will label a post as Analysis only when evidence and reasoning are the primary focus of the post. If the post mainly presents a personal judgment, ranking, or prediction and uses little supporting evidence, it will be labeled Opinion.

**Data Collection Plan:**
I will collect examples from recent and highly engaged posts on r/nba, including game threads, news posts, player debate posts, statistical analysis posts, highlight clips, and meme/reaction posts. I will aim for about 50 examples per label, for a total of 200 annotated examples across three labels: Analysis, News, and Opinion If one label is underrepresented after 200 examples, I will do targeted collection by searching for posts that are more likely to contain that label, such as searching for “highlight,” “stat,” “trade,” “injury,” “ranking,” or “analysis,” while making sure the examples still come from real r/nba posts.

**Evaluation Metrics:**
I will use accuracy, precision, recall, and F1-score to evaluate the classifier. Accuracy is useful for measuring overall performance, but it is not enough because some labels may be easier or more common than others. Precision will show how often the model is correct when it assigns a label, while recall will show whether the model is missing important examples of a label. I will also use macro-F1 because it gives equal weight to each label and is better for this task if the dataset is not perfectly balanced.

**Definition of Success:**
A successful classifier should correctly identify the main type of r/nba post most of the time, especially distinguishing substantive Analysis from unsupported Opinion. I would consider the model genuinely useful if it reaches around 80% overall accuracy and a macro-F1 score of at least 0.75 on a held-out test set. For deployment in a real community tool, I would also want no label to have extremely poor recall, because the tool should not consistently miss one type of post.

**Hard Examples**
3 Hard examples and how i decided:
1- "[BS Podcast] Lowe: The league is gonna be spared the #1 talking point between games 5 and 6 being 'is Wemby going to be suspended for game 6' because of a flagrant foul...they're spared this whole officiating discussion because the Knicks saved their ass on it. Simmons: He would've gotten suspended."
This one looks like news as well, however they are not reporting news, they're interpreting an event and discussing consequences, that why its analysis.
2-"Steven Adams Says Today’s Bigs Are Not Good At "Trench Work" Like Boxing Out"
This one looks like a news or analysis, however its actually an opinion, if it was like "Today's bigs are not good at boxing out. Looking at rebound positioning data from the last 15 years." then it would have become analysis
3- Bobby Marks: "I'm still of the belief it's Miami because when you look at Giannis, it's the superstar checklist of 3 things [that Buck want]: Draft Capital, Young Players On Controllable Contracts, Win NOW Players. I do think that Miami right now has the best package out there"
This looks like news but its actually an analysis bc he's not just reporting information. he is making a prediction/evaluation and explaining his reasoning.

## AI Tool Plan

### Label Stress-Testing

Before beginning annotation, I will use ChatGPT or Claude to test my label definitions and edge cases. I will provide the definitions for the three labels (Analysis, News, and Opinion) and ask the model to generate 5–10 example r/nba posts that sit on the boundary between two labels. If I find examples that cannot be consistently assigned to a single label, I will refine the label definitions and annotation rules before collecting the full dataset. In particular, I expect the most difficult boundary to be between Analysis and Opinion/Hot Take, since many posts combine subjective claims with some supporting evidence.

### Annotation Assistance

I may use ChatGPT to generate preliminary label suggestions for a subset of collected posts. However, all labels used in the final dataset will be reviewed and verified manually.

### Failure Analysis

After evaluating the model, I will collect examples that were misclassified and provide them to ChatGPT for analysis. I will ask the model to identify potential patterns, such as confusion between Analysis and Opinion posts or difficulties handling posts that contain both news and commentary.
