# Supervised-Learning-Challenge-2
Let's break down Step 7 (Evaluation) in detail:
 
1. Understanding the Classification Report
The classification report provides key performance metrics:
•	Precision
•	Recall
•	F1-score
•	Support
•	Accuracy
My  results:
Accuracy: 0.87
Classification Report:
              precision    recall  f1-score   support
        0       0.86       0.86      0.86       29
        1       0.88       0.88      0.88       32

accuracy                        0.87       61
macro avg       0.87       0.87      0.87       61
weighted avg    0.87       0.87      0.87       61
 
2. Is 87% Accuracy a Good Score?
•	87% accuracy is a good score in general, but it depends on the problem.
•	In medical predictions (like heart disease), accuracy alone is not enough.
•	If the dataset is imbalanced (e.g., more patients without heart disease than with it), accuracy can be misleading.
•	That's why Precision, Recall, and F1-score matter more in such cases.
 
3. Difference Between Accuracy and Precision
Accuracy
•	Formula: Accuracy=Correct PredictionsTotal Predictions\text{Accuracy} = \frac{\text{Correct Predictions}}{\text{Total Predictions}} 
•	Interpretation: 
o	Our model correctly predicts heart disease 87% of the time.
o	But accuracy alone doesn’t tell us if the model is good at detecting heart disease cases (1s).
Precision
•	Formula:
Precision=True Positives (TP)True Positives + False Positives (TP+FP)\text{Precision} = \frac{\text{True Positives (TP)}}{\text{True Positives + False Positives (TP+FP)}} 
•	Interpretation:
o	Precision answers: "Of all the patients predicted as having heart disease (1), how many actually have it?"
o	Our model has 88% precision for class 1, meaning that when it predicts heart disease, it is correct 88% of the time.
•	Why does this matter?
o	High Precision → Fewer false positives (wrongly predicting disease when there isn't one).
o	Important in medical tests where false positives can lead to unnecessary treatments.
 
4. What is Recall?
•	Formula:
Recall=True Positives (TP)True Positives + False Negatives (TP+FN)\text{Recall} = \frac{\text{True Positives (TP)}}{\text{True Positives + False Negatives (TP+FN)}} 
•	Interpretation:
o	Recall answers: "Of all actual heart disease cases, how many did the model detect?"
o	Our model has 88% recall for class 1, meaning it correctly identifies 88% of patients who actually have heart disease.
•	Why does this matter?
o	High Recall → Fewer false negatives (failing to detect real cases of heart disease).
o	Important when missing a disease diagnosis is dangerous.
 
5. What is F1-score?
•	Formula: F1-score=2×Precision×RecallPrecision+Recall\text{F1-score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}} 
•	Interpretation: 
o	F1-score is the balance between precision and recall.
o	If you increase precision, recall may go down (and vice versa).
o	Our F1-score is 0.88, meaning your model has a good balance between detecting heart disease and avoiding false alarms.
 
6. Summary
"Our model predicts heart disease with 87% accuracy, which means it is mostly reliable.
However, we also check precision (88%) to see how often a predicted disease case is actually correct and recall (88%) to see how well we detect real cases.
The F1-score (88%) ensures a good balance between these two.
Overall, the model performs well in predicting heart disease, but false positives or negatives could still occur."
 
7. Final Takeaway
•	If false negatives (missing a disease case) are more dangerous → Focus on Recall.
•	If false positives (wrongly predicting disease) are more harmful → Focus on Precision.
•	F1-score balances both and is a strong indicator of model performance.
 
✅ Next Steps:
•	If we want a more balanced model, we can tune hyperparameters of RandomForestClassifier: 
•	rf_classifier = RandomForestClassifier(n_estimators=200, max_depth=10, random_state=42)
•	We can also try other ML models (like SVM or KNN) to compare results.

![image](https://github.com/user-attachments/assets/8a0f41aa-6705-4a12-bbbd-1a4c1977f8ad)
