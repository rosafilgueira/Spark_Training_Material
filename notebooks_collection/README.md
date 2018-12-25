# Instructions for running the Notebooks on Cirrus

1. Login to Cirrus by opening a terminal window and typing `ssh <username>@login.cirrus.ac.uk`, where `<username>` is the username given to you, and using your password
2. _Checkout_ this GitHub repository, by typing this command: `git clone https://github.com/rosafilgueira/Spark_Training_Material` - wait until the whole repository has been checked out before continuing
3. The Notebooks require you to have a copy of Hadoop and SPARK in your own `$HOME` directory, and for three scripts that we've written for you to use them seamlessly. Run the following commands:
    - `cp /lustre/home/shared/y15/spark/spark-2.4.0-bin-hadoop2.7.tar $HOME`
    - `cp /lustre/home/shared/y15/spark/*.sh $HOME`

   If you're familiar with `pbs` commands, you may wish to look at the contents of the `start_interactive.sh` file that you've just copied into your Home directory. Is there anything in there you might want to edit?
4. Run the command `./start_interactive.sh` - once you've been been allocated a node take a note of the node id - notice that the terminal shell now shows `[<username>@<node_id> ~]$`. You will need the node id in step 9.
5. Run the command `./start_spark.sh`, again wait for the command to finish before moving to the next step
6. We now need to `cd` into the directory containing the notebooks: `cd SPARK_Training_Material/notebooks_collection`
7. We need to load the `anaconda` module on Cirrus (modules aren't automatically available): `module load anaconda\python3`
8. We can now run the Jupyter server: `./start_Jupyter_local.sh` - after the script has run, you will see a URL printed in the terminal window of the form `http://localhost:8888?token=<string>` - we'll need this URL in step 10
9. Open a new terminal window, and run the following command: `ssh <username>@login.cirrus.ac.uk -L8888:<node_id>:8888`, where `<username>` is your username, and `<node_id>` is the node id your SPARK instance is running on, from Step 4
10. If you open a browser window on your desktop, you should now be able to navigate to the URL from step 8, and this should display the Jupyter Notebook server
11. You can either start with the Notebooks in this directory (click `1_basics.ipynb` to open the first Notebook), or navigate into LabExercises to work through the Notebooks in this directory. `lab1_basics.ipynb` contains all the basic commands you'll need to run these Notebooks. The official documentation, <http://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb>, contains more in-depth information about some useful commands.
