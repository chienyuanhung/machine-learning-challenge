# machine-learning-challenge

Using the data from NASA Kepler space telescope over a nine-year period to predict the hidden planets outside of our solar system.

There are three categories for the planet data: 'CONFIRMED', 'FALSE POSITIVE', and 'CANDIDATE'

And the featuers in the NASA Kepler space telescope data include : 'koi_fpflag_nt', 'koi_fpflag_ss', 'koi_fpflag_co',   'koi_fpflag_ec', 'koi_period', 'koi_period_err1', 'koi_period_err2', 'koi_time0bk', 'koi_time0bk_err1', 'koi_time0bk_err2', 'koi_impact', 'koi_impact_err1','koi_impact_err2', 'koi_duration', 'koi_duration_err1','koi_duration_err2', 'koi_depth', 'koi_depth_err1','koi_depth_err2', 'koi_prad', 'koi_prad_err1', 'koi_prad_err2',
'koi_teq', 'koi_insol', 'koi_insol_err1', 'koi_insol_err2','koi_model_snr', 'koi_tce_plnt_num', 'koi_steff', 'koi_steff_err1', 'koi_steff_err2', 'koi_slogg', 'koi_slogg_err1', 'koi_slogg_err2', 'koi_srad', 'koi_srad_err1', 'koi_srad_err2', 'ra', 'dec',
'koi_kepmag'

Three algorithm: Support Vector Machine (SVM), K-nearest neighbors (KNN) and Random Forest (RF) were selected for training the model and predicting on the testing data. Grid-search was used to refined the parameters for each algorithm. Eventually, Random Forest scored the highest among the three models 

* select the features
  * I use Support Vector Machine (svc) from Python Scikit_Learn package to test the combinations of features to predict the planets. Here are list of scores for training and testing data
     * with all feature
        Training Data Score: 0.8455082967766546
        Testing Data Score: 0.8415331807780321
    * without ‘ra', 'dec'
        Training Data Score: 0.8464619492656876
        Testing Data Score: 0.830091533180778
    * without all the err2 data
        Training Data Score: 0.8413122258249094
        Testing Data Score: 0.8409610983981693
    * without all the err1 data
         Training Data Score: 0.8361625023841313
         Testing Data Score: 0.8283752860411899
    * without all err1 and err2:
         Training Data Score: 0.8167079916078581
         Testing Data Score: 0.7946224256292906
    * without 'koi_fpflag_nt', 'koi_fpflag_ss','koi_fpflag_co', 'koi_fpflag_ec'
         Training Data Score: 0.6646957848559985
         Testing Data Score: 0.664187643020595
    I decided to take all the err2 data out since they barely affect the scores

* Results for three algorithms after refined by grid-search
  * Support Vector Machine:
    Training Data Score: 0.8842265878313943
    Testing Data Score: 0.8804347826086957
  * K-nearest neighbors:
    Training Data Score: 0.8743086019454511
    Testing Data Score: 0.8106407322654462
  * Random Forest:
    Training Data Score: 1.0
    Testing Data Score: 0.9021739130434783





