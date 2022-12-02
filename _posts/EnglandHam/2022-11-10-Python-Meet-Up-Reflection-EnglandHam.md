---
layout: post
author: EnglandHam
title: "Soojin's Python Meet-up Reflection!"
---

# Austin Python Meet-Up Nov 10, 2022 featuring Nick Schenone "Building An AI APP under 20 Minutes Using OS MLOps tools and MLRUN" (online link available [here](https://youtu.be/mGojPdRqKIg))

## How did it go?
The meeting was quite enriching surrounded by people with vast knowledge, perhaps too complex for me to understand at my current level of understanding in Python. However, the presenter and people in the meeting were welcoming and allowed me to step into the world of AI and deploying models without feeling too overwhelmed by machine learning algorithms and the required programming knowledge when deploying an app. He told us that there are simpler ways to reach a production-quality stage by incorporating the MLOps pipeline.    

## What did you learn?
Before tackling deeper into MLRun, a developmental tool to make an AI app, Nick Schenone taught us about Companion Huggingface Space. The fundamental function is similar to GitHub in terms of sharing and organizing files, but this software allows free storage of all the UI elements as well as the model deployment codes so it's quite handy when developing an app as a team. 
Overall, we learned about MLRun as a tool to create a one-stop shop for MLOps, which builds infrastructure and controls behind the scene data-structure when it comes to building any machine-learning product amongst developmental teams. MLOps with MLRun allows reusable components, automatic containerization, infrastructure orchestration, feature store, model registry, and experiment tracking– all necessary to create an AI app. Having MLRun gives a simplified approach to creating production first into reproducible ways for model deployments. To give us an example, Nick showed us how his models and pipelines are divided into reusable components to share with his other developers for easier orchestration and control of their programming process. Nick also explained to us how MLRun code works to deploy locally and remotely by showing the code below containing the MLRun function for his eye-tracking AI model. He dissected each part of the code and carefully explained how our knowledge of Python can carry over and launch the model into MLRun as a sharable component. 

```python
import mlrun

project = mlrun.get_or_create_project(name="odsc-west", context="./"
serve = mlrun.import_function('hub://v2_model_server')

serve.add_model(key="iris", model_path="https://s3.wasabisys.com/iguazio/models/iris/model.pkl"

```

## Would you find value in this kind of event after class?
Although I am saddened that I couldn’t get the full value of the teaching and knowledge shared by the people at the meet-up, being surrounded by brilliant programmers challenge me to create new values that wouldn’t have been possible without my current programming class. The current class prepared me with basic knowledge to think about the unknowns and amazing flexibilities of Python. This meet-up showed me one of the many possibilities of Python’s magic and infinite capacity. 

## How was the experience different from your expectations?
I knew that my level of expertise in Python would be above my understanding, but I was hoping for more facilitated discussion among peers. I wanted to grow and share what I learned in class and vice versa but this meeting was rather a traditional meet-up and listen to a presenter. Perhaps this is due to the limited access to online meet-ups and the pandemic making it more difficult to create a close community. 

## Could you see yourself becoming a member of a professional community like this in the future?
Ideally, I want to be part of a professional community where I could fully discuss, learn, and be challenged in ways for my peers and me to grow. I currently find the Autin Python meet-ups a bit challenging compared to what I learned so far, but I hope to slowly expand my knowledge and join them so I can get the full benefits and knowledge shared by professional programmers. I believe that the best way to learn is to be surrounded by those who share similar passions and interests.  

Thank you for following me on my coding journey so far! 🙂
