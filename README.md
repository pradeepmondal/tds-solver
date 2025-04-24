# TDS Solver - Paste Your Question, Get Your Answer

This project was developed under the Tools in Data Science coursework @ IIT Madras.
<br />

It is an agent that exposes an endpoint that receives any question of the Graded Assignment via POST request and sends the answer (after solving) as the response.

The Graded Assignments referred are: <br /> <br />
GA 1: https://exam.sanand.workers.dev/tds-2025-01-ga1 <br />
GA 2: https://exam.sanand.workers.dev/tds-2025-01-ga2 <br />
GA 3: https://exam.sanand.workers.dev/tds-2025-01-ga3 <br />
GA 4: https://exam.sanand.workers.dev/tds-2025-01-ga4 <br />
GA 5: https://exam.sanand.workers.dev/tds-2025-01-ga5 <br />

<br />

Core technologies used:
- FastApi
- gpt-4o-mini as the main model
- embeddings for similarity matching
- other tools as needed to solve the given question
- etc.
<br />


This project can be used anywhere, all it needs is 2 api keys in the os environment:
- create the os variable ```AIPROXY_TOKEN``` and assign the value as the LLM provider's API key
- create the os variable ```GEMINI_API_KEY``` and assign the value as the Google's Gemini API key (free tier is enough)
- clone the repository
- globally replace ```"http://aiproxy.sanand.workers.dev/openai/v1/chat/completions"``` with your LLM provider's API url
- create the virtual environment using
   - ```python3 -m venv .venv```
- activate the virtual environment
- install the dependencies using
   - ```pip3 install -r requiremnets.txt```
- run the server using
   - ```python3 server.py```
- access the endpoint @ port 8080/api of the host


Here's an example of a sample request:

```
curl -X POST "localhost:8080/api" \
  -H "Content-Type: multipart/form-data" \
  -F "question=Download and unzip file abcd.zip which has a single extract.csv file inside. What is the value in the "answer" column of the CSV file?" \
  -F "file=@abcd.zip"
```

and here's a sample response:

```
{
  "answer": "1234567890"
}
```

** ensure your local environment has the dependencies listed in ```needed_dependencies.txt``` <br />
** A more user-friendly deployable version is in the pipeline. Stay tuned.

Pradeep Mondal<br/>
24th April, 2025
