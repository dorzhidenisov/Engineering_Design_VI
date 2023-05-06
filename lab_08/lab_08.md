# Lab 8
* # install Python packages
    ```sh
    (lab8) C:\codes\design 6\iot\lesson8>pip install numpy scipy scikit-learn matplotlib pandas tensorflow keras
    ```
* # pyplot_simple.py
    ![](/lab_08/pyplot_simple.PNG)
* # simple_plot.py
    ![](/lab_08/simple_plot.PNG)
* # pyplot_formatstr.py
    ![](/lab_08/pyplot_formatstr.PNG)
* # ticklabels_demo_rotation.py
    ![](/lab_08/ticklabels_demo_rotation.PNG)
* # pyplot_three.py
    ![](/lab_08/pyplot_three.PNG)
* # pyplot_two_subplots.py
    ![](/lab_08/pyplot_two_subplots.PNG)
* # pyplot_scales.py
    ![](/lab_08/pyplot_scales.PNG)
* # pyplot_annotate.py
    ![](/lab_08/pyplot_annotate.PNG)
* # major_minor_demo1.py
    ![](/lab_08/major_minor_demo1.PNG)
* # legend_demo.py
    ![](/lab_08/legend_demo.PNG)
* # scatter_demo.py
    ![](/lab_08/scatter_demo.PNG)
* # histogram_demo_features.py
    ![](/lab_08/histogram_demo_features.PNG)
* # pyplot_text.py
    ![](/lab_08/pyplot_text.PNG)
* # histogram_demo_extended.py
    ![](/lab_08/histogram_demo_extended.PNG)
* # boxplot_demo.py
    ![](/lab_08/boxplot_demo.PNG)
* # linreg.py
    ![](/lab_08/linreg.PNG)
* # interpolation.py
    ![](/lab_08/interpolation.PNG)
* # plot_lda.py
    ![](/lab_08/plot_lda.PNG)
* # plot_lda_qda.py
    ![](/lab_08/plot_lda_qda.PNG)
* # plot_cv_predict.py
    ![](/lab_08/plot_cv_predict.PNG)
* # plot_cv_diabetes.py
    ![](/lab_08/plot_cv_diabetes.PNG)
* # traffic.py
    ```sh
    [[22  3]
    [ 1 41]]
                precision    recall  f1-score   support

            0       0.96      0.88      0.92        25
            1       0.93      0.98      0.95        42

        accuracy                           0.94        67
    macro avg       0.94      0.93      0.94        67
    weighted avg       0.94      0.94      0.94        67
    ```
* # keras_diabetes.py
    ```
    accuracy: 76.43%
    24/24 [==============================] - 0s 1ms/step
    [1, 0, 1, 0, 1, 0, 0, 1, 1, 0, 0, 1, 1, 1, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 1, 1, 0, 1, 0, 1, 1, 0, 0, 1, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1, 0, 1, 0, 0, 0, 0, 
    1, 0, 0, 1, 0, 1, 1, 0, 1, 0, 1, 1, 0, 0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 0, 1, 0, 1, 0, 0, 0, 1, 1, 1, 0, 0, 0, 1, 0, 1, 0, 0, 1, 1, 0, 0, 1, 1, 1, 0, 0, 0, 1, 1, 0, 0, 0, 1, 1, 0, 0, 0, 1, 1, 1, 
    0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 0, 0, 0, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, 1, 0, 0, 0, 1, 1, 0, 0, 1, 0, 0, 1, 1, 0, 0, 0, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1, 1, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 1, 0, 1, 0, 1, 1, 
    1, 1, 1, 1, 1, 0, 1, 0, 1, 0, 1, 0, 0, 0, 1, 1, 0, 1, 0, 0, 1, 0, 1, 1, 1, 1, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1, 0, 1, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 1, 1, 0, 1, 1, 1, 0, 0, 0, 0, 1, 
    1, 0, 1, 0, 0, 0, 0, 1, 1, 0, 0, 1, 0, 1, 0, 1, 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 1, 0, 0, 0, 1, 0, 1, 1, 1, 0, 0, 1, 0, 1, 0, 0, 0, 0, 1, 1, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 1, 0, 0, 0, 0, 0, 1, 1, 1, 0, 1, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0, 
    0, 1, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 1, 0, 1, 0, 0, 0, 0, 1, 1, 1, 0, 1, 1, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 1, 1, 0, 1, 0, 0, 1, 0, 0, 0, 0, 1, 1, 1, 0, 0, 1, 0, 0, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 
    0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 1, 0, 1, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 1, 1, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 
    0, 0, 1, 0, 0, 1, 1, 1, 1, 0, 0, 0, 1, 1, 1, 0, 1, 0, 0, 0, 0, 0, 1, 0, 0, 1, 0, 1, 1, 0, 0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 0, 0, 0, 1, 0, 1, 1, 0, 1, 0, 1, 1, 0, 1, 0, 1, 0, 1, 1, 1, 0, 1, 1, 0, 0, 1, 0, 0, 0, 0, 1, 1, 1, 0, 0, 0, 0, 0, 1, 1, 
    0, 1, 0, 0, 0, 1, 1, 1, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 1, 1, 0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 1, 1, 1, 0, 0, 0, 0, 1, 0, 1, 0, 1, 1, 0, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 0, 0, 1, 0, 1, 1, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1, 1, 1, 0, 1, 0, 
    1, 0, 1, 1, 1, 0, 1, 0, 1, 1, 1, 0, 0, 0, 0, 1, 1, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 0, 0, 0, 1, 1, 1, 0, 0, 0, 1, 0, 1, 1, 0, 1, 0, 1, 0, 0, 0, 0, 1, 0]
    ```
* # keras_first_network.py
    ```
    Accuracy: 77.34
    ```
* # Titanic example
    ![](/lab_08/titanic%201.PNG)
    ```
    Survived:
    Sex     Pclass
    female  1         0.968085
            2         0.921053
            3         0.500000
    male    1         0.368852
            2         0.157407
            3         0.135447
    Name: Survived, dtype: float64
    Number of Missing Fare: 1
    Indices of Missing Fare: 152
    Survived:
    Sex     Pclass  Fare_Bracket
    female  1       2               0.833333
                    3               0.977273
            2       1               0.914286
                    2               0.900000
                    3               1.000000
            3       0               0.593750
                    1               0.581395
                    2               0.333333
                    3               0.125000
    male    1       0               0.000000
                    2               0.400000
                    3               0.383721
            2       0               0.000000
                    1               0.158730
                    2               0.160000
                    3               0.214286
            3       0               0.111538
                    1               0.236842
                    2               0.125000
                    3               0.240000
    Name: Survived, dtype: float64
    ```
* # Data Analysis CPU usage vs Memory Available GB
    ```sh
    (lab8) C:\codes\design 6\iot\lesson8>python plt_final.py
    (lab8) C:\codes\design 6\iot\lesson8>python plt_cv2.py
    ```
    ![](/lab_08/plt_final%201.png)
    ![](/lab_08/plt_final%202.png)
    ![](/lab_08/plt_final%203.png)
    ![](/lab_08/plt_final%204.png)
    ![](/lab_08/plt_final%205.png)
    ![](/lab_08/plt_final%206.png)
    ![](/lab_08/plt_cv2.png)