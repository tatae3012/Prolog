# Frame Based System

## Overview

A prototype of Frame Based System (FBS) for University application.
 
### Network of Frames 

  <table>
    <tr>
     <td><img src="https://github.com/tatae3012/Prolog/blob/master/Frame%20Based%20System/1.png"></td>
    </tr>
  </table>
  
### How to Use

The frames provided in fbs.fis file can be used to:

a. Add a new frame =  add(Frame,Attributes) :- frame(Frame,Attributes),write(frame(Frame,Attributes)),write('already exists'),!.
                      add(Frame,Attributes) :- asserta(frame(Frame,Attributes)),write('Frame is added')
                                                  
b. Delete a frame  =  delete(Frame) :- retract(frame(Frame,_)).
                      delete(Frame) :- error(['No frame ', Frame, ' to delete']).                                          

* c. Query a frame   =  query(Frame,Slot,Value) :- frame(Frame,Slots),member(Slot-Value,Slots).
                      * query(Frame,Slot,Value) :- frame(Frame,Slots),member(is_aClass,Slots),query(Class,Slot,Value).
                      * query(Frame,Slot,Value) :- frame(Frame,Slots),member(a_part_ofClass,Slots),query(Class,Slot,Value).
                      * query(Frame,Slot,Value) :- frame(Frame,Slots),member(akoParent,Slots),query(Parent,Slot,Value).
