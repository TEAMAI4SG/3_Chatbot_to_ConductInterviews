# 03.🎙️ Using Chatbot to Conduct Interviews
## 🧑‍💻 BUS 118I Digital Innovation

---

## 🎯 Learning Goal: 
1. Learn the basic components of Watson Assistant (or most chatbots): intents, entities, dialogs.
2. Build a simple chatbot that can interview users.

---

## ⏱️ Estimated time: 
- 45 minutes

---

## 📚 Material:

- [Watson Assistant Documentation](https://cloud.ibm.com/docs/assistant?topic=assistant-getting-started)
- To make the following survey, it might be helpful to have some knowledge of:
  - [Dialog Skill](https://cloud.ibm.com/docs/watson-assistant?topic=watson-assistant-skill-dialog-add)
  - [Intents](https://cloud.ibm.com/docs/watson-assistant?topic=watson-assistant-intents)
  - [Entities](https://cloud.ibm.com/docs/watson-assistant?topic=watson-assistant-entities)
  - [Dialog](https://cloud.ibm.com/docs/watson-assistant?topic=watson-assistant-dialog-build)

---

## 🗺️ Dialog outline: 

In this tutorial, the following dialog or conversation flow will be created. If you would like to understand more about dialog, then please refer to IBM’s [dialog overview](https://cloud.ibm.com/docs/watson-assistant?topic=watson-assistant-dialog-build) and the diagram below.

1. Welcome
2. Did you have a good weekend? (y/n)
   1) Yes (Intent): “That's great to hear! I hope you had a restful                  weekend.”
   2) No (Intent): “I’m sorry to hear that. :( I hope next weekend will be           better.”
3. What did you do over the weekend?
   1) Relax (Intent): “That’s good, sometimes you need to take time for              yourself to do better moving forward!”
   2) Work (Intent): “Wow, that’s great! You sure were productive over the           weekend. Good job!”
4. Anything else


![Picture 1](screenshots/pic1.png)

---


## 🚶‍♂️Steps: 

## 🧰 Part 1 Create a new assistant

1. Log in to [https://cloud.ibm.com/login] with your IBM account that you created using your SJSU email account.
2. Search for **“Watson Assistant**” in the search bar on the top, then click on the service under **Catalog Results**. Finally, **Launch Watson Assistant**

![Picture 2](screenshots/pic2.png)

3. You will be taken to the Catalog page to create the service. Please make sure that your location is set to **Dallas (us-south).** 

![Picture 3](screenshots/pic3.png)

4. Scroll down to the end and note your service name should have a default similar to “Watson Assistant -t8”. Click on **Create** on the bottom right to create your service.

![Picture 4](screenshots/pic4.png) 

a. If you are getting an error message as seen below, follow these     steps.

![Picture 5](screenshots/pic5.png)

b. Select delete. Give the page a few moments to load and you should see the following. Type **“Watson Assistant” under Name**. Hit the three dots and then select delete. Once deleted, navigate back to the Watson Assistant page and continue following the steps. 

![Picture 6](screenshots/pic6.png)

5. After creating the service, click on **Launch Watson Assistant** to launch the tool. 

![Picture 7](screenshots/pic7.png)

6. Once you’re on the **Welcome to watsonx Assistant** page, name your assistant **“Student Weekend Life Survey”**. Leave the description blank and click **Create Assistant** then **Next** on the upper right hand corner.

7. On the “Personalize your assistant” page, select **“Web”** under “Tell us where your assistant will live”. Under “Which industry do you work in?”, select **“N/A (I am a student)”**. Under “What is your role on the team building the assistant?”, select **“Developer”**. Under “Which statement describes your needs best?” select **“I’m using the product to complete a course or certification”** and click **Next.**

8. On the “Customize your chat UI” page, just click **Next**. 
9. On the “Preview your assistant” page, click on **Create**.

10. On the side bar, click on **“Assistant settings”.**


![Picture 8](screenshots/pic8.png)

11. Scroll down and click on **“Activate dialog”**. Click on **“Activate dialog”** again on the pop-up.

![Picture 9](screenshots/pic9.png)

12. On the side bar, click on the new **Dialog** button.

![Picture 10](screenshots/pic10.png)

13. **Submit a screenshot like the one below.
(Important: Please click on the person icon on the upper right corner to show your name in the screenshot otherwise you will not receive credit.)**

![Picture 11](screenshots/pic11.png)

**Note: For the following assistant responses, you don’t need to include the quotations.**

---

## 🧱 Part 2 Create the dialog skeleton

1. Click on the **“Create dialog +”** button.

2. Click the **Welcome** node,  adjust the text under, “Assistant responds,” with **“Hi there! I'm an AI Helper to see your experience during the weekend.”** **(***Don’t include quotations for the responses)**

![Picture 12](screenshots/pic12.png)

3. Click on the menu ( ⋮ ) on the upper right corner of the Welcome node and click **Add node below**.

![Picture 13](screenshots/pic13.png)


4. In the new node, the first textbox has a hint text “Enter node name (optional)”, name it **“Did you have a good weekend?”**

5. In the box underneath “Assistant responds” and “Text”, type **“Did you have a good weekend?”** for the assistant’s response


![Picture 14](screenshots/pic14.png)


6. Click on the menu ( ⋮ ) for the node you just edited and click **“Add node below”**
7. In the new node, name it **“What did you do this weekend?”** This is similar to Step 5.
8. In the box underneath “Assistant responds” and “Text”, type **“What did you do this weekend?”** for the assistant’s response. This is similar to Step 6.
9. **Submit a screenshot like the one below.
(Important: Please click on the person icon on the upper right corner to show your name in the screenshot otherwise you will not receive credit.)**


![Picture 15](screenshots/pic15.png)

---

## 💬 Part 3 Create the intents to catch users’ replies

We’ll be adding two intents **(yes and no)** to accompany the question: **“Did you have a good weekend?”** and two intents **(relax and work)** for the question: **“What did you do this weekend?”**

1. Click on the **Intents** tab in the left navigation bar.

![Picture 16](screenshots/pic16.png)


2. Click on **Create Intent**
3. Name one intent **“yes”** and click on **Create intent**

![Picture 17](screenshots/pic17.png) 

4. In the **User example** area, enter **“yes”** and click on **Add example** (or hit **Enter**). Then repeat and add the following “User examples” **(Intents are possible user responses or questions the chatbot is taught to recognize.):**
- Yes
- I did.
- Yeah
- Yup
- Mmhmm
- I think so


![Picture 18](screenshots/pic18.png)


5. Click the **blue back button** (not your browser back button) to go back to the Create Intents page, then Click on **Create Intent** on the top right.

6. Repeat Steps 2-4 to create another intent “no,” except with the following **User Examples:**

- No
- Nope
- Nah
- Not at all
- Don’t think so

7. Click the **blue back button** (not your browser back button) to go back to the **Create Intents** page, then Click on Create Intent on the top right.
8. Repeat Step 2-4 and add another intent **“relax,”** except with the following **User Examples:**

- baked a lot
- played sports
- mostly relaxed
- hiking
- watched movies
- did some of my hobbies

9. Click the **blue back button** (not your browser back button) to go back to the **Create Intents** page, then Click on Create Intent on the top right.

10. Repeat Step 2-4 and add another intent **“work,”** except with the following **User Examples:**

- I worked at my part-time job.
- I was mostly working.
- I worked on some projects.
- I worked.
- Working
- Studying
- doing homework
- working on deadlines


11. **Submit a screenshot like the one below.
(Important: Please click on the person icon on the upper right corner to show your name in the screenshot otherwise you will not receive credit.)**

![Picture 19](screenshots/pic19.png)

12. Click the **blue back button** (not your browser back button) to go back to the Create Intents page.

---

## 🔗 Part 4 Connect the dialog skeleton and intents

Additional resources: [https://cloud.ibm.com/docs/assistant?topic=assistant-getting-started]

1. Go to **Content Catalog** on the left navigation bar **(These are existing intents already created by IBM.)** and look for **“General,”** then click **Add content**

![Picture 20](screenshots/pic20.jpg) 

2. Go to **Intents** to view the intents from the **General Category** you added to your skill. For example, **General_About_You** or **General_Agent_Capabilities.** You can explore the type of user responses under each intent.

![Picture 21](screenshots/pic21.png)

3. Go to the **Dialog** tab, which can be found in the left navigation bar.
Click on the **“Did you have a good weekend?”** node. Under the **“If assistant recognizes”** area, add **“#General_Greetings”** as the condition. 

Note: The #General_Greetings intent was imported from Content Catalog in Step 1 and is catching common user greetings, such as “Hi” or “Hello.” Conditions will be used to capture a user’s response and give a reply in the following steps.

![Picture 22](screenshots/pic22.png)

4. Click on the menu ( ⋮ ) for the **“Did you have a good weekend?”** node and click on **Add a child node.**

![Picture 23](screenshots/pic23.png)

5. Repeat and add another child node for **“Did you have a good weekend?”** **(You should now have two child nodes).**


![Picture 24](screenshots/pic24.png)

6. Click on the first child node. Next, enter **“#yes”** as the condition under **“If assistant recognizes”**

7. Finally, type **“That's great to hear! I hope you had a restful weekend.**” for the assistant’s response.

![Picture 25](screenshots/pic25.png)


8. Click on the second child node. Next, enter **“#no”** into the condition under **“If assistant recognizes”**
9. Finally, type **“I'm sorry to hear that. :( I hope next weekend will be better!”**

![Picture 26](screenshots/pic26.png)

10. Now, **add two child nodes** for the node **“What did you do this weekend?”**, similar to steps 5 and 6. 
In the first child node, add the **“#relax”** intent and type the reply, **“That’s good, sometimes you need to take time for yourself to do better moving forward!”** This is similar to Steps 7 and 8.
In the second child node, add the **“#work”** intent and type the reply, “**Wow, that’s great! You sure were productive over the weekend. Good job!”** This is similar to Steps 7 and 8.

11. **Submit a screenshot like the one below to get credit for the assignment.
(Important: Please click on the person icon on the upper right corner to show your name in the screenshot otherwise you will not receive credit.)**


![Picture 27](screenshots/pic27.png)


---

## 🧵 Part 5 [Establish a conversation flow](https://cloud.ibm.com/docs/watson-assistant?topic=watson-assistant-dialog-overview)

1. Look at the child nodes for the node **“Did you have a good weekend?”.**


pic

2. Select the **“#yes”** node. Scroll down to **“Then assistant should”** and choose the **Jump to** option, then select the next node in the conversation, **“What did you do this weekend?”** node and choose **“Respond”**

pic

3. Repeat Step 2 for the **“#no”** node. The following image is what you should receive after creating the jumps. 
p

4. You’re done! Try the conversation in the **“Try it”** panel on the top right hand corner using some of the answers we created. 
**Note: You’ll need to say hi to start the conversation. Do you remember the #General_Greeting intent we added to the “Did you have a good weekend?” node?**


p

---

## 🏁 Part 6 A challenge for you

Revise your chatbot so that after the chatbot provides a response, you will have an additional final response saying goodbye to the user. **Hint:** You will need to add a new node and specify what the chatbot should do after users receive a response to **“What did you do this weekend?”**

**Submit a screenshot like the one below to get credit for the assignment.**

Sample screenshot:



---

## 🎓 Well done! You’ve not only built a chatbot; you’ve engineered a conversation. This lab marks a meaningful step in transforming curiosity into capability.



