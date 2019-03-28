#1 GOOGLE DRIVE
Put `colab` directory somewhere on Google Drive. Remember full path to it. Keep in mind, that path is prefixed by `gdrive/My Drive`, e.g. if you put it into Google Drive root without changing it's name, it's full path will be `gdrive/My Drive/colab`.

#2 JUPYTER NOTEBOOK
Just copy Jupyter notebook provided to your Google Colaboratory.

Remember to change `project_full_path` variable value to the path from step 1.

#3 COLABORATORY RUNTIME PREPARATION

Open Jupyter notebook in Google Colaboratory. From **Runtime** menu select **Change runtime type** menu item. Set **Runtime type** dropdown list value to **Python 3**. Set **Hardware acceleration** dropdown list value to **GPU**. Click **Save** button.

#4 MODEL PREPARATION

Use `download_mode.py` locally to download GPT-2 model you want.

Alternatively, download 177M model as a .zip archive from https://goo.gl/qBhYx4

When you have model, upload it to `colab/models` subdirectory. Note that each model has to be in a separate subdirectory, e.g. `colab/models/117M`, `colab/models/custom-2` etc.

#5 DATASET PREPARATION

Move files you wish the model to train on to `colab/dataset` subdirectory.  

#6 RUNNING
Just run Jupyter notebook provided (**Runtime** menu **Run all** item).

As you run it, from time to time you will have to authorize Google Colaboratory to use your Google Drive. When encountered with *"Go to this URL in a browser: https://accounts.google.com/o/oauth2/auth?<...>* while executing last code cell, click the authorization link (it starts with https://accounts.google.com/o/oauth2/auth?) and authorize Google Drive usage with account you used in step 1. Afterwards, you will have to copy authorization code provided by Google to a field in Jupyter Notebook output.

If you manually stop cell executing training, it will save it's state to checkpoints directory. Also, you will have to restart runtime manually if you manually stopped the execution beforehand, it is done through selecting **Runtime** menu **Restart runtime** item. 