**Harry Potter Text Generator**

This is the code for my text generator that I used to train on all 7 Harry Potter books.

**Preprocessing** - First, I preprocessed the text from all the books. I merged them into one file and removed all irrelevant signs and characters. I tried different configurations of signs and in the end left only the most relevant and frequent characters. During training, I could observe that the model performed much better when it had fewer options(signs) to choose from during training.
![dict_values](https://user-images.githubusercontent.com/66701870/148061695-958b1e74-af19-4cfa-931d-e2bcbca96ecf.png)

**Architecture** - I tried using different architectures and got the best results with 2 layers of LSTM and 2 layers of droput.
![my_model](https://user-images.githubusercontent.com/66701870/148061773-ceb3803f-8027-4cbb-90d9-970fbe612ba7.png)

**Hyperparameters** - I tried different sets of hyperparameters after selecting the architecture.

* *NUMBER OF MEMORY UNITS(both LSTM layers)*: [64, 128, 256, 512, 1024]

* *DROPOUT*: [0.1, 0.2, 0.3]

* *BATCH SIZE*: [1, 2, 4, 8, 16, 32, 64, 128]

* *SEQUENCE LENGTH*: [50, 100, 200] #The length of the sequence of characters after which my model is supposed to predict the next character in the sequence

I used the grid search method and started training them for several epochs. After this initial search, I took the top 3 sets of hyperparameters and started longer tests.
After these I found that I get the lowest categorical_crossentropy loss of 1.076 with: 

NUMBER OF UNITS:512 | DROPOUT:0.1 | BATCH:64 | LENGHT_SEQUENCE:50
![tensorboard](https://user-images.githubusercontent.com/66701870/148061829-f7cb8a90-673c-4480-bd99-0146b511c58d.png)
