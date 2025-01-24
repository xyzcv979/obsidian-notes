
**Weekdays:**

**Morning (Before Work):**
- workout, shower, eat breakfast
- Leetcode, read technical books/papers

**Evening (After Work):**
- Review what you've learned today, practice gratitude
- Decompress, entertainment
- late night coding (leetcode, personal projects)

**Weekends:**
- Leetcode contest
- personal projects
- reading technical books/papers

**Tips:**
- Prioritize tasks based on your goals. If you're preparing for job interviews, allocate more time to LeetCode. If you're focused on personal projects, allocate more time to coding.
- Use Pomodoro technique (e.g., 25 minutes of focused work, followed by a 5-minute break) to maintain productivity.
- Set specific, achievable goals for each session.
- Adapt the schedule as needed. Life happens, and flexibility is essential.
- Ensure you get enough rest. Consistent sleep is crucial for effective learning and problem-solving.


## Books
DDIA
System design book

## Research papers
Pick a paper weekly
3 phase reading
Take notes, summarize learnings in blog post

## Interview Prep
Neetcode list
Company tagged leetcode most popular
Behavioral prep
### Topics:
Programming languages
Data structures
Algorithms
Object Oriented Design
System design
Databases
Distributed Systems
Networking
Operating Systems

## Personal project ideas:
- ReInvent the wheel - Start rebuilding things
	- HTTP server  
	- Git
	- Database
	- Implement paxos/raft
- Projects to build to learn a new language
	- Todo app (CLI)
		- Objectives:
			- Read/write data to file system
			- Print tabular data
			- CLI application w/ multiple commands
		- commands:
			- add tasks
			- list tasks
			- complete tasks
			- delete tasks
	- Backend web API - Calculator 
		- One caveat is building a stateless API instead of typical CRUD app. Full focus on API implementation and don't have to worry about the datastore
		- Considerations:
			- perform input validation
			- logging requests
		- APIs
			- add, subtract, multiply, divide
	- Web scraper (CLI)
		- scrape URL recursively for any dead links that return 4xx and log them to console
		- Objectives
			- CLI, add concurrency (goroutines, channels) for performance to scrape multiple sites at same time, parse HTML
		- Considerations
			- Handle pages already visited
			- Handle redirects
			- This form of scraping won't work on javascript websites, use only headless browser?
	- URL Shorterner
		- build web application that takes in URL and return short url that opens the site
		- Considerations
			- HTTP redirects
			- Handle URL not found
			- Use html template package to build web pages like for go
	- Currency converter
		- Built in terminal but not CLI program. Use terminal UI (charmbracelet library)
		- Objectives
			- Integrate with third party API

Problem solving is me describing a task that needs to get accomplished and you breaking it into tiny, actionable pieces.

For example, when I'm first learning a new programming language or framework I typically make (the same) 3 applications to get myself familiar.

**A simple todo app**.
**An app to get my local weather**.
**And application to parse csv data to JSON**.

Between these three I cover a LOT of ground within a language and learn most of the underpinnings that I'm going to use day-to-day when problem solving. Thinking about it, the skills from the abovementioned are **file i/o, date/time handling, string parsing, file manipulation, string formatting, network connectivity, and optionally, parallelism** (of network calls). Each of these is going to involve objects and error handling to become more familiar with how a language handles unexpected stuff