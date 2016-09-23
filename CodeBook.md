## CodeBook: Data Science Specialization course series: Getting and Cleaning Data Course Project


>
>These signals were used to estimate variables of the feature vector for each pattern:  
>'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
>
>		tBodyAcc-XYZ
>		tGravityAcc-XYZ
>		tBodyAccJerk-XYZ
>		tBodyGyro-XYZ
>		tBodyGyroJerk-XYZ
>		tBodyAccMag
>		tGravityAccMag
>		tBodyAccJerkMag
>		tBodyGyroMag
>		tBodyGyroJerkMag
>		fBodyAcc-XYZ
>		fBodyAccJerk-XYZ
>		fBodyGyro-XYZ
>		fBodyAccMag
>		fBodyAccJerkMag
>		fBodyGyroMag
>		fBodyGyroJerkMag
>
>	Additional vectors obtained by averaging the signals in a signal window sample. 
>	These are used on the angle() variable:
>
>		gravityMean
>		tBodyAccMean
>		tBodyAccJerkMean
>		tBodyGyroMean
>		tBodyGyroJerkMean
>
>	The set of variables that were estimated from these signals are: 
>
>		mean(): Mean value
>		std(): Standard deviation
>		mad(): Median absolute deviation 
>		max(): Largest value in array
>		min(): Smallest value in array
>		sma(): Signal magnitude area
>		energy(): Energy measure. Sum of the squares divided by the number of values. 
>		iqr(): Interquartile range 
>		entropy(): Signal entropy
>		arCoeff(): Autorregresion coefficients with Burg order equal to 4
>		correlation(): correlation coefficient between two signals
>		maxInds(): index of the frequency component with largest magnitude
>		meanFreq(): Weighted average of the frequency components to obtain a mean frequency
>		skewness(): skewness of the frequency domain signal 
>		kurtosis(): kurtosis of the frequency domain signal 
>		bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
>		angle(): Angle between to vectors.

##### Unit:

Features are normalized and bounded within [-1,1]. In other words, they are unitless.

------------------------------------------------------------------------------------------------
#### Original data sets: selected input data variables

Based on the requirement of the course project, I only selected those input variables
related to the measurements on the mean and standard deviation for each measurement.
(see the section of "Instruction and Requirements" in README.md)

They are the following:

	tBodyAcc-mean()-X           tBodyAcc-mean()-Y           tBodyAcc-mean()-Z           tBodyAcc-std()-X           
	tBodyAcc-std()-Y            tBodyAcc-std()-Z            tGravityAcc-mean()-X        tGravityAcc-mean()-Y       
	tGravityAcc-mean()-Z        tGravityAcc-std()-X         tGravityAcc-std()-Y         tGravityAcc-std()-Z        
	tBodyAccJerk-mean()-X       tBodyAccJerk-mean()-Y       tBodyAccJerk-mean()-Z       tBodyAccJerk-std()-X       
	tBodyAccJerk-std()-Y        tBodyAccJerk-std()-Z        tBodyGyro-mean()-X          tBodyGyro-mean()-Y         
	tBodyGyro-mean()-Z          tBodyGyro-std()-X           tBodyGyro-std()-Y           tBodyGyro-std()-Z          
	tBodyGyroJerk-mean()-X      tBodyGyroJerk-mean()-Y      tBodyGyroJerk-mean()-Z      tBodyGyroJerk-std()-X      
	tBodyGyroJerk-std()-Y       tBodyGyroJerk-std()-Z       tBodyAccMag-mean()          tBodyAccMag-std()          
	tGravityAccMag-mean()       tGravityAccMag-std()        tBodyAccJerkMag-mean()      tBodyAccJerkMag-std()      
	tBodyGyroMag-mean()         tBodyGyroMag-std()          tBodyGyroJerkMag-mean()     tBodyGyroJerkMag-std()     
	fBodyAcc-mean()-X           fBodyAcc-mean()-Y           fBodyAcc-mean()-Z           fBodyAcc-std()-X           
	fBodyAcc-std()-Y            fBodyAcc-std()-Z            fBodyAccJerk-mean()-X       fBodyAccJerk-mean()-Y      
	fBodyAccJerk-mean()-Z       fBodyAccJerk-std()-X        fBodyAccJerk-std()-Y        fBodyAccJerk-std()-Z       
	fBodyGyro-mean()-X          fBodyGyro-mean()-Y          fBodyGyro-mean()-Z          fBodyGyro-std()-X          
	fBodyGyro-std()-Y           fBodyGyro-std()-Z           fBodyAccMag-mean()          fBodyAccMag-std()          
	fBodyBodyAccJerkMag-mean()  fBodyBodyAccJerkMag-std()   fBodyBodyGyroMag-mean()     fBodyBodyGyroMag-std()     
	fBodyBodyGyroJerkMag-mean() fBodyBodyGyroJerkMag-std() 

