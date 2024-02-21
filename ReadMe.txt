Title: Capacitive Sensing for Natural Environment Biomechanics Monitoring
Primary Admin: Owen Pearl
URL: https://simtk.org/projects/csdataset

Overview: This capacitive sensing dataset comprises data from two different studies with capacitive sensing (organized in the two subsequent folders).

-------------------------------------------------------------------------------------------------------------------------------------------------------

ShankOnlyExperiments: 

Short Description: Capacitive sensing measurements of muscle bulging at the shank from 20 subjects time-synchronized with electromyography and simulated muscle forces using optical motion capture and an instrumented treadmill 

Long Description: The first dataset of its kind to include time-synchronized measurements of (1) muscle bulging acquired via a wearable, low-cost lower limb capacitive sensing sleeve at the shank, (2) neural excitation measurements from electromyography, and (3) inferred muscle moments from static optimization performed in OpenSim with optical motion capture and instrumented treadmill data. 20 participants were recorded walking normally and with a 5-degree toe-in foot progression angle, a therapeutic modification used to mitigate progression of knee osteoarthritis. Measurements for CS and EMG were taken both inside a traditional motion capture laboratory environment and outside in natural environments.

~~ EXPLANATION ~~

-------------
MetaData.xlsx

Includes meta data on the subjects participating in both the indoor/outdoor and 
baseline/toe-in trials. The meta data file includes age, height, mass, sex, dominant leg, 
leg length, and preferred walking speed.

---------------------
IndoorWalkingData.mat

Contains a struct with time synchronized GRF data, body kinematics, dynamics, CS profile, 
neural excitation from EMG, and simulated muscle moment from static optimization.

Order of Data (IndoorWalkingData.dataLabels) and units
GRF Data (N, m, Nm)
Kinematics (deg)
Dynamics (% BodyWeight * Height)
CS Profile
EMG Signals
Simulated Muscle Force (N)

IndoorWalkingData = 

  struct with fields:

          numSubjects: 17
             numSteps: 15
    numSamplesPerStep: 100
        percentStance: [1×100 double]
           dataLabels: {1×64 cell}
            Subject01: [1×1 struct]
            Subject02: [1×1 struct]
            Subject03: [1×1 struct]
            Subject04: [1×1 struct]
            Subject05: [1×1 struct]
            Subject06: [1×1 struct]
            Subject07: [1×1 struct]
            Subject08: [1×1 struct]
            Subject09: [1×1 struct]
            Subject10: [1×1 struct]
            Subject11: [1×1 struct]
            Subject12: [1×1 struct]
            Subject13: [1×1 struct]
            Subject14: [1×1 struct]
            Subject15: [1×1 struct]
            Subject16: [1×1 struct]
            Subject17: [1×1 struct]


----------------------
OutdoorWalkingData.mat

Contains a struct with CS, EMG, and FPA data for 15 baseline and toe-in steps for comparing 
the ability to capture minor gait difference with CS and EMG.

OutdoorWalkingData = 

  struct with fields:

          numSubjects: 7
             numSteps: 15
    numSamplesPerStep: 100
          percentGait: [1×100 double]
            Subject01: [1×1 struct]
            Subject02: [1×1 struct]
            Subject10: [1×1 struct]
            Subject17: [1×1 struct]
            Subject18: [1×1 struct]
            Subject19: [1×1 struct]
            Subject20: [1×1 struct]

Subject01 =
	
   struct with fields:

      Baseline: [1×1 struct]
         ToeIn: [1×1 struct]
    Difference: [1×1 struct]
	
-------------------------------------------------------------------------------------------------------------------------------------------------------

ShankAndThighExperiments: 

Short Description: Capacitive sensing measurements of muscle bulging at both the shank and thigh for 11 subjects with mocap data, IMU data, EMG data, and MRI results.

Long Description: The first dataset of its kind to include measurements of (1) muscle bulging acquired via wearable lower limb capacitive sensing sleeves located at both the shank and thigh of both legs, (2) neural excitation measurements from electromyography, (3) optical motion capture and instrumented treadmill data, (4) XSens inertial measurement unit data, and (5) magnetic resonance imaging (MRI) body composition scan results. 10 healthy participants were recorded walking normally and with a mock impaired stiff-knee gait, along with 1 total knee arthroplasty patient. Measurements for CS, IMUs, and mocap were taking simultaneously, as well as measurements of EMG, IMUs, and mocap inside of the lab on an instrumented treadmill. The provided dataset enables the comparison of CS data with any biomarker of interest in a consistent OpenSim/MATLAB ready formatting.

~~ EXPLANATION ~~

-------------
MetaData.xlsx

Includes meta data on the participants. The meta data file includes age, height, 
mass, sex, dominant leg, leg length, and preferred walking speed.

----------------------
WalkingData.mat

Contains a struct with all data organized and labeled. This data is roughly segmented to the start and ends of the trials, however the IMU data, CS data, and EMG data are not perfectly time-synced to the mocap and GRF data (which are both spatially and time synced together). To time sync the wearables data, use the IMUs (IMUs are also onboard both the CS and EMG sensors) and compare with the GRF data for precise time syncing and alignment.

WalkingData.(SubID).(Trial)

ans = 

  struct with fields:

        SubjectInfo: [1×1 struct] - struct with the meta data for each subject
         MarkerData: [1×1 struct] - Markers measured with optical motion capture system (spatially synced, and time synced with GRF data)
          ForceData: [1×1 struct] - Ground reaction forces as measured by the force plates in the global coordinate system (synced with motion capture data)
          AccelData: [1×1 struct] - Accelerations measured from IMUs (time synced within IMU data)
           GyroData: [1×1 struct] - Angular velocities measured from IMUs (time synced within IMU data)
         MagnetData: [1×1 struct] - Magnetometer readings from XSens IMUs (time synced within IMU data)
    OrientationData: [1×1 struct] - Orientations (quaternions) from XSens's built in 9-DOF sensor-fusion filter (time synced within IMU data)
	
			- AND - 
	
            LCSData: [1×1 struct] - Left shank and thigh CS data
            RCSData: [1×1 struct] - Right shank and thigh CS data
			
			- OR - 
			
			EMGData: [1x1 struct] - Full body EMG data from both legs

--------------------
MRI Results (folder)

SIDMRIData.csv (file) A delimited report of each participants muscle composition MRI measurements
SIDMRIFiberLength.csv (file)  A delimited report of the resting muscle fiber lengths of each participant as measured with MRI
	