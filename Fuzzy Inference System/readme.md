# Fuzzy Inference System

## Overview

Implementation of FIS (Fuzzy Inference System) using METLAB fuzzy logic toolbox and evaluating the performance of a student. The goal is to find the overall performance of the student. The evaluation criteria are based on the following three input parameters. The output of the system is the performance score of a given student in range [0, 10].  
 
Inputs: 
	a. Academics: Performance in academics are measured by CGPA (scale 0-10)<br/>  
	b. Sports: Total number of games won or participated (scale 0-10)<br/> 
	c. Co-curricular activities: the number of certificates (participation and winning certificate in the range of 0 to 10).<br/>   
 
## Implementation  

### Defining Membership Functions

1. ACADEMICS: Define and fuzzy membership function 
	  
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/1.jpg"></td>
    </tr>
  </table>
  
Academics is distributed in three ranges ie, poor, average and good. If cgpa is less than 4, it comes in poor category. The average ranges between 3 and 8 where the plot is stable for 5 to 7.  Finally, 8 above is considered to be in good category. 

  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/2.jpg"></td>
    </tr>
  </table>
	  
2. SPORTS: Define and fuzzy membership function 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/3.jpg"></td>
    </tr>
  </table>
  
Sports is distributed in three ranges ie, poor, average and good. If number of games won is less than 2, it comes in poor category. The average ranges between 1 and 5. Finally, 5 above is considered to be in good category. Here, we have started the good range early because even these values are considered good in the field of sports.

  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/4.jpg"></td>
    </tr>
  </table> 
  
3. CO-CURRICULUM: Define and fuzzy membership function 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/5.jpg"></td>
    </tr>
  </table>
  
Co-curriculum is distributed in 3 ranges ie, poor, average and good. If number of certificates is less than 2, it comes in poor category. The average ranges between 1 and 6. The plot is stable for most of this range Finally, 4 above is considered to be in good category. The performance keeps on increasing after that.
   
   <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/6.jpg"></td>
    </tr>
  </table>

4. PERFORMANCE: Define and fuzzy membership function 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/7.jpg"></td>
    </tr>
  </table>
  
Performance is distributed in three ranges ie, poor, average and good. If the cumulative performance is less than 3, it comes in poor category. The average ranges between 2 and 8 with the peak in the mid value. Finally, 8 above is considered to be in good category. 

  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/8.jpg"></td>
    </tr>
  </table>
 
### Defining Fuzzy Rule Based System
  
Based on the nature of FIS input and output variables used and general logical sense, a rule base is defined that suits best for our student performance model.
<pre>
RULE BASE: 
	1. If (academics is good) then (performance is good) 
	2. If (academics is average) and (sports is good) and (co-curricular is good) then (performance is good) 
	3. If (academics is average) and (sports is good) and (co-curricular is not good) then (performance is good) 
	4. If (academics is average) and (sports is not good) and (co-curricular is good) then (performance is good) 
	5. If (academics is average) and (sports is average) and (co-curricular is average) then (performance is average) 
	6. If (academics is average) and (sports is poor) and (co-curricular is poor) then (performance is poor) 
	7. If (academics is average) and (sports is average) and (co-curricular is poor) then (performance is average) 
	8. If (academics is average) and (sports is poor) and (co-curricular is average) then (performance is average) 
	9. If (academics is poor) and (sports is good) and (co-curricular is good) then (performance is average)  
	10. If (academics is poor) and (sports is not good) and (co-curricular is not good) then (performance is poor) 

  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/9.jpg"></td>
    </tr>
  </table>
</pre>  
 
### Results

The following results are obtained on developing FIS to compute performance of the student. 	 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/10.jpg"></td>
    </tr>
  </table>
   
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/11.jpg"></td>
    </tr>
  </table> 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/12.jpg"></td>
    </tr>
  </table> 
 
   <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/ScreenShots/13.jpg"></td>
    </tr>
  </table>
  
The inputs are given to the system and based on the plots and rules, first fuzzification and after that defuzzification takes place. Centroid defuzzification logic is used, since we have 3 inputs thus, centroid is the optimal point.
