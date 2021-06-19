# Automatic-Code-Translation
### SJSU Masters Project 295A/B

#### Data Set
https://console.cloud.google.com/marketplace/details/github/github-repos

A transcoder is a machine translator that translates a program written in one programming language to another programming language. This is particularly useful when we want to upgrade our scripts written in older versions of programming languages into newer versions. Also, sometimes there will be a need to convert recently developed languages like CoffeeScript, TypeScript into a popular or omnipresent language like JavaScript. Over the past few years, there were many approaches examined and implemented for similar case study like translations between language pairs. For instance French to English, English to German, and so on. The initial experiments for these translations are done using traditional Neural Machine Translation models, where the datasets from both the languages are labeled manually and the models are trained to learn the translations in both languages. This was referred to as Neural Machine Translation of bilingual corpora in a supervised machine learning setting. This approach has achieved satisfactory results for the translations like French to English.

However, if this approach is applied to the machine translations between the programming languages, it would require a lot of human effort where one should have expertise on the programming language for labeling the datasets and becomes costly sometimes[5]. In order to avoid this, there has been a lot of research work on translating the programming languages without needing the parallel corpora. In the recent study from the Facebook AI research team, the authors Lachaux et. all [14] have achieved translating the programming language without needing the parallel corpora. Their model completely relied upon the monolingual corpora in an unsupervised machine learning setting which requires no expertise on either of the programming language pairs. They have incorporated three phases while building their model: The first one is cross programming language model pretraining, in this phase the sequences from programming with the same meaning are mapped to the same latent representation. The second one is denoising auto-encoding which initializes the encoder and decoder of the seq2seq model with the XLM model that is pre-trained. The last one is back-translation, which generates two models while the translation of target to the source programming language and vice versa. These two models are then trained in parallel until convergence.
           
With more than 80% of in-person financial transactions and up to 95% of all ATM transactions using COBOL, legacy languages such as FORTRAN for High Performance Computing, Lisp  are still widely used. These legacy languages are not compatible or convenient to work with and have dearth of developers making improvements or concerted platforms for them. Though the Facebook study has achieved satisfactory results in translating the programming languages, their models could translate among Python, C++, and Java. Our goal of the project is to explore more on the translations among programming languages in addition to Python, Java, and C++. Our main focus is to develop models that rely completely on monolingual corpora without using parallel corpora that requires manual labeling and achieve higher accuracy. Our models will be evaluated using various algorithms and different test cases will be generated to check their efficiency.

## Project Architecture:

![image](https://user-images.githubusercontent.com/47293060/118346348-a26a7000-b4ef-11eb-8c5f-84377b8fd72e.png)

Our end-to-end project design has a front-end component with a MERN stack, a CUDA environment for Training and a neural transcompiler, called a transformer. The transformer has been pre trained on C++, Java and Python programs and requires less time to tune and train when compared to its counterparts like RNN and LSTM. Transfer Learning is applied when it comes to training the model on R and Python alternatively between batches of back translation and the denoising auto encoder approaches. The model uses Adam Optimizer, paired with an attention mechanism to achieve excellent results.
