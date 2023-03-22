# BPMN-experiment
Work-In-Progress

# Actors / Organisational Artefacts
![BPMN Actors](../main/ImageAssets/BPMNActors.png)

# Positive & Negative Outcome Example
Positive Outcome: Vaccinee agrees with the vaccination and gets vaccinated.

Negative Outcome:  Vaccinee strongly requested for an unavailable vaccine and ultimately could not 
be vaccinated.

# List of Triggers and Activities
![BPMN Trigger&Activities1](../main/ImageAssets/BPMNTriggerActivities1.png)
![BPMN Trigger&Activities2](../main/ImageAssets/BPMNTriggerActivities2.png)

# Complex Advanced BPMN Construct Examples
To achieve high semantic and pragmatic quality in the mapping process.

## Event-Driven (Exclusive) XOR Split Gateway
![BPMN Construct1](../main/ImageAssets/BPMNConstruct1.png)
There will be a race between external events. This is denoted below in figure 1 by utilizing an event-driven exclusive (XOR) split gateway. The event-driven exclusive split gateway is shown as a gateway with a pentagon surrounded by a double-line circle. Unlike a data driven XOR gateway, this gateway is always followed by either catching events or receiving tasks. In figure 1, the event-driven exclusive split gateway will only execute when either the timer event or the message event occurs. The gateway execution will follow the path of whichever event that occurs first. A regular execution of figure 1 will see a consent process being provided, followed by the completed forms being received. However, to include the clinic’s closing hours and as well as the identified processes, a timer event for 6pm daily is included. When this timer event occurs, the token in the prior event-driven exclusive split gateway will follow down the path of the timer event. This timer event is followed by asking the vaccinee to complete the form at home and to return tomorrow. A second timer event is set to occur on the next day where the process continues by waiting for the completed forms. 

## Exception Handling Boundary Event
![BPMN Construct2](../main/ImageAssets/BPMNConstruct2.png)
An exception handling boundary event is a type of intermediate event. It is shown on an activity boundary as a catching intermediate event in figure 2. This event can be triggered at any time during the execution of the associated tasks. The exception handling boundary event often deviates from the best-possible-case scenario and is utilized to better model all possible problem causes in the process. In this scenario, the exception stems from the vaccinee and are not part of the process, as such, it is deemed as an unsolicited exception. In figure 2, this event is paired with an end terminate event to immediately end the process instance for the current level and any sub-processes. An exception handling boundary event is first used in figure 2 to model the potential of the vaccinee notifying relevant staff members that they had received a flu vaccine within a fortnight. This is an exception and is often unforeseeable. The process is unable to further proceed, as vaccinee is unable to be vaccinated, this process will be ended with end terminate event. If the exception handling boundary event is not triggered, the process will continue with the best-possible-case scenario where the vaccinee gets vaccinated.  