The complete list of variables of each feature vector is available in 'features.txt'


---------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------
### Tidy data sets

#### Tiday data set: new variable names

* New variable names were from selected input data variables (see previous section)
* The names were modified mainly to avoid any unnecessary errors in R when this tidy data set 
  is used as an input data during any data analysis in the future. The methods and reasons are 
  based on the instruction from the course video-sildes (Week 4: Editing text variables).
  
  + The following were modified:
    -- lower cases; removed bad characters "()"; replaced "-" to "."

* The activity names are also be modified such as: lower cases; removed "_"
  new activity names: laying, sitting, standing, walking, walkingdownstairs and walkingupstairs.
  
-------------------------------------------------------------------------------------------------------------
#### Tidy data set: data structure

* There are 180 observations of 68 variables.

		'data.frame':	180 obs. of  68 variables:
		 $ activity                 : chr  
		 $ subject                  : int  
		 $ tbodyacc.mean.x          : num 
		 $ tbodyacc.mean.y          : num  
		 $ tbodyacc.mean.z          : num  
		 $ tbodyacc.std.x           : num  
		 $ tbodyacc.std.y           : num 
 		 $ tbodyacc.std.z           : num  
		 $ tgravityacc.mean.x       : num   
		 $ tgravityacc.mean.y       : num  
		 $ tgravityacc.mean.z       : num   
		 $ tgravityacc.std.x        : num  
		 $ tgravityacc.std.y        : num  
		 $ tgravityacc.std.z        : num  
		 $ tbodyaccjerk.mean.x      : num  
		 $ tbodyaccjerk.mean.y      : num 
 		 $ tbodyaccjerk.mean.z      : num  
		 $ tbodyaccjerk.std.x       : num  
		 $ tbodyaccjerk.std.y       : num  
		 $ tbodyaccjerk.std.z       : num  
		 $ tbodygyro.mean.x         : num  
		 $ tbodygyro.mean.y         : num  
		 $ tbodygyro.mean.z         : num  
		 $ tbodygyro.std.x          : num  
		 $ tbodygyro.std.y          : num  
		 $ tbodygyro.std.z          : num  	 
		 $ tbodygyrojerk.mean.x     : num  
		 $ tbodygyrojerk.mean.y     : num  
		 $ tbodygyrojerk.mean.z     : num  
		 $ tbodygyrojerk.std.x      : num  
		 $ tbodygyrojerk.std.y      : num  
		 $ tbodygyrojerk.std.z      : num  
		 $ tbodyaccmag.mean         : num  
		 $ tbodyaccmag.std          : num  
		 $ tgravityaccmag.mean      : num  
		 $ tgravityaccmag.std       : num  
		 $ tbodyaccjerkmag.mean     : num  
 		 $ tbodyaccjerkmag.std      : num  
 		 $ tbodygyromag.mean        : num  
		 $ tbodygyromag.std         : num  
		 $ tbodygyrojerkmag.mean    : num  
		 $ tbodygyrojerkmag.std     : num  
		 $ fbodyacc.mean.x          : num   
		 $ fbodyacc.mean.y          : num  
		 $ fbodyacc.mean.z          : num  
		 $ fbodyacc.std.x           : num  
		 $ fbodyacc.std.y           : num  
		 $ fbodyacc.std.z           : num  
		 $ fbodyaccjerk.mean.x      : num  
		 $ fbodyaccjerk.mean.y      : num  
		 $ fbodyaccjerk.mean.z      : num  
		 $ fbodyaccjerk.std.x       : num  
		 $ fbodyaccjerk.std.y       : num  
 		 $ fbodyaccjerk.std.z       : num  
		 $ fbodygyro.mean.x         : num  
		 $ fbodygyro.mean.y         : num  
		 $ fbodygyro.mean.z         : num  
		 $ fbodygyro.std.x          : num  
		 $ fbodygyro.std.y          : num  
		 $ fbodygyro.std.z          : num  
		 $ fbodyaccmag.mean         : num  
		 $ fbodyaccmag.std          : num  
		 $ fbodybodyaccjerkmag.mean : num  
		 $ fbodybodyaccjerkmag.std  : num  
		 $ fbodybodygyromag.mean    : num  
		 $ fbodybodygyromag.std     : num  
		 $ fbodybodygyrojerkmag.mean: num  
		 $ fbodybodygyrojerkmag.std : num  
 
---------------------------------------------------------------------------------------------

=============================================================================================================







