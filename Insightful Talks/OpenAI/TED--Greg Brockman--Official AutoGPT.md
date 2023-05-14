# TED--Greg Brockman--Official AutoGPT



Chinese Brief: [OpenAI现场演示官方版AutoGPT！创作画画发推一条龙，自主调用外部应用完成任务](https://mp.weixin.qq.com/s/rMS8IdS0qdq6Y2nl-UM-Ew)



Video: [Open AI 联合创始人 Greg Brockman 在 TED 大会现场演讲视频_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1514y1f74G/?spm_id_from=333.788.top_right_bar_window_history.content.click&vd_source=57ac3ae5415445af2ffe1e61e1722d73)



## Notes of the Video

### Demonstration of GPT+Plugin

> Today I want to show you the current state of (OpenAI GPT) technology and some of the underlying design principles we hold dear.



In first example, he showed how to use a DALL-E2 plugin to let GPT to create a suggestion for a meal and then draw a picture according to the suggestion.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230423225818829.png" alt="image-20230423225818829" />*The generated image*



Then, he asked the GPT to make a shopping list for the food inside the above picture and tweet it out for the TED viewers.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230423230608499.png" alt="image-20230423230608499" />

*AI using plugin*

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230423230747921.png" alt="image-20230423230747921" />

*Results of the shopping listed created by GPT*

> By having this unified language interface on top of the tools the AI is able to take away all the details from you.

> Traditional UI will not go away. It's just we have a new augmented way to build them.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230423235142639.png" alt="image-20230423235142639" />

*GPT uses Zapler Plugin to tweet*

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230423235229212.png" alt="image-20230423235229212" />

*The tweet generated*

### Explain How They Build This

> To train GPT, its a two step process.
>
> 1st we produce what Touring would have called a child machine through an unsupervised learning process. We just show it the whole world of Internet and say predict what comes next and text you've never seen before. And this process imbues it with all sorts of wonderful skills.
>
> 2nd step, teach the AI what to do with the skills (that it have learned through unsupervised learning), and for this we provide feedback. We have the AI try out multiple things, give us multiple suggestions and then human rates them says this one's better than that one.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230423235858861.png" alt="image-20230423235858861" style="zoom:50%;" />

*Human feedbacks which option is better*

> This allows the AI to generalize, to infer your intent, and to be applied in scenarios that it has not seen before.

Some times, things we do not generally expect to teach the AI are important, for example, simple math.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230424000337016.png" alt="image-20230424000337016" />

*Teach AI to say when human is wrong*

It is then very important to obtain **high quality feedback**.

> Now, providing high quality feedback is a hard thing

Simple Loss function will lead to unsatisfactory performance, it even will result the AI to cheat.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230424000642371.png" alt="image-20230424000642371" />

*If you teach a kid to clean a floor and if all you check is the cleaness of the floor, this may happen.*

AI itself can be used to produce those high quality feedbacks.

He introduce a `browsing` tool, which can be used to fact check the content that GPT provides. By this way, GPT can do supervised learning from the feedback.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230424233401521.png" alt="image-20230424233401521" style="zoom:50%;" />

> Human uses this fact checking tool is doing it in order to produce data for another AI to become more useful to human. This could really be expected to be much more common in the future.

By combing human management, oversight, and feedback, and the machine is operating in a way that's inspectable and trustworthy, he believes more trustworthy machines can be created, which leads to solution even to impossible problems.



### The Strength of GPT to Handle Excel Files

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230424234102610.png" alt="image-20230424234102610" style="zoom:50%;" />

He presented a model named Code Interpreter. He directly upload a csv file containing all the AI papers in arXiv. The model automatically analyze it and provide insightful outcomes.

<img src="./TED--Greg Brockman--Official AutoGPT.assets/image-20230424234528482.png" alt="image-20230424234528482" style="zoom:50%;" />

GPT can take in super high level instruction, like "make some exploratory graphs", which has lots of possible intent behind it.

 