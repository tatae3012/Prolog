# Fuzzy Inference System

## Overview

Implementation of FIS (Fuzzy Inference System) using METLAB fuzzy logic toolbox and evaluating the performance of a student. The goal is to find the overall performance of the student. The evaluation criteria are based on the following three input parameters. The output of the system is the performance score of a given student in range [0, 10].  
 
Inputs: 
	a. Academics: Performance in academics are measured by CGPA (scale 0-10)<br/>  
	b. Sports: Total number of games won or participated (scale 0-10)<br/> 
	c. Co-curricular activities: the number of certificates (participation and winning certificate in the range of 0 to 10).<br/>   
 
## Implementation  

1. ACADEMICS: Define and fuzzy membership function 
	  
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/1.png"></td>
    </tr>
  </table>
  
Academics is distributed in three ranges ie, poor, average and good. If cgpa is less than 4, it comes in poor category. The average ranges between 3 and 8 where the plot is stable for 5 to 7.  Finally, 8 above is considered to be in good category. 

	  
2. SPORTS: Define and fuzzy membership function 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/2.png"></td>
    </tr>
  </table>
  
Sports is distributed in three ranges ie, poor, average and good. If number of games won is less than 2, it comes in poor category. The average ranges between 1 and 5. Finally, 5 above is considered to be in good category. Here, we have started the good range early because even these values are considered good in the field of sports.

3. CO-CURRICULUM: Define and fuzzy membership function 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/3.png"></td>
    </tr>
  </table>
  
Co-curriculum is distributed in 3 ranges ie, poor, average and good. If number of certificates is less than 2, it comes in poor category. The average ranges between 1 and 6. The plot is stable for most of this range Finally, 4 above is considered to be in good category. The performance keeps on increasing after that.
   
4. PERFORMANCE: Define and fuzzy membership function 
 
  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Fuzzy%20Inference%20System/4.png"></td>
    </tr>
  </table>
  
Performance is distributed in three ranges ie, poor, average and good. If the cumulative performance is less than 3, it comes in poor category. The average ranges between 2 and 8 with the peak in the mid value. Finally, 8 above is considered to be in good category. 

 

•	Define Fuzzy rule base that seems to be suitable for the given system.  	 

Based on the nature of FIS input and output variables used and general logical sense, we have defined a rule base that suits best for our student performance model.

RULE BASE: 
1.	If (academics is good) then (performance is good) (1)  
2.	If (academics is average) and (sports is good) and (co-curricular is good) then (performance is good) (1)  
3.	If (academics is average) and (sports is good) and (co-curricular is not good) then (performance is good) (1)  
4.	If (academics is average) and (sports is not good) and (co-curricular is good) then (performance is good) (1)  
5.	If (academics is average) and (sports is average) and (co-curricular is average) then (performance is average) (1)  
6.	If (academics is average) and (sports is poor) and (co-curricular is poor) then (performance is poor) (1)  
7.	If (academics is average) and (sports is average) and (co-curricular is poor) then (performance is average) (1)  
8.	If (academics is average) and (sports is poor) and (co-curricular is average) then (performance is average) (1)  
9.	If (academics is poor) and (sports is good) and (co-curricular is good) then (performance is average) (1)  
10.	If (academics is poor) and (sports is not good) and (co-curricular is not good) then (performance is poor) (1)  
  
 
 
•	Develop FIS to compute performance of the student 	 
 
TEST CASES: 
   
 
 
 
 
 
  

The inputs are given to the system and based on the plots and rules, first fuzzification and after that defuzzification takes place. We have used centroid defuzzification logic, since we have 3 inputs- the centroid is the optimal point.