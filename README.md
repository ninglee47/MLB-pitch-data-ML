## Data analysis, visualization and machine learning of MLB pitching data.

### Data source

 Original dataset comes from [Kaggle](https://www.kaggle.com/pschale/mlb-pitch-data-20152018).  
 

### Introduciton
The goal is using PITCHf/x data to classify pitch types(EX. sinker, change up....).  

Pithch type Code:  
CH - Changeup, CU - Curveball, EP - Eephus*, FC - Cutter, FF - Four-seam Fastball, FO - Pitchout (also PO)*  
FS - Splitter, FT - Two-seam Fastball, IN - Intentional ball, KC - Knuckle curve, KN - Knuckeball  
PO - Pitchout (also FO)*, SC - Screwball*, SI - Sinker, SL - Slider,UN - Unknown*  
*these pitch types occur rarely  

### Data preprocessing:  
1. Remove following variables which do not have cause-effect relationships betweeen pitch types.  
   ('sz_bot', 'sz_top', 'type_confidence', 'code', 'type', 'event_num', 'b_score', 'ab_id', 'b_count', 's_count',
 'outs', 'pitch_num', 'on_1b', 'on_2b', 'on_3b','zone')  

2. Remove rare pith types,pitch-out and intentional ball.

3. Base on Variance Thresholding and Variable correlation analysis, following variables are excluded:  
   ('end_speed', 'break_y', 'y0', 'z0')


### Model evaluateion:  
Cross Validation scores  
1. Kernal SVM: 0.745  
2. RandomForest: 0.748  
3. GaussianNB: 0.649  
4. LogisticRegression: 0.700  
5. Neural network: 0.7775

### Models of individual pitchers (Neral network):
## F1 Score
1. Clayton Kershaw: 0.99
2. Gerrit Cole: 0.92 
3. Zack Greinke: 0.97

