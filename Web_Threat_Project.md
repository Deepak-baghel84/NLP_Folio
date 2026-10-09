
## Web Threat Detection



using this we can identify the malicious websites and prevent from the frauds like someone send you need to pay this much of amount on this site else your account get suspended, you won something to crab the prize you have to pay this much of amount.


what is SharePoint in enterprises to keep the data, collaborate with the data.


Feature engineering is part of data preprocessing.
There are multiple steps related to data like,
ETL, data parsing, Data ingestion, data cleaning, data wrangling, feature engineering, data preprocessing, data transformations.

Complete process is same for the gen ai like core ml, only the training part got differ mainly, (data related part will be the same and evaluation).

Application(Project) development is one thing but scaling, optimizing and enhancements are the major things need to do in projects. like how you reduce latency(time taken to load document) ,cost of llm etc.
(Ai system design)


1 = yes , 0 = no ,  -1 = unknown

predictor file for inferencing part : means testing(predicting) over the trained model


screenshot _,48, 150 min

workflow: we have data in csv format we load the data then train a model using xgboost or Ann then save the trained model as .pkl file. then load the model and does inferencing or predictions.


python -m inference.predictor



Working of predictor-->web extractor:

user passes any website URL then request goes to web extractor(separate module) which using beautiful soup extract all the required features(30 existing features) then we pass to a validator(method) to check all features are exist or null then validate. Then all features will passes to the model(which we trained and loaded as .pkl file) and get inference which gives us the probability of legit, phishing based on that we return the response.





mlflow : Generally used for the tracking application, keep the information of complete pipeline, what metrices we capturing, what model we are training. Its like Lang smith .
Langsmith is easy to implement like simply using a api key but for mlflow we need to write code some classes and functions.


interview q in there.



run mlflow ui, given commands documents.
all the logs, training part will be saved over the mlflow and can be track and visible over there. it is open source platform.
we get the complete overview of the ui, pipeline, logs no need to check code again and again.
precision, accuracy, f1 scire, recall and hyperparameters(parameters) used during training visible there


screenshot: 120, 204

Remember:
On which port Fastapi, Flask run how to pass custom port.
port mapping is very important in docker 8000(docker port), 8080(local port)



Deployment:
Automatic load balancer(alb) + Api Gateway + Lambda + ui over the s3(static website) ==> For routing the Api
 App runner

Port Mapping: Docker image run inside a container( it is a vm) which contains some port address, so currently our application is running in this port and we want to run it over the internet/browser for that we map the docker port to internet port.


screenshot:  55


for mvp and quick deployment use : App runner or elastic-beanstalk


all information about deployment


Roles and policies : How different services will interact with each other for that need to define some incline or other policies or roles.

=============================================================================================================================================

General conversation about web scrapping:

options.add_argument(...)
options is an instance of uc.ChromeOptions() (from undetected-chromedriver).

The method add_argument("--flag") lets you pass command-line arguments to the Chrome browser when it launches.

These arguments modify Chrome’s behavior. For example:

--no-sandbox: Disables Chrome’s sandbox security model (sometimes needed in restricted environments).

--disable-blink-features=AutomationControlled: Prevents websites from detecting that Chrome is being controlled by automation (helps bypass bot-detection scripts).

So, add_argument is essentially a way to customize how Chrome starts up.

🔹 Flow of Your Code
Create ChromeOptions object

python
options = uc.ChromeOptions()
This object stores all the configuration settings for the browser.

Add custom arguments

python
options.add_argument("--no-sandbox")
options.add_argument("--disable-blink-features=AutomationControlled")
These arguments tweak Chrome’s startup behavior.

Launch Chrome with options

python
driver = uc.Chrome(options=options, use_subprocess=True)
This starts a Chrome browser instance using undetected-chromedriver.

use_subprocess=True ensures Chrome runs in a separate subprocess, which can improve stability.

Driver is ready

At this point, driver is your active browser automation object.

You can now use it to navigate pages, scrape data, or interact with web elements.

🔹 Visual Flow
Code
uc.ChromeOptions() → add_argument() → configure browser → uc.Chrome(options=...) → driver ready
👉 In short: add_argument is how you pass startup flags to Chrome, and the flow is: create options → add arguments → launch Chrome with those options → get driver to control the browser.

Would you like me to also explain why these specific flags are commonly used in web scraping (like avoiding detection and sandbox issues)?

But in this we does not uses any way to tweak the security of the chrome browser options = uc.ChromeOptions()
        driver = uc.Chrome(options=options,use_subprocess=True)
        search_url = f"https://www.flipkart.com/search?q={query.replace(' ', '+')}"
        driver.get(search_url)
You’re right — in the second snippet you shared, you’re not adding any special arguments to tweak Chrome’s security or automation-detection features. Let me walk you through the flow of that code:

🔹 Step-by-step flow
Create ChromeOptions object

python
options = uc.ChromeOptions()
This initializes a configuration object for Chrome.

At this point, no arguments are added, so Chrome will run with its default settings.

Launch Chrome with options

python
driver = uc.Chrome(options=options, use_subprocess=True)
This starts a Chrome browser instance using undetected-chromedriver.

Since no arguments were added, Chrome runs normally, without tweaks like disabling sandbox or hiding automation.

Build search URL

python
search_url = f"https://www.flipkart.com/search?q={query.replace(' ', '+')}"
Takes the user’s query string, replaces spaces with + (URL-friendly format), and creates a Flipkart search URL.

Navigate to the search page

python
driver.get(search_url)
The browser opens the Flipkart search results page for the given query.

🔹 Key difference from your first snippet
In the first snippet, you used:

python
options.add_argument("--no-sandbox")
options.add_argument("--disable-blink-features=AutomationControlled")
These arguments tweak Chrome’s behavior (security sandbox and automation detection).

In the second snippet, you didn’t add any arguments. So Chrome runs with its default configuration — no bypasses, no tweaks.

🔹 Why this matters
Without arguments, Chrome is more “vanilla” — it behaves like a normal user browser.

With arguments, you can:

Avoid detection by anti-bot measures.

Work around restrictions in certain environments (like Docker or CI/CD pipelines).

Customize performance or debugging options.

👉 So in short: the second snippet is a simpler flow — it just launches Chrome with default settings and navigates to Flipkart. The first snippet is a more advanced flow where you deliberately tweak Chrome’s startup behavior to avoid detection or restrictions.

Would you like me to show you a side-by-side comparison table of common Chrome arguments and what they do, so you can decide when to use them?




Incorrect use of os.mkdir with exist_ok

os.mkdir does not accept exist_ok. Only os.makedirs does.

 In Python, you can’t put an except after a for loop like that. The except must directly follow the try block it belongs to.







install setuptools

If the element does not exist (because no popup showed up at that moment), Selenium raises a NoSuchElementException.(code for removing pop up from browser)




zEfFJL   title
 
