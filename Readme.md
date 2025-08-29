---

# STL-10 Image Classification with PyTorch

<br>

A little project where I taught a machine to tell the difference between airplanes, cats, dogs, and a few other things. I used the STL-10 dataset and fine-tuned a ResNet18 model to see how well it could learn.

It was a great way to get my hands dirty with the entire process, from getting the data ready to seeing the final predictions. And honestly, it turned out better than I expected.

<br>

### A Quick Look at the Results

Here are some of the fun visuals that came out of this experiment.

| Accuracy & Loss Curves |
| :---: |
| <img width="576" height="455" alt="accuracy-over-epochs" src="https://github.com/user-attachments/assets/0767cfe2-e4aa-4737-afb8-d6c43e30c46e" />
|  <img width="567" height="455" alt="loss-over-epochs" src="https://github.com/user-attachments/assets/663f2b1f-4fed-41c6-bec6-a77360dff464" />

<br>

## What's Inside?

I kept the toolkit pretty focused for this one. Everything you see here was done with:

*   **Python:** The language holding everything together.
*   **PyTorch:** For building and training the neural network. A really enjoyable framework to work with.
*   **Torchvision:** Made it super simple to grab the STL-10 dataset and a pre-trained ResNet18 model.
*   **NumPy:** For some of the behind-the-scenes number crunching.
*   **Matplotlib & Scikit-learn:** I used these to create the plots and the confusion matrix you see above. Helps a lot in figuring out what the model is actually doing.

<br>

## How It Works

My approach was pretty straightforward. I wanted to stand on the shoulders of giants, not reinvent the wheel.

1.  **Data First:** The STL-10 dataset has these neat 96x96 pixel images. The first step was just loading them and getting them ready. I also did a little data augmentation—flipping images horizontally—to give the model more variety to learn from.

2.  **Borrowing a Brain (Transfer Learning):** I grabbed a ResNet18 model that had already been trained on the massive ImageNet dataset. The idea is that this model already knows a lot about general image features.

3.  **A Little Surgery:** I snipped off the model's original final layer and replaced it with a new one that fit the 10 classes of my STL-10 dataset.

4.  **Fine-Tuning:** Then, I trained this slightly modified model on the STL-10 images for just a few epochs. It's mostly about teaching the model to apply what it already knows to this new, specific task. I used the Adam optimizer and Cross-Entropy Loss to guide the learning process.

<br>

## So, How Did It Do?

Pretty well!

The model reached over **95% accuracy** on the validation set.

It learned to distinguish between the classes with pretty high confidence. Looking at the confusion matrix, it seems like it sometimes got 'cat' and 'dog' mixed up, and 'deer' with 'horse', which kind of makes sense. Overall, though, I was really happy with the performance, especially for a fairly quick training run.

<br>

## Want to Run It Yourself?

If you want to give it a spin, it's easy.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/Dawood-ML/Resnet-Transfer-learing-stl10-dataset.git)
    cd Resnet-Transfer-learing-stl10-dataset
    ```

2.  **Set up an environment:** It's probably best to use a virtual environment.
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the libraries:**
    ```bash
    pip install torch torchvision numpy matplotlib scikit-learn
    ```

4.  **Run the notebook:**
    Open the `resnet.ipynb` file in Jupyter Notebook or JupyterLab and run the cells. It should download the dataset automatically and start training.

---

Thanks for checking this out! It was a fun learning experience.
