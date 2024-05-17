# Anote_AI_Challenge

Name: Arnav Kulkarni
Email: a3kulkarni@ucsd.edu
Linkedin URL: https://www.linkedin.com/in/a3kulkarni/

Technical Approach:

Training Dataset: I used Finance Bench dataset and RAG dataset for training purpose. As individually they are not large enough, I combined both of these datasets into a single dataset. For this dataset, I picked just question, answer and context for every record in each of these datasets and created a combination of 350 records. I used train test split to divide the dataset into 80-20 train-test split, so that 70 examples were used as a validation set while 280 examples were used as a training set.

Methodology: I used Llama2 model using transformers package for the question answering task. This is because the architecture of Llama is a decoder only architecture, which is suitable for a task which involves the generative ability of the model. Encoder only models like BERT may not be very reliable when it comes to a task where text generation is also involved. In addition, Llama models have good understanding of the context and as this task needed a strong understanding of the context to answer the question, I decided to train Llama2 model for it. I used AutoTokeniser for the tokenisation and then used peft for fine tuning. Due to resource constraints, it is difficult to train large number of parameters that the Llama2 model has, therefore I implemented LoRA (Low Rank Adaptation) for this task, and reduced the number of trainable parameters significantly (I reduced the number of parameters to a large extent due to lack of access to GPUs except the Google Colab).

Limitations: Due to lack of access to GPUs and resource constraints, Llama3 could not be implemented. Llama3 could have performed even better on the given data for the QnA task. I used the Llama model with the least number of parameters and implemented LoRA to manage the limitations. Furthermore, only 0.1 epochs were run for the model, because when I tried running it for one epoch then the disk limit would exceed and it would crash. If the resource constraints are not the issue then more number of parameters can be considered for training which will further improve the model performance on our data.

Experience of working with Kensho Benchmarks: I wasnt able to submit due to some technical error


