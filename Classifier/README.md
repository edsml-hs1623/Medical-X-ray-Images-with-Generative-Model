## DL module coursework 2

<img src="https://drive.google.com/uc?id=1DG7dis2Daa9MObZP7pK5HBMBQiHMED-D" width="700"/>

Relase date: 14:00h Thursday 14th December 2023

Submission deadline: 18:00h Friday 15th December 2023

**At 18:00h on Friday I will clone the repositories, so make sure to have everything commited by then.**

<br>

## **Tasks**

### Task 1
Classify the hand images in the `test_hands` folder using any method you have learned during the module. The classifier should classify test hands using the following labels:

- `0`: real hand
- `1`: VAE hand
- `2`: GAN hand

<br>

### Task2
Answer the two questions at the end of this README file. Answer them in the README itself and commit and push your modified README file to your repository.

<br>



## Deliverables

Your final repository should contain the following:

1. `yourusername_classified_hands.csv`: a comma-separated value file with the name of the hand in the test set, then a comma, and then the prediction for this hand image. It should look like:

	```
	test_hand_0001.jpeg, 2
	test_hand_0002.jpeg, 0
	...
	```
with the appropriate lable values that your classifier generates. Add this new file to the repo and do not put it inside any subfolder please.

2. `yourusername_DLcw2_clean.ipynb`: a clean notebook with your classifier workflow (similar to the one you created in coursework 1), should include data preparation, network implementation, final training, final evaluation of the test set, writing of the csv file, and any other step you have done that is not related to hyperparameter tunning or network design tests (only steps using your best and final classifier model). 

3. `yourusername_DLcw2_hypertune.ipynb`: as in coursework 1, a notebook where you explore your best hyperparameter values for your final network design and training that you will include in `yourusername_DLcw2_clean.ipynb`.

**[IMPORTANT]: I do not provide templates this time, you can design it as you wish, but you will be assessed on the clarity and tidiness of your submitted notebooks. And remember that  all code cells should be executed before you commit and push the notebooks to the repo.**

4. `README.md` — Modified version of this README file that includes your answers to the questions you will find below. Please stick to the word limit, I will not assess anything written beyond the given word limit.

5. `references.md` — List of your references you have used in similar to the one you provided in coursework 1. You have to create the markdown file yourself this time.

<br>

## **Task 1 - Classifier**

### Datasets
You will find the following folders in this repository:
- `real_hands`: contains real hands (but feel free to use more from the first coursework repo if you think it is a good idea.
- `VAE_hands`: contains hands generated using VAEs.
- `GAN_hands`: contains hands generared using GANs.
- `test_hands`: contains a mix of real hands, VAE-generated hands, and GAN-generated hands.

Use the four datasets as you see fit to design and implement a classifier to label the images in the `test_hands` folder as:

- real hands (label: `0`)
- VAE-generated hands (label: `1`)
- GAN-generated hands (label: `2`)

You have to implement your network explicitly and train it from randomly initialised weights (no transfer learning), but you can use any architecture you think is useful.

<br>

## **Task 2 - Questions**
Modify this README file to include the answers to the questions below.

### Question 1 [150 words maximum]
If I asked you to do the first coursework again, but now I gave you 5 days and 500 compute units (instead of 100 compute units), what would you do differently to improve your results. In this case, you would be able to use any architecture we have seen in class. Justify your answers well, and do not go over the word limit. You can use bullet points and a maximum of one diagram/figure/table to support your answer.

###ANSWER to question 1:

I would still choose GAN for the following reasons:
- GAN produces more realistic images (important for medical use)
- GAN gives better results but it is computationally expensive and unstable, so can benefit from more time and compute units (I nearly ran out of all 100 compute units last time)

Things I would also make a change:
- Use a deeper architecture (including dropout and batch normalisation) for discriminator and generator to capture complex patterns and structures
- Apply data augmentation during training to improve the model's generalization

<br>

### Question 2 [100 words maximum]
Additionally to the newly defined hypotethical assessment in **Question 1**, if i told you that now the images were 512x512 pixels instead of 32x32, and I gave you a choice between these two extra resources:

**a.** as much compute power as you want, but only have the 10000 images provided. <br>
**b.** as many more images in your dataset as you want, but only have the 500 compute units availabe.

Which one would you choose and why? Again justify your answers and use bullet points or tables as you see fit.

###ANSWER to question 2:

I would choose option a. in this case for the following reasons:
- The quality of model is more important than the quantity of images given (Can use a deeper architecture without the concern of running out of all compute units).
- High computational resources can accelerate the training process, allowing for more iterations and convergence towards a better-performing model.
- Higher-resolution images (512x512) means more details are kept in the image, so simple structure might not be competent for the generating intricate and realistic images
- While choosing option b. might increase the diversity of output and reduce the risk of overfitting becasue of more inputs given, intricate and detailed images derived from option a. are more crucial for medical images
