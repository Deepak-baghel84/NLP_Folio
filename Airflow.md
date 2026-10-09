
## Airflow

(Need to be run PostgreSQL/MySQL server over the docker, create a image first.
To run db(Mysql/PostgreSQL) in local required a container.

astronomer is first step without it you can't work with astronomer.
1298225887
)

Like hamare pass multiple tasks h aur we want to execute them sequentially or parallelly so rather then having multiple scheduler we write a script to perform the task.

like hamare pass 3 clients h and we want to add one more then simply add them in config file.

initially we pass some default arguments like kitni times retry karna hai and after how much time.

ye with dag karke start hota hai(where we define start_date and other parameters), when you run your script, then script goes to the airflow server then dashboard or ui will be visible over the Airflow inteface there easily.

Then we define diffrent tasks(as decorators) and write the seprate methods for each tasks, defining tasks(decorator) is option it can be done withot writing it.

Note: Like we need to run same dag for development and production phases so simply changing source of data we can do using same script.

At the end we define the flow or priorities for each tasks.

(owner data engine hi nahi h new dag's m)

Like at what task pipeline get stopped, what error occured, what is time, region  and so on.. will be checked in audit.
Airflow is like a vm.

we can connect gcp(cloud), Airflow and Big query so that simply read and write can be happen through Big Query.


There is one dag to monitor all dag's, means success or failure of all the pipelines will be visible in this single dag ki which pipelines continuously failing , getting notification hourly came in the airflow of special dag.

TO kya hota h, suppose tumne facebook pr koi add dekhi tune us pr click kia then uska session create hoga, tumne kitna time spend kiya, ye ek event h then another event is ki tumne konsa vehicle dekha (2,4 wheeler) ye sab GA4(google analytics) se track hota h then through api hum use extract karte h through pipeline.
so initially kya hota tha ki 5 events ke liye 5 files(dag) create kr dia, now humne kya kiya ki ek single dag banaya aur through configurations hum all events(report) ko single dag se manage kar rahe hai(aur modular hai).

There is dag's which also depends on other dag's means first one dag run then based on the result of that dag other dag run to create summary like.
suppose one dag(pipeline) run that stored data in big query then after 10 minute other pipeline run to check the difference in past and current data to create the summary of that.
