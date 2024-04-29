# Forecasting Using Fourier Transformations in Trendz Analytics

## **Overview** 

Trendz Analytics is equipped with state-of-the-art tools for time-series prediction, offering end-to-end support from data preprocessing to complex forecasting techniques. Among these, Fourier Transformations stand out for their ability to decompose time series into fundamental frequencies, allowing for a nuanced understanding of cyclic patterns and trends.

## **Fourier Transformations:**
* Fourier Transformations convert time-series data from the time domain into the frequency domain, revealing the cyclical components within the data.
* This technique is particularly powerful for identifying and exploiting repetitive patterns in time-series data, making it highly applicable for seasonal forecasting.
* Trendz Analytics harnesses Fourier Transformations to offer precise and insightful forecasting, especially for datasets with pronounced periodicity.

## **Steps**

1. **Login:**

    * Begin by signing into Trendz Analytics with your ThingsBoard.cloud credentials.

2. **Load the Dataset:**

    * We focus on a dataset from a sealing machine, comprising columns like id, times, shift status, Lower Vertical Sealing Temperature, Upper Vertical Sealing Temperature, Front/Right Horizontal Sealing Temperature, and Back/Left Horizontal Sealing Temperature.

    * Our goal is to predict future values for Lower Vertical Sealing Temperature and Upper Vertical Sealing Temperature.

    * Initially, we display the dataset in a **Table** format to closely inspect the sealing temperatures. Subsequently, the **Line** format will be utilized to visualize and forecast the data trends.

        ![alt text](<../images/default model/format data visualization.png>)

    * Data visualization with Table

        ![alt text](<../images/default model/vertical bawah 26-29 march.png>)

    * Data visualization with Line

        ![alt text](<../images/default model/vertical bawah 26-29 march line.png>)

3. Forecasting with Fourier Transformations:
    * Switch to data visualization in **Line** format.

    * Activate the **Prediction** checkbox for the forecast field, indicated by a green box in the illustration.

        ![alt text](<../images/default model/1_.jpg>)

    * Choose **FOURIER** as the prediction method from the dropdown.

        ![alt text](<../images/default model/2_.jpg>)

    * Define the **Prediction Unit** as days.

    * Enter the desired **Prediction Range** (e.g., next 1 day).

        ![alt text](<../images/default model/3_.jpg>)

4. Forecast Results with Fourier Transformations:

    * Construct your forecast visualization. Click **BUILD** to generate and view the prediction outcomes.
    * Lower Vertical Sealing Temperature: Below illustration showcases the Fourier Transformation forecast for the Lower Vertical Sealing Temperature over the upcoming day.
        ![alt text](<../images/default model/vb.jpg>) 

    * Upper Vertical Sealing Temperature: The subsequent image illustrates the prediction for the Upper Vertical Sealing Temperature, also for the next day.
        ![alt text](<../images/default model/va.jpg>)

5. Evaluate the Forecast Model:
    * Implement in-sample forecasting: The evaluation of the Fourier model's efficacy employs a dataset split into training and testing partitions, with data from 5 days divided into 4 days for training and 1 day for testing.
    * Use Python in Google Colaboratory for manual forecast evaluation, leveraging metrics like MAE, MSE, RMSE, and MAPE to gauge model performance. Here are the metrics for the Fourier Transformations forecasting model:


        | Temperature | MAE | MSE | RMSE | MAPE |
        |:---:|:---:|:---:|:---:|:---:|
        | Lower Vertical | 35.04 | 1884.67 | 43.41 | 19.56 |
        | Upper Vertical | 35.5 | 1975.83 | 44.45 | 20.70 |

        Follow this link for comprehensive metric details [Metrics Evaluation in GColab](https://colab.research.google.com/drive/1tdeSHLz1CGEFum7ImrCmJbACjzgFd4jg?usp=sharing)

## Conclusion
The integration of Fourier Transformations within Trendz Analytics offers a sophisticated approach for dissecting and forecasting time series data, especially when periodic patterns are prominent. For further insights, consult the [Trendz Analytics Documentation](https://thingsboard.io/docs/trendz/).
