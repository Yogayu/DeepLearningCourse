Doc:

https://docs.google.com/document/d/1LW0jc2nlehiwTX2YSILLF_qZa_tl-9s8DSIXS2jI8Bc/edit?usp=sharing

Dear Xinyu,

Thank you for sharing these materials and formulating your questions. In brief, we should aim to explain the concepts in multiple ways. First, different students may gain an understanding along different paths. Second, we can experiment with each method and discover which is more effective. Third, we should develop new embodied ways to enact the various concepts.

I mention "embodied" because in teaching network topologies and packet switching, I experimented with multiple ways to teach it, including Youtube videos that seemed really straightforward to me, and the embodied enactments of the concepts in class were dramatically more effective. The really obvious and well-made video explanations were surprisingly ineffective at introducing the concepts; they work much better as tools to help students compress and remember the concepts. 

So I want us to explore this to develop new forms of explaining and experiment with them -- using the principle that if you do something yourself with your own body, and maybe participate in an activity where other people are doing the same thing with their bodies, you will gain a much more intuitive and robust understanding than if you just watch a graphic. Embodied learning may have the advantage that the actions are remembered in several modalities -- touch, kinesthetics, vision, sound, and even smell -- and this may make it much easier to recall as a real event rather than a constructed abstraction. 

Wikipedia says "Dunn and Dunn define kinesthetic learners as students who require whole-body movement to process new and difficult information." However, the point is not that some students only learn this way, but that all students may find it easy to learn this way -- even if some are also able to learn the same information in all kinds of other ways. Embodied learning may form a kind of base level that works by default for everyone.

This involves two tasks that you can plunge into. The first is to parse and sequence the learning task. The second is to create a separate exercise for each parsed component.

Parsing and sequencing the learning task is obviously to analyze the task into its different components and to create a particular sequence of these components. For instance, the 3Blue1Brown videos structure the explanation by explaining the logic of how a network in principle could be used to recognize hand-written numbers, and then explains how you could train such a network. This is likely a good pedagogical move -- it separates the process into two tasks, thus simplifying the task.

However, for a humanities audience, it would be better if we could use a more interesting example than numbers. Let's think of a small set that has some limited set of features -- which features can ideally explain a neural network? 3Blue uses low-resolution numbers, but is this really necessary to explain the essential functions of a neural network? What is the simplest set of properties that can be used to illustrate the logic of a network? Consider something that everyone is intuitively interested in -- maybe the color of eyes, or different kinds of M&Ms, or the fingers of one or both hands. Which set of familiar objects has the properties we want?

3Blue explains the layers of the network by imagining that the first layer will recognize a series of edges, the second layer will recognize collections of layers that from small features, and the third layer then disambiguates the objects by selecting the unique and distinguishing combinations of these small features. This breaks down the recognition task into simple analytical steps -- and he adds that the actual network may not be solving the task in this way, but you could imagine a network solving the task by behaving in this way.

So the first question to ask is, which objects should we use to classify? These objects will be permanently associated with machine learning by our students. 

More generally, we should try to explain the math, in the way that 3blue for instance does with the sigmoid function. The aim is to explain everything, so that the mathematical formalisms also make sense. It's especially important for humanities students to explain the mathematics, otherwise they'll view the formulas as inexplicable -- we want them to realize that the formulas just express what they already understand.

In short, I suggest we need to have a really clear understanding of each step and then use our imagination to develop new, interesting, and intuitive activities that model these steps in an embodied fashion, so that students acquire a rich experiential understanding of each step to the point where they're absolutely comfortable and secure with it. Let's see if we can build this in such a way that students who really don't think of themselves as understanding equations will acquire a full understanding of deep learning, including the mathematical formalisms.

Prof Steen

Dear Prof. Steen,

Thanks for your replay of those questions. I sincerely appreciate your suggestions. The idea explains the concepts in multiple ways gives me some inspiration.

First, embodied learning is a great idea. As for the experiment, I mentioned in the previous course design, we could let students work as nodes and weights (or maybe activate function), in the playground, to form a neural network. Their goal is to deliver information, do some calculations, and get the output to do classification. The way students connect can be through paper cups phone or by running from one person to the next to deliver information. They should get a lot of fun out of it. Is this plan feasible? If possible, I can further refine the experiment.

For those who learn this course online, It would be hard to interact with each other physically. Well, the core of embodied Learning is to mobilize students' various senses(touch, kinesthetics, vision, sound) to learn. Is a short, fun video a good way to do this too? It also contains rich visual, kinesthetic, and auditory stimuli. There are two categories of video, one is screen recording. This kind of video tells the knowledge point while drawing on the plane. Another is to add a variety of pictures and animation. When I investigated relevant contents, I also found a series of video in Crash Course which belongs to the second category. They explain various kinds of knowledge vividly and interestingly through about 10 minutes' video.

I want to try to make videos of the second kind. I only have a little experience in making videos and it should take a lot of time to make the video. So, can I currently focus on adjusting the content which has been described in words so far, (from basic perceptron to forward backpropagation of deep forward neural network ) and try to make the corresponding video?

Our main purpose is to make students interested and enthusiastic about deep learning and feel that it is a subject that they can understand. Therefore, if they can thoroughly understand the deep forward neural network and practice some applications, they can lay a solid foundation.

Secondly, "Which objects should we use to classify?" I used the IRIS Flower data set in a previous section. There are three kinds of flowers: Iris Setosa, Iris Versicolour, and Iris Virginica. Two of which are linearly separable and one of which is linearly indivisible. We can explain different flower classifications at different stages. 
Building neural network likes building blocks. We can teach students to understand the basic building blocks, and then show them how the blocks fit together to form more complex neural networks. This example, while much clearer and simpler than handwritten numeral recognition, contains the most basic building blocks and how to build them. Of course, I would also like to think about whether there are other more suitable classifications.

The third point is about exercise. Yes, exercise is a must, and it may not be reflected in the courses that have been completed. In the late, I want to divide exercises into two categories, one is aimed to review the knowledge in each section, such as essay questions and some related thinking questions. Another kind of questions can be derived from the content outside the classroom, which can be further extended and thought deeply. Those questions are aimed to give students more space and freedom to learn more and deeper relevant content. What do you think? The idea is this, and we can talk more about that later.

Best wishes,
Xinyu You