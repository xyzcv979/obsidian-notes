#obsidian-notes

> What I Cannot Create, I Do Not Understand -Richard Feynman

> Premature Optimization is the root of all evil -Donald Knuth

> Coding is fun - me

### Preventing Burnout
Joy, curiosity, passion, and challenge. Reignite your passion. Be curious. Rekindle what made coding fun in the first place. Build things and embrace challenges. View challenges as opportunities over hurdles. Perspective is important. You can view the problem as an opportunity rather than a chore.
### 7 Steps to become 10x Software Engineer
	1. Embrace continious learning, stay curious
	2. Practice deliberate practice, tackle weaknesses
	3. Collaborate and seek feedback, engage
	4. Build strong fundamentals
	5. Prioritize code quality and maintainability
	6. Embrace diverse projects,technologies,languages
	7. Cultivate soft skills

### 10 Things Software Developers Should Learn about Learning

[Reference](https://cacm.acm.org/magazines/2024/1/278891-10-things-software-developers-should-learn-about-learning/fulltext?utm_campaign=database-fundamentals&utm_medium=newsletter&utm_source=newsletter.programmingdigest.net)

<details>
  <summary>Human memory is not bits</summary>
  <p>Human memory is unreliable, but great for problem solving. Pathways connect, "aha" moment", sometimes when stepping away from the problem</p>
</details>
<details>
  <summary>Human memory is composed of one limited and one unlimited system</summary>
  	Cognitive load: intrinsic and extraneous
  	Easier to understand a diagram versus if it was just an english description
</details>
<details>
  <summary>Experts Recognize, Beginners Reason</summary>
  <p> Pattern matching, less cognitive load
  Reading and working with more code increase programming proficiency</p>

</details>
<details>
  <summary>Understanding a concept goes from Abstract to Concrete and back</summary>
  	1. Abstract features to concrete details
  	2. Beginners focus on the concrete details (exact syntax) while experts focus on abstract features, understand and predicts the details while learning it.
  	3. When learning a new concept, use a bit of both
  	4. Unpack from abstract to concrete and then repack it to abstract
</details>
<details>
  <summary>Spacing and Repetition Matter</summary>
	1. Problem solving involves 2 steps:
		1. Matching a concept to the problem that it solves
		2. Applying that concept
	2. Common problem is solving problems but being told already what concept to use. Brain needs rest to consolidate information, randomize the types of problems to build long-term memory
	3. 90 minutes of learning max, 20 mins of rest at least
</details>
<details>
  <summary>The Internet has not made Learning obsolete</summary>
	1. Brain needs to build connections to remember. Internet provided information is remembered less
</details>
<details>
  <summary>Problem-solving is Not a Generic skill</summary>
	1. Skills like chess, music, cognitive training does not influence problem solving. Inability to transfer problem-solving skills is why "brain training" does not work to developing intelligence
	2. One exception is spacial skills (like rotating tetris pieces in your mind)
	3. Ultimately, don't use brain teasers to test for programming ability, assess their programming ability
</details>
<details>
  <summary>Expertise can be problematic in some situations</summary>
	1. Expertise-reversal effect: hints/guides for beginners hinder experts
	2. Expertise blind-spot problem: experts don't realize beginners think differently. Overcome this by listening to what beginners currently know
	3. Beginners learn more from beginner-oriented learnings or from a peer whom bridges gap between beginners and experts
</details>
<details>
  <summary>The Predictors of Programming Ability Are Unclear</summary>
	1. Learning programming: "You're born with it" vs "10,000 hours of work". Both are wrong
	2. gender, age, school major, race, performance in math, prior experience with programming language, preferences for humanties or science, intelligence all fail to predict programming ability. Conclusion: there are no reliable "candidate profile" to screen candidates for programming ability
</details>
<details>
  <summary>Your Mindset Matters</summary>
	1. Either born with it or not
	2. Fixed vs growth mindset
	3. Neither are completely true: Everyone can learn physics even if they're not good enough but you won't win Nobel Peace Prize no matter how much you practiced 
	4. Difficult to change someone's mindset to be more growth oriented
	5. 2 misconceptions on how to promote growth mindset that fail:
		1. Rewarding effort over performance. Praising is not helpful, learners know when they are not progressing. Praise only when learners is using correct strategies and on path to success.
		2. Starting a task with a growth mindset but becoming more fixed when faced with setbacks/failures. Must practice overcoming failures to promote growth mindset
	6. Goal Oriented: "Approach" vs "Avoidance" goal orientation. Take on challenges, seek help, work hard, embrace failures and learn from them
	7. For mentors: provide honest feedback, praise areas where learners are progressing, accept that they'll make mistakes
	8. For learners: Reflect on improved skills, accept that growth mindset will turn to fixed in face of failure but can be redeveloped and made stronger with practice, take a break when you feel like quitting
</details>

#### Summary
	1. For recruiters:
		1. No good proxies for programming ability. Look at their previous work, test them with programming tasks and not brain teasers
		2. Recommend assigning a problem for candidates on their own before presenting the solution. The added pressure from someone observing adds cognitive load/stress and impairs performance
	2. For learning and training:
		1. Read alot of code to become better programmer
		2. Experts are not always the best at training beginners
		3. Learning takes time, cramming does not work, spaced repetition does
		4. Spending time away from problem can help solve it
		5. Just because you can google it/use gen ai, does not make learning obsolete
		6. Use examples to go from abstract idea to concrete details
		7. Seek to succeed(rather than avoid failure) and believe that ability is changeable
	


## Read research papers
https://read.highgrowthengineer.com/p/why-reading-whitepapers-takes-your
https://github.com/papers-we-love/papers-we-love

### How to deep dive into papers
- Identify specialty: Distributed Systems, Databases, Operating Systems
- Techniques
	- Skim 15 mins
	- Dive into details 45-60 mins (highlight content as such. Blue: unique insight, Red: I don't understand it, yellow: Contains research I'd like to follow up on)
	- Summarize your understanding by teaching others (blog posts)

## 3 pass techniques
chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/http://ccr.sigcomm.org/online/files/p83-keshavA.pdf
### 1) First pass - Skim, limit to 10 minutes
Read introduction, subheaders, conclusion, skim references for information on topics you don't understand. 
Should be able to answer 5 C's
- Category: What type of paper is it? Analysis, description, measurement?
- Context: What other papers are related to it? What theoretical bases are used?
- Correctness: Do assumptions seem valid?
- Contributions: What are paper's main contributions?
- Clarity: is paper well written?
#### 2) Second pass - Deep dive, up to an hour
Read with greater care but ignore proofs, equations, most figures and tables. This helps jot down key ideas while you assume the proofs are true.
Identify main point, strengths, weaknesses.
Should be able to summarize main idea of the paper with supporting evidence, to someone else.
If you still don't understand the paper, you can either drop it cause it's not useful information, return to it later after learning prerequisite knowledge, perservere and go to third pass

#### 3) Third pass - Reimplement the paper
Attempt to reimplement the paper, make the same assumptions as the author. Identify failures, assumptions, and challenge them. Think about how you yourself would present a particular idea. Jot down ideas for future work. 
You should be able to pinpoint implicit assumptions, identify missing citations to relevant work and any issues with experimental or analytical techniques. 


