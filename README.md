# **GPS Spoofing Detection and Mitigation for Unmanned Aerial Vehicles: Leveraging Machine Learning Methods**-
The proliferation of commercial unmanned aerial vehicles (UAV's) has revolutionized industries like precision agriculture and disaster response. However, their significant reliance on global positioning system (GPS) for navigation exposes them to malicious GPS spoofing attacks. 

GPS spoofing is an attempt to manipulate a GPS receiver by broadcasting manipulated signals. The results of a successful GPS spoofing attack can have extreme consequences with respect to the safety of the mission, equipment, payload, infrastructure and most importantly human lives. 

Various methods have been introduced to detect GPS spoofing; however, most methods require expensive hardware. In this paper we propose machine learning algorithms to detect GPS spoofed signals. In comparison to other proposed algorithms, XGBOOST reveals its superiority in performance using precision, recall and F1-Score as benchmarks; with a precision of 85.41\%, recall of 86.91\% and F1-Score of 86.14\%. Other models, including random forest had a precision performance of 79.60\%, recall performance of 79.80\% and F1-Score of 79.70\%; decision tree classifier had a precision of 84.04\%, recall of 84.53\% and an F1-Score of 84.28\%; and logistic regression had a recall of 25.00\%, recall of 27.21\% and F1-Score of 21.93\%, exhibiting varying degrees of performance. Computational efficiency and scalability are emphasized, ensuring the framework's suitability for resource-constrained UAV deployments. 


# Background and Motivation
Unmanned aerial vehicles (UAVs), also known as drones, are used in a variety of fields of study, including the military, civil defence, border surveillance, traffic management,meteorology, firefighting, agriculture (to spread pesticides in crops), and people-finding, as shown in figure 1. A bird's eye perspective that can be used almost anywhere and at any time is now available to drone users. As a result, the market for UAVs has grown significantly, and it is predicted that it will reach USD 102.38 billion by 2030 (Unmanned Aerial Vehicle (UAV) Drones Market Size 2022-2030. 2022). Furthermore, technical improvements have made it possible to operate small drones with a smartphone rather than remote controllers.

![Applications for Drones](https://github.com/user-attachments/assets/42c716d4-6818-4f94-bea7-aaa617924f00)


# Significance of the Study
As seen in figure 2, spoofing attack carries the greatestweight of all the cybersecurity. Once a spoofing attack is successful, the attacker is command, and the 3 data integrity is breeched. Commercial unmanned aerial vehicles are systems that are under order based on the application of the end user. Their usage is on the rise, but the security is still in question as most of the manufactures never take into consideration the privacy and protection settings.

![PIECHART](https://github.com/user-attachments/assets/6c843542-8a12-4554-a64e-116ac08e994c)


# Archictecture of the Attacks
In order to navigate and control themselves accurately, unmanned aerial vehicles (UAVs) significantly rely on GPS signals. However, spoofing attacks, in which malicious actors trick UAVs with false GPS signals, can disrupt operations and grant unauthorised access to restricted airspace and pose a risk to safety. Commercial UAVs likewise rely on a centralised system, as shown in figures 3 and 4 respectively, making it simple for an attacker to shoot them down.

![Centralized (1)_page-0001](https://github.com/user-attachments/assets/ed381379-4d95-46d5-a9b8-7af2a9f4344c)

![CENTR](https://github.com/user-attachments/assets/9e189064-cb56-4249-85fa-c6fb9c9cafd0)



# System Flow Diagram
The system flow proposesa solution that is accomplished in four stages. In the first phase taking note of the accurate GPS signals of the current location. The latitude and the longitude are set. This is achieved with the GPS receiver in communication with the windows GNSS/GPS simulator started. In the second stage GPS signals are collected with the GPS receiver in communication with other equipments both software and hardware (i.e. (i) the authentic signals have the GPS receiver that does affect the overall output of the signals from the satellites (ii) the spoofed signals have the Hack RF with the GPS receiver mouse. In the third stage, the session of the collected GPS signals from the satellites are then stored in a file. In the fourth stage, the stored file is the pre-processed for analysis in Python. The design and implementation solution provided is a whole movement to track accurate real-time GPS spoofing detected signal. The subsequent subsections discuss the design and implementation of GPS spoofing detection algorithm based on machine learning.

(i). The initial phase involves defining specific satellites, their GPS coordinates, and a height threshold during data acquisition.
(ii). Once signals are detected, they are tracked individually.
(iii). Signals from each Pseudo Random Noise (PRN) are divided into two groups based on measured values: the spoofing group with high correlation and the authentic group with low correlation. Trajectory length is considered during this categorization.
(iv). The authentic group can have an unrestricted number of observable GNSS satellites. Configurations for dataset parameters are adjusted as needed, with careful attention to GPS receiver compatibility and versions. Some signals may be removed if they cannot be received due to their location, potentially limiting the size of the authentic group.
(v). Members of the authentic group are selected to provide the most consistent navigation solution with minimal variance. If a signal from the spoofing group shows weak associations with its peers in that group and offers a more stable navigation solution when swapped with a signal from the authentic group, an exchange is made. This process is illustrated in figure 3 with a flowchart.

![Drawing3 (1)_page-0001](https://github.com/user-attachments/assets/ced2049f-00d0-4678-9297-0408a1a24376)

# Set up
In order to collect data, all the system components must be able to communicate. Figure 4 is the proposed outlook before implementation. The GPS simulator must receive GPS signals from the GPS receiver and transmit the signals which are received to the satellite. The spoofer must receive and sieve out the mixed signals and hence generate them. Figure 4 is the outlook of the real-life implementation with all the system components in communication receiving data from the satellites.

![Drone Spoofing_page-0001](https://github.com/user-attachments/assets/6c516fca-44f0-442d-8a41-aa38614d2622)

# Environment

To improve the accuracy in detecting of real-time GPS spoofing signals of UAVs, this thesis proposes a solution that is accomplished in four stages. In the first phase taking note of the accurate GPS signals of the current location. The latitude and the longitude are set. This is achieved with the GPS receiver in communication with the windows GNSS/GPS simulator started. In the second stage GPS signals are collected with the GPS receiver in communication with other equipment both software and hardware (i.e. (i) the authentic signals have the GPS receiver that does affect the overall output of the signals from the satellites (ii) the spoofed signals have the HackRF with the GPS receiver mouse. In the third stage, the session of the collected GPS signals from the satellites are then stored in a file. In the fourth stage, the stored file is the pre-processed for analysis in Python. The design and implementation solution provided is a whole movement to track accurate real-time GPS spoofing detected signal. The subsequent subsections discuss the design and implementation of GPS spoofing detection algorithm based on machine learning. Figure 5 depicts GPS simulator configuration with parameters set.

![Drawing2 (1)_page-0001](https://github.com/user-attachments/assets/6e78077e-e961-495d-9ba7-c764bf7037bf)

## GPS Simulator Configuration

![GNSS](https://github.com/user-attachments/assets/f40f84c2-2765-418f-aa0c-10f1f7c0ba21)

# Software
In order to achieve a successful GPS spoofing attack, it must be considered that the practical limitations of an attack which is essentially in the tracking phase, the counterfeit signals will not be acquired by the receiver without force reacquisition and inside a building. In order to configure the longitude and latitude, we use the command;
C:\Users\acer\Downloads\Project1>Project1.exe -b 8 -e brdc2140.23n -l 52.633079,-1,139386,88
The fake, structured GPS signals that the GPS spoofer sends out can be decoded by GPS receivers and used to carry out its operations. The HackRF and the GPS receiver need to be connected to the Windows computer before using the command;
C:\ProgramFiles\PothosSDR\bin>hackrf_transfer.exe -t gpssim.bin -f 1575420000 -s 2600000 -a 1 -x 0 
on the command line. The USB connectivity for the GPS receiver (COMM 9600) is read.
C:\Users\acer\Downloads\Project1>Project1.exe -b 8 -e brdc2140.23n -l 52.633079,-1,139386,88

C:\Program Files\PothosSDR\bin>hackrf_transfer.exe -t gpssim.bin -f 1575420000 -s2600000 -a 1 -x 0

![GPS](https://github.com/user-attachments/assets/03c2a757-fe37-40eb-b9aa-65d30d2cdb22)

# Machine Learning Algorithm Selection Models
Converting Signals
After the data is collected there is need to process it through a GPS simulator. Both directed and delayed mixed signal generators are converted with IF Down conversion. The aim for this process is to check if the so to be deployment machine learning model can classify the signals if mixed. The delayed signals are time stamp generated and the conversion is the change in distance.


When the parameters are set, the machine learning algorithm has to be able to distinguish the signals. Signal and measurement processing begins which parameters are parsed onto for feature extraction. The machine learning algorithm should be the spoofing detector in the signals during the online phase. The spoofed signals are all generated with the HackRF which acts as a Software Defined Radio (SDR). During the offline phase, the machine learning algorithm must perform adjustments in weight specifications in order to train the model.




