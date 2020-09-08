# Before You Start

Before starting with moduel testing please complelte the following task.

## Task 1: Create Data Resources

1. In the *Studio* interface, view the **Datastores** page. Your Azure ML workspace already includes two datastores based on the Azure Storage account that are created along with the workspace. These are used to store notebooks, configuration files, and data.

   > **Note**: In a real-world environment, you'd likely add custom datastores that reference your business data stores - for example, Azure blob containers, Azure Data Lakes, Azure SQL Databases, and so on. You'll explore this later in the course.

2. In the *Studio* interface, view the **Datasets** page. Datasets represent specific data files or tables that you plan to work with in Azure ML.
3. Create a new dataset from web files, using the following settings:
    * **Basic Info**:
        * **Web URL**: https://aka.ms/diabetes-data
        * **Name**: diabetes dataset (*be careful to match the case and spacing*)
        * **Dataset type**: Tabular
        * **Description**: Diabetes data
    * **Settings and preview**:
        * **File format**: Delimited
        * **Delimiter**: Comma
        * **Encoding**: UTF-8
        * **Column headers**: Use headers from first file
        * **Skip rows**: None
    * **Schema**:
        * Include all columns other than **Path**
        * Review the automatically detected types
    * **Confirm details**:
        * Do not profile the dataset after creation
4. After the dataset has been created, open it and view the **Explore** page to see a sample of the data. This data represents details from patients who have been tested for diabetes, and you will use it in many of the subsequent labs in this course.

## Task 2: Use the Azure ML SDK in a Compute Instance

You can perform most asset management tasks to set up your environment in the *Studio* interface, but it's also important to be able to script configuration tasks to make them easier to repeat and automate.

1. In [Azure Machine Learning studio](https://ml.azure.com), on the **Compute** page for your workspace, view the **Compute Instances** tab, and if necessary, click **Refresh** periodically until the compute instance you created in the previous lab has started.
2. Refresh the Azure Machine Learning studio web page in your browser to ensure your authenticated session has not expired. Then click your compute instance's **Jupyter** link  to open Jupyter Notebooks in a new tab. If prompted, sign in using the Microsoft account associated with your Azure subscription.
3. In the notebook environment, create a new **Terminal**. This will open a new tab with a command shell.
4. The Azure Machine Learning SDK is already installed in the compute instance image, but it's worth ensuring you have the latest version, with the optional packages you'll need in this course; so enter the following command to update the SDK packages:

    ```bash
    pip install --upgrade azureml-sdk[notebooks,automl,explain]
    ```

    You may see some warnings as the package dependencies are installed. You can ignore these.

    > **More Information**: For more details about installing the Azure ML SDK and its optional components, see the [Azure ML SDK Documentation](https://docs.microsoft.com/python/api/overview/azure/ml/install?view=azure-ml-py).

5. Next, run the following commands to change the current directory to the **Users** directory, and retrieve the notebooks you will use in the labs for this course:

    ```bash
    cd Users
    git clone https://github.com/MicrosoftLearning/DP100
    ```

6. After the command has completed, close the terminal tab and view the home page in your Jupyter notebook file explorer. Then open the **Users** folder - it should contain an **DP100** folder, containing the files you will use in the rest of this lab.
7. In the **Users/DP100** folder, open the **01B - Intro to the Azure ML SDK.ipynb** notebook. Then read the notes in the notebook, running each code cell in turn.
8. When you have finished running the code in the notebook, on the **File** menu, click **Close and Halt** to close it and shut down its Python kernel. Then close all Jupyter browser tabs.
9. If you're finished working with Azure Machine Learning for the day, in Azure Machine Learning studio, on the **Compute** page, select your compute instance and click **Stop** to shut it down. Otherwise, leave it running for the next lab.
