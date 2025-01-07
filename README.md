<p align="center">
  <img src="https://i.imgur.com/aaIsFC6.png" alt="Traffic Examination"/>
</p>

# Building a Dashboard using Splunk
- Download Splunk Enterprise
 https://www.splunk.com/en_us/download/splunk-enterprise.html
- Installing Splunk on Windows
 https://www.splunk.com/en_us/resources/videos/installing-splunk-enterprise-on-windows.html
- Import data into Splunk
 After installing Splunk Enterprise and creating an account, import “prepared_data.csv” by selecting “Add Data”.

![image](https://github.com/user-attachments/assets/a60dd86b-f46f-46b4-ae21-d225a92bab4e)

- Then, click on “Upload files from my computer”. This means that the “prepared_data.csv” file should already be saved on your computer.

![image](https://github.com/user-attachments/assets/24349683-939c-4d89-b450-66da23cb204d)

- Select the file from your computer, then click on next. In the “Set Source Type” section, you may see a caution sign error, as shown below.

![image](https://github.com/user-attachments/assets/90fc0e0d-521f-4ee1-bc6f-b64352e19945)

- Go to Timestamp on the left and change from “Auto” to “Current time”, then click on “Save As”. You can name this “fraud_dectection.csv” and save.

![image](https://github.com/user-attachments/assets/f6cd746e-24ac-4b29-88c7-fdc777262f66)

- Click on "Next" until you get the result below.

![image](https://github.com/user-attachments/assets/6b0a0c15-a576-47eb-a9b3-061d594cdab6)

Analysing the Data
- Click on “Start Searching” to start analysing. On the left, you can find the “Interesting Fields” section.

![image](https://github.com/user-attachments/assets/16007bde-f7c7-476c-a32d-818a9f158902)

Creating the Dashboard
- One of the ways to create a dashboard in Splunk is via search.

![image](https://github.com/user-attachments/assets/a9af9c2a-30e9-46fc-aec9-1c9ef203d475)

For example, to add “Count by category” to your dashboard, type out
sourcetype="fraud_detection.csv" | top category
in the search field. This action counts
the number in each category, and you should get something like the example below:

![image](https://github.com/user-attachments/assets/db034faf-a61a-4997-96f1-236e22e28d01)


To add this chart to your dashboard, go to “Save As > New Dashboard > Dashboard Title = “Fraud Detection Dashboard” > Classic Dashboards > Save to Dashboard. This creates your
dashboard.

![image](https://github.com/user-attachments/assets/5222d669-4be7-453a-9bc3-2edaaa9c11e6)

To get “Fraud detected by category”, type sourcetype="practicesplunk.csv" fraud="1" | stats count values(fraud) by category in the search field. This counts the number of fraudulent activities recorded for each category.

To get “Gender with the most fraudulent activity by category”, type sourcetype="practicesplunk.csv" fraud="1" gender="F'" | stats count values(fraud) by category.



# Conclusion
The implementation of a Splunk-based dashboard significantly enhanced our fraud detection capabilities at Commonwealth Bank. This data visualization tool allowed for rapid identification of suspicious activities, enabling prompt preventive measures against potential fraud. The dashboard's effectiveness lies in its ability to:
- Consolidate and visualize complex data sets
- Highlight anomalies and patterns indicative of fraudulent behavior
- Facilitate quick triage and response to potential threats

By leveraging these visual analytics, I was able to streamline our fraud detection process, ultimately safeguarding both the bank and its customers from financial losses. This approach has proven to be more efficient and effective than traditional methods, allowing for a proactive stance in fraud prevention.










