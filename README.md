# ForParticipants
### Rules and Guidelines for Evaluation of Sepsis Prediction Algorithm: 

1. Participants will be provided with a <b>TestSet</b> of 1000 cases that will have same format as the training data (i.e. .psv files) except that SepsisLabel column will not be present. Dataset will be shared on https://github.com/GEHC-SepsisChallengeSIH/ForParticipants. A snapshot of data format is shown here in italics:
<i>
HR|O2Sat|Temp|SBP|MAP|DBP|Resp|EtCO2|BaseExcess|HCO3|FiO2|pH|PaCO2|SaO2|AST|BUN|Alkalinephos|Calcium|Chloride|Creatinine|Bilirubin_direct|Glucose|Lactate|Magnesium|Phosphate|Potassium|Bilirubin_total|TroponinI|Hct|Hgb|PTT|WBC|Fibrinogen|Platelets|Age|Gender|Unit1|Unit2|HospAdmTime|ICULOS
NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|67|0|0|1|-33.04|1
81.0|99.5|35.2|145.0|101.0|77.0|16.0|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|104.0|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|NaN|67|0|0|1|-33.04|2
</i>

2. Participants have to <b>submit</b> both their predictions on the <b>test set and the model code</b>.

3. Once the TestSet is shared, participants will have <b>20 minutes</b> to submit their predictions on test set and model code. 

4. For predictions both PredictedProbability and PredictedLabel is to be given for each time point in each record. A snapshot of prediction format is shown here in italics:
<i>
  PredictedProbability|PredictedLabel<br>
  0.1|0<br>
  0.7|1<br>
  0.7|1<br>
  0.7|1<br>
</i>

5. A sample of expected prediction format is shared in folder <b>PredLabels_Example</b>. It gives a sample prediction for a sample test set of 1000 cases. 
(PredLabels_Example folder available on https://github.com/GEHC-SepsisChallengeSIH/ForParticipants)


6. At the time of submission you must share two folders:<br>
<b>[Team Name]_Predictions:</b> This folder should be in same format as folder <b>PredLabels_Example</b>. It must have 1000 .psv files starting from P0001.psv to P1000.psv<br>
<b>[Team Name]_Model:</b> This should have your model code. <br>
    <b><i>How to share your model and code</i></b><br>
    1. Each team must create it's own private repository on github.com <br>
    2. Teams must add user GEHC-SepsisChallenge (https://github.com/GEHC-SepsisChallengeSIH) as collaborator to their respective repository <br>
    3. User GEHC-SepsisChallenge owns repository https://github.com/GEHC-SepsisChallengeSIH/ForParticipants where test dataset will be provided at the time of evaluation.<br>
    4. Teams must then upload their prediction folder and model folder on their respective repository <br>
  
7. Algorithm Evaluation will be carried out using the script <b>evaluate_sepsis_score.py.</b><br>
  (Script available on https://github.com/GEHC-SepsisChallengeSIH/ForParticipants)


8. This script accepts two folders as follows: <br>
  python evaluate_sepsis_score.py [True Label Directory] [Predicted Directory]<br>
  Your prediction folder name will be put in [Predicted Directory]. The script will throw exception if the format of prediction folder
  or files is not as per norms stated above. If script fails to evaluate the prediction folder, the submission of that team will
  be rejected with no further chance of re-evaluation.

9. Sample output of the above script is shown here in italics:
<i>
  AUROC|AUPRC|Accuracy|F-measure|Utility
  0.38917632265976954|0.08633207353283748|0.11654613284425085|0.1765448646968549|0.7185162369708721
</i><br><br>

10. The evaluation criteria will be mean value of above mentioned 5 metrices: <br>
Final Score = (AUCROC + AUPRC + Accuracy + F-measure + Utility)/5 <br>
 
11. Please visit https://github.com/GEHC-SepsisChallengeSIH/ForParticipants for more information.<br>
-------------------Best Wishes-------------------

Sources:<br>
https://physionet.org/content/challenge-2019/1.0.0/ <br>
https://github.com/physionetchallenges/evaluation-2019 <br>
https://archive.physionet.org/users/shared/challenge-2019/ <br>
