# 2305 18371V1

**Source Document:** `2305.18371v1.pdf`  
**Total Pages:** 6  

---

## --- Page 1 ---

### Section: Introduction

This article has been accepted for publication in the proceedings of the
2023 IEEE International Workshop on Advances in Sensors and Interfaces (IWASI).

ColibriUAV: An Ultra-Fast, Energy-Efficient
Neuromorphic Edge Processing UAV-Platform with

Event-Based and Frame-Based Cameras

Sizhen Bian∗, Lukas Schulthess∗, Georg Rutishauser∗, Alfio Di Mauro∗, Luca Benini∗†, Michele Magno∗

∗Departement Informationstechnologie und Elektrotechnik, ETH Z¨urich, Switzerland
†Dipartimento di Ingegneria dell’Energia Elettrica e dell’Informazione, Universit`a di Bologna, Bologna, Italy

Abstract—The
interest
in
dynamic
vision
sensor
(DVS)-
powered unmanned aerial vehicles (UAV) is raising, especially due
to the microsecond-level reaction time of the bio-inspired event
sensor, which increases robustness and reduces latency of the
perception tasks compared to a RGB camera. This work presents
ColibriUAV, a UAV platform with both frame-based and event-
based cameras interfaces for efficient perception and near-sensor
processing. The proposed platform is designed around Kraken,
a novel low-power RISC-V System on Chip with two hardware
accelerators targeting spiking neural networks and deep ternary
neural networks.Kraken is capable of efficiently processing both
event data from a DVS camera and frame data from an RGB
camera. A key feature of Kraken is its integrated, dedicated
interface with a DVS camera. This paper benchmarks the end-
to-end latency and power efficiency of the neuromorphic and
event-based UAV subsystem, demonstrating state-of-the-art event
data with a throughput of 7200 frames of events per second and
a power consumption of 10.7 mW, which is over 6.6 times faster
and a hundred times less power-consuming than the widely-used
data reading approach through the USB interface. The overall
sensing and processing power consumption is below 50 mW,
achieving latency in the milliseconds range, making the platform
suitable for low-latency autonomous nano-drones as well.

Index Terms—Event camera, event interface, autonomous
drone, on-the-edge computing, autonomous navigation

#### I. INTRODUCTION

The autonomous navigation of agile UAVs requires fast
response times from environment perception to motor instruc-
tions, as well as high energy efficiency to handle complex
computing tasks. In recent years, various sensing modalities
have been explored for reliable autonomous decision-making,
including UWB [1], Time-of-Flight (ToF) sensors [2], and
radar [3]. However, the most popular sensing approach for
local positioning and obstacle avoidance of drones is still
vision sensors such as RGB cameras, which provide richer
contextual information and unlock more functionalities of
UAVs than other sensing modalities [2].

Despite the advantages of vision sensors, the volume of
streamed vision data is large and challenges the memory
footprint of limited hardware resources of a miniaturized UAV
during data processing. Researchers have thus struggled to
compress image-processing models to fit onboard for fast and
energy-efficient data processing [4], [5].

This work was supported by the Innosuisse project Eye-Tracking 103.364
IP-ICT with Agreement Number: 2155011780, and the Innovation Programme
APROVIS3D under the Grant 20CH21 186991.

Event-based cameras, also called dynamic vision sensors,
show promise for improving energy efficiency and latency in
robotic applications [6]. By exploiting the bio-inspired princi-
ple of sparse event train where an event is only generated when
a pixel’s brightness changes, the event camera generates much
less redundant data, which is attractive for a resource-limited
edge platform. The microsecond level of temporal resolution
and sparsity of the output enables faster motion capturing
without introducing motion blur [7]. Moreover, pixels have a
logarithmic response to the brightness signal, which allows the
event camera a very high dynamic range, being able to see dark
and bright regions simultaneously [8]. The output of a DVS
is based on a threshold mechanism: each pixel will memorize
the logarithm of the brightness when an event is triggered and
continuously monitor the brightness change respective to the
memorized value. When the difference crosses the thresholds,
the next event is triggered, and the stored brightness value
is updated [9]. The transmitted events consist of the pixel’s
location, the timestamp, and the polarity of the change, where
the increase of brightness is represented with an ON event and
the decrease with an OFF event.

Today’s event-based cameras are still characterized by high
power consumption due to their IO interface, in contrast to the
low power consumption of the sensors [10]. This is especially
due to the non-standard communication protocol they adopt.
Today’s DVS cameras connect with external chips through a
USB interface, reducing the benefits of energy efficiency and
latency in real end-to-end application scenarios [11], [12].

However, USB DVS cameras are already used to collect
datasets and in UAV applications, often coupled with GPUs
[13]. Nevertheless, considering the particularity of the event
data format in the spatial and temporal domains, to fully lever-
age the benefits of the bio-inspired event-based paradigm, new
models and algorithms are needed to extract typical features
from the asynchronous and high-temporal resolution event
streams in the spatial and temporal domains. Additionally,
efficient neuromorphic platforms are required to handle the
event streams from the DVS and enable the realization of the
paradigm’s performance potential [14].

One approach to processing event data is the spiking neural
network (SNN) [19], [20], which closely mimics the natural
neural network, transmitting information only when the mem-
brane potential of the neuron reaches the specific threshold.

© 2023 IEEE. Personal use of this material is permitted. Permission from IEEE must be obtained for all other uses, in any current or
future media, including reprinting/republishing this material for advertising or promotional purposes, creating new collective works, for

resale or redistribution to servers or lists, or reuse of any copyrighted component of this work in other works.

arXiv:2305.18371v1  [cs.CV]  27 May 2023


## --- Page 2 ---

TABLE I
DRONES EQUIPPED WITH DYNAMIC VISION SENSORS (DVS)

Computing
Unit

Event
Camera

interface
Algorithm
Pinf (mW) a
Tinf
(ms) a
Tsamp
(ms) b
Tclose loop
(ms) c
Pclose loop
(mW) c

[11]-2020
NVIDIA Jet-
son TX2

two
SEES1

USB2.0
Ego-motion
compensa-
tion

1000+
(Watt
level)

3.56
10
N/A d
1000+
(Watt
level)

[15]-2022
NVIDIA Jet-
son TX2

DAVIS2404
USB2.0
Sparse Gated
Recurrent
Network

1000+
(Watt
level)

500
≈
1000-
2000
N/A
1000+
(Watt
level)

[12]-2015
Odroid
U3
quad-core
computer

two
DVS128

USB2.0
event-
based
circle
tracker, EKF

1000+
(Watt
level)

4.5
N/A
N/A
1000+
(Watt
level)

[16]-2020
UP Board
DAVIS
240C
USB2.0
hough
transform,
kalman filter

1000+
(Watt
level)

12
3
N/A
1000+
(Watt
level)

[17]-2021
Loihi, Kapo-
hoBay

DAVIS
240C
SAER e
Hough trans-
form

1000+
(Watt
level)

0.25
0.15
N/A
1000+
(Watt
level)
[18]-2022
Intel
NUC
computer

two
DAVIS346

USB3.0
graph-based
optimization

1000+
(Watt
level)

N/A
N/A
N/A
1000+
(Watt
level)
Ours
Kraken
DAV132S
SAER
SNN
35.6f
163
(131+32)f
300
163
(131+32)h
46.98 (35.6 +
11.076 + 0.3)f

a Pinf, Tinf: Processing unit power/latency during inference of each instance. The power includes both idle state power and active state power.
b Tsamp: The window of each instance, includes both data collection and preprocessing.
c Latency and power consumption from event perceiving to motor command giving.
d Not available.
e Synchronous address event representation interface.
f Inference time and power including the preprocessing on the fabric controller, close loop time and power including the DVS camera and the interfaces.
See Table III for details.

Then the neuron fires, generating a spike that is propagated
to other neurons. SNNs preserve the temporal context in the
spike train and attempt to exploit the salient information from
spike numbers or rates in a certain window. Because of their
non-differentiability, the backpropagation mechanism cannot
be directly applied to training SNNs. Thus, surrogate gradients
were explored for learning SNNs’ synaptic weight and axonal
delay parameters, like SLAYER [21] or STBP [22]. These
approaches take much time for training but make full use of
the temporal resolution of the data, achieving promising results
in accuracy and latency [23], [24].

On the hardware side, over the years, different computing
platforms have been used for interpreting the event data
input, including traditional digital processors such as Nvidia
Jetson [11] and a new generation of neuromorphic processors,
designed in both academia and industry, and examples are
TrueNorth [25] from IBM, Loihi [26] and its platform Kapoo
bay [17] from Intel, and DYNAP-SE [27] from ETH Z¨urich.
Neuromorphic platforms are designed to use artificial neurons
to do computations and have the potential to push the envelope
of energy efficiency and execution speed [26]. However, these
neuromorphic chips support general SNN processing and are
not necessarily optimized for edge event data processing
in a seamless neuromorphic path from event perception to
decision-making.

In 2022, researchers from ETH Z¨urich published an embed-
ded heterogeneous system on chip (SoC) RISC-V based, called
Kraken [28], which integrates a neuromorphic accelerator,
sparse neural engine (SNE) [29], aiming to accelerate SNN
inference tasks at the extreme edge efficiently. Kraken is
designed to optimize energy efficiency and low latency, and it

embeds two on-chip camera interfaces: one for shutter-based
cameras and another for event-based cameras, linking a ternary
deep neural network on frame-form data and a spiking neural
network for event-form data. The Kraken platform enables
seamless neuromorphic processing of event data from percep-
tion to decision-making at the extreme edge, and it represents a
significant step towards the practical implementation of end-to-
end energy-efficient, bio-inspired event-based vision systems.

This work presents the design and development of Colibri-
UAV, which is the first energy-efficient drone platform based
on the Kraken SoC. The platform includes both an event-based
camera and an RGB camera to evaluate end-to-end latency,
power, and energy efficiency. The main goal of the paper is to
provide an experimental platform that exploits an event-based
camera and neuromorphic accelerator for future UAV-related
tasks and eventually create agile UAV systems with increased
robustness under aggressive and jerky maneuvers.

The main contributions of this paper are as follows:

• The design and implementation of ColibriUAV, the first
neuromorphic deep learning edge platform in the form
of a drone. It includes a low-power event camera and
a low-power heterogeneous SoC that integrates a sparse
neuron engine for event train processing. The platform
also preserves the frame camera interface for future
evaluation.

• Profiling and evaluating the latency and energy of the
event-based subsystem. With experimental results, the pa-
per shows that ColibriUAV achieves the state-of-art event
data reading interface with 7200 event-frames per second
throughput and 10.7 milliwatt power consumption, which
is over 6.6 times faster and a hundred times less power


## --- Page 3 ---

### Section: Related work

than the widely used data reading approach through a
USB interface.

• Benchmarking the close-loop neuromorphic performance
of ColibriUAV using a reference neural network featuring
a latency of 163 ms, power of 46.98 mW, and energy
consumption of 9.224 mJ for the end-to-end task from
events to motor control.

#### II. RELATED WORK

In recent years, research on low-latency event camera-
embedded drones has rapidly grown, as summarized in Table I.
Falanga et al. [11] utilized two SEES1 event cameras on a
quadrotor and leveraged the temporal information contained
in the event stream to distinguish between static and dynamic
objects, with the aim of avoiding approaching obstacles with
fast response times. They reported an overall latency of only
3.5 milliseconds, which is sufficient for reliable detection
and avoidance of fast-moving obstacles. Andersen et al. [15]
proposed sparse convolutions for detecting gates in a race track
using event-based vision, and achieved success rates between
0.2 to 1.0 for gate detection with different angular rates and
scene illumination levels. Mueggler et al. [12] proposed a
method that tracks spherical objects on the image plane using
probabilistic trackers that are updated with each incoming
event. They experimentally demonstrated that the method
enables initiating evasive maneuvers early enough to avoid
collisions. Dimitrova et al. [16] explored one-dimensional
attitude tracking using a dualcopter platform equipped with
an event camera and reported promising results of the event-
camera-driven closed-loop control. The state estimator per-
forms with an update rate of 1 kHz and a latency of 12
milliseconds. The first work of a neuromorphic vision-based
controller on a chip, solving a high-speed UAV control task,
is shown in [17], where the DVS events are used as inputs to
the neuronal cores of a neuromorphic chip using an address
event representation interface and processed directly by the
SNN. The proposed visual processing, from incoming events
to estimated angle, on Loihi takes only 0.25 milliseconds. The
first event-based stereo visual-inertial odometry is described in
[18], which leverages the complementary advantages of event
streams, standard images, and inertial measurements for robust
state estimation. The method was successfully validated on a
quadrotor platform under low-light environments.

Although different focuses have been put into the combina-
tion of drones and event cameras, none of the existing works
emphasize the performance increase in latency and power that
neuromorphic form sensing and computing can bring. They
mainly deployed the algorithms on more general platforms like
GPUs or small-form computers, which heavily increase the
load of a drone and limit its agility. For example, KapohoBay,
used in [17], shows impressive inference speed benefiting
from the onboard spike processing. However, the KapohoBay
platform consumes hundreds of milliwatts of power even in
idle state, thus not suitable for practical deployment on drones.

This paper presents the design and development of a mil-
liwatt drone that features a System on Chip (SoC) with dual

Fig. 1.
System architecture: ColibriUAV with Dual Camera and Kraken
Development Board.

Fig. 2. Recordings at one particular event frame of the DVS132S (left) and
an RGB camera (right): a scene with two bins.

camera interface and two hardware accelerators. In addition, it
includes an 8-core RISC-V parallel processor for other tasks
and embedded control.

#### III. SYSTEM ARCHITECTURE

In this section we detail the design and implementation
of ColibriUAV, an end-to-end edge vision UAV system that
includes both perception, computing, and actuation, as shown
in Figure 1. The platform can connect both the event camera
and the frame camera directly to the Kraken SOC through
an interface. In this section, we describe the core components
used for the proposed ColibriUAV. The platform is built upon
the commercially available drone frame Outlaw 270 racer,
which uses four powerful motors of type RSII 2306 2400KV
from Emax with a maximum thrust of 1720 g.

The onboard flight controller F722-SE from Matek, together
with the brushless electronic speed controller Xrotor Micro
40A from Hobbywing, implements the basic control func-
tionalities. A 4S LiPo battery pack of type Nano-tech with
a capacity of 4500 mA h provides the energy for autonomous
operation.

Although ColibriUAV can host both an RGB camera and
an event-based camera, this paper focuses on the event-based
camera to evaluate its latency and energy-efficiency.

#### IV. DESIGN AND IMPLEMENTATION

A. ColibriUAV Platform

ColibriUAV is designed around Kraken to exploit the data
from event and frame cameras, process the information, and
supply controlling information to the UAV pilot. It is designed
to fit on the drone’s frame while providing full flexibility
and adaptability for even smaller nano drones.The SAER


![In recent years, research on low-latency event camera- embedded drones has rapidly grown, as summarized in Table I. Falanga et al. [11] utilized two SEES1 event cameras on a quadrotor and leveraged the temporal information contained in the event stream to distinguish between static and dynamic objects, with the aim of avoiding approaching obstacles with fast response times. They reported an overall latency of only 3.5 milliseconds, which is sufficient for reliable detection and avoidance of fast-moving obstacles. Andersen et al. [15] proposed sparse convolutions for detecting gates in a race track using event-based vision, and achieved success rates between 0.2 to 1.0 for gate detection with different angular rates and scene illumination levels. Mueggler et al. [12] proposed a method that tracks spherical objects on the image plane using probabilistic trackers that are updated with each incoming event. They experimentally demonstrated that the method enables initiating evasive maneuvers early enough to avoid collisions. Dimitrova et al. [16] explored one-dimensional attitude tracking using a dualcopter platform equipped with an event camera and reported promising results of the event- camera-driven closed-loop control. The state estimator per- forms with an update rate of 1 kHz and a latency of 12 milliseconds. The first work of a neuromorphic vision-based controller on a chip, solving a high-speed UAV control task, is shown in [17], where the DVS events are used as inputs to the neuronal cores of a neuromorphic chip using an address event representation interface and processed directly by the SNN. The proposed visual processing, from incoming events to estimated angle, on Loihi takes only 0.25 milliseconds. The first event-based stereo visual-inertial odometry is described in [18], which leverages the complementary advantages of event streams, standard images, and inertial measurements for robust state estimation. The method was successfully validated on a quadrotor platform under low-light environments. | Fig. 1. System architecture: ColibriUAV with Dual Camera and Kraken Development Board.](images/page_003_fig_01.png)
*Caption/Context: In recent years, research on low-latency event camera- embedded drones has rapidly grown, as summarized in Table I. Falanga et al. [11] utilized two SEES1 event cameras on a quadrotor and leveraged the temporal information contained in the event stream to distinguish between static and dynamic objects, with the aim of avoiding approaching obstacles with fast response times. They reported an overall latency of only 3.5 milliseconds, which is sufficient for reliable detection and avoidance of fast-moving obstacles. Andersen et al. [15] proposed sparse convolutions for detecting gates in a race track using event-based vision, and achieved success rates between 0.2 to 1.0 for gate detection with different angular rates and scene illumination levels. Mueggler et al. [12] proposed a method that tracks spherical objects on the image plane using probabilistic trackers that are updated with each incoming event. They experimentally demonstrated that the method enables initiating evasive maneuvers early enough to avoid collisions. Dimitrova et al. [16] explored one-dimensional attitude tracking using a dualcopter platform equipped with an event camera and reported promising results of the event- camera-driven closed-loop control. The state estimator per- forms with an update rate of 1 kHz and a latency of 12 milliseconds. The first work of a neuromorphic vision-based controller on a chip, solving a high-speed UAV control task, is shown in [17], where the DVS events are used as inputs to the neuronal cores of a neuromorphic chip using an address event representation interface and processed directly by the SNN. The proposed visual processing, from incoming events to estimated angle, on Loihi takes only 0.25 milliseconds. The first event-based stereo visual-inertial odometry is described in [18], which leverages the complementary advantages of event streams, standard images, and inertial measurements for robust state estimation. The method was successfully validated on a quadrotor platform under low-light environments. | Fig. 1. System architecture: ColibriUAV with Dual Camera and Kraken Development Board.*


![• Benchmarking the close-loop neuromorphic performance of ColibriUAV using a reference neural network featuring a latency of 163 ms, power of 46.98 mW, and energy consumption of 9.224 mJ for the end-to-end task from events to motor control. | II. RELATED WORK](images/page_003_fig_02.png)
*Caption/Context: • Benchmarking the close-loop neuromorphic performance of ColibriUAV using a reference neural network featuring a latency of 163 ms, power of 46.98 mW, and energy consumption of 9.224 mJ for the end-to-end task from events to motor control. | II. RELATED WORK*


## --- Page 4 ---

### Section: Event-based Camera

interface is supported by an 80-pin board-to-board connector
for data transfer with the DVS132S camera. Besides this, a
CPI camera connector is also available for frame-based vision
data receiving. Power of different domains of the Kraken chip,
including the always-on fabric controller, power-switchable
cluster, and independent power-switchable accelerators (SNE
and CUTIE), is supplied by individual buck converters.

B. Event-based Camera

For the design, we selected the event camera DVS132S
from iniVation AG, for its low power and real-time high-speed
[30]. It features a resolution of 132x104 with 10 µm pixel side
length on a 65 nm process and a synchronous address-event
representation (SAER) readout capable of 180 Meps (million
events per second) throughput. The power efficiency, com-
pared to prior versions [31], [32], has been mainly achieved
by changing to a lower supply voltage of 1.2 V. For example,
the chip consumes only 250 µW with 100 Keps running at
1 K event frames per second. With on-chip digital circuitry,
the whole pixel array can be read synchronously, producing
event frames when a SAMPLE request occurs. The event frame
is transferred into the pixel memory and then streamed out
following the X\Y scan clock. The event frame rate is thus
dependent on the SAMPLE request frequency.

The ON/OFF event of each pixel is generated depending on
whether the changed luminosity of this pixel is larger than the
pre-configured threshold. Both the number of possible events
in each frame (from 0 to 13728) and the sample rate influence
the power consumption of the chip. The events are streamed
through the SAER port, which also supports pre-readout pixel-
parallel noise and spatial redundancy suppression, aiming to
eliminate the redundant events caused mainly by flicker. It
is worth noting that there are two simultaneous streams of
output data: the X/Y address with one byte and the ON/OFF
events with one byte recording the events of four pixels (2x2).
Thus, to stream out all events, 13728 events in one frame, only
3432 (66x52) system clocks for one frame are needed (when
not considering the sparse auxiliary clocks). Figure 2 shows
an event-frame reading of the DVS132S at a single time step
while in motion. The red dots represent the ON events, while
the green dots represent the OFF events.

C. Kraken SoC

The Kraken is the core of ColibriUAV. Kraken is a hetero-
geneous SoC [28] optimized for power-efficient edge com-
puting, particularly for event- and frame-based low-power
visual processing by integrating acceleration engines. Kraken
is composed of three subsystems: one fabric controller (a 32bit
RI5CY/CV32E40P core), a parallel ultra-low-power (PULP)
cluster with eight 32bit RISC-V cores, and a dedicated ac-
celerator domain that hosts two dedicated hardware acceler-
ators: SNE (Sparse Neural Engine) and CUTIE (Completely
Unrolled Ternary Inference Engine).

The fabric controller acts as the main programmable control
unit, hosting the main interconnection busses towards the main
L2 memory and the advanced peripheral bus (APB), which

controls all SoC peripherals. The computing cluster imple-
ments dedicated Instruction-Set Architecture (ISA) extensions
like hardware loops, multiply and accumulate, and vectorial
instructions for low-precision machine learning workloads. A
128 KiB tightly coupled data memory (L1) is shared among
the cores to serve all memory requests.

The dedicated accelerator domain is composed of SNE
targeting spiking convolutional neural network (SCNN) in-
ference, and CUTIE, a TNN (ternary) accelerator designed
to maximize energy efficiency by minimizing data movement
during inference. To be noticed, the accelerator domain has
two clock sources: one is from the fabric controller, which is
used to clock the interface logic between the accelerators and
the system interconnect, and the other is a dedicated one to
clock the accelerators’ computing engines.

#### V. EXPERIMENTAL RESULTS

An edge vision system’s power consumption and closed-
loop latency are mainly composed of four parts: the sensor,
the processor, the actuator, and the interface between them
for data/command transmission. For instance, a sensor with
smaller resolution and lower output precision, and a shorter
data/command transmission distance, results in less power
consumption and faster temporal response. In this section,
we evaluate the power consumption and latency separately
for the DVS camera, Kraken, and interfaces in the proposed
ColibriUAV. As the power and latency of the actuator, i.e., the
motor and flight controller, highly depend on different UAV
platforms targeting different application scenarios, this work
does not evaluate this part.

A. DVS Camera

The DVS132S is a variant of the original iniVation DVS,
which has an analog pixel with per-pixel timestamping at the
output and is optimized for very low power consumption.
We measure the power consumed by the DVS132S sensing
module by measuring the voltage of two low-value resistors
located before the digital and analog voltage inputs to the
sensor, separately. The analog input shows a constant power
consumption of 0.36 mW (which can vary depending on the
bias configuration), while the digital input shows ultra-small
power consumption up to 0.06 mW depending on the number
of events, which is much less than the power consumption of
other DVS cameras [33].

As the event-frame sampling rate is configured on the
Kraken chip and influences the power consumed by the
DVS132S, the sampling rate was set to 7.2 kHz while the
Kraken SoC runs at 50 MHz system clock. The time spent
to receive one event frame from the camera to the fabric
controller of Kraken is thus a maximum of only 139 µs
(one full-events frame), thanks to the SAER interface that
groups events from all pixels in a frame. This is one of the
main differences between our UAV platform and other UAVs
incorporating DVS, which usually use the USB port to transfer
data from the camera to the processing unit.


## --- Page 5 ---

### Section: Motor control with PWM and end-to-end evaluation

TABLE II
DVS INTERFACE

Modulesa
Throughputa (efpsb)
Powerc(mW)
USB [12], [15], [16], [18]
1087
over 1000 d

SAER on FPGA [10]
874
17.6
SAER on ColibriUAV
7200
10.656e

a Assuming fully populated event frame (13728 events).
b Event-frames per second.
c Power consumption of the host platform when fetching data from the DVS
camera (power consumption of DVS camera is not considered).
d In the level of W, depending on the host platform like Loihi KapohoBay,
Jetson TX2, Odroid computer, etc.
e Measured with 0.9 V for FC and 1.8 V for IO domain on Kraken, the system
clock is 50 MHz.

The time spent on USB depends on the number of events
in each event frame. USB 2.0 is specified for 480 Mbit/s. An
event from the DVS is encoded in 32 bits, yielding a transfer
duration of 0.067 µs [12]. Therefore, each event frame will
take a maximum of 920 µs. In [10], the authors built an event
data streaming node with a low-power FPGA that deployed a
DVS driver module that physically interacts with the SAER
interface of the DVS132S camera. The low-power FPGA can
reach a reading speed of 874 Efps consuming only 17.6 mW
of power. Table II summarizes the throughput and power
of different interface solutions. Our platform achieves very
high throughput with nearly one million events per second,
which would take more than 6.6 seconds by USB and 8.2
seconds by SA´ER accomplished on low-power FPGA [10].
The power consumption for event data fetching also shows
impressive efficiency, consuming only 10.7 mW, while USB-
based solutions consume power on the order of watts [34].

For the performance evaluation of the neuromorphic algo-
rithm on the SNE on Kraken, a proof of concept network
has been evaluated in our previous work [35]. The spiking
neural network is composed of two convolutional layers and
two fully-connected layers and trained with the spatiotemporal
backpropagation (STBP) described in [22] in a quantization-
aware way, and then deployed in a layer-by-layer fashion. This
network does not have the goal of evaluating the accuracy
for a specific application task (such as object avoidance), but
rather benchmarking the latency and energy for a medium-
sized network. To configure the SNE to execute a specific
layer of an SNN, the first step is to configure the engine and a
few hyperparameters that are needed for each layer, including
the base potential at which neurons are reset after firing, the
firing threshold of the neurons, the rate at which the threshold
is adapted, the minimum time between two consecutive spikes
of the same neuron, and the amount of shifting applied to each
timestep. Then, the trained weights are converted to SNE’s
internal format and loaded into the engine’s kernel memories.
Finally, the streamers are configured to trigger the execution of
SNE over a stream of events. The input streamer is configured
to start loading the input events to the accelerator, and the
output streamer is configured to specify the last expected event
and a pointer to an accessible memory region that will be
filled by produced events. During the layer execution, a tiling

TABLE III
PERFORMANCE OF COLIBRIUAV ON REFERENCE NEURAL NETWORK

Modulesa
Latency (ms)
Power (mW)b
Energy (mJ)b

DVS
and
SAER
(single event-frame)

0.069
11.076c
0.0008

DVS
and
SAER
(one window / 4350
event frames)

300
11.076
3.323

Preprocessing
(Cluster)

131
34
4.5

Inference (SNE)
32
44
1.4
PWM(50% duty)
<0.001
0.3
<0.001
Total
163 d
46.98e
9.224

a Network is deployed on SNE with input events window size of 300 ms.
b Power and energy are observed in the active status of the system dealing
with one event frame in a pipeline way, namely the whole power consumed
on all components.
c Where is camera itself consumes 0.420 mW.
d Data sensing and transmission is in parallel with SNE inference, thus not
accumulated.
b Power and energy are observed in the active status of the system dealing
with one event frame in a pipeline way, namely the whole power consumed
on all components.
e The average total power consumption during inference is 35.6 mW.

method is used to adjust the layer processing to the limited
resources available on SNE.

B. Motor control with PWM and end-to-end evaluation

For the motor command transition, suppose the obtained
motor commands are forwarded to the actuator module in the
form of PWM signals, with a 50 MHz system clock, the time
spent on PWM signal transmission will be below 1 µs, without
considering the path time. The power consumed by PWM
generation is observed by monitoring the change in power
consumption when the development board is in the idle state
and in PWM transmitting state.

Table III lists the time and power consumed by ColibriUAV.
Altogether, 163 ms are spent from the event data readout
to the PWM signals arriving at the flight control unit. Of
this, a significant amount of time (131 ms) is spent on spike
preprocessing in the cluster. The latency here can be further
decreased by memory usage optimization. The time spent on
SNE is 32 ms for a complete SNN inference. The power
consumed on the platform is 46.98 mW, including the camera,
the Kraken SoC, and the interfaces, and only 9.2 mJ for each
complete loop. As far as we know, this work is the first to
describe the latency and power performance of a complete,
closed-loop neuromorphic UAV platform that can handle event
data from a DVS camera onboard.

#### VI. CONCLUSION

This work describes ColibriUAV, a milliwatts drone plat-
form that uses the Kraken SoC with an embedded neu-
romorphic accelerator and the benchmarks for the latency
and power consumption of various components in the event
signal processing pipeline and concludes that the closed-loop
neuromorphic approach from event perception to decision-
making offers promising performance for drone applications.
The paper also presents a state-of-the-art event data fetching


## --- Page 6 ---

### Section: References

interface that is much faster and uses significantly less power
than the USB approach used in existing DVS-equipped UAVs.
In future work, the authors plan to investigate complete
onboard event-based autonomous navigation, including real-
time target tracking, obstacle recognition and avoidance, and
optical flow estimation, using the proposed UAV platform.

#### REFERENCES

[1] V. Niculescu, D. Palossi, M. Magno, and L. Benini, “Energy-efficient,

precise uwb-based 3-d localization of sensor nodes with a nano-uav,”
IEEE Internet of Things Journal, 2022.
[2] H. M¨uller, N. Zimmerman, T. Polonelli, M. Magno, J. Behley,

C. Stachniss, and L. Benini, “Fully on-board low-power localization
with multizone time-of-flight sensors on nano-uavs,” arXiv preprint
arXiv:2212.00710, 2022.
[3] L. Miccinesi, L. Bigazzi, T. Consumi, M. Pieraccini, A. Beni, E. Boni,

and M. Basso, “Geo-referenced mapping through an anti-collision radar
aboard an unmanned aerial system,” Drones, vol. 6, no. 3, p. 72, 2022.
[4] A. Suleiman, Z. Zhang, L. Carlone, S. Karaman, and V. Sze, “Navion:

A 2-mw fully integrated real-time visual-inertial odometry accelerator
for autonomous navigation of nano drones,” IEEE Journal of Solid-State
Circuits, vol. 54, no. 4, pp. 1106–1119, 2019.
[5] L. Lamberti, V. Niculescu, M. Barci´s, L. Bellone, E. Natalizio, L. Benini,

and D. Palossi, “Tiny-pulp-dronets: Squeezing neural networks for faster
and lighter inference on multi-tasking autonomous nano-drones,” in 2022
IEEE 4th International Conference on Artificial Intelligence Circuits and
Systems (AICAS).
IEEE, 2022, pp. 287–290.
[6] G. Gallego, T. Delbr¨uck, G. Orchard, C. Bartolozzi, B. Taba, A. Censi,

S. Leutenegger, A. J. Davison, J. Conradt, K. Daniilidis et al., “Event-
based vision: A survey,” IEEE transactions on pattern analysis and
machine intelligence, vol. 44, no. 1, pp. 154–180, 2020.
[7] C. Haoyu, T. Minggui, S. Boxin, W. YIzhou, and H. Tiejun, “Learning

to deblur and generate high frame rate video with an event camera,”
arXiv preprint arXiv:2003.00847, 2020.
[8] H. Rebecq, R. Ranftl, V. Koltun, and D. Scaramuzza, “High speed and

high dynamic range video with an event camera,” IEEE transactions on
pattern analysis and machine intelligence, vol. 43, no. 6, pp. 1964–1980,
2019.
[9] T. Delbruck, Y. Hu, and Z. He, “V2e: From video frames to realistic

dvs event camera streams,” arXiv e-prints, pp. arXiv–2006, 2020.
[10] A. Di Mauro, M. Scherer, J. F. Mas, B. Bougenot, M. Magno, and

L. Benini, “Flydvs: An event-driven wireless ultra-low power visual
sensor node,” in 2021 Design, Automation & Test in Europe Conference
& Exhibition (DATE).
IEEE, 2021, pp. 1851–1854.
[11] D. Falanga, K. Kleber, and D. Scaramuzza, “Dynamic obstacle avoid-

ance for quadrotors with event cameras,” Science Robotics, vol. 5, no. 40,
p. eaaz9712, 2020.
[12] E. Mueggler, N. Baumli, F. Fontana, and D. Scaramuzza, “Towards

evasive maneuvers with quadrotors using dynamic vision sensors,” in
2015 European Conference on Mobile Robots (ECMR).
IEEE, 2015,
pp. 1–8.
[13] T. Stoffregen, G. Gallego, T. Drummond, L. Kleeman, and D. Scara-

muzza, “Event-based motion segmentation by motion compensation,” in
Proceedings of the IEEE/CVF International Conference on Computer
Vision, 2019, pp. 7244–7253.
[14] A. Gruel, A. Vitale, J. Martinet, and M. Magno, “Neuromorphic event-

based spatio-temporal attention using adaptive mechanisms,” in 2022
IEEE 4th International Conference on Artificial Intelligence Circuits
and Systems (AICAS).
IEEE, 2022, pp. 379–382.
[15] K. F. Andersen, H. X. Pham, H. I. Ugurlu, and E. Kayacan, “Event-based

navigation for autonomous drone racing with sparse gated recurrent
network,” in 2022 European Control Conference (ECC).
IEEE, 2022,
pp. 1342–1348.
[16] R. S. Dimitrova, M. Gehrig, D. Brescianini, and D. Scaramuzza,

“Towards low-latency high-bandwidth control of quadrotors using event
cameras,” in 2020 IEEE International Conference on Robotics and
Automation (ICRA).
IEEE, 2020, pp. 4294–4300.
[17] A. Vitale, A. Renner, C. Nauer, D. Scaramuzza, and Y. Sandamirskaya,

“Event-driven vision and control for uavs on a neuromorphic chip,”
in 2021 IEEE International Conference on Robotics and Automation
(ICRA).
IEEE, 2021, pp. 103–109.

[18] P. Chen, W. Guan, and P. Lu, “Esvio: Event-based stereo visual inertial

odometry,” arXiv preprint arXiv:2212.13184, 2022.
[19] F. Ponulak and A. Kasinski, “Introduction to spiking neural networks:

Information processing, learning and applications.” Acta neurobiologiae
experimentalis, vol. 71, no. 4, pp. 409–433, 2011.
[20] J. H. Lee, T. Delbruck, and M. Pfeiffer, “Training deep spiking neural

networks using backpropagation,” Frontiers in neuroscience, vol. 10, p.
508, 2016.
[21] S. B. Shrestha and G. Orchard, “Slayer: Spike layer error reassignment

in time,” Advances in neural information processing systems, vol. 31,
2018.
[22] Y. Wu, L. Deng, G. Li, J. Zhu, and L. Shi, “Spatio-temporal backpropa-

gation for training high-performance spiking neural networks,” Frontiers
in neuroscience, vol. 12, p. 331, 2018.
[23] P.-Y. Tan, C.-W. Wu, and J.-M. Lu, “An improved stbp for training high-

accuracy and low-spike-count spiking neural networks,” in 2021 Design,
Automation & Test in Europe Conference & Exhibition (DATE).
IEEE,
2021, pp. 575–580.
[24] T. Taunyazov, Y. Chua, R. Gao, H. Soh, and Y. Wu, “Fast texture

classification using tactile neural coding and spiking neural network,”
in 2020 IEEE/RSJ International Conference on Intelligent Robots and
Systems (IROS).
IEEE, 2020, pp. 9890–9895.
[25] F. Akopyan, J. Sawada, A. Cassidy, R. Alvarez-Icaza, J. Arthur,

P. Merolla, N. Imam, Y. Nakamura, P. Datta, G.-J. Nam et al.,
“Truenorth: Design and tool flow of a 65 mw 1 million neuron
programmable neurosynaptic chip,” IEEE transactions on computer-
aided design of integrated circuits and systems, vol. 34, no. 10, pp.
1537–1557, 2015.
[26] M. Davies, N. Srinivasa, T.-H. Lin, G. Chinya, Y. Cao, S. H. Choday,

G. Dimou, P. Joshi, N. Imam, S. Jain et al., “Loihi: A neuromorphic
manycore processor with on-chip learning,” Ieee Micro, vol. 38, no. 1,
pp. 82–99, 2018.
[27] S. Moradi, N. Qiao, F. Stefanini, and G. Indiveri, “A scalable mul-

ticore architecture with heterogeneous memory structures for dynamic
neuromorphic asynchronous processors (dynaps),” IEEE transactions on
biomedical circuits and systems, vol. 12, no. 1, pp. 106–122, 2017.
[28] A. Di Mauro, M. Scherer, D. Rossi, and L. Benini, “Kraken: A

direct event/frame-based multi-sensor fusion soc for ultra-efficient visual
processing in nano-uavs,” arXiv preprint arXiv:2209.01065, 2022.
[29] A. Di Mauro, A. S. Prasad, Z. Huang, M. Spallanzani, F. Conti, and

L. Benini, “Sne: an energy-proportional digital accelerator for sparse
event-based convolutions,” in 2022 Design, Automation & Test in Europe
Conference & Exhibition (DATE).
IEEE, 2022, pp. 825–830.
[30] C. Li, L. Longinotti, F. Corradi, and T. Delbruck, “A 132 by 104 10µm-

pixel 250µw 1kefps dynamic vision sensor with pixel-parallel noise and
spatial redundancy suppression,” in 2019 Symposium on VLSI Circuits.
IEEE, 2019, pp. C216–C217.
[31] C. Brandli, R. Berner, M. Yang, S.-C. Liu, and T. Delbruck, “A 240×

180 130 db 3 µs latency global shutter spatiotemporal vision sensor,”
IEEE Journal of Solid-State Circuits, vol. 49, no. 10, pp. 2333–2341,
2014.
[32] B. Son, Y. Suh, S. Kim, H. Jung, J.-S. Kim, C. Shin, K. Park, K. Lee,

J. Park, J. Woo et al., “4.1 a 640× 480 dynamic vision sensor with a
9µm pixel and 300meps address-event representation,” in 2017 IEEE
International Solid-State Circuits Conference (ISSCC).
IEEE, 2017,
pp. 66–67.
[33] iniVation,
“iniVation:
specification
of
current
versions,”
2020,
last access: 01-03-2923. [Online]. Available: https://inivation.com/
wp-content/uploads/2020/09/2020-09-16-DVS-Specifications.pdf
[34] R. Berner, T. Delbruck, A. Civit-Balcells, and A. Linares-Barranco, “A 5

meps $100 usb2. 0 address-event monitor-sequencer interface,” in 2007
IEEE International Symposium on Circuits and Systems.
IEEE, 2007,
pp. 2451–2454.
[35] G. Rutishauser, R. Hunziker, A. Di Mauro, S. Bian, L. Benini,

and M. Magno, “Colibries: A milliwatts risc-v based embedded sys-
tem leveraging neuromorphic and neural networks hardware accelera-
tors for low-latency closed-loop control applications,” arXiv preprint
arXiv:2302.07957, 2023.
