# 2101 00292V1

**Source Document:** `2101.00292v1.pdf`  
**Total Pages:** 39  

---

## --- Page 1 ---

### Section: I Introduction

1

Jamming Attacks and Anti-Jamming Strategies in

Wireless Networks: A Comprehensive Survey

Hossein Pirayesh and Huacheng Zeng
Department of Computer Science and Engineering, Michigan State University, East Lansing, MI USA

Abstract—Wireless networks are a key component of the
telecommunications infrastructure in our society, and wireless
services become increasingly important as the applications of
wireless devices have penetrated every aspect of our lives.
Although wireless technologies have signiﬁcantly advanced in
the past decades, most wireless networks are still vulnerable to
radio jamming attacks due to the openness nature of wireless
channels, and the progress in the design of jamming-resistant
wireless networking systems remains limited. This stagnation can
be attributed to the lack of practical physical-layer wireless tech-
nologies that can efﬁciently decode data packets in the presence
of jamming attacks. This article surveys existing jamming attacks
and anti-jamming strategies in wireless local area networks
(WLANs), cellular networks, cognitive radio networks (CRNs),
ZigBee networks, Bluetooth networks, vehicular networks, LoRa
networks, RFID networks, and GPS system, with the objective
of offering a comprehensive knowledge landscape of existing
jamming/anti-jamming strategies and stimulating more research
efforts to secure wireless networks against jamming attacks.
Different from prior survey papers, this article conducts a
comprehensive, in-depth review on jamming and anti-jamming
strategies, casting insights on the design of jamming-resilient
wireless networking systems. An outlook on promising anti-
jamming techniques is offered at the end of this article to
delineate important research directions.

Index Terms—Wireless security, physical-layer security, jam-
ming attacks, denial-of-services attacks, anti-jamming techniques,
cellular, Wi-Fi, LoRa, ZigBee, Bluetooth, RFID

#### I. INTRODUCTION

With the rapid proliferation of wireless devices and the
explosion of Internet-based mobile applications under the
driving forces of 5G and artiﬁcial intelligence, wireless ser-
vices have penetrated every aspect of our lives and become
increasingly important as an essential component of the
telecommunications infrastructure in our society. In the past
two decades, we have witnessed the signiﬁcant advancement
of wireless communication and networking technologies such
as polar code [1], [2], massive multiple-input multiple-output
(MIMO) [3]–[5], millimeter-wave (mmwave) [6], [7], non-
orthogonal multiple access (NOMA) [8]–[11], carrier aggrega-
tion [12], novel interference management [13], learning-based
resource allocation [14], [15], software-deﬁned radio [16], and
software-deﬁned wireless networking [17]. These innovative
wireless technologies have dramatically boosted the capacity
of wireless networks and the quality of wireless services,
leading to a steady evolution of cellular networks towards
5th generation (5G) and Wi-Fi networks towards 802.11ax.
With the joint efforts from academia, federal governments, and
private sectors, it is expected that high-speed wireless services

will become ubiquitously available for massive devices to
realize the vision of Internet of Everything (IoE) in the near
future [18].

As we are increasingly reliant on wireless services, security
threats have become a big concern about the conﬁdentiality,
integrity, and availability of wireless communications. Com-
pared to other security threats such as eavesdropping and
data fabrication, wireless networks are particularly vulnerable
to radio jamming attacks for the following reasons. First,
jamming attacks are easy to launch. With the advances in
software-deﬁned radio, one can easily program a small $10
USB dongle device to a jammer that covers 20 MHz bandwidth
below 6 GHz and up to 100 mW transmission power [34].
Such a USB dongle sufﬁces to disrupt the Wi-Fi services in
a home or ofﬁce scenario. Other off-the-shelf SDR devices
such as USRP [35] and WARP [36] are even more powerful
and more ﬂexible when using as a jamming emitter. The
ease of launching jamming attacks makes it urgent to secure
wireless networks against intentional and unintentional jam-
ming threats. Second, jamming threats can only be thwarted
at the physical (PHY) layer but not at the MAC or network
layer. When a wireless network suffers from jamming attacks,
its legitimate wireless signals are typically overwhelmed by
irregular or sophisticated radio jamming signals, making it
hard for legitimate wireless devices to decode data packets.
Therefore, any strategies at the MAC layer or above are
incapable of thwarting jamming threats, and innovative anti-
jamming strategies are needed at the physical layer. Third,
the effective anti-jamming strategies for real-world wireless
networks remain limited. Despite the signiﬁcant advancement
of wireless technologies, most of current wireless networks
(e.g., cellular and Wi-Fi networks) can be easily paralyzed by
jamming attacks due to the lack of protection mechanism. The
vulnerability of existing wireless networks can be attributed
to the lack of effective anti-jamming mechanisms in practice.
The jamming vulnerability of existing wireless networks also
underscores the critical need and fundamental challenges in
designing practical anti-jamming schemes.

This article provides a comprehensive survey on jam-
ming attacks and anti-jamming strategies in various wire-
less networks, with the objectives of providing readers with
a holistic knowledge landscape of existing jamming/anti-
jamming techniques and stimulating more research endeav-
ors in the design of jamming-resistant wireless networking
systems. Speciﬁcally, our survey covers wireless local area
networks (WLANs), cellular networks, cognitive radio net-
works (CRNs), vehicular networks, Bluetooth networks, ad

arXiv:2101.00292v1  [cs.CR]  1 Jan 2021


## --- Page 2 ---

2

#### TABLE I: This survey article versus prior survey papers.

Ref.
Studied networks
Studied layers
Attacks techniques
Anti-attack strategies
Attack detection
[19]
WSNs
PHY
[20]
WSNs
PHY/Network/Session
[21]
ZigBee networks
PHY/MAC
×
×
[22]
WSNs
PHY/MAC/Network/Transport/Application
[23]
WSNs/WLANs
PHY
[24]
WSNs
PHY/MAC
[25]
CRNs
MAC
[26]
CRNs
MAC
[27]
CRNs
MAC
[28]
CRNs
PHY/MAC
×
[29]
CRNs
MAC
×
×
[30]
Cellular networks
PHY/Link/Network
×
×
[31]
Ad-hoc networks
PHY/MAC
[32]
OFDM networks
PHY
×
×
[33]
Ad-hoc networks
PHY/MAC

This
article

WLANs/Cellular/CRNs/
ZigBee/Bluetooth/Vehicular/

GPS/RFID networks

PHY/MAC/Implementation

hoc networks, etc. For each type of wireless network, we
ﬁrst offer an overview on the system design and then provide
a primer on its PHY/MAC layers, followed by an in-depth
review of the existing PHY-/MAC-layer jamming and defense
strategies in the literature. Finally, we offer discussions on
open issues and promising research directions.

Prior to this work, there are several survey papers on
jamming and/or anti-jamming attacks in wireless networks
[19]–[33]. In [19], the authors surveyed the jamming attacks
and defense mechanisms in WSNs. In [20], Zhou et al.
surveyed the security challenges on WSNs’ network protocols,
including key establishment, authentication, integrity protec-
tion, and routing. In [21], Amin et al. surveyed PHY and
MAC layer attacks on IEEE 802.15.4 (ZigBee networks). In
[22], Raymond et al. focused on denial-of-service attacks and
the countermeasures in higher WSNs’ network protocols (e.g.,
transport and application layers). [23] classiﬁed the attacks
and countermeasure techniques from both the attacker and
the defender’s perspective, the game-theoretical models, and
the solutions used in WSNs and WLANs. In [24], Xu et al.
surveyed jamming attacks, jamming detection strategies, and
defense techniques in WSNs. In [25], Zhang et al. surveyed
a MAC layer attack, known as Byzantine attack (a.k.a. false-
report attack), and its possible countermeasures in cooperative
spectrum sensing CRNs. In [26], Das et al. surveyed a MAC
layer security threat called primary user emulation attack, its
detection mechanisms, and defense techniques in CRNs. [27]–
[29] summarized the jamming attacks, MAC layer security
challenges, and detection techniques in CRNs. [30] surveyed
the denial of service attacks in LTE cellular networks. [31],
[33] reviewed the generic PHY-layer jamming attacks, detec-
tion, and countermeasures in wireless ad hoc networks. In [32],
Shahriar et al. offered a comprehensive overview of PHY layer
security challenges in OFDM networks. Table I summarizes
the existing survey works on jamming and/or anti-jamming
attacks in wireless networks.

Unlike prior survey papers, this article conducts a compre-

hensive review on up-to-date jamming/anti-jamming strategies,
and provides the necessary PHY/MAC-layer knowledge to
understand the jamming/anti-jamming strategies in various
wireless networks. The contributions of this paper are sum-
marized as follows.

• We conduct a comprehensive, in-depth review on existing
jamming attacks in various wireless networks, including
WLANs, cellular networks, CRNs, Bluetooth and ZigBee
networks, LoRaWANs, VANETs, UAVs, RFID systems,
and GPS systems. We offer the necessary PHY/MAC-
layer knowledge to understand the destructiveness of
jamming attacks in those networks.

• We conduct an in-depth survey on existing anti-jamming
strategies in different wireless networks, including power
control, spectrum spreading, frequency hopping, MIMO-
based jamming mitigation, and jamming-aware protocols.
We quantify their jamming mitigation capability and
discuss their applications.

• In addition to the review of jamming and anti-jamming
strategies, we discuss the open issues of jamming threats
in wireless networks and point out promising research
directions.

The remainder of this article is organized following the
structure as shown in Fig. 1. In Section II, we survey jamming
and anti-jamming attacks in WLANs. In Section III, we survey
jamming and anti-jamming attacks in cellular networks. In
Section IV, we survey jamming and anti-jamming attacks
in cognitive radio networks. Sections V and VI offer an in-
depth review on jamming attacks and anti-jamming techniques
for ZigBee and Bluetooth networks, respectively. Section VII
presents an overview of jamming attacks and anti-jamming
techniques in LoRa communications. Section VIII studies
existing jamming and anti-jamming techniques for vehicular
networks, including on-ground vehicular transportation net-
works (VANETs) and in-air unmanned aerial vehicular (UAV)
networks. Section IX reviews jamming and anti-jamming tech-
niques for RFID systems, and Second X reviews those tech-


## --- Page 3 ---

### Section: II Jamming and Anti-Jamming Attacks in WLANs

3

WLANs

Jamming attacks/
anti jamming techniques

Cellular 
networks

CRNs

ZigBee 
networks
Bluetooth

networks

Section Ⅱ

Section Ⅲ

Section Ⅳ

Section Ⅴ 
Section Ⅵ

Research 
direction

Section Ⅺ

Vehicular

networks

RFID 
systems

LoRaWANs

Section Ⅶ

Section Ⅷ

Section Ⅸ

GPS 
systems

Section Ⅹ

Fig. 1: The structure of this article.

Internet

Desktop  PC

TV & media player

Smart phone

Printer

Camera
Laptop

Jammer

Wi-Fi router

Internet server

Video game

console

Jamming signal
Wi-Fi signal

Jammer

Fig. 2: Illustration of jamming attacks in a Wi-Fi network.

niques for GPS systems. Section XI discusses open problems
and points out some promising research directions. Section XII
concludes this article. Table II lists the abbreviations used in
this article.

#### II. JAMMING AND ANTI-JAMMING ATTACKS IN WLANS

WLANs become increasingly important as they carry even
more data trafﬁc than cellular networks. With the proliferation
of wireless applications in smart homes, smart buildings, and
smart hospital environments, securing WLANs against jam-
ming attacks is of paramount importance. In this section, we
study existing jamming attacks and anti-jamming techniques
for a WLAN as shown in Fig. 2, where one or more malicious
jamming devices attempt to disrupt wireless connections of
Wi-Fi devices. Prior to that, we ﬁrst review the MAC and PHY
layers of WLANs, which will lay the knowledge foundation
for our review on existing jamming/anti-jamming strategies.

A. A Primer of WLANs

As shown in Fig. 2, WLANs are the most dominant wireless
connectivity infrastructure for short-range and high-throughput

#### TABLE II: List of abbreviations.

Abbreviation
Explanation
AP
Access Point
ARF
Automatic Rate Fallback
ARQ
Automatic Repeat Request
BLE
Bluetooth Low Energy
COTS
Commercial Off-The-Shelf
CP
Cyclic Preﬁx
CRC
Cyclic Redundancy Check
CRN
Cognitive Radio Network
CSMA/CA
Carrier-Sense Multiple Access/Collision Avoidance
CSS
Cooperative Spectrum Sensing
DCI/UCI
Downlink/Uplink Control Information
DoS
Denial of Service
DSSS
Direct-Sequence Spread Spectrum
FC
Fusion Center
FHSS
Frequency Hopping Spread Spectrum
GMSK
Gaussian Minimum Shift Keying
GPS
Global Positioning System
ICI
Inter Channel Interference
LoRaWAN
LoRa Wide Area Network
LTE
Long Term Evolution
LTF
Long Training Field
MAC
Medium Access Control
MCS
Modulation and Coding Scheme
MIB/SIB
Master/System Information Block
MIMO
Multiple Input Multiple Output
MMSE
Minimum Mean Square Error
MU-MIMO
Multi User Multiple Input Multiple Output
NAV
Net Allocation Vector
NDP
Null Data Packet
NOMA
Non-Orthogonal Multiple Access
OFDM
Orthogonal Frequency Division Multiplexing
PBCH
Physical Broadcast Channel
PDCCH/PUCCH
Physical Downlink/Uplink Control Channel
PDSCH/PUSCH
Physical Downlink/Uplink Shared Channel
PHICH
Physical Hybrid ARQ Indicator Channel
PRACH
Physical Random Access Channel
PRB
Physical Resource Block
PSS/SSS
Primary/Secondary Synchronization Signal
PU
Primary User
PUE
Primary User Emulation
RAA
Rate Adaptation Algorithm
RAT
Radio Access Technology
RFID
Radio-Frequency Identiﬁcation
RSI
Road Side Infrastructure
RSSI
Received Signal Strength Indicator
RTS/CTS
Request To Send/Clear To Send
SC-FDMA
Single Carrier Frequency Division Multiple Access
SDR
Software Deﬁned Radio
SNR
Signal to Noise Ratio
STF
Short Training Field
SU
Secondary User
UAV
Unmanned Aerial Vehicle
USRP
Universal Software Radio Peripheral
VANET
Vehicular Network
VHT
Very High Throughput
WCDMA
Wideband Code Division Multiple Access
WLAN
Wireless Local Area Network
WSN
Wireless Sensor Network
ZF
Zero Forcing

Internet services and have been widely deployed in population-
dense scenarios such as homes, ofﬁces, campuses, shopping
malls, and airports. Wi-Fi networks have been designed based
on the IEEE 802.11 standards, and 802.11a/g/n/ac standards
are widely used in various commercial Wi-Fi devices such as
smartphones, laptops, printers, cameras, and smart televisions.
Most of Wi-Fi networks operate in unlicensed industrial,


## --- Page 4 ---

### Section: II-A1 MAC-Layer Protocols

4

Transmitter

Receiver

Other

#### DIFS

#### RTS

#### SIFS

#### CTS

Data packet
SIFS

#### ACK

#### SIFS

#### DIFS

#### NAV (RTS)

#### NAV (CTS)

NAV (data)

Defer Access

#### CW

#### CW

Time

Fig. 3: The RTS/CTS protocol in 802.11 Wi-Fi networks [38].

scientiﬁc, and medical (ISM) frequency bands, which have
14 overlapping 20 MHz channels on 2.4 GHz and 28 non-
overlapping 20 MHz channels bandwidth in 5 GHz [37]. Most
Wi-Fi devices are limited to a maximum transmit power of
100 mW, with a typical indoor coverage range of 35 m.
A Wi-Fi network can cover up to 1 km range in outdoor
environments in an extended coverage setting.

1) MAC-Layer Protocols: Wi-Fi devices use CSMA/CA as
their MAC protocols for channel access. A Wi-Fi user requires
to sense the channel before it sends its packets. If the channel
sensed busy, the user waits for a DIFS time window and backs
off its transmissions for a random amount of time. If the user
cannot access the channel in one cycle, it cancels the random
back-off counting and stands by for the channel to be idle
for the DIFS duration. In this case, the user can immediately
access the channel as the longer waiting users have priority
over the users recently joined the network.

The CSMA/CA MAC protocol, however, suffers from the
hidden node problem. The hidden node problem refers to the
case where one access point (AP) can receive from two nodes,
but those two nodes cannot receive from each other. If both
nodes sense the channel idle and send their data to the AP, then
packet collision occurs at the AP. The RTS/CTS (Request-to-
Send and Clear-to-Send) protocol was invented to mitigate the
hidden node problem, and Fig. 3 shows the RTS/CTS protocol
mechanism. The transmitter who intends to access the channel
waits for the DIFS duration. If the channel is sensed idle, the
transmitter sends an RTS packet to identify the receiver and the
required duration for data transmission. Every node receiving
the RTS sets its Net Allocation Vector (NAV) to defer its try
for accessing the channel to the subsequent frame exchange.

While previous and current Wi-Fi networks (e.g., 802.11g,
802.11n and 802.11ac) use the distributed CSMA/CA protocol
for medium access control, the next-generation 802.11ax Wi-
Fi networks (marketed as Wi-Fi 6) come with a centralized
architecture with features such as OFDMA, both uplink and
downlink MU-MIMO, trigger-based random access, spatial
frequency reuse, and target wake time (TWT) [39], [40].
Despite these new features, 802.11ax devices will be backward
compatible with the predecessor Wi-Fi devices. Therefore, the
jamming and anti-jamming attacks designed for 802.11n/ac
Wi-Fi networks also apply to the upcoming 802.11ax Wi-Fi
networks.

2) Frame Structures: Most Wi-Fi networks use OFDM
modulation at the PHY layer for both uplink and downlink

L-LTF
L-SIG
Data Field
L-STF

8 µs 
8 µs
4 µs

Legacy preamble

(a) Legacy Wi-Fi frame structure.

L-LTF
L-SIG
L-STF
VHT-
SIG-A

#### VHT-

#### STF

#### VHT-

#### LTF

VHT-
SIG-B
Data Field

8 µs
8 µs
4 µs
8 µs
4 µs
4 µs per 
symbol

4 µs

#### VHT Modulation

(b) VHT Wi-Fi frame structure.

Fig. 4: Two frame structures used in 802.11 Wi-Fi networks.

Scrambler
Bit-to-symbol

mapping
Conv. encoder

&interleaving

Symbol-to-bit

mapping

Channel 
estimation
Channel 
equalization

Conv.
decoder
Descrambler

(a) VHT Wi-Fi transmitter.

(b) VHT Wi-Fi receiver.

Subcarrier

mapping
Add

CP
IFFT
DAC
RF front

end

Spatial 
mapping
n
n
n
Input data

bits

n

m
m
m
m

Packet 
detection

Coarse frequency

correction

Time 
synchronization
RF front

end
 ADC
m
m
m
m

Fine frequency

correction
Remove

CP
FFT

m
m

Output 
decoded bits

m
m
m
m
m
n

m

n
n
n

Fig. 5: A schematic diagram of baseband signal processing for
an 802.11 Wi-Fi transceiver [38] (n ≤4 and m ≤8).

transmissions. Fig. 4(a) shows the legacy Wi-Fi (802.11a/g)
frame, which consists of preamble, signal ﬁeld, and data ﬁeld.
The preamble comprises two STFs and two LTFs, mainly used
for frame synchronizations and channel estimation purposes.
In particular, STF consists of ten identical symbols and is used
for start-of-packet detection, coarse time and frequency syn-
chronizations. LTF consists of two identical OFDM symbols
and is used for ﬁne packet and frequency synchronizations.
LTF is also used for channel estimation and equalization.
Following the preamble, the signal (SIG) ﬁeld carries the
necessary packet information such as the adopted modulation
and coding scheme (MCS) and the data part’s length. SIG ﬁeld
is always transmitted using BPSK modulation for minimizing
the error probability at the receiver side. Data ﬁeld carries
user payloads and user-speciﬁc information. Wi-Fi may use
different MCS (e.g., OQPSK, 16-QAM, 64-QAM) for data bits
modulation, depending on the link quality. Four pilot signals
are also embedded into four different tones (subcarriers) for
further residual carrier and phase offset compensation in the
data ﬁeld.

Fig. 4(b) shows the VHT format structure used by 802.11ac.
As shown in the ﬁgure, it consists of L-STF, L-LTF, L-SIG,
VHT-SIG-A, VHT-STF, VHT-LTF, VHT-SIG-B, and Data
Field. To maintain its backward compatibility with 802.11a/g,
the L-STF, L-LTF, and L-SIG in the VHT frame are the same
as those in Fig. 4(a). VHT-SIG-A and VHT-SIG-B are for
similar purpose as the header ﬁeld (HT-SIG) of 11n and SIG


## --- Page 5 ---

### Section: II-A3 PHY-Layer Signal Processing Modules

5

ﬁeld of 11a. In 802.11ac, signal ﬁelds are SIG-A and SIG-
B. They describe channel bandwidth, modulation-coding and
indicate whether the frame is for a single user or multiple
users. These ﬁelds are only deployed by the 11ac devices and
are ignored by 11a and 11n devices. VHT-STF has the same
function as that of the non-HT STF ﬁeld. It assists the 11ac
receiver to detect the repeating pattern. VHT-LTF consists of
a sequence of symbols and is used for demodulating the rest
of the frame. Its length depends on the number of transmitted
streams. It could be 1, 2, 4, 6, or 8 symbols. It is mainly used
for channel estimation purposes. Data ﬁeld carries payload
data from the upper layers. When there are no data from upper
layers, the ﬁeld is referred to as the null data packet (NDP) and
is used for measurement and beamforming sounding purposes
by the physical layer.

3) PHY-Layer Signal Processing Modules: Fig. 5 shows
the PHY-layer signal processing framework of a legacy Wi-
Fi transceiver. On the transmitter side, the data bitstream is
ﬁrst scrambled and then encoded using a convolutional or
LDPC encoder. The coded bits are modulated according to
the pre-selected MCS index. Then, the modulated data and
pilot signals are mapped onto the scheduled subcarriers and
converted to the time domain using OFDM modulation (IFFT
operation). Following the OFDM modulation, the cyclic preﬁx
(CP) is appended to each OFDM symbol in the time domain.
After that, a preamble is attached to the time-domain signal.
Finally, the output signal samples are up-converted to the
desired carrier frequency and transmitted over the air using
a radio frequency (RF) front-end module.

Referring to Fig. 5 again, on the receiver side, the received
radio signal is down-converted to baseband I/Q signals, which
are further converted to digital streams by ADC modules.
The start of a packet can be detected by auto-correlating
the received signal stream with itself in a distance of one
OFDM symbol to identify the two transmitted STF signals
within the frame. The received STF signals can be used
to coarsely estimate the carrier frequency offset, which can
then be utilized to correct the offset and improve the timing
synchronization accuracy. Timing synchronization can be done
by cross-correlating the received signal and a local copy of
the LTF signal at the receiver. LTF is also used for ﬁne
frequency offset correction. Once the signal is synchronized,
it is converted into the frequency domain using the OFDM de-
modulation, which comprises CP removal and FFT operation.

The received LTF symbols are used to estimate the wireless
channel between the Wi-Fi transmitter and receiver for each
subcarrier. Channel smoothing, which refers to interpolating
the estimated channel for each subcarrier using its adjacent
estimated subcarriers’ channels, is usually used to suppress
the impact of noise in the channel estimation process. The
estimated channels are then used to equalize the channel
distortion of the received frame in the frequency domain. The
received four pilots are used for residual carrier frequency,
and phase offsets correction. After phase compensation, the
received symbols are mapped into their corresponding bits.
This process is called symbol-to-bit mapping. Following the
symbol-to-bit mapping, convolutional or LDPC decoder and
descrambler are applied to recover the transmitted bits. The

recovered bits are fed to the MAC layer for protocol-level
interpretation.

B. Jamming Attacks

With the primer knowledge provided above, we now dive
into the review of existing jamming attacks in WLANs. In
what follows, we ﬁrst survey the generic jamming attacks
proposed for Wi-Fi networks but can also be applied to other
types of wireless networks and then review the jamming
attacks that delicately target the PHY transmission and MAC
protocols of Wi-Fi communications.

1) Generic Jamming Attacks: While there are many jam-
ming attacks that were originally proposed for Wi-Fi networks,
they can also be applied to other types of wireless systems.
We survey these generic jamming attacks in this part.
Constant Jamming Attacks: Constant jamming attacks refer
to the scenario where the malicious device broadcasts a
powerful signal all the time. Constant jamming attacks not
only destroy legitimate users’ packet reception by introducing
high-power interference to their data transmissions, but they
also prevent them from accessing the channel by continuously
occupying it. In constant jamming attacks, the jammer may
target the entire or a fraction of channel bandwidth occupied
by legitimate users [31], [33]. In [41], Karishma et al. ana-
lyzed the performance of legacy Wi-Fi communications under
broadband and partial-band constant jamming attacks through
theoretical exploration and experimental measurement. The
authors conducted experiments to study the impact of jamming
power on Wi-Fi communication performance when the data
rate is set to 18 Mbps. Their experimental results show that
a Wi-Fi receiver fails to decode its received packets under
broadband jamming attack (i.e., 100% packet error rate) when
the received desired signal power is 4 dB less than the received
jamming signal power (i.e., signal-to-jamming power ratio,
abbreviated as SJR, less than 4 dB). The theoretical analysis in
[41], [42] showed that Wi-Fi communication is more resilient
to partial-band jamming than broadband jamming attacks. The
experimental results in [41] showed that, for the jamming
signal with bandwidth being one subcarrier spacing (i.e.,
312.5 KHz), Wi-Fi communication fails when SJR < −19 dB.
In [34], Vanhoef et al. used a commercial Wi-Fi dongle
and modiﬁed its ﬁrmware to implement a constant jamming
attack. To do so, they disabled the CSMA protocol, backoff
mechanism, and ACK waiting time. To enhance the jamming
effect, they also removed all interframe spaces and injected
many packets for transmissions.
Reactive Jamming Attacks: Reactive jamming attack is also
known as channel-aware jamming attack, in which a malicious
jammer sends an interfering radio signal when it detects legit-
imate packets transmitted over the air [43]. Reactive jamming
attacks are widely regarded as an energy-efﬁcient attack strat-
egy since the jammer is active only when there are data trans-
missions in the network. Reactive jamming attack, however,
requires tight timing constraints (e.g., < 1 OFDM symbols,
4 µs) for real-world system implementation because it needs
to switch from listening mode to transmitting mode quickly.
In practice, a jammer may be triggered by either channel


## --- Page 6 ---

### Section: II-B2 WiFi-Specific Jamming Attacks

6

energy-sensing or part of a legitimate packet’s detection (e.g.,
preamble detection). In [44], Prasad et al. implemented a
reactive jamming attack in legacy Wi-Fi networks using the
energy detection capability of cognitive radio devices. In [45],
[46], Yan et al. studied a reactive jamming attack where a
jammer sends a jamming signal after detecting the preamble
of the transmitted Wi-Fi packets. By doing so, the jammer
is capable of effectively attacking Wi-Fi packet payloads.
In [47], Schulz et al. used commercial off-the-shelf (COTS)
smartphones to implement an energy-efﬁcient reactive jammer
in Wi-Fi networks. Their proposed scheme is capable of
replying ACK packets to the legitimate transmitter to hijack its
retransmission protocol, thereby resulting in a complete Wi-Fi
packet loss whenever packet error occurs. In [48], Bayrak-
taroglu et al. evaluated the performance of Wi-Fi networks
under reactive jamming attacks. Their experimental results
showed that reactive jamming could result in a near-zero
throughput in real-world Wi-Fi networks. In [34], Vanhoef et
al. implemented a reactive jamming attack using a commercial
off-the-shelf Wi-Fi dongle. The device decodes the header of
an on-the-air packet to carry out the attack implementation,
stops receiving the frame, and launches the jamming signal.
Deceptive Jamming Attacks: In deceptive jamming attacks,
the malicious jamming device sends meaningful radio signals
to a Wi-Fi AP or legitimate Wi-Fi client devices, with the aim
of wasting a Wi-Fi network’s time, frequency, and/or energy
resources and preventing legitimate users from channel access.
In [49], Broustis et al. implemented a deceptive jamming
attack using a commercial Wi-Fi card. The results in [49]
showed that a low-power deceptive jammer could easily force
a Wi-Fi AP to allocate all the network’s resources for pro-
cessing and replying fake signals issued by a jammer, leaving
no resource for the AP to serve the legitimate users in the
network. In [50], Gvozdenovic et al. proposed a deceptive jam-
ming attack on Wi-Fi networks called truncate after preamble
(TaP) jamming and evaluated its performance on USRP-based
testbed. TaP attacker lures legitimate users to wait for a large
number of packet transmissions by sending them the packets’
preamble and the corresponding signal ﬁeld header only.
Random and Periodic Jamming Attacks: Random jamming
attack (a.k.a. memoryless jamming attack) refers to the type
of jamming attack where a jammer sends jamming signals for
random periods and turns to sleep for the rest of the time.
This type of jamming attack allows the jammer to save more
energy compared to a constant jamming attack. However, it
is less effective in its destructiveness compared to constant
jamming attack. Periodic jamming attacks are a variant of
random jamming attacks, where the jammer sends periodic
pulses of jamming signals. In [48], the authors investigated the
impact of random and periodic jamming attacks on Wi-Fi net-
works. Their experimental results showed that the random and
periodic jamming attacks’ impact became more signiﬁcant as
the duty-cycle of jamming signal increases. The experimental
results in [48] also showed that, for a given network throughput
degradation and jamming pulse width, the periodic jamming
attack consumes less energy than the random jamming attack.
It is noteworthy that, compared to the random jamming attack,
periodic jamming attack bears a higher probability of being

detected as it follows a predictable transmission pattern.
Frequency Sweeping Jamming Attacks: As discussed ear-
lier, there are multiple channels available for Wi-Fi communi-
cations on ISM bands. For a low-cost jammer, it is constrained
by its hardware circuit (e.g., very high ADC sampling rate
and broadband power ampliﬁer) in order to attack a large
number of channels simultaneously. Frequency-sweeping jam-
ming attacks were proposed to get around of this constraint,
such that a jammer can quickly switch (e.g., in the range of
10 µs) to different channels. In [51], Bandaru analyzed Wi-
Fi networks’ performance under frequency-sweeping jamming
attacks on 2.4 GHz, where there are only 3 non-overlapping
20 MHz channels. The preliminary results in [51] showed that
the sweeping-jammer could decrease the total Wi-Fi network
throughput by more than 65%.

2) WiFi-Speciﬁc Jamming Attacks: While the above jam-
ming attacks are generic and can apply to any type of wireless
network, the following jamming attacks are dedicated to the
PHY signal processing and MAC protocols of Wi-Fi networks.
Jamming Attacks on Timing Synchronization: As shown
in Fig. 5, timing synchronization is a critical component
of the Wi-Fi receiver to decode the data packet. Various
jamming attacks have been proposed to thwart the signal
timing acquisition and disrupt the start-of-packet detection
procedure, such as false preamble attack, preamble nulling
attack, and preamble warping attack [32], [52], [53]. These
attacks were sophisticatedly designed to thwart the timing
synchronization process at a Wi-Fi receiver. False preamble
attack [52], [53], also known as preamble spooﬁng, is a simple
method devised to falsely manipulate timing synchronization
output injecting the same preamble signal as that in legitimate
Wi-Fi packets. By doing so, a Wi-Fi receiver will not be
capable of decoding the desired data packet as it will fail in
the correlation peak detection. Preamble nulling attack [52],
[53] is another form of timing synchronization attacks. In this
attack, the jammer attempts to nullify the received preamble
energy at the Wi-Fi receiver by sending an inverse version of
the preamble sequence in the time domain. Preamble nulling
attack, however, requires perfect knowledge of the network
timing, so it is hard to be realized in real Wi-Fi networks.
Moreover, preamble nulling attack may have considerable er-
ror since the channels are random and unknown at the jammer.
Preamble warping attack [52], [53] designed to disable the
STF-based auto-correlation synchronization at a Wi-Fi receiver
by transmitting the jamming signal on the subcarriers where
STF should have zero data.
Jamming Attacks on Frequency Synchronization: For a
Wi-Fi receiver, carrier frequency offset may cause subcarri-
ers to deviate from mutual orthogonality, resulting in inter-
channel interference (ICI) and SNR degradation. Moreover,
carrier frequency offset may introduce an undesired phase
deviation for modulated symbols, thereby degrading symbol
demodulation performance. In [54], Shahriar et al. argued
that, under off-tone jamming attacks, the orthogonality of
subcarriers in an OFDM system would be destroyed. This idea
has been used in [55], where the jammer takes down 802.11ax
communications by using 20–25% of the entire bandwidth to
send an unaligned jamming signal. In Wi-Fi communications,


## --- Page 7 ---

7

Wi-Fi 
tranmsissions

Wi-Fi burst #1
Wi-Fi burst #2
Wi-Fi burst #L

#### OFDM sym #1

CP
CP
CP

Jamming 
transmissions
Time

OFDM sym #2
OFDM sym #N

Fig. 6: Illustration of a jamming attack targeting on OFDM
symbol’s cyclic preﬁx (CP) [61].

frequency offset in Wi-Fi communications is estimated by
correlating the received preamble signal in the time domain.
Then, the preamble attacks proposed for thwarting timing
synchronization can also be used to destroy the frequency
offset correction functionalities. In [56], two attacks have
been proposed to malfunction the frequency synchronization
correction: preamble phase warping attack and differential
scrambling attack. In the preamble phase warping attack, the
jammer sends a frequency shifted version of the preamble,
causing an error in frequency offset estimation at the Wi-
Fi receiver. Differential scrambling attack targets the coarse
frequency correction in Fig. 5, where STF is used to estimate
the carrier frequency. The jammer transmits interfering signals
across the subcarriers used in STF, aiming to distort the peri-
odicity pattern of the received preamble required for frequency
offset estimation.
Jamming Attacks on Channel Estimation: As shown in
Fig. 5, channel estimation and channel equalization are es-
sential modules for a Wi-Fi receiver. Any malfunction in their
operations is likely to result in a false frame decoding output.
A Wi-Fi receiver uses the received frequency-domain preamble
sequence to estimate the channel frequency response of each
subcarrier. A natural method to attack channel estimation and
channel equalization modules is to interfere with the preamble
signal. Per [52], [57], the preamble nulling attack can also be
used to reduce the channel estimation process’s accuracy. The
simulation results in [57] showed that, while preamble nulling
attacks are highly efﬁcient in terms of active jamming time and
power, they are incredibly signiﬁcant to degrade network per-
formance. However, it would be hard to implement preamble
nulling attacks in real-world scenarios due to the timing and
frequency mismatches between the jammer and the legitimate
target device. The impact of synchronization mismatches on
preamble nulling attacks has been studied in [58]. In [59]
and [60], Sodagari et al. proposed the singularity of jamming
attacks in MIMO-OFDM communication networks such as
802.11n/ac, LTE, and WiMAX, intending to minimize the rank
of estimated channel matrix on each subcarrier at the receiver.
Nevertheless, the proposed attack strategies require the global
channel state information (CSI) to be available at the jammer
to design the jamming signal.
Jamming Attacks on Cyclic Preﬁx (CP): Since most wireless
communication systems employ OFDM modulation at the
physical layer and every OFDM symbol has a CP, jamming
attacks on OFDM symbols’ CP have attracted many research
efforts. In [61], Scott et al. introduced a CP jamming attack,
where a jammer targets the CP samples of each transmitted

#### AP

User 1

NDPA
NDP

#### CBAF

#### SIFS

Time

User 2

User 3

#### BRPF

#### CBAF

#### BRPF

#### CBAF

SIFS
SIFS

#### SIFS

#### SIFS

#### SIFS

Fig. 7: The beamforming sounding protocol in 802.11 VHT
Wi-Fi networks.

OFDM symbol, as shown in Fig. 6. The authors showed
that the CP jamming attack is an effective and efﬁcient
approach to break down any OFDM communications such as
Wi-Fi. The CP corruption can easily lead to a false output of
linear channel equalizers (e.g., ZF and MMSE). Moreover, the
authors also showed that the CP jamming attack saves more
than 80% energy compared to constant jamming attacks to
pull down Wi-Fi transmissions. However, jamming attack on
CP is challenging to implement as it requires jammer to have
a precise estimation of the network transmission timing [32].
Jamming Attacks on MU-MIMO Beamforming: Given the
asymmetry of antenna conﬁgurations at an AP and its serving
client devices in Wi-Fi networks, recent Wi-Fi technologies
(e.g., IEEE 802.11ac and IEEE 802.11ax) support multi-user
MIMO (MU-MIMO) transmissions in their downlink, where
a multi-antenna AP can simultaneously serve multiple single-
antenna (or multi-antenna) users using beamforming technique
[37]. To design beamforming precoders (a.k.a. beamforming
matrix), a Wi-Fi AP requires to obtain an estimation of the
channels between its antennas and all serving users. Per
IEEE 802.11ac standard, the channel estimation procedure
in VHT Wi-Fi communications is speciﬁed by the following
three steps: First, the AP broadcasts a sounding packet to
the users. Second, each user estimates its channel using the
received sounding packet. Third, each user reports its channel
estimation results to the AP.

Fig. 7 shows the beamforming sounding protocol in VHT
Wi-Fi networks. The AP issues a null data packet announce-
ment (NDPA) in order to reserve the channel for channel
sounding and beamforming processes. Following the NDPA
signaling, the AP broadcasts a null data packet (NDP) as
the sounding packet. The users use the preamble transmitted
within the NDP to estimate the channel frequency response
on each subcarrier. Then, the Givens Rotations technique is
generally used to decrease the channel report overhead, where
a series of angles are sent back to the AP as the compressed
beamforming action frame (CBAF), rather than the original
estimated channel matrices. The AP uses beamforming report
poll frame (BRPF) to manage the report transmissions among
users.

In [62], Patwardhan et al. studied the VHT Wi-Fi beam-
forming vulnerabilities. They have built a prototype of a
radio jammer using a USRP-based testbed that jams the NDP
transmissions such that the users will no longer be able to
estimate their channels and then report false CBAFs. Their
experimental results showed that, in the presence of the NDP


## --- Page 8 ---

### Section: II-B3 A Summary of Jamming Attacks

8

#### TABLE III: A summary of existing jamming attacks in Wi-Fi networks.

Attacks
Ref.
Mechanism
Strngths
Weaknesses

Generic jamming attacks

[31], [33],
[34], [41], [42]
Constant jamming attack
Highly effective
Energy inefﬁcient

[43]–[46],
[34], [47], [48]
Reactive jamming attack
Highly effective
Energy efﬁcient
Hardware constraints

[49], [50]
Deceptive jamming attack
Energy efﬁcient
Less effective
[48]
Random and periodic jamming attack
Energy efﬁcient
Less effective
[51]
Frequency sweeping jamming attack
Highly effective
Energy inefﬁcient

Timing synchronization
attacks
[32], [52]

Preamble jamming attack
False preamble timing attack
Preamble nulling attack

High Effective
Energy-efﬁcient
High stealthy

Hard to implement
Tight timing synchronization required

Frequency synchronization
attacks

[54], [55]
Asynchronous off-tone jamming attack
Energy-efﬁcient
High stealthy
Less effective
[56]
Phase warping attack
Differential scrambling attack

Channel estimation
(pilot) attacks

[52], [58]
Pilot jamming attack
Energy-efﬁcient
High Effective
High stealthy

Hard to implement
Tight timing synchronization required
[57], [58]
Pilot nulling attack
[59], [60]
Singularity jamming attack

Cyclic preﬁx
attacks
[61]
Cyclic preﬁx (CP) jamming attack

Energy-efﬁcient
High effective
High stealthy

Hard to implement
Tight timing synchronization required

Beamforming attacks
[62]
NDP jamming attack
Energy-efﬁcient
Applies to 802.11ac/ax and beyond

MAC layer
jamming attacks

[63], [64]

CTS corruption jamming attack
ACK corruption jamming attack
Data corruption jamming attack
DIFS-wait jamming attack

Energy-efﬁcient
High Effective
High stealthy

Tight timing synchronization required

[65]
Fake RTS transmissions
[34]
Selﬁsh jamming attack
Rate adaption
algorithm attacks
[66]–[68]
Keeping the network throughout
below a threshold

Energy-efﬁcient
High stealthy
Less effective

jamming attack, less than 7% of packets could be successfully
beamformed in MU-MIMO transmission.

Jamming Attacks on MAC Protocols: A series of MAC-
layer jamming attacks, also called intelligent jamming attacks,
have been proposed in [63], [64], aiming to degrade Wi-Fi
communications’ performance. The main focus of intelligent
jamming attacks is on corrupting the control packets such as
CTS and ACK packets used by Wi-Fi MAC protocols. For
CTS attack, the jammer listens to the RTS packet transmitted
by an active node, waits a SIFS time slot from the end of
RTS, and jams the CTS packet. Failing to decode the CTS
packet can simply stop data communication. A similar idea
was proposed to attack ACK packet transmissions. As the
transmitter cannot receive the ACK packet, it retransmits the
data packet. Retransmission continues until the TCP limit is
reached or an abort is issued to the application. An intelligent
jamming attack can also target the data packet where the
jammer senses the RTS and CTS and sends the jamming signal
following a SIFS time slot.

Per [63], [64], DIFS wait jamming is another form of MAC-
layer attack, in which the jammer continuously monitors the
channel trafﬁc and sends a short pulse jamming signal when it
senses the channel idle for a DIFS period, aiming to cause an
interference for the next transmission. Also, per [65], MAC-
layer jamming attacks can be designed to keep the medium
busy, preventing other nodes from accessing the channel by
sending fake RTS packet to reserve the channel for the longest
possible duration. In [34], Vanhoef et al. implemented a selﬁsh
jamming attack in Wi-Fi networks using a cheap commercial
Wi-Fi dongle. The dongle’s ﬁrmware was particularly modiﬁed
to disable the backoff mechanism and shrink the SIFS time
window to implement the attack.

Algorithm Attacks on Rate Adaptation: In Wi-Fi networks,
rate adaptation algorithms (RAAs) were mainly designed to
make a proper modulation and coding scheme (MCS) selection
for data modulation. RRAs can be considered as a defense
mechanism to overcome lossy channels in the presence of low-
power interference and jamming signals. However, the pattern
designed for RRAs can be targeted by jammer to degrade the
network throughput below a certain threshold. RAAs change
the transmission MCS based on the statistical information of
the successful and failed decoded packets. The Automatic Rate
Fallback (ARF) [69], SampleRate [70], and ONOE [71] are
the main RAAs using in commercial Wi-Fi devices.

In [66], Noubir et al. investigated the RAAs’ vulnerabilities
against periodic jamming attacks. In [67] and [68], Orakcal
et al. evaluated the performance of ARF and SampleRate
RAAs under reactive jamming attacks. The simulation results
showed that, in order to keep the throughput below a certain
threshold in Wi-Fi point-to-point communications, higher RoJ
is required in ARF RAA compared to the SampleRate RAA,
where the RoJ is deﬁned as the ratio of the number of jammed
packets to the total number of transmitted packets. This reveals
that SampleRate RAA is more vulnerable to jamming attacks.

3) A Summary of Jamming Attacks: Table III summarizes
existing jamming attacks in WLANs. We hope such a table
will facilitate the audience’s reading and offer a high-level
picture of different jamming attacks.

C. Anti-Jamming Techniques

In this subsection, we review existing anti-jamming coun-
termeasures proposed to eliminate or alleviate the impacts of
jamming threats in WLANs. In what follows, we categorize the
existing anti-jamming techniques into the following classes:


## --- Page 9 ---

### Section: II-C1 Channel Hopping Techniques

9

channel hopping, MIMO-based jamming mitigation, coding
protection, rate adaptation, and power control. We note that,
given the destructiveness of jamming attacks and the complex
nature of WLANs, there are no generic solutions that can
tackle all types of jamming attacks.

1) Channel Hopping Techniques: Channel hopping is a
low-complexity technique to improve the reliability of wireless
communications under intentional or unintentional interfer-
ence. Channel hopping has already been implemented in
Bluetooth communications to enhance its reliability against
undesired interfering signals and jamming attacks. In [72],
Navda et al. proposed to use channel hopping to protect
Wi-Fi networks from jamming attacks. They implemented a
channel hopping scheme for Wi-Fi networks in a real-world
environment. The reactive jamming attack can decrease Wi-
Fi network throughput by 80% based on their experimental
results. It was also shown that, by using the channel hopping
technique, 60% Wi-Fi network throughput could be achieved
in the presence of reactive jamming attacks when compared to
the case without jamming attack. In [73], Jeung et al. used two
concepts of window dwelling and a deception mechanism to
secure WLANs against reactive jamming attacks. The window
dwelling refers to adjusting the Wi-Fi packets’ transmission
time based on the jammer’s capability. Their proposed de-
ception mechanism leverages an adaptive channel hopping
mechanism in which the jammer is cheated to attack inactive
channels.

2) Spectrum Spreading Technique: Spectrum spreading is
a classical wireless technique that has been used in several
real-world wireless systems such as 3G cellular, ZigBee, and
802.11b. It is well known that it is resilient to narrowband
interference and narrowband jamming attack. 802.11b employs
DSSS to enhance link reliability against undesired interference
and jamming attacks. It uses an 11-bit Barker sequence for
1 Mbps and 2 Mbps data rates, and an 8-bit complementary
code keying (CCK) for 5.5 Mbps and 11 Mbps data rates.
In [41], Karishma et al. evaluated the resiliency of DSSS
in 802.11b networks against broadband, constant jamming
attacks through simulation and experiments. Their simulation
results show that the packet error rate hits 100% when SJR
< −3 dB for 1 Mbps data rate, when SJR < 0 dB for
2 Mbps data rate, when SJR < 2 dB for 5.5 Mbps data
rate, and when SJR < 5 dB for 11 Mbps data rate. Their
experimental results show that an 802.11b Wi-Fi receiver fails
to decode its received packets when received SJR < −7 dB
for 1 Mbps data rate, when SJR < −4 dB for 2 Mbps data
rate, when SJR < −1 dB for 5.5 Mbps data rate, and when
SJR < 2 dB for 11 Mbps data rate. In addition, [74] evaluated
the performance of 11 Mbps 802.11b DSSS communications
under periodic and frequency sweeping jamming attacks. The
results show that 802.11b is more resilient against periodic
and frequency sweeping jamming attacks compared to OFDM
802.11g.
3) MIMO-based Jamming Mitigation Techniques: Recently,
MIMO-based jamming mitigation techniques emerge as a
promising approach to salvage wireless communications in the
face of jamming attacks. In [45], [46], Yan et al. proposed
a jamming-resilient wireless communication scheme using

MIMO technology to cope with the reactive jamming attacks
in OFDM-based Wi-Fi networks. The proposed anti-jamming
scheme employs a MIMO-based interference mitigation tech-
nique to decode the data packets in the face of jamming signal
by projecting the mixed received signals into the subspace
orthogonal to the subspace spanned by jamming signals.
The projected signal can be decoded using existing channel
equalizers such as zero-forcing technique. However, this anti-
jamming technique requires the knowledge of channel state
information of both the desired user and jammer. Convention-
ally, a user’s channel can be estimated in this case because
the reactive jammer starts transmitting jamming signals in the
aftermath of detecting the preamble of a legitimate packet.
Therefore, the user’s received preamble signal is not jammed.
Moreover, it is shown in [45] that the complete knowledge of
the jamming channel is not necessary, and the jammer’s chan-
nel ratio (i.e., jammer’s signal direction) sufﬁces. Based on
this observation, the authors further proposed inserting known
pilots in the frame and using the estimated user’s channel to
extract the jammer’s channel ratio. In [75], a similar idea called
multi-channel ratio (MCR) decoding was proposed for MIMO
communications to defend against constant jamming attacks.
In the proposed MCR scheme, the jammer’s channel ratio is
ﬁrst estimated by the received signals at each antenna when
the legitimate transmitter stays silent. The jammer’s channel
ratio and the preamble in the transmitted frame are then used
to estimate the projected channel component, which are later
deployed to decode the desired signal.

While it is not easy to estimate channel in the presence
of an unknown jamming signal, research efforts have been
invested in circumventing this challenge. In [76], Zeng et
al. proposed a practical anti-jamming solution for wireless
MIMO networks to enable legitimate communications in the
presence of multiple high-power and broadband radio jamming
attacks. They evaluated their proposed scheme using real-
world implementations in a Wi-Fi network. Their scheme ben-
eﬁts from two fundamental techniques: A jamming-resilient
synchronization module and a blind jamming mitigation equal-
izer. The proposed blind jamming mitigation module is a
low-complex linear spatial ﬁlter capable of mitigating the
jamming signals from unknown jammers and recovering the
desired signals from legitimate users. Unlike the existing
jamming mitigation algorithms that rely on the availability
of accurate jamming channel ratio, the algorithm does not
need any channel information for jamming mitigation and
signal recovery. Besides, a jamming-resilient synchronization
algorithm was also crafted to carry out packet time and
frequency recovery in the presence of a strong jamming
signal. The proposed synchronization algorithm consists of
three steps. First, it alleviates the received time-domain signal
using a spatial projection-based ﬁlter. Second, the conventional
synchronization techniques were deployed to estimate the start
of frame and carrier frequency offset. Third, the received
frames by each antenna were synchronized using the estimated
frequency offset. The proposed scheme was validated and
evaluated in a real-world implementation using GNURadio-
USRP2. It was shown that the receiver could successfully
decode the desired Wi-Fi signal in the presence of 20 dB


## --- Page 10 ---

### Section: II-C4 Coding Techniques

10

stronger than the signals of interest.

4) Coding Techniques: Channel coding techniques are orig-
inally designed to improve the communication reliability in
unreliable channels. In [77] and [78], the performance of
low-density parity codes (LDPC) and Reed-Solomon codes
were analyzed for different packet sizes under noise (pulse)
jamming attacks with low duty cycle. It was shown that, for
long size packets (e.g., a few thousand bits), LDPC coding
scheme is a suitable choice as it can achieve throughput close
to its theoretical Shannon limit while bearing a low decoding
complexity.

5) Rate Adaptation and Power Control Techniques: Rate
adaptation and power control mechanisms are proposed to
combat jamming attacks, provided that wireless devices have
sufﬁcient power supply and the jamming signal’s power is
limited. In [66], a series of rate adaptation algorithms (RAAs)
were proposed to provide reliable and efﬁcient communication
scheme for Wi-Fi networks. Based on channel conditions,
RAAs set a data rate such that the network can achieve the
highest possible throughput. Despite the differences among
existing RAAs, all RAAs trace the rate of successful packet
transmissions and may increase or decrease the data rate
accordingly. A power control mechanism is another technique
that can be used to improve wireless communication perfor-
mance over poor quality links caused by interference and
jamming signals. However, the power control mechanisms
are highly subjected to the limit of power budget available
at the transmitter side. Clearly, rate adaptation and power
control techniques will not work in the presence of high power
constant jamming attacks.

In [79], [80], Pelechrinis et al. studied the performance
of these two techniques (rate adaptation and power control)
in jamming mitigation for legacy Wi-Fi communications via
real-world experiments. It was shown that the rate adaptation
mechanism is generally effective in lossy channels where the
desired signal is corrupted by low-power interference and jam-
ming signals. When low transmission data rates are adopted,
the jamming signal can be alleviated by increasing the transmit
power. Nevertheless, power control is ineffective in jamming
mitigation at high data rates. In [81], a randomized RAA
was proposed to enhance rate adaptation capability against
jamming attacks. The jammer attack was designed to keep the
network throughput under a certain threshold, as explained
earlier in RAA attacks. The main idea of this scheme lies in
an unpredictable rate selection mechanism. When a packet is
successfully transmitted, the algorithm randomly switches to
another data rate with a uniform distribution. The proposed
scheme shows higher reliability against this class of attacks.
The results in [81] show that a jammer aiming to pull down
network throughput below 1 Mbps will need to transmit a
periodic jamming signal with 3× more energy in order to
achieve the same performance when legacy ARF algorithm
applies.

In [49], an alternative approach was proposed for RAAs to
cope with low-power jamming attacks using packet fragmenta-
tion. Although the smaller-sized packet transmissions induce
more considerable overhead to the network, it can improve
communications reliability under periodic and noise jamming

Cellular phone or IoT

Radio jammer

Cellular tower

Cellular signal

Jamming signal

Fig. 8: Jamming attack in a cellular network.

attacks by reducing each packet’s probability of being jammed.
In [82], Garcia et al. borrowed the concept of cell breathing
in cellular networks and deployed it in dense WLANs for
jamming mitigation purposes. Here, cell breathing refers to
the dynamic power control for adjusting an AP’s transmission
range. That is, an AP decreases its transmission range when
bearing a high load and increases its transmission range when
bearing a light load. Meanwhile, load balancing was proposed
as a complementary technique to cell breathing. For a WLAN
with cell breathing capability, the jamming attack can be
treated as a case with a high load imposed on target APs
[82].

6) Jamming Detection Mechanisms: In [83], Pu˜nal et al.
proposed a learning-based jamming detection scheme for Wi-
Fi communications. The authors used the parameters of noise
power, the time ratio of channel being busy, the time interval
between two frames, the peak-to-peak signal strength, and
the packet delivery ratio as the training dataset, and used the
random forest algorithm for classiﬁcation. The performance
of the proposed scheme was evaluated under constant and
reactive jamming attacks. The simulation results show that
the proposed scheme could detect the presence of jammer
with 98.4% accuracy for constant jamming and with 94.3%
accuracy for reactive jamming.

7) A Summary of Anti-Jamming Techniques:
Table IV
summarizes existing anti-jamming techniques designed for
WLANs.

#### III. JAMMING AND ANTI-JAMMING ATTACKS IN

#### CELLULAR NETWORKS

Although cellular networks have been evolving for more
than four decades, existing cellular wireless communications
are still vulnerable to jamming attacks. The vulnerability can
be mainly attributed to the lack of practical yet efﬁcient anti-
jamming techniques at the wireless PHY/MAC layer that are
capable of securing radio packet transmissions in the presence
of jamming signals. The vulnerability also underscores the
critical need for an in-depth understanding of jamming attacks
and for more research efforts on the design of efﬁcient anti-
jamming techniques. In this section, we consider a cellular
network under jamming attacks, as shown in Fig. 8. We ﬁrst


## --- Page 11 ---

### Section: III-A A Primer of Cellular Networks

11

#### TABLE IV: A summary of anti-jamming techniques for WLANs.

Anti-jamming technique
Ref.
Mechanism
Application Scenario
Channel hopping
techniques

[72]
Channel hopping scheme for Wi-Fi networks
All jamming attacks on a channel
[73]
Window dwelling and adaptive channel hopping
Reactive jamming attack on a channel

DSSS techniques
[41], [74]
802.11b performance evaluation
Constant, periodic, and
frequency-sweeping jamming attacks

MIMO-based
techniques

[45], [46]
Mixed received signals projection onto the subspace
orthogonal to the jamming signal.
Reactive jamming attack

[75]
Multi-channel ratio (MCR) decoding
Constant jamming attack

[76]
Blind jamming mitigation and jamming-resilient
synchronization
Constant jamming attack

Coding techniques
[77], [78]
LDPC and Reed-Solomon code schemes’ analysis
Low-power random jamming attack

Rate adaptation and
power control techniques

[79], [80]
Rate adaptation and power control mechanism evaluation
Random and periodic jamming attacks
[81]
Randomized rate adaptation algorithm
Reactive jamming attacks
[49]
Packet fragmentation
Low-power random jamming attack
[82]
Cell breathing and load balancing concepts
Low-power constant jamming attack
Detection mechanisms
[83]
Multi-factor learning-based algorithm
Constant and reactive jamming attacks

provide a primer of cellular networks, focusing on long-term
evolution (LTE) systems. Then, we conduct an in-depth review
on existing jamming attacks and anti-jamming strategies at the
PHY/MAC layers of cellular networks.

A. A Primer of Cellular Networks

Cellular networks have evolved from the ﬁrst generation
toward the ﬁfth-generation (5G). While 5G is still under con-
struction, we focus our overview on 4G LTE/LTE-advanced
cellular networks. Generally speaking, the jamming attacks
in 4G LTE networks can also apply to 5G networks as they
share the same wireless technologies at the PHY/MAC layers.
4G LTE/LTE-advanced has been widely adopted by mobile
network operators to provide wide-band, high throughput, and
extended coverage services for mobile devices. Due to its
success in mobile networking, the LTE framework is now
known as the primary reference scheme for future cellular
networks such as 5G. LTE supports channel bandwidth from
1.4 MHz to 20 MHz in licensed frequency spectrum and
targets 100 Mbps peak data rate for downlink transmissions
and 50 Mbps peak data rate for uplink transmissions. LTE was
designed to support both TDD and FDD transmission schemes
for further spectrum ﬂexibility. It uses OFDM modulation
scheme in downlink and SC-FDMA (DFTS-OFDM) in uplink
transmissions.

In what follows, we will overview the PHY and MAC layers
of LTE, including its downlink/uplink time-frequency resource
grid, the uplink/downlink transceiver structure, and the random
access procedure.
LTE Downlink Resource Grid: Fig. 9 shows a portion of
LTE downlink resource grid for 5 MHz channel bandwidth.
The frame is of 10 ms time duration in the time domain and
includes ten equally-sized 1 ms subframes. Each subframe
consists of two time slots, each composed of seven (or six)
OFDM symbols. In the frequency domain, a generic subcarrier
spacing is set to 15 KHz. Every 12 consecutive subcarriers
(180 KHz) in one time slot are grouped as one physical
resource block (PRB). Depending on the channel bandwidth
(i.e., FFT size), the frame may have 6 ≤PRB ≤110. The
LTE downlink resource grid shown in Fig. 9 carries multiple
physical channels and signals for different purposes [84],
which we elaborate as follows.

#### RB 0

#### RB 1

#### RB 2

RB 24
Subframe 0

Slot 1
Slot 0

Subframe 9

Slot 1
Slot 0

#### RB 9

#### RB 10

Subframe 1

Slot 1
Slot 0

5 MHz

RS
PDCCH
PDSCH
PBCH
SSS
PSS

Fig. 9: LTE downlink resource grid [85].

• Synchronization signals consist of primary synchroniza-
tion signal (PSS) and secondary synchronization signal
(SSS), both of which are used for UE frame timing
synchronization and cell ID detection.

• Reference signals (a.k.a. pilot signals) are used for chan-
nel estimation and channel equalization. There are 504
predeﬁned reference signal sequences in LTE, each cor-
responding to a 504 physical-layer cell identity. Different
reference signal sequences are used in neighbor cells.

• Physical downlink shared channel (PDSCH) is the pri-
mary physical downlink channel and is used to carry user
data. The main part of the system information, known as
system information blocks (SIBs), required for random
access procedure is also transmitted using PDSCH.

• Physical downlink control channel (PDCCH) is used
to transmit downlink control information (DCI), which
carries downlink scheduling decisions and power control
commands.

• Physical broadcast channel (PBCH) carries the system
information called master information block (MIB), in-
cluding downlink transmission’s bandwidth, PHICH con-
ﬁguration, and the number of transmit antennas. PBCH
is always transmitted within the ﬁrst 4 OFDM symbols
of the second slot in subframe 0 and mapped to the six
resource blocks (i.e., 72 subcarriers) centered around DC
subcarrier.

LTE Uplink Resource Grid: To conserve mobile devices’
energy consumption, LTE employs single carrier frequency
division multiple access (SC-FDMA) for uplink data trans-
mission. Compared to OFDM modulation, SC-FDMA mod-
ulation renders a better PAPR performance and provides a


## --- Page 12 ---

12

Slot 1
Slot 0
Slot 1
Slot 0

#### RB 0

#### RB 1

#### RB 2

#### RB 24

#### RB 9

#### RB 10

5 MHz

1 Subframe
1 Subframe

PUCCH
PUSCH
PRACH
DRS
SRS

Slot 0

Fig. 10: LTE uplink resource grid.

better battery lifetime for mobile devices. Fig. 10 shows the
resource grid for uplink transmission. Most of the physical
transport channels and the signal processing blocks in an LTE
transceiver are common for uplink and downlink. In what
follows, we focus only on their differences:

• Demodulation reference signals (DRS) are used for uplink
channel estimation.

• Sounding reference signals (SRS) are transmitted for the
core network to estimate channel quality for different
frequencies in the uplink transmissions.

• Physical uplink shared channel (PUSCH) is the primary
physical uplink channel used for data transmission and
UE-speciﬁc higher layer information.

• Physical uplink control channel (PUCCH) is used to
acknowledge the downlink transmission. It is also used
to report the channel state information for downlink
channel-dependent transmission and request time and
frequency resources required for uplink transmission.

• Physical random access channel (PRACH) is used by the
UE for the initial radio link access.
LTE Downlink Transceiver Structure: Fig. 11(a) shows
the signal processing block diagram used for PDSCH trans-
mission. PDSCH is the main downlink physical channel,
which carries user data and system information. The transport
block(s) to be transmitted are delivered from the MAC layer.
Legacy LTE can support up to two transport blocks in parallel
for downlink transmission. For each transport block, the signal
processing chain consists of CRC attachment, code block seg-
mentation, channel coding, rate matching, bit-level scrambling,
data modulation, antenna mapping, resource block mapping,
OFDM modulation, and carrier up-conversion. CRC is at-
tached for error detection in received packets at the receiver
side. Code block segmentation segments an over-lengthed code
block into small-size fragments matched to the given block
sizes deﬁned for Turbo encoder. It is particularly applied when
the transmitted code block exceeds 6,144 bits. Turbo coding
is used for error correction. Rate matching is applied to select
the exact number of bits required for each packet transmission.
The scrambled codewords are mapped into corresponding
complex symbol blocks. Legacy LTE can support QPSK,
16QAM, 64QAM, and 256QAM, corresponding to two, four,
six, and eight bits per symbol, respectively. The modulated
codeword(s) are mapped into different predeﬁned antenna
port(s) for downlink transmission. Antenna port conﬁgura-
tion can be set such that it realizes different multi-antenna

schemes, including spatial multiplexing, transmit diversity,
or beamforming. Codeword(s) can be transmitted on up to
eight antenna ports using spatial multiplexing. For transmit
diversity, only one codeword is mapped into two or four
antenna ports. The symbols are assigned to the corresponding
PDSCH resource units, as illustrated in Fig. 9. The other
physical channels and signals are then added to the resource
grids. The resource grids on each antenna port are injected
through the OFDM modulation and then up-converted to the
carrier frequency and transmitted over the air.

Fig. 11(b) shows the signal processing block diagram of
a receiver for downlink frame reception. It comprises syn-
chronization, OFDM demodulation, channel estimation and
equalization, and data extraction blocks. We elaborate on them
as follows.

• Synchronization: PSS and SSS are used for detecting the
start of a frame and searching for the cell ID. Particularly,
the received signal is cross-correlated with PSS to ﬁnd the
PSS and SSS positions. A SSS cross-correlation is later
performed to ﬁnd the cell ID. LTE uses the CP, which is
appended to the end of every OFDM symbol, to estimate
carrier frequency offset in the time domain.

• OFDM Demodulation: OFDM demodulation is per-
formed to transform the received signals from the time
domain to the frequency domain, where the resource grid
is constructed for further process.

• Channel Estimation: Channel estimation is performed by
leveraging the reference signals embedded in the resource
grid. Speciﬁcally, it is done by the following three steps:
i) the received reference signals are extracted from the
received resource grid; ii) least square or other method
is used to estimate the channel frequency responses at
the reference positions in the resource grid; and iii) the
estimated channels are interpolated using an averaging
window, which can apply to the time domain, the fre-
quency domain, or both of the resource grid.

• Channel equalization: The estimated channel is used to
equalize the received packet. Minimum mean square error
(MMSE) or zero-forcing (ZF) are the most two equalizers
used in cellular systems. For the MMSE equalizer, it is
also required to take the noise power into account as well.
The noise power is estimated by calculating the variance
between original and interpolated channel coefﬁcients on
the pilot subcarriers. Compared to the MMSE equalizer,
the ZF equalizer does not require the knowledge of noise
power. It tends to offer the same performance as MMSE
equalizer in the high SNR scenario.

PDSCH is extracted from the received resource grid and
demodulated into bits. The received bits are then fed into the
reverse process of PDSCH in order to recover the transport
data.
LTE Uplink Transceiver Structure: In the uplink, the scram-
bled codewords are mapped into QPSK, 16QAM, or 64QAM
modulated blocks. The block symbols are divided into sets
of M modulated symbols, where each set is fed into DFT
operation with the length of M. Finally, physical channels
and reference signals are mapped into resource blocks, as


## --- Page 13 ---

### Section: III-B Jamming Attacks

13

CRC
Turbo coding
Code block 
segmentation
Scrambling
Modulation

Resource grid

mapping

Rate 
matching
Transport

block

n

All other downlink physical

channels and signals

OFDM 
modulation
DAC
RF front

end

n
n
n
n

m
m
m
m
m
m
m
Layer 
mapping
Precoding
n

(a)

OFDM 
demodulation

Channel 
estimation
Frame timing 
synchronization

Frequency offset

estimation

ZF/MMSE 
equalization
Layer 
demapping

ADC
RF front

end

PDSCH 
extraction
Demodulaion
CRC 
check

Turbo 
decoding
Descrambling
Transport

block

p
p
p
p
p
p
p

p
p
m
m
m
m
m

Interpolation
Noise 
estimation
p

m

(b)

Fig. 11: (a) The schematic diagram of downlink LTE PDSCH signal processing. (b) The schematic diagram of a LTE receiver
to decode PDSCH signal. (n ≤8, m ≤2, and p ≤4)

illustrated in Fig. 10, and fed into the OFDM modulator.
The uplink receiver structure is similar to that of PDSCH
decoding in the downlink except that the frequency and symbol
synchronizations to the cell and frame timing of the cell are
performed in the cell search procedure.
LTE Random Access Process: Before an LTE user can
initiate the random access procedure with the network, it has
to synchronize with a cell in the network and successfully
receive and decode the cell system information. LTE users
can acquire the cell’s frame timing and determine the cell ID
using PSS and SSS synchronization signals transmitted within
the downlink resource grid, as illustrated in Fig. 9. PDSCH
and PBCH carry system information in the downlink resource
grid. Once the system information is successfully decoded,
the user can communicate with the network throughout the
random access procedure. The basic steps in the random access
procedure have been illustrated in Fig. 12. In the ﬁrst step,
the LTE user transmits the random access preamble (i.e.,
PRACH in uplink resource grid as illustrated in Fig. 10) for
uplink synchronization. It allows the eNodeB to estimate the
transmission timing of the user. In the second step, the eNodeB
responds to the preamble transmission by issuing an advanced
timing command to adjust uplink timing transmission based
on the delay estimated in the ﬁrst step. Moreover, the uplink
resources required for the user in the third step are provided
in this step. In the third step, the user transmits the mobile-
terminal identity to the network using the UL-SCH resources
assigned in the second step. In the fourth and ﬁnal step, the
network transmits a contention-resolution message to the user
using DL-SCH.

B. Jamming Attacks

With the above knowledge of LTE networks, this section
dives into the review of malicious jamming attacks in cellular
networks. A jammer may attempt to disrupt cellular wireless
communications either using generic jamming attacks (see

User
eNodeB
Synchronized to the cell 
through cell search process

Random access preamble

Random access response

#### RRC signaling

Uplink timing

adjusment

User data

#### RRC signaling

Fig. 12: Illustration of random access process in cellular
networks.

Section II-B) or using cellular-speciﬁc jamming attack strate-
gies.

In [86], Romero et al. studied the performance of LTE
uplink transmission under a commercial frequency-sweeping
jamming attack. The authors conducted experiments to evalu-
ate the sensitivity of uplink reference signal when the jammer
sweeps the 20 MHz channel within T microseconds, where
T ∈[1, 200]. The EVM of uplink demodulation reference
signal was measured at the receiver and used as the perfor-
mance metric. The experimental results show that, for a given
signal-to-jamming ratio (SJR), a jammer with T ∈[20, 40] is
least destructive (yielding highest EVM), while a jammer with
T ∈[160, 200] is most destructive (yielding lowest EVM).

In [87] and [88], Zorn et al. proposed an intelligent jamming
attack for WCDMA cellular networks, with the aim of forcing


## --- Page 14 ---

### Section: III-B1 Jamming Attacks on Synchronization

14

a victim user to switch from WCDMA to GSM service. To
do so, the jammer sends interfering signal to degrade the
SNR of WCDMA cell primary common pilots. The authors
argued that, if the SNR of WCDMA CPCPCH is below a
certain threshold, the user will leave the WCDMA to use GSM
service. Through experiments, the authors show that 37 dBm
jamming power is sufﬁcient to force a user leave WCDMA to
join GSM service.

As we discussed earlier in section III-A, the PHY layer
of LTE is made up of several physical signals and channels
that carry speciﬁc information throughout the downlink and
uplink resource grid to provide reliable and interference-
free communications between eNodeB and users within a
cell. In what follows, we focus on cellular-speciﬁc jamming
attacks that target on PHY-layer downlink/uplink signaling and
channels of cellular networks.

1) Jamming Attacks on Synchronization: In cellular net-
works, synchronization signals, PSS and SSS, are critical for
the cell search process, through which a user can obtain the
frequency synchronization to a cell, the frame timing of the
cell, and the physical identity of the cell. An LTE user must
perform a cell search before initializing the random access
procedure, and the cell search is also performed for cell
reselection and handover. In FDD LTE networks, synchro-
nization signals are transmitted within the last two OFDM
symbols of the ﬁrst time slot of subframe 0 and subframe
5, as illustrated in Fig. 9. Once a user decodes PSS, it will
ﬁnd the cell’s timing, the two positions of SSS, and partial
information of cell identity. Then, SSS is used to acquire frame
timing (start of packet) and determine cell identity. Once cell
identity is obtained, the user becomes aware of the reference
signals and their positions within the resource grid used in
downlink transmission. This information allows the user to
perform channel estimation and extract the system information
by decoding PBCH and PDSCH.

Clearly, the synchronization process is critical in cellular
networks. If a user fails to detect the synchronization signals,
it cannot conduct the cell search process and cannot access
it. The synchronization process is, however, vulnerable to
jamming attacks. In [89], Krenz et al. studied jamming attack
on synchronization signals and PBCH. The authors studied the
LTE network under such jamming attacks where the jammer
interferes with the bandwidth portions occupied by synchro-
nization signals. In [90] and [91], Litchman et al. investigated
the vulnerabilities of LTE networks to synchronization signals
spooﬁng attack, where the jammer intentionally sends fake
PSS and SSS signals to lure the LTE user. The authors claim
that the synchronization signals spooﬁng attack is an efﬁcient
denial-of-service attack in cellular networks by the following
two arguments. First, synchronization signals occupy a small
fraction of the downlink resource grid (e.g., < 0.7% of the
total resource grid in 5 MHz channel bandwidth) to carry
information. That means the jammer entails very low air trans-
missions to jam the synchronization signals. Second, per [84],
once the LTE user receives the fake synchronization signals, it
will decode the PBCH to acquire the master information block
(MIB). If the user fails to receive MIB, it believes the cell is
out of service and selects the most robust neighboring cell in

the same channel, thereby degrading the network performance.

2) Jamming Attacks on PDCCH and PUCCH: PDCCH and
PUCCH are critical control channels in cellular networks, and
their vulnerability to jamming attacks have been investigated.
In [92], Aziz et al. considered PDCCH and PUCCH as
potential physical channels that a smart jammer may target
to interrupt since they carry critical control information on
downlink and uplink resource allocations. Before a jammer
can attack the PDCCH, it requires to decode the physical
control format indicator channel (PCFICH) that determines the
position of the PDCCH resource elements within the downlink
frame. In [93], Kakar et al. studied PCFICH jamming attacks.
Control format indicator (CFI) is a two-digit binary data
encoded into 32 bits codeword and modulated into 16 QPSK
symbols and mapped into 16 sparse resource elements within
the downlink resource grid. It was argued in [93] that the
jamming attack on PCFICH is an efﬁcient and effective
jamming strategy in LTE networks because PCFICH occupies
only a small fraction of the downlink resource grid and carries
vital information on PDCCH resource allocations. That means
the user will no longer be able to decode the PDCCH and
suffer from a denial of service when jamming the PCFICH.
In [94], Lichtman et al. analyzed the physical uplink control
channel (PUCCH) vulnerabilities against jamming attacks. The
authors argued that a jammer could simply attack PUCCH
only by learning the LTE channel bandwidth since PUCCH
is transmitted on the uplink resource grid’s edge. That means
the PUCCH highly susceptible to jamming attacks as their
locations within the resource grid is ﬁx and predictable for a
malicious attacker.

3) Jamming Attacks on PDSCH and PUSCH: PDSCH and
PUSCH carry user data and upper-layer network information
and dominate the major available resources in downlink and
uplink transmissions, respectively. In [90], Litchman et al.
investigated the vulnerability of PDSCH and PUSCH under
jamming attacks. However, the jamming attacks on PDSCH
and PUSCH require the synchronization to the cell and a
prior knowledge of control information and cell ID. In [95],
Girke et al. implemented a PUSCH jamming attack using
srsLTE testbed for a smart grid infrastructure and evaluated
uplink throughput for different jamming gains. The results in
[95] show that the total number of received packets reduces
approximately by 90% under jamming signal 35 dB stronger
than PUSCH signal.

4) Jamming Attacks on PBCH: PBCH is used to carry
MIB information in downlink required for LTE users to initial
random access process. MIB conveys the information on
downlink cell bandwidth, PHICH conﬁguration, and system
frame number (SFN) required at the user side for packet
reception and data extraction. PBCH is transmitted only within
the ﬁrst subframe and mapped to the central 72 subcarriers
regardless of channel bandwidth. In [90] and [91], PBCH
jamming attack was introduced as an effective and efﬁcient
adversary attack to the LTE PHY-layer communications. This
is because the PBCH carries essential system information
for the user and occupies a limited portion of the resource
elements (i.e., < 0.7%) in the downlink resource grid [99].
PBCH jamming attack prevents LTE users from performing


## --- Page 15 ---

### Section: III-B5 Jamming Attacks on PHICH

15

#### TABLE V: A summary of existing jamming attacks for cellular networks.

Attacks
Ref.
Mechanism
Strength
Weakness
Generic jamming
attacks
[86]
Frequency-sweeping jamming attack
Easy to implement
High effective

Energy-inefﬁcient
Less stealthy
WCDMA CPCPCH
jamming attacks
[87], [88]
Forcing a user to leave WCDMA RAN and
switch to GSM by interfering the CPCPCH signal

Energy-efﬁcient
High stealthy

Cell synchronization required
Less effective
Synchronization
signals jamming
attacks

[89]
PSS and SSS corruption jamming attack
Energy-efﬁcient
High effective
High stealthy

Tight timing constraint
[90], [91],
[32], [52]
synchronization signals’ spooﬁng attack

PDCCH/PUCCH
jamming attacks

[92]
Downlink control information (DCI) jamming attack
Energy-efﬁcient
High effective
High stealthy

cell synchronization required
[93]
Control format indicator (CFI) jamming attack
[94]
Uplink control channel attack
PDSCH/PUSCH
jamming attacks
[90], [95]
User data corruption jamming attack
System information block (SIB) jamming attack
High effective
Energy-inefﬁcient
cell synchronization required

PBCH jamming
attacks
[89]–[91]
Master information block (MIB) jamming attack

Energy-efﬁcient
High effective
High stealthy

cell synchronization required

PHICH jamming
attacks
[90]
Hybrid-ARQ acknowledgement bit jamming attack

energy-efﬁcient
High effective
High stealthy

cell synchronization required

Reference signal
jamming attacks

[90]–[92]
Reference signal jamming attack
Energy-efﬁcient
High Effective
High stealthy

cell synchronization required
[57]
Reference signal nulling attack

[59], [60]
Singularity jamming attack in MIMO-OFDM
communications

Random access
attacks
[96]–[98]
PRACH, handover and link re-establishing jamming attack

Energy-efﬁcient
High Effective
High stealthy

cell synchronization required

their random access process. This may lead LTE users to
switch to neighbor cells [99]. In [89], Krenz et al. evaluated
the network’s performance under the PBCH jamming attack
using a real-world system implementation. Their experimental
results show that the LTE communications can be blocked
when the jamming signal is 3 dB stronger than the desired
signal at LTE receivers.

5) Jamming Attacks on PHICH: Physical hybrid automatic
repeat request (ARQ) indicator channel (PHICH) is used to
carry hybrid-ARQ ACKs and NACKs in response to PUSCH
transmissions. The hybrid-ARQ acknowledgment is a single
bit of information (i.e.,‘1’ stands for ACK and ‘0’ stands for
NACK). The bit is further repeated three times, modulated by
BPSK, and spread with an orthogonal sequence to minimize
the error probability of the acknowledgment detection. PHICH
occupies a small portion of the downlink resource grid (e.g.,
≤0.3% in 10 MHz channel bandwidth). In [90], Lichtman et
al. introduced a jamming attack on PHICH, where a jammer
attacks the logic of ACK/NACK bit in order to degrade
the network performance by wasting the resources for false
retransmission requests.

6) Jamming Attacks on Reference Signal: Reference sig-
nals are transmitted within the frame for channel estimation
purposes. Downlink reference signals (pilots) are generated
using a pseudo-random sequence in the frequency domain,
followed by a quadrature phase shift keying (QPSK) mod-
ulation scheme. The reference signals in the LTE downlink
resource grid are transmitted on a subset of predeﬁned sub-
carriers. The estimated channel responses for the subcarriers
carrying reference signals are later interpolated for the entire
bandwidth.

In [90]–[92], the authors introduced potential jamming
attack on cell-speciﬁc reference signals. The LTE user under
reference signals jamming attack will fail to demodulate the
physical downlink channels transmitted within the downlink

resource grid. Moreover, it will lose its initial synchronization
to the cell and fail to perform the handover process [92].
However, a jamming attack on reference signals requires prior
knowledge of the cell identity to determine the resource grid’s
reference signals’ position.

In [57], Clancy et al. proposed a reference signal nulling
attack (a.k.a. pilot nulling attack). This attack attempts to force
the received energy at the pilot OFDM samples (i.e., reference
signal resource elements) to zero, thereby disabling channel
estimation capability at cellular networks. In [59] and [60],
Sodagari et al. studied pilot jamming attack in MIMO-OFDM
communications, where their main goal is to design jamming
signal so that the estimated channel matrix at a cellular receiver
is rank-deﬁcient and, as a result, the channel matrix will no
longer be invertible. This prevents the cellular receiver from
correctly equalizing the received resource grid.

7) Jamming Attacks on Random Access: An LTE user can
establish a radio connection to a cellular base station by
using a random access procedure, provided that it correctly
performs cell search as explained in Section III-A. In [96]–
[98], jamming attacks on PRACH were introduced as one of
the critical PHY-layer vulnerabilities in LTE networks. The
jamming attacks on random access channels will cause DoS
by preventing LTE users from connecting to the network
or reestablishing the link in a handover process. However,
neither theoretical analysis nor experimental measurements
were presented for PRACH jamming attacks.

8) A Summary of Jamming Attacks: Table V presents a
summary of existing jamming attacks that were delicately
designed for cellular networks. The table also outlines the
primary mechanism, strength, and weakness of each jamming
attack.


## --- Page 16 ---

### Section: III-C Anti-Jamming Techniques

16

C. Anti-Jamming Techniques

In the presence of security threats from existing and po-
tential jamming attacks, researchers have been studying anti-
jamming strategies to thwart jamming threats and secure
cellular wireless services. In what follows, we survey existing
anti-jamming strategies and present a table to summarize the
state-of-the-art jamming defense mechanisms.

1) MIMO-based Jamming Mitigation Techniques: The anti-
jamming strategies, such as the ones originally designed for
WLANs in [45], [46], [75], [76], can also be applied to
secure wireless communications in cellular networks. The
interference cancellation capability of MIMO communications
can be enhanced when the number of antennas installed on the
devices tends to be large (i.e., massive MIMO technology).
However, massive MIMO is very likely deployed in cellular
base stations (eNodeB) as it requires a high power budget and
a large space to accommodate massive number of antennas.
Therefore, massive MIMO techniques are exploited to mitigate
jamming attacks in the cellular uplink transmissions.

In [100], a massive MIMO jamming-resilient receiver was
designed to combat constant broadband jamming signal in the
uplink transmission of cellular networks. The basic idea behind
their design is to reserve a portion of pilots in a frame so that
these unused pilots can be leveraged to estimate the jammer’s
channel. At the same time, a legitimate user can also estimate
its desired channel in the presence of jamming signal. This can
be done using the pilots in a frame based on the large number
law originated from the massive number of antennas on BS.
With the estimated channel information, a linear spatial ﬁlter
can be designed at the BS to mitigate the jamming signal and
recover the legitimate signal.

In [101], Vinogradova et al. proposed to use the received
signal projection onto the estimated signal subspace to nullify
the jamming signal. The main challenge in this technique is
to ﬁnd the correct user’s signal subspace. The eigenvector
corresponding to the legitimate user eigenvalue in eigenvalue
decomposition of the received covariance matrix can be used
for signal projection. It is known that the user’s eigenvalues
can be expressed as its transmitted power when the legitimate
user’s and jammer’s power are distinct. In this case, the eigen-
values corresponding to the legitimate users can be selected
by an exhaustive search over all the calculated eigenvalues.

2) Spectrum Spreading Techniques: Spectrum spreading
is a classic anti-jamming technique, which has been used
in 3G CDMA, WCDMA, TDS-CDMA cellular systems. It
is particularly effective in coping with narrowband jamming
signals. At the PHY layer of WCDMA communications, the
bit-streams are spread using orthogonal channelization codes
called orthogonal variable spreading factor (OVSF) codes. The
length of OVSF codes are determined by a spreading factor
(SF) that varies in the range from 4 to 512 for downlink
and from 4 to 256 for uplink. The chip rate of WCDMA
communications is 3.84 Mcps, and the bit rate can be adjusted
by selecting different SF values.

In [102], Pinola et al. studied the performance of WCDMA
PHY layer under broadband jamming attacks by conducting
experimental measurements. The authors reported the results
for different services provided by WCDMA. For the uplink

services, the acceptable quality can be achieved when SJR
≥−22 dB for voice service, SJR ≥−13 dB for text message
service, and SJR ≥−16 dB for data service with SF = 32 (i.e.,
64 kbps data rate). For the downlink services, the acceptable
quality can be achieved when SJR ≥−26 dB for voice service,
SJR ≥−14 dB for text message service, and SJR ≥−18 dB
for data service with SF = 32.

3) Multiple Base Stations Schemes: In addition to MIMO-
based jamming mitigation, another approach for coping with
jamming attacks in cellular networks is rerouteing the trafﬁc
using alternative eNodeB. When current serving eNodeB is
under jamming attacks and out of service, a user can re-
connect to another eNodeB if available [103]. This mechanism
has already been used in LTE networks. When a user fails to
decode the MIB of its current serving eNodeB, it will search
for the strongest neighboring eNodeB for a new connection
[84].

4) Coding and Scrambling Techniques: Coding and scram-
bling techniques have also been used to protect wireless
communications against jamming attacks in cellular networks.
In [104], Jover et al. focus on the security enhancement for
the physical channels of LTE networks, including PBCH,
PUCCH, and PDCCH. These physical channels carry crucial
information and must be well protected against malicious jam-
ming adversary. To protect the information in these physical
channels, the authors proposed using spectrum spreading for
PBCH modulation, scrambling the PRB allocation for PUCCH
transmissions, and distributed encryption scheme for PDCCH
coding.

5) Dynamic Resource Allocation Schemes: The static re-
source allocation for the physical channel such as PUCCH is
regarded as the main vulnerability of the LTE framework that
can be used by a malicious attacker to interrupt the legiti-
mate transmissions, thereby causing DoS to the network. The
PUCCH is transmitted on the edges of the system bandwidth,
as illustrated in Fig. 10. It carries HARQ acknowledgments in
response to PDSCH transmissions. When the acknowledgment
signals cannot be correctly decoded, the eNodeB will need
to retransmit the downlink data packets, thereby imposing
trafﬁc congestion on the network and wasting the resources.
In [94], Lichtman et al. studied the vulnerability of PUCCH
and proposed a dynamic resource allocation scheme for
PUCCH transmission by incorporating a jamming detection
mechanism. In the jamming detection process, the energy of
the received PUCCH signal is continuously monitored and
compared with the signal strength of other physical channels to
identify any unexpected received energy behavior. Moreover,
the number of consecutive errors on PUCCH decoding is
tracked to detect the jamming attack on PUCCH. The key
idea of the proposed dynamic resource allocation scheme
is to assign pseudo-random resource elements or a diverse
combination of resource blocks for PUCCH transmissions in
the uplink frame.

6) Jamming Detection Mechanisms: In [105], Arjoune et al.
studied the performance of existing machine learning methods
in jamming detection for 5G communications. Particularly,
the authors evaluated the accuracy of neural networks, super
vector machine (SVM), and random forest algorithms. They


## --- Page 17 ---

### Section: III-C7 A Summary of Anti-Jamming Techniques

17

#### TABLE VI: A summary of existing anti-jamming techniques for cellular networks.

Anti-jamming technique
Ref.
Mechanism
Application scenario

MIMO-based techniques
[100]
Massive MIMO jamming-resilient receiver: jammer’s channel estimation,
and spatial linear ﬁlter design to mitigate jamming signal.
Constant jamming attack

[101]
Jamming signal nulliﬁcation using signal projection techniques
Constant jamming attack
Spreading spectrum techniques
[102]
Evaluating of WCDMA-based cellular RAN against jamming attacks
Constant jamming attack
Alternative eNodeB
[103]
Rerouting the user’s trafﬁc via alternative eNodeBs.
DoS jamming attacks

Coding techniques
[104]
Spread spectrum for PBCH modulation, scrambling of PRB allocation for
PUCCH transmission, distributed encryption scheme for PDCCH coding.

PBCH and PDCCH/PUCCH
jamming attack
Dynamic resource allocation
[94]
Dynamic resource allocation for PUCCH transmissions.
PUCCH jamming attack
Jamming detection mechanisms
[105]
Machine learning algorithms using PER, RSS, and PDR features
Constant jamming attack

Primary User
Secondary User
Fusion Center
Attacker

(a)
(b)

Fig. 13: (a) Security attack in a cooperative sensing cognitive
radio network, (b) Security attack in a non-centralized cogni-
tive radio network.

generated the database using packet error rate, packet delivery
ratio, and the received signal strength features. The simulation
results show that the random forest algorithms achieve higher
accuracy (95.7%) in jamming detection compared to other
algorithms.

7) A Summary of Anti-Jamming Techniques: To facilitate
the reading for the audience, we summarize existing cellular-
speciﬁc anti-jamming techniques as well as their mechanisms
in Table VI.

#### IV. JAMMING AND ANTI-JAMMING ATTACKS IN

#### COGNITIVE RADIO NETWORKS (CRNS)

In this section, we survey the jamming and anti-jamming
strategies in cognitive radio networks. Following the previous
section structure, we ﬁrst provide an introduction of CRN
and then review the jamming and anti-jamming attacks in
literature. Fig. 13 describes a general scheme of security
attacks on centralized and distributed CRNs.

A. Background

Cognitive radio network (CRN) is a technique proposed
to alleviate the spectrum shortage problem by enabling un-
licensed users to coexist with incumbent users in licensed
spectrum bands without inducing interference to incumbent
communications. Thus, a CRN has two types of users: primary
users (PUs), which are also known as licensed users or
incumbent users, and secondary users (SUs), which are also
known as unlicensed users or cognitive users. In order to
realize spectrum access for cognitive users, spectrum sensing
plays a crucial role. Cooperative spectrum sensing (CSS)
refers to combining the sensing results reported from multiple

secondary users (SUs) and coming up with a near-optimal
carrier sensing output to improve the spectrum utilization.

The main components in CSS are signal detection, hy-
pothesis testing, and data fusion [106]. Signal detection in
CSS is independently carried out by active SUs to sense
the medium and record the raw information on possible PU
activities. Signal detection can be implemented using matched
ﬁltering, energy detection, or feature detection techniques.
While matched ﬁltering and feature techniques use PU’s
signal shaping and packet format to detect the presence of
its transmissions, the energy detection method does not need
to have prior knowledge of the PU’s protocols, making it
easy to implement. However, the energy detection method
will not be able to differentiate between the PU’s transmitted
signal and unknown noise and interference sources, resulting
in a decrease of the sensing accuracy [107]. After signal
detection, each user uses hypothesis analysis to reach to a
binary decision whether the medium is busy or not. The
hypothesis analysis can be performed using the Bayesian test,
the Neyman-Pearson test, and the sequence probability ratio
test [108]. Once individual SUs have made their decisions,
data fusion is performed by leveraging the reports received
from the SUs to turn them into a solid output. Data fusion
can be done centralized or decentralized, corresponding to the
network setting.

In centralized CCS, each SU’s detection results are transmit-
ted to a common control entity known as fusion center (FC).
The FC performs the data fusion processing and broadcasts the
ﬁnal results to all the SUs collaborated in the sensing phase.
Unlike centralized fusion, which relies on a fusion center to
collect the data and make the fusion, for decentralized fusion
in cognitive radio ad-hoc networks (CRAHN), no dedicated
central entity exists to perform data fusion, and instead, each
sensor exchanges its sensing output with its neighbors and
iteratively fuses the sensing outputs from its neighbors [25].

B. Jamming Attacks

In what follows, we survey the jamming attacks uniquely
designed for CRNs.

1) Primary User Emulation (PUE) Attacks: In conventional
CRNs, secondary users rely on spectrum sensing to realize
spectrum access opportunistically. This implies that secondary
users need to vacate the channel upon an incumbent signal
is detected. In this case, secondary users must re-sense the
spectrum again for other idle channels. This process is referred
to as spectrum hand-off. Spectrum hand-off can result in


## --- Page 18 ---

### Section: IV-B2 False-Report Attacks

18

performance degradation for secondary users as their available
time for spectrum access is wasted for the spectrum sensing
process. In general, this inherent concept of cognitive radio
networks may be targeted by an adversary attacker to prevent
secondary users access the channel. The primary user emu-
lation attack refers to the scenario where the attacker mimics
the primary user signal’s interface (transmits fake primary user
signal), so the secondary users treat the attacker as the primary
user and vacate the channel [26].

An attacker may launch the PUE attack as a selﬁsh attack
or a malicious attack:

• Selﬁsh attack: In [109], Jo et al. studied a selﬁsh PUE
attack in which the attacker utilizes a PUE attack to
prevent legitimate secondary users from accessing the
spectrum while it can exclusively acquire the spectrum
resources. This means that a non-legitimate secondary
user launches a PUE attack to maximize its utilization
from the spectrum channels.

• Malicious Attack: The main objective of the malicious
PUE attack is to cause denial of service to the secondary
networks [110]. In [111], Chen et al. investigated the
malicious PUE attack in centralized cooperative spectrum
sensing CRNs. In [112], the authors proposed an ad-
vanced malicious PUE attack design in which the attacker
ﬁrst estimates the primary user transmit power and design
the incumbent signal such that the legitimate secondary
users receive the fake signal with the same power as the
received primary user signal. The proposed design allows
the attacker to stay undetectable.

2) False-Report Attacks: In cooperative spectrum sensing,
secondary users send their local channel sensing results to a
fusion center that analyzes the reports and makes a global
decision on CRN’s channel access. It is well known that
centralized cooperative spectrum sensing can improve CRN
interference management by synthesizing the diverse reports
from multiple secondary nodes.

False-report Attack, also known as spectrum sensing data
falsiﬁcation (SSDF) attack or Byzantine Attack, is one of
the main MAC-layer security threats on cooperative spectrum
sensing in CRNs. False-report attack refers to the scenario
where the malicious network sends misleading channel sensing
reports to the fusion center to cause miss spectrum decision
[25]. Per [113], false-report attack is mainly conducted in the
following two forms;

• Malicious Attack: In this class, the malicious network
injects false local sensing results to degrade the perfor-
mance of decision-making in the fusion center. In [114]
and [115], the authors considered a malicious false-report
attack model in which the attacker performs channel
sensing and local decision and then sends a random value
with its opposite decision output distribution. In [116],
Fatemieh et al. introduced ”vandalism” attack where the
malicious attackers report the channel as unused when
it is busy in order to impose interference to the primary
network transmissions.

• Selﬁsh Attacks: Selﬁsh false-report attack refers to the
scenario in which the attacker intends to vacate the

spectrum for its exclusive usage by reporting fake channel
busy information to the fusion center [113].

False report attack is also investigated from the network
setting perspective in the literature; In [117]–[119], the authors
focused on the false-report attack in centralized cooperative
spectrum sensing where a fusion center generates the ﬁnal
decision on available channel detection.

In [120]–[123], the authors considered false-report attack in
decentralized cooperative spectrum sensing networks, where
the channel access decision is made through iterative infor-
mation exchange among cognitive users. Compared to cen-
tralized cooperative spectrum sensing, the authors argued that
decentralized cooperative spectrum sensing is more susceptible
to false-report attack as there is no common control unit to
receive all the users’ local channel sensing and perform the
global decision. Studies in [124] showed that the false-report
attack would be more destructive if the attacker acquires a
prior-knowledge of the cooperative spectrum sensing protocols
and fusion techniques used in the fusion center before it starts
to launch the attack.

In [125], Penna et al. evaluated the performance of the
cooperative spectrum sensing CRNs under statistical false-
report attack in which the attackers are assumed to have
certain attack probability, instead of following a predeﬁned
attack strategy. It was shown that the statistical attacks are
more challenging to be detected compared to non-probabilistic
false-report attacks. In [126], Rawat et al. demonstrated the
impact of attack population on false-report attack performance.
The authors used Kullback-Leibler divergence (KLD) as a
measurement metric to validate the detection performance. It
was shown that the attack would be more destructive as the
number of malicious nodes increases.

3) Jamming Attacks on Secondary Network and Common
Control Channel: The common control channel is a medium
through which the secondary nodes share their channel sens-
ing reports. Common control channel attack refers to the
overwhelming secondary network common control channel
by fake MAC control frames. The attacker network launches
the common control channel attack in order to cause denial
of service to the secondary network. In [127], Bian et al.
argued that the common control channel attack beneﬁts from
the following two features: First, it is hard to be detected as
it injects the MAC control frames identical to the secondary
networks’ protocols. Second, it is an energy-efﬁcient attack
as it requires to send a small number of control packets to
saturate the common control channel.

4) Learning-based Jamming Attacks: In [128], the authors
proposed a deep learning-based jamming attack on cognitive
radio networks. The proposed scheme takes advantage of
users’ ACK reports to train a deep learning classiﬁer to
predict whether an ACK transmission would occur through
the medium. The performance of the proposed jamming attack
was compared with a random jamming attack and a sensing-
based reactive jamming attack. The simulation results show
that the proposed deep-learning jamming attack could degrade
the network’s throughput to 0.05 packet/slot. As a compar-
ison, the authors also show that the network’s throughput


## --- Page 19 ---

### Section: IV-B5 A Summary of Existing Jamming Attacks

19

#### TABLE VII: A summary of jamming attacks in CRNs.

Attacks
Ref.
Description

#### PUE attacks

[109]
Used PUE attack to vacate the spectrum for its exclusive usage.
[111]
Used malicious PUE attack to cause DoS in centralized cooperative spectrum sensing CRNs.
[112]
Designed an advance malicious PUE attack by taking the PU’s receive power into account.

False-report
attacks

[113]
Introduced selﬁsh false-report attack where the attacker sends fake channel busy reports
to exclusively access the channel.
[114], [115]
Proposed an attack to report a value opposite to its local sensing decision to degrade the FC performance.
[116]
Designed an attack to report the channel as unused when it is busy to cause interference to the primary network.
[117]–[119]
Studied false-report attack in centralized cooperative spectrum sensing.
[120]–[123]
Studied false-report attack in decentralized cooperative spectrum sensing networks.
[124]
Proposed spectrum sensing protocol-aware false report attack.
[125]
Proposed probabilistic false report attack.
[126]
Studied the impact of attack population on false-report attack performance.
Common control
channel attacks
[127]
Evaluated the impact of jamming attack on common control channel.

Learning-based
jamming attacks
[128]
Proposed to use users’ ACK reports to train a deep learning classiﬁer for the attack initializing.

#### TABLE VIII: A summary of anti-jamming techniques for CRNs.

Ref.
Description

Anti-jamming
techniques

[129]
Proposed random channel hopping against PUE attack.
[130]
Introduce Tri-CH, an anti-jamming channel hopping algorithm.
[131]
Used zero-sum game modeling and a channel hopping defense strategy.
[132]
Proposed JRCC game modeling; Cooperation for control channel allocation and adaptive rate learning for primary user.
[133]
Proposed a game theoretical approach to model the CRN under jamming attack.
[134]
Propose JENNA; Random channel hopping and network coding for control packets sharing.

is 0.38 packet/slot under the random jamming attack and
0.14 packet/slot under the sensing-based jamming attack.
5) A Summary of Existing Jamming Attacks: Table VII is
a summary of existing attacks that were dedicatedly designed
for CRNs.

C. Anti-Jamming Techniques

Generally speaking, the anti-jamming strategies presented
in Section II-C (e.g., MIMO-based jamming mitigation) can
also be applied to thwarting jamming attacks in CRNs. Ta-
ble VIII summarizes existing anti-jamming strategies uniquely
designed for CRNs. In what follows, we elaborate on these
anti-jamming strategies.

Per [129], [131], [135], game-theoretical modeling is a well-
known technique used in CRNs to express the interaction
among different parties contributing to the network. Partic-
ularly, the stochastic zero-sum game is widely adopted to
model the interaction between secondary users and adversary
jamming attackers since they have opposite objectives.

In [129], Li et al. proposed that secondary users randomly
hop over the multiple channels to countermeasure PUE jam-
ming attacks. For the secondary network, each user needs to
search the optimal tradeoff between choosing good channels
and avoiding jamming signals. In [130], Chang et al. intro-
duced Tri-CH, an anti-jamming channel hopping algorithm
for cognitive radio networks. In [131], the interaction between
the secondary network and attackers is formulated as a zero-
sum game, and a channel-hopping defense strategy is proposed
using the Markov decision process.

In [132], Lo et al. proposed JRCC, a jamming resilient
control channel game that models the strategies chosen by
cognitive users and an attacker under the impact of primary
user activity. JRCC uses user cooperation for control channel
allocation and adaptive rate learning for primary user using the

Win-or-Learn-Fast scheme. The optimal control channel allo-
cation strategy for secondary users is derived using multiagent
reinforcement learning (MARL).

In [133], a game-theoretical approach is picked up to model
the cognitive radio users’ interactions in the presence of a
jamming attack. Secondary users at each stage update their
strategies by observing the channel quality and availability
and the attackers’ strategy from the status of jammed channels.
The strategies deﬁned for cognitive users consider the number
of channels they can reserve to transmit control and data
messages and how they can switch between the different
channels. A minimax-Q learning method is used to ﬁnd the
optimal anti-jamming channel selection strategy for cognitive
users.

In [134], Asterjadhi et al. propose a scheme called JENNA,
jamming evasive network-coding neighbor-discovery algo-
rithm, to secure cognitive radio networks against PUE jam-
ming attack. JENNA combines random channel hopping and
network coding to share the control packets to neighbor users.
The proposed neighbor-discovery algorithm is fully distrusted
and scalable.

#### V. JAMMING AND ANTI-JAMMING ATTACKS IN ZIGBEE

NETWORKS
In this section, we survey existing jamming attacks and anti-
jamming techniques in ZigBee networks. Following the same
structure of previous sections, we ﬁrst offer a primer of ZigBee
communication and then explore existing jamming and anti-
jamming strategies that were uniquely designed for ZigBee
networks.

A. A Primer of ZigBee Communication

ZigBee is a key technology for low-power, low-data-
rate, and short-range wireless communication services such


## --- Page 20 ---

### Section: V-B Jamming Attacks

20

Preamble

Start of

Frame 
Delimiter

Frame 
Length 
(7 bits)

#### PHY Service Data Unit (PSDU)

4 Octets

Reserve

(1 bit)

1 Octet
1 Octet
0-127 Bytes

Synchronization Header
PHY Header
PHY Payload

Fig. 14: ZigBee frame structure.

as home automation, medical data collection, and indus-
trial equipment control [136]. With the proliferation of low-
power IoT devices, ZigBee becomes increasingly important
and emerges as a crucial component of wireless networking
infrastructure in smart home and smart city environments.
ZigBee was developed based on the IEEE 802.15.4 standard.
It operates in the unlicensed spectrum band from 2.4 to
2.4835 GHz worldwide, 902 to 928 MHz in North America
and Australia, and 868 to 868.6 MHz in Europe. On these unli-
censed bands, sixteen 5 MHz spaced channels are available for
ZigBee communications. At the PHY layer, ZigBee uses offset
quadrature phase-shift keying (OQPSK) modulation scheme
and direct-sequence spread spectrum (DSSS) coding for data
transmission. A typical data rate of ZigBee transmission is
250 kbit/s, corresponding to 2 Mchip/s.
Fig. 14 shows the frame structure of ZigBee communica-
tion. The frame consists of a synchronization header, PHY
header, and data payload. Synchronization header comprises a
preamble and a start of frame delimiter (SFD). The preamble
ﬁeld is typically used for chip and symbol timing, frame
synchronization, and carrier frequency and phase synchroniza-
tions. The preamble length is four predeﬁned Octets (32 bits)
that all are binary zeros. The SFD ﬁeld is a predeﬁned Octet,
which is used to indicate the end of SHR. Following the SFD is
the PHY header, which carries frame length information. PHY
payload carries user payload and user-speciﬁc information
from the upper layers.

Fig. 15 shows the block diagram of the baseband signal
processing in a ZigBee transceiver. Referring to Fig. 15(a), at
a ZigBee transmitter, every 4 bits of the data for transmission
are mapped to a predeﬁned 32-chip pseudo-random noise
(PN) sequence, followed by a half-sine pulse shaping process.
The chips of the PN sequence are modulated onto carrier
frequency by using the OQPSK modulation scheme. Referring
to Fig. 15(b), at a ZigBee receiver, the main signal processing
block chain comprises coarse and ﬁne frequency correction,
timing recovery (chip synchronization), preamble detection,
phase ambiguity resolution, and despreading. The RF front-
end module ﬁrst demodulates the received signal from carrier
radio frequency to baseband. The received chip sequences are
passed through a matched ﬁlter to boost the received SNR.
Then, an FFT-based algorithm is typically used for coarse
frequency offset estimation. What follows is a closed-loop
PLL-based algorithm for ﬁne carrier frequency, and phase
offsets correction. Timing recovery (chip synchronization) can
be performed using classic methods such as zero-crossing or
Mueller-Muller error detection. Following the timing recovery
is the preamble detection, which can compensate for the
phase ambiguity generated by the ﬁne frequency compensation
module. Finally, the decoded chips are despreaded to recover
the original transmitted bits.

Bit-to-
symbol

O-QPSK 
modulator
Symbol
-to-chip
0100101
...

I-phase

Q-phase

1
0
0
0
0
1

0
1
1
1
0
0

...

...

(a) ZigBee transmitter structure.

RF front

end
ADC
Energy 
detection

Matched

filtering

Coarse frequency

correction

Fine frequency

correction

Timing Recovery
(chip synchroniztaion)
Preamble 
detection
Phase ambiguity

resolution
Despreading
1010010...

(b) ZigBee receiver structure.

Fig. 15: The signal processing block diagram of a ZigBee
transceiver.

Jammer

Motion sensor

Alarm system

Smoke 
detector

Smart things

hub

Adjustable

#### LED bulb

Smart plug

Safety speaker

Temperature

sensor

Smart lock

Jamming signal

Fig. 16: Illustration of jamming attacks in a ZigBee network.

B. Jamming Attacks

Since ZigBee is a wireless communication system, the
generic jamming attack strategies (e.g., constant jamming,
reactive jamming, deceptive jamming, random jamming, and
frequency-sweeping jamming) presented in Section II-B can
also be applied to ZigBee networks. Here, we focus on the
jamming attack strategies that were delicatedly designed for
ZigBee networks, as shown in Fig. 16. Table IX presents the
existing ZigBee-speciﬁc jamming attacks in the literature. In
what follows, we elaborate on these jamming attacks.

In [137], the authors studied the impact of constant radio
jamming attack on connectivity of an IEEE 802.15.4 (ZigBee)
network. They evaluated the destructiveness of jamming attack
in an indoor ZigBee environment via experiments. In their
experiments, the ZigBee network was conﬁgured in a tree
topology, and a commercial ZigBee module with modiﬁed
ﬁrmware was used as the radio jammer. The authors reported
the number of nodes affected by a jamming attack when the
jammer was located at different locations.

In [138], the authors studied reactive radio jamming attacks
in ZigBee networks, focusing on improving the effectiveness
and practicality of reactive jamming attacks. The reactive
jammer ﬁrst detects ZigBee packets in the air by searching for


## --- Page 21 ---

### Section: V-C Anti-Jamming Techniques

21

#### TABLE IX: A summary of jamming attacks and anti-jamming strategies for ZigBee networks.

Ref.
Description

Jamming
attacks

[137]
Studied the performance of constant jamming attack on ZigBee communications.
[138]
Implemented reactive jamming attack in ZigBee communications using real-world implementation.
[139]
Designed the energy depletion attack on ZigBee networks.
[140]
Proposed cross technology jamming attack on ZigBee communications

Anti-jamming
techniques

[141]
Proposed a MIMO-based receiver using machine learning to cancel the jamming and decode the desired signal.
[142]
Evaluated conventional DSSS performance against interference and jamming signals.
[143]
Introduced randomized differential DSSS (RD-DSSS) scheme.
[144], [145]
Proposed an anti-jamming scheme (Dodge-Jam) based on channel hopping and frame segmentation.

[146]
Proposed a MAC-layer anti-jamming scheme based on frame masking, channel hopping,
packet fragmentation, and fragment replication.
[147]
Designed digital ﬁlter to reject the frequency components of periodically cycling jamming attacks.
[148], [149]
Proposed to manage the reaction time of the reactive jammer and use the unjammed time slots to transmit data.

[150]
Proposed jamming attack detection based on extracting statistics from jamming-free
symbols of DSSS synchronizer.
[140]
Proposed a multi-staged cross-technology jamming attack detection.

the PHY header in ZigBee frames shown in Fig. 14, and then
sends a short jamming signal to corrupt the detected ZigBee
packets. The results show that the jamming signal of more than
26 µs time duration sufﬁces to bring the packets reception rate
of a ZigBee receiver down to zero. The authors also built a
prototype of the proposed jamming attack on a USRP testbed
and evaluated its performance in an indoor environment. Their
experimental results show that the prototyped jammer blocks
more 96% packets in all scenarios.

In [139], Cao et al. presented an energy depletion attack
targeting on ZigBee networks. Through sending fake packets,
the proposed attack intends to keep the ZigBee receiver busy
and waste its physical resources (e.g., CPU). The authors
evaluated the cost of such an attack in terms of energy
consumption, time requirement, and computational cost of
processing the fake messages. It was shown that the energy
depletion attack can serve as a DoS attack in ZigBee networks
by depleting the airtime resource and leaving no airtime for
serving legitimate users.

In [140], Chi et al. proposed a cross-technology jamming
attack on ZigBee communications, where a Wi-Fi dongle was
used as the malicious jammer to interrupt ZigBee commu-
nication using Wi-Fi signal. The ﬁrmware of Wi-Fi dongle
was modiﬁed to disable its carrier sensing and set the SIFS
and DIFS time windows to zero, such that the Wi-Fi dongle
can continuously transmit packets. The reasons for using Wi-
Fi cross-technology to attack ZigBee communications are
three-fold: i) Wi-Fi dongle is cheap and easy to be driven
as a constant jammer; ii) a WiFi-based jammer is easy to
detect as its trafﬁc tends to be considered legitimate; iii)
Wi-Fi bandwidth (20 MHz) is larger than ZigBee bandwidth
(5 MHz), making it possible to pollute several ZigBee channels
at the same time.

C. Anti-Jamming Techniques

Anti-jamming strategies such as MIMO-based jamming mit-
igation and spectrum spreading techniques can also be applied
to ZigBee communications against jamming attacks. Partic-
ularly, ZigBee employs DSSS at its PHY layer, which can
enhance the link reliability against jamming and interference
signals. Table IX presents existing anti-jamming attacks that

were delicately designed for ZigBee networks. We elaborate
on these works in the following.

As a performance baseline, Fang et al. [142] studied the bit
error rate (BER) performance of DSSS in ZigBee communi-
cations. Their theoretical analysis and simulation show that, in
the AWGN channel, a ZigBee receiver renders BER = 10−1

when SNR = 3 dB, BER = 10−2 when SNR = 6 dB, and
BER = 10−3 when SNR = 8 dB. These theoretical results
provide a reference for the study of ZigBee communications
in the presence of jamming attacks.

In [141], Pirayesh et al. proposed a MIMO-based jamming-
resilient receiver to secure ZigBee communications against
constant jamming attack. They employed an online learning
approach for a multi-antenna ZigBee receiver to mitigate un-
known jamming signal and recover ZigBee signal. Speciﬁcally,
the proposed scheme uses the preamble ﬁeld of a ZigBee
frame, as shown in Fig. 14, to train a neural network, which
then is used for jamming mitigation and signal recovery. A
prototype of the proposed ZigBee receiver was built using a
USRP SDR testbed. Their experimental results show that the
proposed ZigBee receiver achieves 100% packet reception rate
in the presence of jamming signal that is 20 dB stronger than
ZigBee signal. Moreover, it was shown that the proposed Zig-
Bee receiver yields an average of 26.7 dB jamming mitigation
gain compared to commercial off-the-shelf ZigBee receivers.

In [143], a randomized differential DSSS (RD-DSSS)
scheme was proposed to salvage ZigBee communication in
the face of a reactive jamming attack. RD-DSSS decreases
the probability of being jammed using the correlation of
unpredictable spreading codes. In [145] and [144], a scheme
called Dodge-Jam was proposed to defend IEEE 802.15.4
ACK frame transmission against reactive jamming attacks.
Dodge-Jam relies on two main techniques: channel hopping
and frame segmentation. Particularly, frame segmentation is
done by splitting the original frame into multiple small blocks.
These small blocks are shifted in order when retransmission
is required. In this scenario, the receiver can recover the
transmitted frame after a couple of retransmission. In [146], a
MAC-layer protocol called DEEJAM was proposed to reduce
the impact of jamming attack in ZigBee communications.
DEEJAM offers four different countermeasures, namely frame
masking, channel hopping, packet fragmentation, and redun-


## --- Page 22 ---

### Section: VI Jamming and Anti-Jamming Attacks in Bluetooth Networks

22

Jammer

Portable

speaker

Earphone

Headphone
Mouse

Video game

controller

Smart 
watch

Smart phone

Jamming signal

Fig. 17: Jamming attack in a Bluetooth network.

dant encoding, to defend against different jamming attacks.
Speciﬁcally, frame masking refers to using a conﬁdential start
of frame delimiter (SFD) symbols by the ZigBee transmitter
and receiver when a jammer is designed to use the SFD
detection for its transmission initialization. Channel hopping
was proposed to defend against reactive jamming attacks.
Packet fragmentation was proposed to defend against scan
jamming. Redundant encoding (e.g., fragment replication) was
designed to defend against noise jamming.

In [147], the impact of a periodically cycling jamming attack
on ZigBee communication was studied, and a digital ﬁlter was
designed to reject the frequency components of the jamming
signal. In [148] and [149], an anti-jamming technique was
proposed to defend against high-power broadband reactive
jamming attacks for low data rate wireless networks such as
ZigBee. The proposed technique undertakes reactive jammers’
reaction time and uses the unjammed time slots to transmit
data. In [150], Spuhler et al. studied a reactive jamming attack
and its detection method in ZigBee networks. The key idea
behind their design is to extract statistics from the jamming-
free symbols of the DSSS synchronizer to discern jammed
packets from those lost due to bad channel conditions. This
detection method, however, focuses only on jamming attacks
without considering jamming defense mechanism. In [140],
Chi et al. proposed a detection mechanism to cope with
cross-technology jamming attacks. Their proposed detection
technique consists of several steps, including multi-stage chan-
nel sensing, sweeping channel, and tracking the number of
consecutive failed packets. Once the number of failed packets
exceeds a certain threshold, the ZigBee device transmits its
packets even if the channel is still busy, letting the signal
recovery be made at the receiver side.

#### VI. JAMMING AND ANTI-JAMMING ATTACKS IN

#### BLUETOOTH NETWORKS

In this section, we survey existing jamming and anti-
jamming attacks in a Bluetooth network, as shown in Fig. 17.
By the same token, we ﬁrst offer a primer of the PHY and
MAC layers of Bluetooth communication and then review the
existing jamming/anti-jamming techniques that were dedicat-
edly designed for Bluetooth networks.

Preamble
Access 
Address

Coding 
Indicator
Payload

8/16/80 Bits

Term 1

32 Bits
2 Bits
16-2056 Bits
3 Bits

CRC
Term 2

24 Bits
3 Bits

Fig. 18: Bluetooth low energy frame structure.

A. A Primer of Bluetooth Communication

Bluetooth is a wireless technology that has been deployed
for real-world applications for many years. It was initially
designed for short-range device to device (D2D) communi-
cation and then evolved toward many other communication
purposes in the IoT applications. A Bluetooth network, also
known as a piconet, is typically composed of one master
device and up to seven slave devices. A Bluetooth device
can serve as a master node in only one piconet, but it can
be connected to multiple piconets as a slave. In response to
the low power constraints in IoT networks, a new concept of
Bluetooth Low Energy (BLE) was recently introduced to offer
a more energy-efﬁcient and ﬂexible communication scheme
compared to classic Bluetooth technology. BLE operates in
unlicensed 2.4GHz–2.4835GHz ISM frequency bands, where
there are 40 channels of 2 MHz bandwidth available for its
communications. Unlike Wi-Fi channels, the BLE channels
are not overlapping. In its latest version (e.g., BLE v5), BLE
can support 1 Msym/s and 2 Msym/s symbol rates, where
1 Msym/s symbol rate is the mandatory modulation scheme
while 2 Msym/s symbol rate is optional. BLE at 1 Msym/s
modulation may use packet frames with coded or uncoded
data. Fig. 18 shows a general packet structure for BLE at
1 Msym/s transmission. As can be seen, a BLE packet consists
of a preamble, access address, payload, and CRC. The coding
indicator and termination ﬁelds are further transmitted within
the packet for the coded frame format, as shown in Fig. 18.

Fig. 19 shows the block diagram of baseband signal process-
ing in a Bluetooth device. At the transmitter side, the generated
frame is fed into a whitening (scrambling) operation to avoid
transmitting long sequences consisting of consecutive zeros
or ones. FEC and pattern mapping are used when the coded
frame format is transmitted. The scrambled data is encoded
using a 1/2 rate binary convolutional FEC encoder. Pattern
mapping might be used to map each encoded bit to 4-bits
symbol to decrease the error decoding probability. The ﬁnal
bits to be sent are modulated on the carrier frequency using
Gaussian minimum shift keying (GMSK). The data rate of
uncoded packet format transmission is 1 Mbps. The data rate
of coded packet format is 500 kbps. After applying pattern
mapping to the encoded bits, the data rate is 125 kbps.

Referring Fig. 19(b), at the receiver side, the received signal
power is adjusted using an AGC block. Following AGC,
the DC offset of the received signal is removed. A coarse
frequency offset correction algorithm is employed to estimate
and compensate the carrier frequency mismatch between the
transmitter and receiver clocks. The received signal is later
passed through a Gaussian matched ﬁlter to reduce the noise.
In the aftermath of matched ﬁltering, the frame timing syn-
chronization is performed based on preamble detection. Then,
the received frame is demodulated using the GMSK demodu-


## --- Page 23 ---

### Section: VI-B Jamming Attacks

23

Frame 
generation
Whitening
0100101
...
FEC 
coding

Pattern 
mapping

GMSK 
modulation

(a) BLE transmitter structure.

RF front

end

DC offset 
removing
AGC
Frequency offset

correction

Matched

filtering

GMSK 
demodulation
FEC 
decoding
CRC check

Timing 
Recovery

Pattern 
demapping
Dewhitening
1010010...

(b) BLE receiver structure.

Fig. 19: Signal processing block diagram of Bluetooth com-
munication.

lation block. FEC decoding and pattern de-mapping are used
when the coded packet frames are transmitted. Finally, the
decoded bits are de-whitened and the CRC check is performed
to check the correctness of the decoded bits.

FHSS is a key technology of Bluetooth communications as
it enhances the reliability of Bluetooth link in the presence
of intentional or unintentional interference. With FHSS, Blue-
tooth packets are transmitted by rapidly hopping over a set
of predeﬁned channels, following a mutually-agreed hopping
pattern. Conventional Bluetooth has 79 distinct and separate
channels, each of 1 MHz bandwidth. The new standard,
Bluetooth Low Energy (BLE), has 40 distinct channels, each
of 2 MHz bandwidth. The hopping pattern is determined by
a pseudo-random spreading code, which is shared with the
receiver to keep transmitter and receiver synchronized during
the channel hopping. The spreading code must be shared after
a pre-shared key establishment process to secure the data
communication.

B. Jamming Attacks

In the original design of Bluetooth communication systems,
frequency hopping spread spectrum (FHSS) technology was
adopted to avoid interference so as to improve the commu-
nication reliability. The inherent FHSS technology provides
Bluetooth systems with the capability of coping with jamming
attacks to some extent. For this reason, the study of jamming
attacks in Bluetooth networks is highly overlooked, and the
investigation of Bluetooth-speciﬁc jamming attacks is very
limited in the literature.

However, the FHSS technology is effective only for narrow-
band, low-power jamming attacks; and it becomes ineffective
when the bandwidth of high-power jamming signal spans over
all possible Bluetooth channels, i.e., 2.4 −2.4835 GHz ISM
band. In fact, such a jamming attack can be easily launched
in practice, thanks to the advancement of SDR technology.
In light of powerful jamming attacks, Bluetooth networks are
vulnerable to generic jamming attacks (e.g., constant, reactive,
and deceptive jamming attacks, see Section II-B) as much as
other wireless communication systems.

In the context of Bluetooth networks, although many works
have been done to investigate the underlying security vulner-
abilities of Bluetooth applications (see, e.g., [151]–[154]), the
research effort on investigating jamming attacks for Bluetooth

communications remains very limited. In [155], K¨oppel et al.
built an intelligent jamming attack that synchronously tracks
Bluetooth communications and sends the jamming signal. The
proposed algorithm estimates the frequency hopping sequence
of Bluetooth communications by i) decoding the master’s up-
per address part (UAP) and the lower address part (LAP), and
ii) determining the communication’s clock. The jammer uses
the estimated clock to synchronize itself with the Bluetooth
devices. The experimental results demonstrate that a jammer is
capable of completely blocking Bluetooth communications if
the jammer can obtain a correct estimate of frequency hopping
sequence and clock.

C. Anti-jamming Techniques

As mentioned before, FHSS is the key technology used
at the physical layer of Bluetooth communication, which
has a certain capability of taming interference and jamming
signals. The pre-shared key establishment, however, is itself a
challenging constraint in the presence of jamming attacks.

In Bluetooth communication, FHSS relies on a pre-shared
key at a pair of devices to determine their frequency hop-
ping pattern. The key establishment procedure (for reaching
the consent on frequency hopping pattern at transmitter and
receiver) exposes Bluetooth networks to adversarial jamming
attackers. In [156]–[159], uncoordinated FHSS schemes were
proposed to secure the key establishment procedure for Blue-
tooth communication in the presence of jamming attacks.
These schemes employ a randomized FHSS technique, where
a pair of Bluetooth devices randomly switch over multiple
channels before being able to initiate the communication. Once
the two Bluetooth devices come across on the same channel,
they exchange the hopping and spreading keys. To fasten the
convergence of the procedure, one approach is to let Bluetooth
transmitter hop over the channels much faster than Bluetooth
receiver (e.g., 20 times faster).

In [160], Xiao et al. proposed a collaborative broadcast
scheme to eliminate the need for pre-shared key exchanging
in an uncoordinated FHSS technique. The authors considered
a star-topology network, where a master node intends to
broadcast a message to its multiple slave nodes. The key
idea behind this scheme is to broadcast messages in all
possible channels and use the nodes having already acquired
the message to serve as relays to forward the messages to
other nodes. It is assumed that the jammer cannot block all
available channels; otherwise, the proposed algorithm will not
work. Multiple channel selection schemes, including random,
sweeping-channel, and static, were considered for relaying
broadcast messages. Packet reception rate and cooperation
gain were investigated to evaluate the performance of the
proposed scheme. Experimental results conﬁrm a signiﬁcant
improvement of jamming resiliency. Moreover, it was shown
that, for a certain jamming probability, when there is a small
number of slave nodes in the network (e.g., less than 50),
sweeping channel selection achieves a higher packet reception
rate. But for a large number of nodes, static channel selection
outperforms other channel selection methods.


## --- Page 24 ---

### Section: VII Jamming and Anti-Jamming Attacks in LoRa Networks

24

Payload

CRC
Preamble
PHY Header 
PHY Payload
PHY
 Header CRC

MAC Header 
MAC Payload
MIC

Frame 
Header
Port Field
Frame Payload

Fig. 20: The structure of LoRa frame.

#### VII. JAMMING AND ANTI-JAMMING ATTACKS IN LORA

#### NETWORKS

A. A Primer of LoRaWANs

LoRa is a low power wide area networking (LPWAN) tech-
nology. It recently becomes popular thanks to its promising
features such as open-source development, easy deployment,
ﬂexibility, security, cost effectiveness, and energy efﬁciency.
LoRa has been widely used in diverse IoT applications such as
smart parking, smart lighting, waste management services, life
span monitoring of civil structures, and air and noise pollution
monitoring. Compared to other low-power wireless technolo-
gies (e.g., ZigBee and Bluetooth), LoRa offers a large coverage
(5km–15km). LoRa is a lightweight communication system
with low-complexity signal processing and low-complexity
MAC protocols. It consumes only 120–150 mW power in its
transmission mode. The lifetime of a LoRa device varies in
the range from 2 to 5 years, depending on its in-use duty cycle
[161].

LoRa uses chirp spread spectrum (CSS) modulation for its
data transmission. It supports a data rate from 980 bps to
21.9 kbps and spreading factors (SF) from 6 to 12. In the
CSS modulation, data is carried by frequency modulated chirp
pulses. The CSS modulation scheme appears to be resilient
to both interference and Doppler shift, making it particularly
suitable for long-range mobile applications.

LoRa operates in sub-GHz ISM bandwidth in North Amer-
ica. On 902.3MHz–914.9 MHz spectrum, 64 channels are
deﬁned for LoRa, each of 125 kHz bandwidth. On 1.6MHz
spectrum, 8 channels are deﬁned for LoRa’s uplink transmis-
sion, each of 500kHz bandwidth. On 923.3MHz–927.5MHz
spectrum, 8 channels are deﬁned for LoRa’s downlink trans-
mission, each of 500kHz bandwidth. Typically, LoRa operates
in a star-network topology, where one or multiple LoRa
devices are served by a central gateway connected to a network
server.
Packet Structure: Fig. 20 shows the structure of a LoRa
packet. The preamble comprises a sequence of upchirps and
a sequence of downchirps. The number of upchirps in the
preamble depends on the data rate and spreading factor. The
downchirps in the preamble is used for packet detection and
clock synchronization.

The PHY header and its CRC ﬁelds are optional and
transmitted to indicate the length of PHY payload. The PHY
payload consists of MAC header, MAC payload, and message
integrity code (MIC). Depending on the selected data rate,
the maximum user payload size varies in the range of 11
to 242 bytes. MAC header is 1-byte data, specifying MAC

Hamming

encoder
Whitening
0100101
...

Interleaving
CSS 
modulation
Frame 
generation

RF front

end

Preamble

(a) The LoRa transmitter structure.

RF front

end
De-interleaving

De-whitening

Frequency offset

correction

Hamming

decoder

Packet 
synchronization
CSS 
demodulation

#### 0100101...

(b) The LoRa receiver structure.

Fig. 21: The schematic diagram of LoRa transceiver.

message type (MType) such as uplink/downlink data, join
request, and accept request. LoRa supports both “conﬁrmed”
data transmission and “unconﬁrmed” data transmission. The
former requires a receiver to acknowledge the frame reception,
while the latter requires no ACK feedback. The MAC payload
consists of a frame header (FHDR), an optional port ﬁeld
(FPort), and frame payload, as shown in Fig. 20. The frame
header (FHDR) mainly carries the end-device address, and the
frame payload carries the application-speciﬁc end-device data.

LoRa supports bi-directional communications. That is, when
a LoRa device sends an uplink packet, it waits for two window
time slots for downlink data. This means that the downlink
transmission requires a LoRa device to send the uplink packets
ﬁrst. In a LoRaWAN, the ALOHA scheme is used as the
medium control protocol for LoRa devices to access the
channel for their uplink transmissions.
Transceiver Structure: Fig. 21 shows the schematic diagram
of a LoRa transceiver structure. At the transmitter side, the
bits to be transmitted are ﬁrst encoded using a Hamming
encoder. The encoded bits are fed into the whitening module to
avoid transmitting a long sequence of consecutive zeros/ones.
Following the whitening module, the interleaving module is
applied to the scrambled bits. The preamble sequence is
attached to the processed bits, and all are modulated on the
carrier frequency using the CSS modulation. At the receiver
side, the received frame is synchronized using the preamble
detection followed by the carrier frequency offset correction.
The received frame is demodulated using CSS demodulation
block and fed into the deinterleaving block, dewhitening block,
and hamming decoder, sequentially.

B. Jamming Attacks

In this subsection, we overview the jamming attacks on
LoRa communications. In [162], Aras et al. investigated the
vulnerabilities of LoRa communications under triggered jam-
ming attack and selective jamming attack. The authors showed
that, despite using spreading spectrum scheme at low data rate,
LoRaWAN is still highly susceptible to jamming attacks.

• Triggered jamming: Triggered jamming attack is similar
to reactive jamming attack. Once the jammer detects
the preamble transmitted by a LoRaWAN device, it will
broadcast jamming signal. [162] conducted experiments
to evaluate the performance of LoRaWAN under triggered


## --- Page 25 ---

### Section: VII-C Anti-jamming Techniques

25

Payload

CRC
Preamble
PHY Header 
PHY
 Header CRC

MAC 
Header 
MAC Payload
MIC

Jamming
Selection
Detection
Packet Int.

Listening
Transmitting

Fig. 22: Illustration of selective jamming attack on LoRa
packet transmissions [162].

jamming attack, where a commodity LoRa end-device is
used as triggered jammer. The experimental results show
that the packet reception rate of a legitimate LoRa device
drops to 0.5% under the triggered jamming attack.

• Selective jamming: Fig. 22 shows the basic idea of
selective jamming attack studied in [162], where a jam-
mer sends jamming signal upon decoding the MAC
header and the end-device address. The selective jamming
attack can block a particular device’s communications
in a LoRaWAN while causing no interference to other
devices in the network. The authors ran experiments to
evaluate the performance of selective jamming attack in
a LoRaWAN. They used two commodity LoRa devices
and programmed the jammer such that it targets one of
their communications. Experimental results show that the
packet reception rate at the victim LoRa device drops to
1.3% under the selective jamming attack.

In [163], Huang et al. built a prototype of a reactive
jammer against LoRaWAN communications using a commod-
ity LoRa module. The proposed algorithm jointly use the
LoRa preamble detection and the signal strength indicator
(RSSI) for efﬁciently detecting LoRa channel activity. The
authors evaluated the performance of the proposed jammer
in LoRaWAN via conducting real-world experiments. They
considered the impact of the SF and the jammer’s bandwidth
on signal detection. The packet delivery rate was used to
measure the performance of the victim LoRa device under
the proposed jamming attack. Their results demonstrate that a
jammer can achieve more than 90% accuracy in LoRa packet
detection when the jammer’s SF and bandwidth are matched
with the legitimate LoRa signal. Moreover, the results show
that, for most scenarios, when jamming signal is 3 dB stronger
than LoRa signal, a LoRa receiver fails to decode the received
packets and the packet delivery rate drops to zero.

In [164], Butun et al. studied the security challenges regard-
ing the LoRaWAN communications. A LoRaWAN v1.1 ar-
chitecture comprising end-devices, gateways, network servers,
and application servers was considered. At the PHY layer, the
authors investigated the replay attack on join-request signaling
in LoRaWANs. The attacker requires to jointly sniff the join-
request signal and interferes with it at a LoRa gateway. The
attacker also interrupts the second join-request attempt and
simultaneously sends the stored join-request signal captured
in the ﬁrst device’s attempt. It was argued that the gateway
tends to accept the join-request signal spoofed by the attacker
as it has never been used before. In this scenario, the LoRa
device will no longer be synchronized to its serving gateway
as their in-use join-requests are not matched.

Jammer

#### RSI

Jamming siganl

V2V/V2I signal

Fig. 23: Illustration of jamming attacks in a vehicular network.

C. Anti-jamming Techniques

The spreading spectrum technique is the main approach
used in the LoRa technology to secure its communications
against jamming attacks and unintentional interference signals.
As mentioned earlier, LoRa uses the CSS modulation scheme
for its data transmissions, in which every bit to be transmitted
is mapped into the sequence of 2SF chips and modulated onto
the chirp waveform.

Per [165], a LoRa receiver is capable of recovering the
received packets (i.e., yielding zero packet error rate) with
the RSSI as low as −121 dBm when working at 125 KHz
bandwidth and SF = 8. Comparing to conventional FSK
modulation scheme, it is shown that, for a given data rate
of 1.2 Kbps, a LoRa receiver achieves 7 dB to 10 dB lower
receiving sensitivity. Moreover, a LoRa receiver achieves up
to 15 dB gain in the packet reception ratio compared to
conventional FSK receivers.

In [166], Danish et al. proposed a jamming detection
mechanism in LoRaWANs using Kullback Leibler diver-
gence (KLD) and Hamming distance (HD) algorithms. The
KLD-based jamming detection scheme uses the likelihood
of jamming-free received signal’s probability distribution and
the received signal’s probability distribution under jamming
attack. Particularly, the authors used join request transmissions
to determine a mass function of the LoRa device signaling.
If the similarity of the received signal’s distribution and the
acquired mass function is below a certain threshold, the
presence of an undesired interference signal or a jamming
signal will be claimed. Similarly, in the Hamming distance
scheme, the algorithm ﬁnds the average Hamming distance
between the received signal and the training signal. If the
calculated distance diverges from a certain threshold, the
algorithm claims the presence of jamming attacks. The authors
evaluated the performance of their proposed schemes via a
real-world system implementation. The results show 98% and
88% accuracy in jamming detection for the KLD-based and
HD-based algorithms, respectively.

#### VIII. JAMMING AND ANTI-JAMMING ATTACKS IN

#### VEHICULAR WIRELESS NETWORKS

In this section, we survey the jamming attacks and anti-
jamming mechanisms in vehicular wireless communication
networks, including on-ground vehicular ad-hoc network


## --- Page 26 ---

### Section: VIII-A A Primer of Vehicular Wireless Networks

26

Frequency (GHz)

Ch 172
Ch 182
Ch 184
Ch 174
Ch 176
Ch 178
Ch 180

5.920
5.910
5.900
5.890
5.880
5.870
5.860

Control channel
Public Safety
Critical Safety
Service channels
Service channels

Fig. 24: The frequency channels allocated for DSRC.

Time

Control 
channel

Service 
channel
Service 
channel
Sync period

100 ms
Sync period

#### 100 ms

Control 
channel

50 ms
50 ms
Guard interval
4 ms

Fig. 25: The time intervals in 802.11p communications.

(VENET) and in-air unmanned aerial vehicular (UAV) net-
work. In what follows, we ﬁrst provide an introduction of
vehicular wireless communication networks and then review
the jamming/anti-jamming strategies uniquely designed for
vehicular wireless networks.

A. A Primer of Vehicular Wireless Networks

On-Ground VANET: Every year thousands of deaths occur
in the U.S. due to trafﬁc accidents, about 60 percent of which
could be avoided by vehicular communication technologies.
To reduce vehicular fatalities and improve transportation ef-
ﬁciency, the U.S. Department of Transportation (USDOT)
launched the Connected Vehicle Program that works with state
transportation agencies, car manufacturers, and private sectors
to design advanced wireless technologies for vehicular com-
munications. It is a key component of network infrastructure
to realize the vision of an intelligent transportation system
(ITS) by enabling efﬁcient vehicle-to-vehicle (V2V) communi-
cations and/or vehicle-to-infrastructure (V2I) communications.
Compared to stationary and semi-stationary wireless networks
such as Wi-Fi networks, VANETs face two unique challenges
in their design and deployment. First, vehicles are of high
speed. The high speed of the vehicles continuously changes the
network topology in terms of both the vehicles’ positions and
the number of connected vehicles. Second, VANET is a delay-
sensitive communication network. Reliable and timely packet
delivery is of paramount importance for applications such as
collision avoidance in real-world transportation systems.

Dedicated short-range communications (DSRC) is a com-
munication system that enables wireless connectivity for
VANETs. At the PHY and MAC layers, DSRC deploys IEEE
802.11p standard. 802.11p uses the same frame format as
legacy Wi-Fi (Fig. 4(a)) for its data transmission. However,
the channel bandwidth is reduced to 10 MHz to provide higher
link reliability against channel impairments caused by users’
mobility. DSRC operates in the 5.9 GHz frequency band,
where seven distinct channels of 10 MHz are available for
the users’ access, as shown in Fig. 24. The center channel
(control channel) and the two on-edge channels are used to
carry safety messages such as critical information on road
crashes or trafﬁc congestion, while the service channels can
be used for both safety messages and infotainment data such
as video streaming, roadside advertising, and road map and

parking-related information. In the time domain, the resources
are separated into equally-sized time intervals of 100 ms,
known as sync period, as shown in Fig. 25. Every sync period
is divided into two 50 ms intervals. Every user needs to listen
to the control channel within the ﬁrst 50 ms interval to receive
the safety messages as well as obtain the information required
for accessing the available services. In the second 50 ms
interval, the user will switch to the intended service channel
to send/receive infotainment data.

In a VANET, the vehicles, also known as on-board units
(OBUs), and roadside units (RSUs) can communicate in three
different network settings: i) An RSU, similar to a Wi-Fi
AP, serves a set of OBUs having the same basic service set
(BSS) ID. ii) The units with the same BSSID communicate
with each other within an ad-hoc mode, where there is
no dedicated central unit. iii) The out-of-network units can
hear each other, in which the units use a so-called wildcard
BSSID to communicate with each other. The wildcard BSSID
allows the units from different networks to communicate in
a critical moment. While the ﬁrst two network settings are
already deployed in Wi-Fi communications, the third mode is
speciﬁcally designed for VANETs, as they require all units to
be able to receive critical and safety messages.

At the MAC layer, similar to legacy Wi-Fi, 802.11p uses
carrier sensing for channel access. However, on top of the
802.11p MAC mechanism, DSRC takes advantage of an en-
hanced MAC-layer technique, known as enhanced distributed
channel access (EDCA) in IEEE 1609.4, as a prioritized
medium access mechanism to enable critical message exchang-
ing.
In-Air UAV Network: With the signiﬁcant advancement of
robotic and battery technologies in the past decades, UAV
communication networks have drawn an increasing amount
of research interest in the community and enabled a wide
spectrum of applications such as photography, ﬁlm-making,
newsgathering, agricultural monitoring, crime scene inves-
tigations, border surveillance, armed attacks, infrastructure
inspection, search and rescue missions, disaster response, and
package delivery. Depending on the applications, UVAs of
different sizes can be deployed in the network. Small UAVs are
generally used to form swarms, while large UAVs are likely
used in critical military or civilian missions. The speed of
UAVs in different scenarios may vary from 0 m/s to 100 m/s,
depending on the applications [167].

Most UAVs operate in the unlicensed 2.4 GHz and 5.8 GHz
ISM bands. Depending on the application requirements, UAV
networks can be conﬁgured to operate in one of the follow-
ing network topologies: i) star topology, where each UAV
directly communicates with a ground control station; and ii)
mesh network topology, in which UAVs communicate with
each other as an ad-hoc network, and a small number of
them may communicate with ground control station [168].
Moreover, heavier UAVs can be designed to take advantage
of satellite communication (SATCOM) for routing. UAVs
are typically pre-programmed for this service to follow a
ﬂight route using global navigation satellite system (GNSS)
signals. In recent years, many standards have been drafted
to address the challenges regarding UAV communications.


## --- Page 27 ---

### Section: VIII-B Jamming Attacks

27

Cellular networks are currently considered as a promising
infrastructure for UAV activities due to their wide coverage.
3GPP in its release 15 have enhanced the LTE capability to
support UAV communications [169].

B. Jamming Attacks

Given the openness nature of wireless medium for vehic-
ular communications, both VENET and UAV networks are
vulnerable to generic jamming attacks (see Section II-B),
such as constant jamming, reactive, deceptive, and frequency-
sweeping jamming attacks. In this subsection, we focus on the
existing jamming attacks that were dedicatedly designed for
vehicular wireless networks. Table X presents a summary of
existing jamming attacks in vehicular networks.
VANET-Speciﬁc Jamming Attacks: Jamming attacks are
of particular importance in VANETs as the connection loss
caused by the jamming attacks may lead to car collision and
road fatality. A jamming attacker can adopt different strategies
(e.g., constant, reactive, and deceptive jamming) to cause the
loss of wireless connection for V2V and V2I communications
in VANETs. Fig. 23 shows an instance of jamming attack on a
VANET, where the destructiveness of existing jamming attack
strategies has been studied in literature.

In [170], Azogu et al. studied the impact of jamming attacks
on IEEE 802.11p-based V2X communications, where the jam-
mers were designed to dynamically switch to in-use channels.
The authors conducted experiments in a congested city area
using 100 vehicles and 20 RSI, and placed multiple radio
jammers with the range of 100 m in the proximity of RSIs.
They used two 802.11p channels for V2X communications
and packet send ratio (PSR) as the evaluation metric, where
the PSR is the number of packets sent per total number of
queued messages for transmission. The experimental results
show that 10 radio jammers can degrade the network PSR to
0.4.
In [171] and [172], Punal et al. evaluated the achievable
throughput of V2V communications under constant, peri-
odic, and reactive jamming attacks using real-world software-
deﬁned radio implementation. The authors conducted several
real-world experiments in both indoor and outdoor environ-
ments. Particularly, their experiments in an outdoor scenario
show that the packet delivery rates in 802.11p communications
drop to zero when SNJR is less than 9 dB under constant
jamming attack, when SNJR is less than 55 dB under periodic
jamming attack with the duty cycle of 86% and 74 µs period,
and when SNJR is less than 12 dB under reactive jamming
attack with the packet detection duration of 40 µs and jamming
signal duration of 500 µs.

In [173] and [174], Sumra et al. introduced a series of
data integrity attacks, in which an attacker aims to reduce the
accuracy of information travel through a vehicular network.
Their study’s basic idea is that once an attacker receives a
packet, it attempts to alter the packet content and relay the
false packet to a roadside unit or other vehicles.
UAV-Speciﬁc Jamming Attacks: While UAV networks are
vulnerable to the generic jamming attacks in Section II-B, we
focus on those jamming attacks that were deliberately designed

Military

drone

Small UAVs

#### GPS satellite

Ground control

station

Jammer

Legitimate signal

Jamming signal

Fig. 26: Illustration of jamming attacks in a UAV network.

for satellite-based UAV networks. Fig. 26 shows an instance of
jamming attack on UAV networks, Since most UAVs rely on
GPS signals for positioning and navigation, a jamming attacker
may target on their GPS communications to dysfunction UAV
networks. This class of jamming attacks can pose a severe
threat to military UAV networks.

In [175], Hartmann et al. investigated the possible theories
behind the loss of a military UAV (RQ-170 Sentinel) to
Iranian military forces in December 2011. They argued that
a GPS-spooﬁng attack might have been carried out to spoof
the UAV’s position estimation, thereby hijacking the UAV’s
routing decision.

In [176], another UAV-speciﬁc jamming attack, called con-
trol command attack, was studied. In this attack, a jammer
attempts to interrupt the control commands issued by UAVs’
ground control station. Control command attacks can be real-
ized using conventional jamming attacks to block the desired
received signal or by sending fake information to lure UAVs
following incorrect commands. The control command attack
can cause the loss of UAVs and mission failure.

C. Anti-Jamming Techniques

In this subsection, we review the anti-jamming techniques
that were dedicatedly designed for VANETs and UAV net-
works. Table X presents a summary of existing anti-jamming
mechanisms in vehicular networks. We elaborate on them in
the following.
VANET-Speciﬁc Anti-Jamming Techniques: Thus far, very
limited work has been done in the design of anti-jamming
techniques for VENETs. Given that most VENETs are using
IEEE 802.11p (DSRC) for V2V and V2I communications, a
straightforward anti-jamming strategy for VENETs is to switch
to another available wireless network (e.g., cellular), provided
that such an alternative network is available. In addition,
frequency hopping and data relaying techniques have been
studied to secure UAV communications.

In [178] and [179], the authors proposed to cope with
jamming attacks for VANETs by leveraging UAV devices.


## --- Page 28 ---

### Section: IX Jamming and Anti-Jamming Attacks in RIFD Communication Systems

28

#### TABLE X: A summary of jamming attacks and anti-jamming strategies for vehicular wireless networks.

Ref.
Description

Jamming
attacks

VANETs

[170]
Studied constant jamming attacks’ impact on IEEE 802.11p-based V2V communications.

[171], [172]
Evaluated the V2V communications’ performance under constant, periodic,
and reactive jamming attacks
[173], [174]
Introduced data integrity attack.

UAVs
[175]
Investigated jamming attack on UAVs’ satellite communications.
[176]
Introduced jamming attack on UAVs’ control command.

Anti-jamming
techniques

VANETs

[177]
Investigated frequency hopping technique for IEEE 802.11p communications.

[178], [179]
Proposed to use UAV communications to reroute the trafﬁc from jammed regions
to alternative RSUs.
[180]
Proposed to use an unsupervised learning algorithm for detecting mobile jammers.
[181]
Deployed a machine learning-based approach to localize the jammers.

UAVs

[182]
Used power control game modeling for UAV communications under jamming attack.
[183]–[185]
Used power control game modelling for UAV ad-hoc network under jamming attack.

[186]
Used multi-parameter of frequency, motion ,and antenna spatial domains to optimally
compromise the impact of jamming attack.

They studied smart jamming attacks in a VANET, where a
jammer continuously changes its attack strategy based on the
network topology. To salvage the vehicular communications, a
UAV was utilized to relay data for vehicles to the alternative
RSUs when the serving RSU is under jamming attacks. In
this work, a game theory approach was employed to model
the interactions between jammer and UAV, where the jammer
adaptively selects its transmission power, and the UAV makes
decisions for relaying the data.

In [180], Karagiannis et al. proposed to use an unsupervised
learning algorithm for detecting mobile jammers in vehicular
networks. The key component of the proposed scheme is to use
a newly-deﬁned parameter that measures the relative speed of
victim vehicles and the jammer vehicle for training a learning
algorithm. They evaluated the performance of the detection
algorithm in two jamming attack scenarios: i) the jammer pe-
riodically sends jamming signal and maintains a safe distance
from the victim vehicle; and ii) the jammer is unaware of
the possible detection mechanism and sends constant jamming
signal at any distance from the victim vehicle. Their simulation
results show that their proposed algorithm can classify the
attacks with the accuracy of 98.9% under constant jamming
attack and 44.5% under periodic jamming attack.

In [181], Kumar et al. employed a machine learning-based
approach to estimate the location of jammers in a vehicular
network. Particularly, a foster rationalizer was used to detect
any undesired frequency changes stemming from jamming
attacks on legitimate V2V communications. Following the
rationalizer, a Morsel ﬁlter was applied to remove the noise-
like components from jammed signal. The ﬁltered signal was
then injected into a Catboost algorithm to estimate the jam-
mer’s vehicle location. Their simulation results show that the
proposed scheme can predict the jamming vehicle’s position
with an accuracy of 99.9%.

UAV-Speciﬁc Anti-Jamming Techniques: Despite having
attracted more research efforts, UAV networks are still in
its infancy, and the research on UAV-speciﬁc anti-jamming
strategies remains rare. In [182], the authors performed a
theoretical study on anti-jamming power control game for
UAV communications in the presence of jamming attacks,
where the interactions between a jammer and a UAV are
modeled as a Stackelberg game. An optimal power control

strategy for UAV transmissions under jamming attack was
obtained using a reinforcement learning algorithm. In [183]
and [184], Xu et al. studied the anti-jamming problem in a
UAV ad-hoc network, in which every transmitter tends to send
the data toward its desired receiver while causing interference
to other communication links (refers to the co-channel mutual
interference). The problem was formulated as a Bayesian
Stackelberg game, in which a jammer is the leader, and
UAVs are the followers of the game. The optimal transmission
power of UAVs and jammer were analytically derived using
their utility functions optimization. In [185], a model was
developed to take into account the ﬂying process of UAV.
Based on the model, the ﬂying trajectory and transmission
power of the UAV were optimized. In [186], Peng et al.
investigated the jamming attacks in a UAV swarm network,
where a jammer network consisting of multiple nodes attempts
to block the communication between the swarm and its ground
control station. Multiple parameters were taken into account to
provide high ﬂexibility for UAV communications to deal with
jamming attacks. In particular, the UAVs exploited the degrees
of freedom in the frequency, motion, and antenna-based spatial
domains to optimize the link quality in the reception area. A
modiﬁed Q-learning algorithm was proposed to optimize this
multi-parameter problem.

#### IX. JAMMING AND ANTI-JAMMING ATTACKS IN RIFD

#### COMMUNICATION SYSTEMS

In this section, we ﬁrst provide a primer of Radio-frequency
identiﬁcation (RFID) communication and then provide a re-
view on RFID-speciﬁc jamming and anti-jamming attacks.

A. A Primer of RFID Communication

As we enter into the Internet of Everything (IoE) era, RFID
emerges as a key technology in many industrial domains with
an exponential increase in its applications. In RFID commu-
nications, an interrogator (reader) reads the information stored
in simply-designed tags attached to different objects such
as humans, animals, cars, clothes, books, grocery products,
jewelry, etc. from short distances using electromagnetic waves.
An RFID tag can be either passive or active. Passive tags
do not have a battery and use energy harvesting for their
computation and RF signal transmission. Active tags, on the


## --- Page 29 ---

### Section: IX-B Jamming Attacks

29

Tag
Reader

Query

#### RN16

#### EPC

Access

#### ACK

#### RFID

If  counter = 0

If  RN16
ACK

Select

Fig. 27: RFID tag inventory and access processes.

other hand, use battery to drive their computation and RF
circuits.

Fig. 27 shows the medium access protocol used in GEN2
UHF RFID communications [187]. Generally speaking, in an
RFID system, a reader (interrogator) manages a set of tags
following a protocol that comprises the following three phases:

• Select: The reader selects a tag population by sending
select commands, by which a group of tags are informed
for further inquiry process.

• Inventory: In this phase, the reader tries to identify
the selected tags. The reader initializes the inventory
rounds through issuing Query commands. The reader and
RFID tags communicate using a slotted ALOHA medium
access mechanism. Once a new-selected tag receives a
Query command, it sets its counter to a pseudo-random
number. Every time a tag receives the Query command, it
decreases its counter by 1. When the tag’s counter reaches
zero, it responds to the reader with a 16-bit pseudo-
random sequence (RN16). The reader acknowledges the
RN16 signal reception by regenerating the same RN16
and sending it back to the tag. When a tag receives
the replied RN16 signal, it compares the signal with the
original transmitted one. If they are matched, the tag will
broadcast its EPC, and the reader will identify the tag.

• Access: When the inventory phase is completed, the
reader can access the tag. In this phase, the reader may
write/read to/from the tag’s memory, kill, or lock the tag.
From a PHY-layer perspective, an UHF RFID readers
use pulse interval encoding (PIE) and DSB-ASK/SSB-
ASK/PR-ASK modulation for its data transmission, while
a UHF RFID tag uses FM0 or Miller data encoding
and backscattering for carrier modulation. Moreover, the
required energy for the tag’s backscattering is delivered
via the reader’s continuous wave (CW) transmissions
[188].

B. Jamming Attacks

Since RFID communication is a type of wireless commu-
nications, it is vulnerable to generic jamming attacks such
as constant, reactive, and deceptive jamming threats. Fig. 28

Clothes

Vehicles

Animals

Books

Human

Jewelry

Medical 
equipments

Jammer

Jamming signal

Fig. 28: Illustration of jamming attacks in RFID applications.

shows an instance of jamming attack on some applications of
RFID technology. In [189], Fu et al. investigated the impact
of constant jamming attack on UHF RFID communications
and evaluated the system performance through a simulation
model. The results in [189] showed that when the received
RFID reader signal power is 0 dBm, the received jamming
signal power of −15 dBm will be sufﬁcient to break down
the RFID communications. Per [190], Zapping attack is one
of the well-known security attacks to RFID tags, in which an
attacker aims to disable the function of RF front-end circuits in
RFID tags. In a Zapping attack, a malicious attacker produces
a strong electromagnetic induction through the tag’s circuit by
generating a high-power signal in the proximity of the tag’s
antenna. The large amount of energy a tag receives may cause
permanent damage to its RF circuits.

RFID tags are recently used for electronic voting systems
in many countries across the world. In such voting systems,
the votes are written through electronic RFID tags instead of
conventional ballot voting papers. Electronic voting systems
were originally designed to improve the accuracy and speed
of the vote-counting process. Given the importance of voting
services, research on RFID security receives a large amount
of attention from academia and industry. In [191] and [192],
Oren et al. studied two main security threats on RFID commu-
nications: jamming and zapping attacks. The authors studied
these two jamming attacks and evaluated their performances
in terms of their maximum jamming ranges. The author also
investigated the impact of a jammer’s antenna type on its
jamming effectiveness. It was shown that a helical antenna
yields a larger jamming range compared to a hustler or 39 cm
loop antenna.

In [193], Rieback et al. classiﬁed the security threats in
RFID networks into the following categories.

• Spooﬁng attack : A spoof attacker may access a tag’s
memory blocks and alter a tag’s information such that it
is still meaningful to the reader but carries false data.

• Denial-of-Service Attack: This attack refers to a security
threat where a reader will no longer be able to read
data from its corresponding tags. Per [193], DoS attack
in RFID communications can be performed either by
physically isolating the tags (e.g., wrapping the tags in


## --- Page 30 ---

### Section: IX-C Anti-Jamming Techniques

30

Jamming signal
GPS signal

Fig. 29: Illustration of jamming attacks in GPS system.

foils) so the reader can not deliver the required energy
for tag’s backscattering, or by injecting a large amount
of data into medium to overwhelm the reader.

• Replay attack: In [194], Danev et al. introduced a replay
attack where the attacker receives the tag’s signal, stores
it, and re-uses it in different time slots.

• Passive attack : Passive attack is one of the leading
security vulnerabilities in RFID communications, as a
tag’s EPC information can be read by any commercial
off-the-shelf or custom-designed interrogators. In [195],
Cho et al. proposed a brute-force attack in which the
attacker uses brute-forcing algorithms to pass the tag’s
authentication procedure, where it can write to (or read
from) the tag. The recorded data from RFID tags can be
further used for object tracking or spooﬁng attack.

C. Anti-Jamming Techniques

Unlike other types of wireless networks, securing RFID
communication against jamming attacks is a particularly chal-
lenging task due to the passive nature of RIFD tags or low-
energy supply of RFID tags. Generic anti-jamming techniques
(e.g., MIMO-based jamming mitigation, spectrum spreading,
and frequency hopping) appear ineffective or unsuitable for
RFID systems. Most of the existing works focus on authen-
tication issues in RFID networks. For example, Wang et al.
in [196] proposed an authentication scheme to cope with
RFID replay attack. Avanco et al. in [197] proposed a low-
power jamming detection mechanism in RFID networks. The
proposed mechanism detects malicious activities within the
network by exploiting side information such as the received
signal power in adjacent channels, the received preamble, and
the tag’s uplink transmission response.

#### X. JAMMING AND ANTI-JAMMING ATTACKS IN GPS

SYSTEMS
In this section, we survey jamming and anti-jamming attacks
in the Global Positioning System (GPS). By the same token,
we ﬁrst offer a primer of GPS communication system and then
review existing jamming/anti-jamming attacks deliberately de-
signed for GPS systems.

Subframe 1
Subframe 2
Subframe 3
Subframe 4
Subframe 5

Data word

8
Data word

1
HOW
TLM
Data word

2

Data
Parity

24 Bits
6 Bits

Data word

7

Fig. 30: GPS navigation message frame structure.

RF front

end

Signal 
acquisition
ADC
Tracking
Bit and frame 
synchronizations

Measurements
Bit 
decoding

Fig. 31: The schematic diagram of a GPS receiver [198]

A. A Primer of GPS Communication System

GPS was designed to provide on-earth users with an easy
way of obtaining their location and timing information by
establishing a set of satellites that continuously orbit around
the earth and broadcast their location and timing information.
In GPS, an on-earth user ﬁrst acquires a satellite’s time and
location information and then estimate the distance (a.k.a.
pseudo-range) from the satellite to itself by calculating the
time of signal travel. The on-earth user’s geographical location
can be determined mathematically, considering the locations
and estimated pseudo ranges of multiple satellites. As such,
wireless communication in GPS is one-way communication.

Fig. 30 shows the structure of a GPS navigation message,
which consists of 5 equally-sized subframes. Each subframe
is composed of 10 data words, consisting of 24 raw data bits
followed by 6 parity bits. The ﬁrst data word in each subframe
is the telemetry (TLM) word, which is a binary preamble for
subframe detection. It also carries administrative status infor-
mation. Following the TLM word is Handover (HOW) word
and carries GPS time information, which is used to identify
the subframe. Subframe 1 carries the information required for
clock offset estimation. Subframes 2 and 3 consist of satellite
ephemeris data that can be used by the users to estimate the
satellite’s location at a particular time accurately. Subframes
4 and 5 carry almanac data that provides information on all
satellites and their orbits on the constellation.

The navigation message is sent at 50 bps data rate. All
GPS satellites operate in 1575.42 MHz (L1 channel) and
1227.60 MHz (L2 channel) and use one of the following
signaling protocols:

• Course Acquisition (C/A) Code: C/A signal uses a di-
rect sequence spread spectrum (DSSS) with a 1023-chip
pseudo-random spreading sequence, which is replicated
20 times to achieve higher spreading gain. The main lobe
C/A signal bandwidth is 2 MHz and the spreading gain
is 10 × log10(20 × 1023) ≈43 dB. The C/A signal is
transmitted over the L1 frequency channel and is mainly
used to serve civilian users.


## --- Page 31 ---

### Section: X-B Jamming Attacks

31

• P-Code: P-code signal also uses spreading spectrum. The
length of its spreading code is 10, 230 chips per bit. P
signal is more spread over the frequency and can achieve
higher spreading gain (≈53 dB) than the C/A signal.
The signal bandwidth is 20 MHz for the P-code signal. P
signal can be transmitted over both L1 and L2 channels
and used by the US Department of Defense to serve
authorized users.
Fig. 31 shows the structure of a GPS receiver. When
a GPS device receives GPS signal from satellites, it uses
a signal acquisition module to identify the corresponding
satellites. The signal acquisition will be made using C/A code
correlation and exhaustive search over a possible range of
Doppler frequencies. The tracking module modiﬁes the coarse
changes in the phase and frequency of the acquired signal.
Following the phase and frequency tracking, the received chips
are synchronized and demodulated into bits that are used for
measurement.

B. Jamming Attacks

Given that GPS is a one-way communication system, the
potential jamming threat in GPS is mainly posing on on-
earth GPS user devices. Fig. 29 shows an instance of jamming
attack on some GPS-based navigation applications. Since GPS
satellites are very far from earth, on-earth GPS signals can
be easily drowned by jamming signals. Table XI summarizes
existing jamming attacks on GPS communications. We detail
them in the following.

In [199], the performance of a GPS receiver was studied
in the face of jamming attacks. A wide-band commercial
off-the-shelf radio jammer at L1 carrier frequency has been
used to jam an on-board GPS signal. The jamming signal
bandwidth was set to 60 MHz, and its transmit power was
measured to −35 dBW. Carrier-to-Noise Ratio (CNR) was
used to measure the received GPS signal strength. CNR is
a bandwidth-independent metric expressed as the ratio of
carrier power to noise power per hertz. It was shown that,
for stationary and semi-stationary GPS receivers, the CNR
of 30 dB/Hz to −35 dB/Hz sufﬁces for signal detection. In
a jamming-free scenario, it was measured that the CNR is
44 dB/Hz at a GPS receiver.
Signal spooﬁng is another critical security threat to GPS
systems. GPS spooﬁng can be used to falsify the navigation
estimation and timing synchronization. In [200]–[202], the
authors analyzed the performance of civilian GPS receivers
under practical GPS spooﬁng. In addition to global location,
the GPS system provides time information for GPS receivers.
This time information provides time source in the range
from microsecond to seconds for interoperability of many
applications, and the system components that are dispersed
in different time-zone areas [203]. In [204], Kuhn et al.
introduced a potential security threat to GPS communications
called “selective-delay attack”, in which the attacker was
designed to falsify the timing of a GPS receiver by spooﬁng
a delayed version of the signal. They analytically showed that
the current positioning systems are not resilient to selective-
delay attacks.

C. Anti-Jamming Attacks

Since the GPS communication system employs the spectrum
spreading technique for data transmission, it bears 43 dB
spreading gain for C/A code (civilian use) and 52 dB spreading
gain for P-code (military use). The spreading gain enables a
GPS receiver to combat jamming attacks to some extent. In ad-
dition to its inherent spectrum spreading technique, other anti-
jamming techniques (e.g., MIMO-based jamming mitigation)
can also be used to improve its resilience to jamming attacks.
In what follows, we review existing anti-jamming attacks for
GPS in the literature, which are summarized in Table XI.
Jamming Signal Filtering: In [205], Zhang et al. proposed
to enhance a GPS receiver’s resilience to jamming attack by
designing a ﬁltering mask in both time and frequency domains.
Such a ﬁltering mask uses the time and frequency distributions
of the jamming signal to suppress its energy while allowing
GPS signals to pass. In [206], an adaptive notch ﬁlter was
designed to detect, estimate, and block single-tone continuous
jamming signals. Their proposed notch ﬁlter used a second-
order IIR ﬁlter designed in the time domain. In [207], Rezaei
et al. aims to enhance the capability of notch in jamming
mitigation ﬁlter for a GPS receiver. The authors proposed to
use the short-time Fourier transform (STFT) to increase the
time and frequency domain resolution.
Antenna Array Design: Antenna array processing is another
technique that is used by GPS receivers to enhance their
jamming resilience [208]. In [209], Rezazadeh et al. designed
an adaptive antenna system by leveraging the antenna’s pattern
and polarization diversity to nullify the jamming signal in
airborne GPS applications. The authors built a prototype of
the designed antenna and evaluated its performance in the
presence of jamming attack. Their experimental results showed
that the implemented antenna is capable of achieving up to
38 dB jamming suppression gain. In [210], Zhang et al. studied
the challenges associated with the antenna array design for
GPS receiver. The authors proposed an array-based adaptive
anti-jamming algorithm to suppress jamming signal with neg-
ligible phase distortion. In [211], Sun et al. harnessed the
inherent self-coherence feature of GPS signal to mitigate the
jamming signal, as the GPS signal repeats 20 times within each
symbol. In [212], a beamforming technique was designed as
an anti-jamming solution for GPS communications. A spectral
self-coherence beamforming technique was proposed to design
a weight vector to nullify the jamming signal and improve the
desired signal detection.

A similar idea was explored in [213], where the received
signal is ﬁrst projected onto the jamming signal’s orthogonal
space, and a so-called CLEAN method [214] was used to
extract the received GPS signals. The CLEAN method is a
classical approach that iteratively computes the beamforming
vectors to identify the arrival direction of the signals of
interest. It uses the repetitive pattern of the C/A code to
construct the beamforming vectors. The authors evaluated the
performance of their proposed anti-jamming technique via
both computer simulations and real-world experiments. They
considered four GPS signals arriving at different directions
and a continuous wave jamming signal. The simulation results


## --- Page 32 ---

### Section: XI Open Problems and Research Directions

32

demonstrated that their proposed algorithm could successfully
acquire the 4 GPS signal streams when jamming signal power
to noise power ratio (JNR) is 40 dB. Their experimental results
show that, using a 4-antenna array plane, the proposed receiver
can correctly determine its position when JNR is 20 dB.
Jamming Detection Mechanisms: In [215], Gao et al. pro-
posed to use machine learning for spooﬁng attack detection
in GNSS communications. They used isometric mapping and
Laplacian eigen mapping algorithms for feature extraction, and
trained the support vector machine to classify the features and
detect the spooﬁng attack.

#### XI. OPEN PROBLEMS AND RESEARCH DIRECTIONS

In this section, we ﬁrst list some open problems in de-
signing efﬁcient anti-jamming techniques and then point out
some promising research directions toward securing wireless
communication networks against jamming attacks.

A. Open Problems

Despite the signiﬁcant advancement of wireless communi-
cation and networking technologies in the past decades, real-
world wireless communication systems (e.g., Wi-Fi, cellular,
Bluetooth, ZigBee, and GPS) are still vulnerable to malicious
jamming attacks. As wireless services become increasingly
important in our society, the jamming vulnerability of wireless
Internet services poses serious security threats to existing
and future cyber-physical systems. This vulnerability can be
attributed to the lack of practical, effective, and efﬁcient
anti-jamming techniques that can be deployed in real-world
wireless systems to secure wireless communication against
jamming attacks. One may argue that Bluetooth is equipped
with the frequency hopping technique, and ZigBee/GPS is
equipped with spectrum spreading technique, and (therefore)
these networks can survive in the presence of jamming attacks.
This argument, however, is not valid. Bluetooth can only work
in the face of narrow-band jamming attack, and ZigBee/GPS
can only work under a low-power jamming attack. These
wireless systems as well as the most prevailing Wi-Fi and
cellular networks, can be easily paralyzed by a jamming attack
using commercial off-the-shelf SDR devices.

In what follows, we describe some open problems in the
design of anti-jamming techniques, with the aim of spurring
more research efforts on advancing the design of jamming-
resistant wireless communication systems.

1) Effectiveness of Anti-Jamming Techniques: One open re-
search problem is to design effective anti-jamming techniques
for wireless networks. Existing anti-jamming techniques (e.g.,
frequency hopping, spectrum spreading, retransmission, and
MIMO-based jamming mitigation) have a limited ability to
tackle jamming attacks. For example, neither frequency hop-
ping nor spectrum spreading technique is able to salvage
wireless communication services when jamming signal is
covering the full spectrum and stronger than useful signal.
The state-of-the-art MIMO-based technique can offer at most
30 dB jamming mitigation capability for two-antenna wireless
receivers. This indicates that if jamming signal is 22 dB
stronger than the useful signal, the receivers in a wireless

network will not be capable of decoding their packets under
jamming attacks. Therefore, a natural question to ask is how to
design effective anti-jamming techniques for wireless networks
so that those wireless networks can be immune to jamming at-
tacks, regardless of jamming signal power, bandwidth, sources,
and other conﬁguration parameters.

2) Efﬁciency of Anti-Jamming Techniques: Another open
problem is to improve the efﬁciency of anti-jamming tech-
niques. For example, frequency hopping can cope with narrow-
band jamming attacks, but it signiﬁcantly reduces spectral
efﬁciency. Bluetooth uses frequency hopping to be immune
to unknown interference and jamming attack, at the cost of
using only one of 79 channels at one time. Spectrum spreading
technique has been used in ZigBee, GPS, and 3G cellular
networks. It allows these networks to be immune to low-
power jamming attacks. However, their jamming immunity
does not come free. It signiﬁcantly reduces the spectral ef-
ﬁciency by expanding the signal bandwidth using a spreading
code. Retransmission may be salvage wireless communica-
tion, but it also reduces the communication efﬁciency in the
time domain. MIMO-based jamming mitigation also lowers
the spatial degrees of freedom that can be used for useful
signal transmission. Therefore, a question to ask is how to
improve the communication efﬁciency of wireless networks
when they employ anti-jamming techniques to secure their
communications. As expected, the jamming resilience will not
come for free. A more reasonable question is how to achieve
the tradeoff between communication efﬁciency and jamming
resilience of a wireless network.

3) Practicality of Anti-Jamming Techniques: An important
problem that remains open is to bridge the gap between the-
oretical study (or model-based analysis) and practical imple-
mentation. In the past decades, many research works focus on
the theoretical investigation of anti-jamming techniques using
approaches such as game theory and cross-layer optimization.
Despite offering insights to advance our understanding of anti-
jamming design, such theoretical results cannot be deployed
in real-world wireless network systems due to their unrealistic
assumptions (e.g., availability of global channel information,
prior knowledge of jamming actions) and prohibitively high
computational complexity. Securing real-world wireless net-
works (e.g., Wi-Fi, cellular, ZigBee, Bluetooth, and GPS)
calls for the intellectual design of anti-jamming strategies
that can be implemented in realistic wireless environments
where computational power and network-wide cooperation are
limited. Particularly, PHY-layer anti-jamming techniques have
a stringent requirement on their computational complexity.
This is because PHY-layer anti-jamming techniques should
have an ASIC or FPGA implementation in modern wireless
chips, which have a strict delay constraint for decoding each
packet.

4) Securing Wireless Communication System by Design:
A conventional anti-jamming approach for wireless commu-
nication systems is composed of the following three steps: i)
wireless devices detect the presence of jamming attacks, ii)
wireless devices temporarily stop their communications and
invoke an anti-jamming mechanism, and iii) wireless com-
munication resumes under the protection of its anti-jamming


## --- Page 33 ---

### Section: XI-B Research Directions

33

#### TABLE XI: A summary of jamming attacks and anti-jamming strategies for GPS communications.

Ref.
Description

Jamming
attacks

[199]
Analyzed GPS receiver performance under wide-band commercial jamming attacks
[200]–[202]
Investigated the GPS signal spooﬁng.
[203]
Studied the GPS time information attack.
[204]
Used spooﬁng attack to falsify the timing of the military GPS signals.

Anti-jamming
techniques

[205]
Designed a time-frequency mask using the time and frequency distributions of the jamming signal.
[206]
Used adaptive notch ﬁlter design to detect, estimate, and block single-tone continuous jamming signals.
[207]
Used short-time Fourier transform (STFT) to enhance resolution in notch ﬁlter design.
[208]
Designed an adaptive antenna array.
[209]
Designed an adaptive antenna system based on pattern and polarization diversity.
[210]
Proposed an adaptive array-based algorithm with negligible phase distortion.
[211]
Used a beamforming technique considering inherent self-coherence feature of the GPS signals.
[212]
Used a self-coherence beamforming technique to nullify the jamming signal and enhance the desired signal quality.
[213]
Used received signal projection onto the orthogonal space of jamming signal.
[215]
Proposed a learning-based spooﬁng attack detection.

mechanism. This approach, however, is not capable of main-
taining constant wireless connection under jamming attack due
to the separation of jamming detection and countermeasure
invocation, and the disconnection of wireless service may
not be intolerable in many applications such as surveillance
and drone control on the battleﬁeld. Realizing this limitation,
securing wireless communication by design has emerged as
an appealing anti-jamming paradigm and attracted a lot of
research attention in recent years. The basic idea behind this
paradigm is to take into account the anti-jamming requirement
in the original design of wireless systems. By doing so, a
wireless communication system may be capable of offering
constant wireless services without disconnection when suffers
from jamming attacks. For this paradigm, many problems
remain open and need to be investigated, such as the way of
designing anti-jamming mechanisms and the way of striking
a balance between communication efﬁciency and jamming
mitigation capability.

B. Research Directions

Jamming attack is arguably the most critical security threat
for wireless networking services as it is easy to launch but
hard to defend. The limited progress in the design of jamming-
resilient wireless systems underscores the grand challenges in
the innovation of anti-jamming techniques and the critical need
for securing wireless networks against jamming attacks. In
what follows, we point out some promising research direc-
tions.

1) MIMO-based Jamming Mitigation: Given the potential
of MIMO technology that has demonstrated in Wi-Fi and 4/5G
cellular networks, the exploration of practical yet efﬁcient
MIMO-based jamming mitigation techniques is a promising
research direction towards securing wireless networks and
deserves more research efforts. The past decade has witnessed
the explosion of MIMO research and applications in wireless
communication systems. With the rapid advances in signal
processing and antenna technology, MIMO has become a norm
for wireless devices. Most commercial Wi-Fi and cellular de-
vices such as smartphones and laptops are now equipped with
multiple antennas for MIMO communication. Recent results in
[76] show that, compared to frequency hopping and spectrum
sharing, MIMO-based jamming mitigation is not effective in
jamming mitigation but also efﬁcient in spectrum utilization.

In addition, the existing results from the research on MIMO-
based interference management (e.g., interference cancellation,
interference neutralization, interference alignment, etc.) can
be leveraged for the design of MIMO-based anti-jamming
techniques. In turn, the ﬁndings and results from the design
of MIMO-based anti-jamming techniques can also be applied
to managing of unknown interference (e.g., blind interference
cancellation) in Wi-Fi, cellular, and vehicular networks.

2) Cross-Domain Anti-Jamming Design:
Most existing
anti-jamming techniques exploit the degree of freedom in a
single (time, frequency, space, code, etc.) domain to decode
in-the-air radio packets in the presence of interfering signals
from malicious jammers. For instance, channel hopping, which
is used in Bluetooth, manipulates radio signals in the frequency
domain to avoid jamming attack; spectrum spreading employs
a secret sequence in the code domain to whiten the energy
of narrow-band jamming signal to enhance a wireless re-
ceiver’s resilience to jamming attacks; MIMO-based jamming
mitigation aims to project signals in the spatial domain so
as to make useful signal perpendicular to jamming signals.
However, these single-domain anti-jamming techniques appear
to have a limited ability of handling jamming signals due to a
number of factors, such as the available spectrum bandwidth,
the computational complexity, the number of antennas, the
resolution of ADC, the nonlinearity of radio circuit, and
the packet delay constraint. One research direction toward
enhancing a wireless network’s resilience to jamming attacks
is by jointly exploiting multiple domains for PHY-layer signal
processing and MAC-layer protocol manipulation. This direc-
tion deserves more research efforts to explore practical and
efﬁcient anti-jamming designs.

3) Cross-Layer Anti-Jamming Design: For constant jam-
ming attacks, most existing countermeasures rely on PHY-
layer techniques to avoid jamming signal or mitigate jamming
signal for signal detection. With the growth of smart jamming
attacks that target on speciﬁc network protocols (e.g., pream-
ble/pilot signals in Wi-Fi network and PSS/SSS in cellular net-
work), cross-layer design for anti-jamming strategies becomes
necessary to thwart the increasingly sophisticated jamming
attacks. It calls for joint design of PHY-layer signal processing,
MAC-layer protocol design, and network resource allocation
as well as cross-layer optimization to enable efﬁcient wireless
communications in the presence of various jamming attacks.


## --- Page 34 ---

### Section: XI-B4 Machine Learning for Anti-Jamming Design

34

4) Machine Learning for Anti-Jamming Design: Machine
learning has become a powerful technique and has been
applied to many real-world applications such as image recog-
nition, speech recognition, trafﬁc prediction, product recom-
mendations, self-driving cars, email spam, and malware ﬁlter-
ing. It is particularly useful for solving complex engineering
problems whose underlying mathematical model is unknown.
In recent years, machine learning techniques have been used
to secure wireless communications against jamming attacks
(e.g., [179], [216]) and produced some pioneering yet exciting
results. Therefore, the design of learning-based anti-jamming
techniques is a promising research direction that deserves more
research efforts for an in-depth investigation.

#### XII. CONCLUSION

This survey article provides a comprehensive review of
jamming attacks and anti-jamming techniques for Wi-Fi, cellu-
lar, cognitive radio, ZigBee, Bluetooth, vehicular, RFID, and
GPS wireless networks. For each network, we ﬁrst offered
a primer of its PHY and MAC layers and then elaborated
on its vulnerability under jamming attacks, followed by an
in-depth review on existing jamming strategies and defense
schemes. Particularly, we offered informative tables to sum-
marize existing jamming attacks and anti-jamming techniques
for each network, which will help the audience to grasp the
fundamentals of jamming and anti-jamming strategies. We
also listed some important open problems and pointed out
the promising research directions toward securing wireless
networks against jamming attacks. We hope such a survey
article will help the audience digest the holistic knowledge of
existing jamming/anti-jamming research results and facilitate
the future design of jamming-resilient wireless communication
systems.

#### REFERENCES

[1] C. Condo, V. Bioglio, H. Hafermann, and I. Land, “Practical prod-

uct code construction of polar codes,” IEEE Transactions on Signal
Processing, vol. 68, pp. 2004–2014, 2020.
[2] V. Bioglio, C. Condo, and I. Land, “Design of polar codes in 5G new

radio,” IEEE Communications Surveys & Tutorials, 2020.
[3] M. A. Albreem, M. Juntti, and S. Shahabuddin, “Massive MIMO

detection techniques: A survey,” IEEE Communications Surveys &
Tutorials, vol. 21, no. 4, pp. 3109–3132, 2019.
[4] E. Bj¨ornson and L. Sanguinetti, “Scalable cell-free massive MIMO

systems,” IEEE Transactions on Communications, 2020.
[5] L. Liu and W. Yu, “Massive connectivity with massive MIMO—part

ii: Achievable rate characterization,” IEEE Transactions on Signal
Processing, vol. 66, no. 11, pp. 2947–2959, 2018.
[6] X. Wang, L. Kong, F. Kong, F. Qiu, M. Xia, S. Arnon, and G. Chen,

“Millimeter wave communication: A comprehensive survey,” IEEE
Communications Surveys & Tutorials, vol. 20, no. 3, pp. 1616–1653,
2018.
[7] X. Shen, Y. Liu, L. Zhao, G.-L. Huang, X. Shi, and Q. Huang, “A

miniaturized microstrip antenna array at 5G millimeter-wave band,”
IEEE Antennas and Wireless Propagation Letters, vol. 18, no. 8,
pp. 1671–1675, 2019.
[8] P. Kheirkhah Sangdeh, H. Pirayesh, Q. Yan, K. Zeng, W. Lou, and

H. Zeng, “A practical downlink NOMA scheme for wireless LANs,”
IEEE Transactions on Communications, vol. 68, no. 4, pp. 2236–2250,
2020.
[9] B. Makki, K. Chitti, A. Behravan, and M.-S. Alouini, “A survey of

NOMA: Current status and open research challenges,” IEEE Open
Journal of the Communications Society, vol. 1, pp. 179–189, 2020.

[10] Y. Yuan, Z. Yuan, and L. Tian, “5G non-orthogonal multiple access

study in 3GPP,” IEEE Communications Magazine, vol. 58, no. 7,
pp. 90–96, 2020.
[11] X. Chen, G. Liu, Z. Ma, X. Zhang, P. Fan, S. Chen, and F. R. Yu,

“When full duplex wireless meets non-orthogonal multiple access:
Opportunities and challenges,” IEEE Wireless Communications, vol. 26,
no. 4, pp. 148–155, 2019.
[12] A. Goyal and K. Kumar, “LTE-advanced carrier aggregation for en-

hancement of bandwidth,” in Advances in VLSI, Communication, and
Signal Processing, pp. 341–351, Springer, 2020.
[13] N. Naderializadeh, M. A. Maddah-Ali, and A. S. Avestimehr, “Cache-

aided interference management in wireless cellular networks,” IEEE
Transactions on Communications, vol. 67, no. 5, pp. 3376–3387, 2019.
[14] P. Yu, F. Zhou, X. Zhang, X. Qiu, M. Kadoch, and M. Cheriet, “Deep

learning-based resource allocation for 5G broadband TV service,” IEEE
Transactions on Broadcasting, pp. 1–14, 2020.
[15] M. Chen, Z. Yang, W. Saad, C. Yin, H. V. Poor, and S. Cui, “A joint

learning and communications framework for federated learning over
wireless networks,” arXiv preprint arXiv:1909.07972, 2019.
[16] A. M. Wyglinski, R. Getz, T. Collins, and D. Pu, Software-Deﬁned

Radio for Engineers. Artech House, 2018.
[17] W. Xia, Y. Wen, C. H. Foh, D. Niyato, and H. Xie, “A survey

on software-deﬁned networking,” IEEE Communications Surveys &
Tutorials, vol. 17, no. 1, pp. 27–51, 2014.
[18] Y. Miao, X. Liu, K.-K. R. Choo, R. H. Deng, H. Wu, and H. Li,

“Fair and dynamic data sharing framework in cloud-assisted Internet
of everything,” IEEE Internet of Things Journal, vol. 6, no. 4, pp. 7201–
7212, 2019.
[19] A. Mpitziopoulos, D. Gavalas, C. Konstantopoulos, and G. Pantziou,

“A survey on jamming attacks and countermeasures in WSNs,” IEEE
Communications Surveys & Tutorials, vol. 11, no. 4, pp. 42–56, 2009.
[20] Y. Zhou, Y. Fang, and Y. Zhang, “Securing wireless sensor networks:

a survey,” IEEE Communications Surveys & Tutorials, vol. 10, no. 3,
pp. 6–28, 2008.
[21] Y. M. Amin and A. T. Abdel-Hamid, “A comprehensive taxonomy and

analysis of IEEE 802.15.4 attacks,” Journal of Electrical and Computer
Engineering, vol. 2016, 2016.
[22] D. R. Raymond and S. F. Midkiff, “Denial-of-service in wireless sensor

networks: Attacks and defenses,” IEEE Pervasive Computing, vol. 7,
no. 1, pp. 74–81, 2008.
[23] S. Vadlamani, B. Eksioglu, H. Medal, and A. Nandi, “Jamming attacks

on wireless networks: A taxonomic survey,” International Journal of
Production Economics, vol. 172, pp. 76–94, 2016.
[24] W. Xu, K. Ma, W. Trappe, and Y. Zhang, “Jamming sensor networks:

attack and defense strategies,” IEEE network, vol. 20, no. 3, pp. 41–47,
2006.
[25] L. Zhang, G. Ding, Q. Wu, Y. Zou, Z. Han, and J. Wang, “Byzantine

attack and defense in cognitive radio networks: A survey,” IEEE
Communications Surveys & Tutorials, vol. 17, no. 3, pp. 1342–1363,
2015.
[26] D. Das and S. Das, “Primary user emulation attack in cognitive

radio networks: A survey,” IRACST-International Journal of Computer
Networks and Wireless Communications, vol. 3, no. 3, pp. 312–318,
2013.
[27] A. G. Fragkiadakis, E. Z. Tragos, and I. G. Askoxylakis, “A survey on

security threats and detection techniques in cognitive radio networks,”
IEEE Communications Surveys & Tutorials, vol. 15, no. 1, pp. 428–
445, 2012.
[28] R. Di Pietro and G. Oligeri, “Jamming mitigation in cognitive radio

networks,” IEEE Network, vol. 27, no. 3, pp. 10–15, 2013.
[29] A. Attar, H. Tang, A. V. Vasilakos, F. R. Yu, and V. C. Leung, “A

survey of security challenges in cognitive radio networks: Solutions
and future research directions,” Proceedings of the IEEE, vol. 100,
no. 12, pp. 3172–3186, 2012.
[30] R. P. Jover, “Security attacks against the availability of LTE mobility

networks: Overview and research directions,” in Proceedings of inter-
national symposium on wireless personal multimedia communications
(WPMC), pp. 1–9, 2013.
[31] K. Grover, A. Lim, and Q. Yang, “Jamming and anti-jamming tech-

niques in wireless networks: a survey,” International Journal of Ad Hoc
and Ubiquitous Computing, vol. 17, no. 4, pp. 197–215, 2014.
[32] C. Shahriar, M. La Pan, M. Lichtman, T. C. Clancy, R. McGwier,

R. Tandon, S. Sodagari, and J. H. Reed, “PHY-layer resiliency in
OFDM communications: A tutorial,” IEEE Communications Surveys
& Tutorials, vol. 17, no. 1, pp. 292–314, 2014.


## --- Page 35 ---

35

[33] K. Pelechrinis, M. Iliofotou, and S. V. Krishnamurthy, “Denial of

service attacks in wireless networks: The case of jammers,” IEEE
Communications surveys & tutorials, vol. 13, no. 2, pp. 245–257, 2010.
[34] M. Vanhoef and F. Piessens, “Advanced Wi-Fi attacks using commodity

hardware,” in Proceedings of Computer Security Applications Confer-
ence, pp. 256–265, 2014.
[35] M. Ettus, “Universal software radio peripheral (USRP),” Ettus Research

LLC http://www.ettus.com, 2008.
[36] WARP: Wireless Open Access Research Platform, “Warp v3,” 2020.

Available at: https://warpproject.org/trac/wiki/HardwareUsersGuides/
WARPv3 [Online; accessed 2020-09-17].
[37] “IEEE standard for information technology–telecommunications and

information exchange between systems—local and metropolitan area
networks–speciﬁc requirements–part 11: Wireless LAN medium access
control (MAC) and physical layer (PHY) speciﬁcations–amendment 4:
Enhancements for very high throughput for operation in bands below
6 GHz.,” IEEE Std 802.11ac(TM)-2013, pp. 1–425, 2013.
[38] E. Perahia and R. Stacey, Next generation wireless LANs: 802.11n and

802.11ac. Cambridge university press, 2013.
[39] B. Bellalta, “IEEE 802.11ax: High-efﬁciency WLANs,” IEEE Wireless

Communications, vol. 23, no. 1, pp. 38–46, 2016.
[40] E. Khorov, A. Kiryanov, A. Lyakhov, and G. Bianchi, “A tutorial

on IEEE 802.11ax high efﬁciency WLANs,” IEEE Communications
Surveys Tutorials, vol. 21, no. 1, pp. 197–216, 2019.
[41] T. Karhima, A. Silvennoinen, M. Hall, and S.-G. Haggman, “IEEE

802.11 b/g WLAN tolerance to jamming,” in Proceedings of IEEE
Military Communications Conference (MILCOM), vol. 3, pp. 1364–
1370, 2004.
[42] L. Jun, J. H. Andrian, and C. Zhou, “Bit error rate analysis of jam-

ming for OFDM systems,” in wireless telecommunications Symposium,
pp. 1–8, IEEE, 2007.
[43] Y. Cai, K. Pelechrinis, X. Wang, P. Krishnamurthy, and Y. Mo,

“Joint reactive jammer detection and localization in an enterprise WiFi
network,” Computer Networks, vol. 57, no. 18, pp. 3799–3811, 2013.
[44] S. Prasad and D. J. Thuente, “Jamming attacks in 802.11g—a cognitive

radio based approach,” in Proceedings of IEEE Military Communica-
tions Conference (MILCOM), pp. 1219–1224, 2011.
[45] Q. Yan, H. Zeng, T. Jiang, M. Li, W. Lou, and Y. T. Hou, “MIMO-based

jamming resilient communication in wireless networks,” in Proceed-
ings of IEEE International Conference on Computer Communications
(INFOCOM), pp. 2697–2706, 2014.
[46] Q. Yan, H. Zeng, T. Jiang, M. Li, W. Lou, and Y. T. Hou, “Jamming

resilient communication using MIMO interference cancellation,” IEEE
Transactions on Information Forensics and Security, vol. 11, no. 7,
pp. 1486–1499, 2016.
[47] M. Schulz, F. Gringoli, D. Steinmetzer, M. Koch, and M. Hollick,

“Massive reactive smartphone-based jamming using arbitrary wave-
forms and adaptive power control,” in Proceedings of ACM Conference
on Security and Privacy in Wireless and Mobile Networks, pp. 111–
121, 2017.
[48] E. Bayraktaroglu, C. King, X. Liu, G. Noubir, R. Rajaraman, and

B. Thapa, “Performance of IEEE 802.11 under jamming,” Mobile
Networks and Applications, vol. 18, no. 5, pp. 678–696, 2013.
[49] I. Broustis, K. Pelechrinis, D. Syrivelis, S. V. Krishnamurthy, and

L. Tassiulas, “FIJI: Fighting implicit jamming in 802.11 WLANs,” in
Proceedings of International Conference on Security and Privacy in
Communication Systems, pp. 21–40, Springer, 2009.
[50] S. Gvozdenovic, J. K. Becker, J. Mikulskis, and D. Starobinski, “Trun-

cate after preamble: PHY-based starvation attacks on IoT networks,” in
Proceedings of ACM Conference on Security and Privacy in Wireless
and Mobile Networks, pp. 89–98, 2020.
[51] S. Bandaru, “Investigating the effect of jamming attacks on wireless

LANs,” International Journal of Computer Applications, vol. 99,
no. 14, pp. 5–9, 2014.
[52] M. J. La Pan, T. C. Clancy, and R. W. McGwier, “Jamming attacks

against OFDM timing synchronization and signal acquisition,” in Pro-
ceedings of IEEE Military Communications Conference (MILCOM),
pp. 1–7, 2012.
[53] M. J. La Pan, T. C. Clancy, and R. W. McGwier, “Physical layer orthog-

onal frequency-division multiplexing acquisition and timing synchro-
nization security,” Wireless Communications and Mobile Computing,
vol. 16, no. 2, pp. 177–191, 2016.
[54] C. Shahriar, S. Sodagari, R. McGwier, and T. C. Clancy, “Performance

impact of asynchronous off-tone jamming attacks against OFDM,” in
Proceedings of IEEE ICC, pp. 2177–2182, 2013.
[55] S. Zhao, Z. Lu, Z. Luo, and Y. Liu, “Orthogonality-sabotaging attacks

against OFDMA-based wireless networks,” in Proceedings of IEEE

International Conference on Computer Communications (INFOCOM),
pp. 1603–1611, 2019.
[56] M. J. La Pan, T. C. Clancy, and R. W. McGwier, “Phase warping and

differential scrambling attacks against OFDM frequency synchroniza-
tion,” in Proceedings of IEEE International Conference on Acoustics,
Speech and Signal Processing, pp. 2886–2890, 2013.
[57] T. C. Clancy, “Efﬁcient OFDM denial: Pilot jamming and pilot nulling,”

in Proceedings of IEEE International Conference on Communications
(ICC), pp. 1–5, 2011.
[58] C. Shahriar, S. Sodagari, and T. C. Clancy, “Performance of pilot

jamming on MIMO channels with imperfect synchronization,” in
Proceedings of IEEE International Conference on Communications
(ICC), pp. 898–902, 2012.
[59] S. Sodagari and T. C. Clancy, “Efﬁcient jamming attacks on MIMO

channels,” in Proceedings of IEEE International Conference on Com-
munications (ICC), pp. 852–856, 2012.
[60] S. Sodagari and T. C. Clancy, “On singularity attacks in MIMO chan-

nels,” Transactions on Emerging Telecommunications Technologies,
vol. 26, no. 3, pp. 482–490, 2015.
[61] A. L. Scott, “Effects of cyclic preﬁx jamming versus noise jamming in

OFDM signals,” tech. rep., Air Force Institute of Technology Graduate
School of Engineering and Management, 2011.
[62] G. Patwardhan and D. Thuente, “Jamming beamforming: a new attack

vector in jamming IEEE 802.11ac networks,” in Proceedings of IEEE
Military Communications Conference (MILCOM), pp. 1534–1541,
2014.
[63] D. Thuente and M. Acharya, “Intelligent jamming in wireless networks

with applications to 802.11b and other networks,” in Proceedings of
IEEE Military Communications Conference (MILCOM), vol. 6, p. 100,
2006.
[64] M. Acharya, T. Sharma, D. Thuente, and D. Sizemore, “Intelligent

jamming in 802.11b wireless networks,” Proceedings of OPNETWORK.
Washington DC, USA: OPNET, 2004.
[65] R. Negi and A. Rajeswaran, “DoS analysis of reservation based

MAC protocols,” in Proceedings of IEEE International Conference on
Communications (ICC), vol. 5, pp. 3632–3636, 2005.
[66] G. Noubir, R. Rajaraman, B. Sheng, and B. Thapa, “On the robustness

of IEEE 802.11 rate adaptation algorithms against smart jamming,” in
Proceedings of ACM conference on Wireless network security, pp. 97–
108, 2011.
[67] C. Orakcal and D. Starobinski, “Rate adaptation in unlicensed bands

under smart jamming attacks,” in Proceedings of IEEE International
ICST Conference on Cognitive Radio Oriented Wireless Networks and
Communications (CROWNCOM), pp. 1–6, 2012.
[68] C. Orakcal and D. Starobinski, “Jamming-resistant rate adaptation in

Wi-Fi networks,” Performance Evaluation, vol. 75, pp. 50–68, 2014.
[69] S. Biaz and S. Wu, “Rate adaptation algorithms for IEEE 802.11 net-

works: A survey and comparison,” in Proceedings of IEEE Symposium
on Computers and Communications, pp. 130–136, 2008.
[70] J. He, W. Guan, L. Bai, and K. Chen, “Theoretic analysis of IEEE

802.11 rate adaptation algorithm samplerate,” IEEE Communications
Letters, vol. 15, no. 5, pp. 524–526, 2011.
[71] J. He, Z. Tang, H.-H. Chen, and S. Wang, “Performance analysis of

ONOE protocol—an IEEE 802.11 link adaptation algorithm,” Interna-
tional Journal of Communication Systems, vol. 25, no. 7, pp. 821–831,
2012.
[72] V. Navda, A. Bohra, S. Ganguly, and D. Rubenstein, “Using channel

hopping to increase 802.11 resilience to jamming attacks,” in Proceed-
ings of IEEE International Conference on Computer Communications
(INFOCOM), pp. 2526–2530, 2007.
[73] J. Jeung, S. Jeong, and J. Lim, “Adaptive rapid channel-hopping scheme

mitigating smart jammer attacks in secure WLAN,” in Proceedings
of IEEE Military Communications Conference (MILCOM), pp. 1231–
1236, 2011.
[74] I. Harjula, J. Pinola, and J. Prokkola, “Performance of IEEE 802.11

based WLAN devices under various jamming signals,” in Proceedings
of IEEE MILCOM, pp. 2129–2135, 2011.
[75] W. Shen, P. Ning, X. He, H. Dai, and Y. Liu, “MCR decoding: A

MIMO approach for defending against wireless jamming attacks,” in
Proceedings of IEEE Conference on Communications and Network
Security, pp. 133–138, 2014.
[76] H. Zeng, C. Cao, H. Li, and Q. Yan, “Enabling jamming-resistant

communications in wireless MIMO networks,” in Proceedings of IEEE
Conference on Communications and Network Security (CNS), pp. 1–9,
2017.


## --- Page 36 ---

36

[77] G. Noubir and G. Lin, “Low-power DoS attacks in data wireless

LANs and countermeasures,” Proceedings of ACM SIGMOBILE Mobile
Computing and Communications Review, vol. 7, no. 3, pp. 29–30, 2003.
[78] G. Lin and G. Noubir, “On link layer denial of service in data wireless

LANs,” Wireless Communications and Mobile Computing, vol. 5, no. 3,
pp. 273–284, 2005.
[79] K. Pelechrinis, I. Broustis, S. V. Krishnamurthy, and C. Gkantsidis,

“Ares: an anti-jamming reinforcement system for 802.11 networks,”
in Proceedings of international conference on Emerging networking
experiments and technologies, pp. 181–192, 2009.
[80] K. Pelechrinis, I. Broustis, S. V. Krishnamurthy, and C. Gkantsidis,

“A measurement-driven anti-jamming system for 802.11 networks,”
IEEE/ACM Transactions on Networking, vol. 19, no. 4, pp. 1208–1222,
2011.
[81] C. Orakcal and D. Starobinski, “Jamming-resistant rate control in Wi-Fi

networks,” in Proceedings of IEEE Global Communications Conference
(GLOBECOM), pp. 1048–1053, 2012.
[82] E. Garcia-Villegas, M. G´omez, E. L´opez-Aguilera, and J. Casademont,

“Detecting and mitigating the impact of wideband jammers in IEEE
802.11 WLANs,” in Proceedings of International Wireless Communi-
cations and Mobile Computing Conference, pp. 57–61, 2010.
[83] O. Pu˜nal, I. Aktas¸, C.-J. Schnelke, G. Abidin, K. Wehrle, and J. Gross,

“Machine learning-based jamming detection for IEEE 802.11: Design
and experimental evaluation,” in Proceeding of IEEE International
Symposium on a World of Wireless, Mobile and Multimedia Networks,
pp. 1–10, 2014.
[84] E. U. T. R. Access, “Physical channels and modulation,” 3GPP TS,

vol. 36, p. V8, 2009.
[85] E. Dahlman, S. Parkvall, J. Sk¨old, and P. Beming, “3G evolution: HSPA

and LTE for mobile broadband,” Academic Press, 2010.
[86] G. Romero, V. Deniau, and O. Stienne, “LTE physical layer vulner-

ability test to different types of jamming signals,” in Proceedings
of International Symposium on Electromagnetic Compatibility-EMC
EUROPE, pp. 1138–1143, 2019.
[87] S. Zorn, M. Gardill, R. Rose, A. Goetz, R. Weigel, and A. Koelpin, “A

smart jamming system for UMTS/WCDMA cellular phone networks
for search and rescue applications,” in Proceedings of IEEE/MTT-S
International Microwave Symposium Digest, pp. 1–3, 2012.
[88] S. Zorn, M. Maser, A. Goetz, R. Rose, and R. Weigel, “A power saving

jamming system for E-GSM900 and DCS1800 cellular phone networks
for search and rescue applications,” in Proceedings of IEEE Topical
Conference on Wireless Sensors and Sensor Networks, pp. 33–36, 2011.
[89] R. Krenz and S. Brahma, “Jamming LTE signals,” in Proceedings

of IEEE International Black Sea Conference on Communications and
Networking (BlackSeaCom), pp. 72–76, 2015.
[90] M. Lichtman, R. P. Jover, M. Labib, R. Rao, V. Marojevic, and J. H.

Reed, “LTE/LTE-A jamming, spooﬁng, and snifﬁng: threat assessment
and mitigation,” IEEE Communications Magazine, vol. 54, no. 4,
pp. 54–61, 2016.
[91] M. Lichtman, J. H. Reed, T. C. Clancy, and M. Norton, “Vulnerability

of LTE to hostile interference,” in Proceedings of IEEE Global Con-
ference on Signal and Information Processing, pp. 285–288, 2013.
[92] F. M. Aziz, J. S. Shamma, and G. L. St¨uber, “Resilience of LTE

networks against smart jamming attacks: Wideband model,” in Pro-
ceedings of IEEE Annual International Symposium on Personal, Indoor,
and Mobile Radio Communications (PIMRC), pp. 1344–1348, 2015.
[93] J. Kakar, K. McDermott, V. Garg, M. Lichtman, V. Marojevic, and J. H.

Reed, “Analysis and mitigation of interference to the LTE physical
control format indicator channel,” in Proceedings of IEEE Military
Communications Conference (MILCOM), pp. 228–234, IEEE, 2014.
[94] M. Lichtman, T. Czauski, S. Ha, P. David, and J. H. Reed, “Detection

and mitigation of uplink control channel jamming in LTE,” in Pro-
ceedings of IEEE Military Communications Conference (MILCOM),
pp. 1187–1194, 2014.
[95] F. Girke, F. Kurtz, N. Dorsch, and C. Wietfeld, “Towards resilient

5G: Lessons learned from experimental evaluations of LTE uplink
jamming,” in Proceedings of IEEE International Conference on Com-
munications Workshops (ICC Workshops), pp. 1–6, 2019.
[96] F. M. Aziz, J. S. Shamma, and G. L. St¨uber, “Resilience of LTE

networks against smart jamming attacks,” in Proceedings of IEEE
Global Communications Conference, pp. 734–739, 2014.
[97] Y. Arjoune and S. Faruque, “Smart jamming attacks in 5G new radio:

A review,” in IEEE Annual Computing and Communication Workshop
and Conference (CCWC), pp. 1010–1015, 2020.
[98] S. Mavoungou, G. Kaddoum, M. Taha, and G. Matar, “Survey on

threats and attacks on mobile networks,” IEEE Access, vol. 4, pp. 4543–
4572, 2016.

[99] M. Lichtman, R. Rao, V. Marojevic, J. Reed, and R. P. Jover, “5G

NR jamming, spooﬁng, and snifﬁng: threat assessment and mitigation,”
in Proceedings of IEEE International Conference on Communications
Workshops (ICC Workshops), pp. 1–6, 2018.
[100] T. T. Do, E. Bj¨ornson, E. G. Larsson, and S. M. Razavizadeh,

“Jamming-resistant receivers for the massive MIMO uplink,” IEEE
Transactions on Information Forensics and Security, vol. 13, no. 1,
pp. 210–223, 2017.
[101] J. Vinogradova, E. Bj¨ornson, and E. G. Larsson, “Detection and

mitigation of jamming attacks in massive MIMO systems using random
matrix theory,” in Proceedings of IEEE International Workshop on
Signal Processing Advances in Wireless Communications (SPAWC),
pp. 1–5, 2016.
[102] J. Pinola, J. Prokkola, and E. Piri, “An experimental study on jamming

tolerance of 3G/WCDMA,” in Proceedings of IEEE Military Commu-
nications Conference (MILCOM), pp. 1–7, 2012.
[103] B. Makarevitch, “Jamming resistant architecture for WiMAX mesh

network,” in Proceedings of IEEE Military Communications conference
(MILCOM), pp. 1–6, 2006.
[104] R. P. Jover, J. Lackey, and A. Raghavan, “Enhancing the security

of LTE networks against jamming attacks,” EURASIP Journal on
Information Security, vol. 2014, no. 1, p. 7, 2014.
[105] Y. Arjoune, F. Salahdine, M. S. Islam, E. Ghribi, and N. Kaabouch, “A

novel jamming attacks detection approach based on machine learning
for wireless communication,” in Proceedings of IEEE International
Conference on Information Networking (ICOIN), pp. 459–464, 2020.
[106] Q. Wu, G. Ding, J. Wang, and Y.-D. Yao, “Spatial-temporal opportunity

detection for spectrum-heterogeneous cognitive radio networks: Two-
dimensional sensing,” IEEE Transactions on Wireless Communications,
vol. 12, no. 2, pp. 516–526, 2013.
[107] D. Cabric, S. M. Mishra, and R. W. Brodersen, “Implementation issues

in spectrum sensing for cognitive radios,” in Proceedings of Conference
Record of the Thirty-Eighth Asilomar Conference on Signals, Systems
and Computers, vol. 1, pp. 772–776, 2004.
[108] P. K. Varshney, Distributed detection and data fusion. Springer Science

& Business Media, 2012.
[109] M. Jo, L. Han, D. Kim, and H. P. In, “Selﬁsh attacks and detection

in cognitive radio ad-hoc networks,” IEEE network, vol. 27, no. 3,
pp. 46–50, 2013.
[110] S. Anand, Z. Jin, and K. Subbalakshmi, “An analytical model for

primary user emulation attacks in cognitive radio networks,” in Pro-
ceedings of IEEE Symposium on New Frontiers in Dynamic Spectrum
Access Networks, pp. 1–6, 2008.
[111] C. Chen, H. Cheng, and Y.-D. Yao, “Cooperative spectrum sensing in

cognitive radio networks in the presence of the primary user emulation
attack,” IEEE Transactions on Wireless Communications, vol. 10, no. 7,
pp. 2135–2141, 2011.
[112] Z. Chen, T. Cooklev, C. Chen, and C. Pomalaza-R´aez, “Modeling

primary user emulation attacks and defenses in cognitive radio net-
works,” in Proceedings of IEEE International Performance Computing
and Communications Conference, pp. 208–215, 2009.
[113] O. Fatemieh, A. Farhadi, R. Chandra, and C. A. Gunter, “Using

classiﬁcation to protect the integrity of spectrum measurements in white
space networks.,” in Proceedings of NDSS, 2011.
[114] H. Chen, M. Zhou, L. Xie, K. Wang, and J. Li, “Joint spectrum

sensing and resource allocation scheme in cognitive radio networks
with spectrum sensing data falsiﬁcation attack,” IEEE Transactions on
Vehicular Technology, vol. 65, no. 11, pp. 9181–9191, 2016.
[115] L. Zhang, Q. Wu, G. Ding, S. Feng, and J. Wang, “Performance analy-

sis of probabilistic soft SSDF attack in cooperative spectrum sensing,”
EURASIP Journal on Advances in Signal Processing, vol. 2014, no. 1,
p. 81, 2014.
[116] O. Fatemieh, R. Chandra, and C. A. Gunter, “Secure collaborative

sensing for crowd sourcing spectrum data in white space networks,” in
IEEE Symposium on New Frontiers in Dynamic Spectrum (DySPAN),
pp. 1–12, 2010.
[117] R. Chen, J.-M. Park, and K. Bian, “Robust distributed spectrum

sensing in cognitive radio networks,” in IEEE INFOCOM 2008-The
27th Conference on Computer Communications, pp. 1876–1884, IEEE,
2008.
[118] H. Wang, L. Lightfoot, and T. Li, “On PHY-layer security of cognitive

radio: Collaborative sensing under malicious attacks,” in Proceedings
of Annual Conference on Information Sciences and Systems (CISS),
pp. 1–6, 2010.
[119] M. Abdelhakim, L. Zhang, J. Ren, and T. Li, “Cooperative sensing in

cognitive networks under malicious attack,” in Proceedings of IEEE


## --- Page 37 ---

37

International Conference on Acoustics, Speech and Signal Processing
(ICASSP), pp. 3004–3007, 2011.
[120] I. F. Akyildiz, W.-Y. Lee, and K. R. Chowdhury, “CRAHNs: Cognitive

radio ad hoc networks,” AD hoc networks, vol. 7, no. 5, pp. 810–836,
2009.
[121] Z. Li, F. R. Yu, and M. Huang, “A distributed consensus-based cooper-

ative spectrum-sensing scheme in cognitive radios,” IEEE Transactions
on Vehicular Technology, vol. 59, no. 1, pp. 383–393, 2009.
[122] J. A. Bazerque and G. B. Giannakis, “Distributed spectrum sensing for

cognitive radio networks by exploiting sparsity,” IEEE Transactions on
Signal Processing, vol. 58, no. 3, pp. 1847–1862, 2009.
[123] G. Ding, Q. Wu, F. Song, and J. Wang, “Decentralized sensor selection

for cooperative spectrum sensing based on unsupervised learning,” in
Proceedings of IEEE International Conference on Communications
(ICC), pp. 1576–1580, 2012.
[124] B. Kailkhura, Y. S. Han, S. Brahma, and P. K. Varshney, “Dis-

tributed Bayesian detection with byzantine data,” arXiv preprint
arXiv:1307.3544, 2013.
[125] F. Penna, Y. Sun, L. Dolecek, and D. Cabric, “Detecting and coun-

teracting statistical attacks in cooperative spectrum sensing,” IEEE
Transactions on Signal Processing, vol. 60, no. 4, pp. 1806–1822, 2011.
[126] A. S. Rawat, P. Anand, H. Chen, and P. K. Varshney, “Collaborative

spectrum sensing in the presence of Byzantine attacks in cognitive radio
networks,” IEEE Transactions on Signal Processing, vol. 59, no. 2,
pp. 774–786, 2010.
[127] K. Bian and J.-M. Park, “MAC-layer misbehaviors in multi-hop cog-

nitive radio networks,” in Proceedings of US-Korea Conference on
Science, Technology, and Entrepreneurship (UKC2006), pp. 228–248,
2006.
[128] T. Erpek, Y. E. Sagduyu, and Y. Shi, “Deep learning for launching and

mitigating wireless jamming attacks,” IEEE Transactions on Cognitive
Communications and Networking, vol. 5, no. 1, pp. 2–14, 2018.
[129] H. Li and Z. Han, “Dogﬁght in spectrum: Jamming and anti-jamming in

multichannel cognitive radio systems,” in Proceedings of IEEE Global
Telecommunications Conference (GLOBECOM), pp. 1–6, 2009.
[130] G.-Y. Chang, S.-Y. Wang, and Y.-X. Liu, “A jamming-resistant channel

hopping scheme for cognitive radio networks,” IEEE Transactions on
Wireless Communications, vol. 16, no. 10, pp. 6712–6725, 2017.
[131] Y. Wu, B. Wang, K. R. Liu, and T. C. Clancy, “Anti-jamming games

in multi-channel cognitive radio networks,” IEEE journal on selected
areas in communications, vol. 30, no. 1, pp. 4–15, 2011.
[132] B. F. Lo and I. F. Akyildiz, “Multiagent jamming-resilient control

channel game for cognitive radio ad hoc networks,” in Proceedings of
IEEE International Conference on Communications (ICC), pp. 1821–
1826, 2012.
[133] B. Wang, Y. Wu, K. R. Liu, and T. C. Clancy, “An anti-jamming

stochastic game for cognitive radio networks,” IEEE journal on selected
areas in communications, vol. 29, no. 4, pp. 877–889, 2011.
[134] A. Asterjadhi and M. Zorzi, “JENNA: A jamming evasive network-

coding neighbor-discovery algorithm for cognitive radio networks,”
IEEE Wireless Communications, vol. 17, no. 4, pp. 24–32, 2010.
[135] Q. Zhu, H. Li, Z. Han, and T. Basar, “A stochastic game model for jam-

ming in multi-channel cognitive radio systems,” in IEEE International
Conference on Communications, pp. 1–6, 2010.
[136] IEEE 802 Working Group, “IEEE standard for local and metropolitan

area networks–part 15.4: Low-rate wireless personal area networks
(LR-WPANs),” IEEE Std, vol. 802, pp. 4–2011, 2011.
[137] J. Rewienski, M. Groth, L. Kulas, and K. Nyka, “Investigation of con-

tinuous wave jamming in an IEEE 802.15.4 network,” in Proceedings
of International Microwave and Radar Conference (MIKON), pp. 242–
246, 2018.
[138] M. Wilhelm, I. Martinovic, J. B. Schmitt, and V. Lenders, “Short paper:

Reactive jamming in wireless networks: How realistic is the threat?,” in
Proceedings of ACM conference on Wireless network security, pp. 47–
52, 2011.
[139] X. Cao, D. M. Shila, Y. Cheng, Z. Yang, Y. Zhou, and J. Chen, “Ghost-

in-zigbee: Energy depletion attack on Zigbee-based wireless networks,”
IEEE Internet of Things Journal, vol. 3, no. 5, pp. 816–829, 2016.
[140] Z. Chi, Y. Li, X. Liu, W. Wang, Y. Yao, T. Zhu, and Y. Zhang,

“Countering cross-technology jamming attack,” in Proceedings of the
13th ACM Conference on Security and Privacy in Wireless and Mobile
Networks, pp. 99–110, 2020.
[141] H. Pirayesh, P. Kheirkhah Sangdeh, and H. Zeng, “Securing ZigBee

communications against constant jamming attack using neural net-
work,” IEEE Internet of Things Journal, pp. 1–1, 2020.

[142] S. Fang, S. Berber, A. Swain, and S. U. Rehman, “A study on DSSS

transceivers using OQPSK modulation by IEEE 802.15.4 in AWGN
and ﬂat Rayleigh fading channels,” in Proceedings of IEEE TENCON,
pp. 1347–1351, 2010.
[143] Y. Liu, P. Ning, H. Dai, and A. Liu, “Randomized differential DSSS:

Jamming-resistant wireless broadcast communication,” in Proceedings
of IEEE International Conference on Computer Communications (IN-
FOCOM), pp. 1–9, 2010.
[144] J. Heo, J.-J. Kim, S. Bahk, and J. Paek, “Dodge-jam: Anti-jamming

technique for low-power and lossy wireless networks,” in Proceedings
of IEEE International Conference on Sensing, Communication, and
Networking (SECON), pp. 1–9, 2017.
[145] J. Heo, J.-J. Kim, J. Paek, and S. Bahk, “Mitigating stealthy jamming

attacks in low-power and lossy wireless networks,” Journal of Com-
munications and Networks, vol. 20, no. 2, pp. 219–230, 2018.
[146] A. D. Wood, J. A. Stankovic, and G. Zhou, “DEEJAM: Defeating

energy-efﬁcient jamming in IEEE 802.15.4-based wireless networks,”
in Proceedings of IEEE Communications Society Conference on Sensor,
Mesh and Ad Hoc Communications and Networks, pp. 60–69, IEEE,
2007.
[147] B. DeBruhl and P. Tague, “Digital ﬁlter design for jamming mitigation

in 802.15.4 communication,” in Proceedings of International Confer-
ence on Computer Communications and Networks (ICCCN), pp. 1–6,
2011.
[148] Y. Liu and P. Ning, “BitTrickle: Defending against broadband and high-

power reactive jamming attacks,” in Proceedings of IEEE International
Conference on Computer Communications (INFOCOM), pp. 909–917,
2012.
[149] S. Fang, Y. Liu, and P. Ning, “Wireless communications under broad-

band reactive jamming attacks,” IEEE Transactions on Dependable and
Secure Computing, vol. 13, no. 3, pp. 394–408, 2015.
[150] M. Spuhler, D. Giustiniano, V. Lenders, M. Wilhelm, and J. B. Schmitt,

“Detection of reactive jamming in dsss-based wireless communica-
tions,” IEEE Transactions on Wireless Communications, vol. 13, no. 3,
pp. 1593–1603, 2014.
[151] K. M. Haataja and K. Hypponen, “Man-in-the-middle attacks on Blue-

tooth: a comparative analysis, a novel attack, and countermeasures,” in
Proceedings of International Symposium on Communications, Control
and Signal Processing, pp. 1096–1102, 2008.
[152] C. Gehrmann, J. Persson, and B. Smeets, Bluetooth security. Artech

house, 2004.
[153] C. T. Hager and S. F. MidKiff, “An analysis of Bluetooth security

vulnerabilities,” in Proceedings of IEEE Wireless Communications and
Networking (WCNC), vol. 3, pp. 1825–1831, 2003.
[154] M. Jakobsson and S. Wetzel, “Security weaknesses in Bluetooth,” in

Proceedings of Cryptographers’ Track at the RSA Conference, pp. 176–
191, 2001.
[155] S. K¨oppel, “Bluetooth jamming,” Bachelor’s Thesis supervised by

Michael K¨onig and Roger Wattenhofer, ETH Zurich, 2013.
[156] M. Strasser, C. P¨opper, and S. ˇCapkun, “Efﬁcient uncoordinated FHSS

anti-jamming communication,” in Proceedings of ACM international
symposium on Mobile ad hoc networking and computing, pp. 207–218,
2009.
[157] E.-K. Lee, S. Y. Oh, and M. Gerla, “Randomized channel hopping

scheme for anti-jamming communication,” in Proceedings of IEEE
IFIP Wireless Days, pp. 1–5, 2010.
[158] C. Popper, M. Strasser, and S. Capkun, “Anti-jamming broadcast com-

munication using uncoordinated spread spectrum techniques,” IEEE
journal on selected areas in communications, vol. 28, no. 5, pp. 703–
715, 2010.
[159] A. Liu, P. Ning, H. Dai, and Y. Liu, “USD-FH: Jamming-resistant

wireless communication using frequency hopping with uncoordinated
seed disclosure,” in Proceedings of IEEE International Conference on
Mobile Ad-hoc and Sensor Systems (IEEE MASS 2010), pp. 41–50,
2010.
[160] L. Xiao, H. Dai, and P. Ning, “Jamming-resistant collaborative broad-

cast using uncoordinated frequency hopping,” IEEE transactions on
Information Forensics and Security, vol. 7, no. 1, pp. 297–309, 2011.
[161] J. P. S. Sundaram, W. Du, and Z. Zhao, “A survey on LoRa networking:

Research problems, current solutions, and open issues,” IEEE Commu-
nications Surveys & Tutorials, vol. 22, no. 1, pp. 371–388, 2019.
[162] E. Aras, N. Small, G. S. Ramachandran, S. Delbruel, W. Joosen,

and D. Hughes, “Selective jamming of LoRaWAN using commodity
hardware,” in Proceedings of the 14th EAI International Conference on
Mobile and Ubiquitous Systems: Computing, Networking and Services,
pp. 363–372, 2017.


## --- Page 38 ---

38

[163] C.-Y. Huang, C.-W. Lin, R.-G. Cheng, S. J. Yang, and S.-T. Sheu, “Ex-

perimental evaluation of jamming threat in LoRaWAN,” in Proceedings
of IEEE Vehicular Technology Conference, pp. 1–6, 2019.
[164] I. Butun, N. Pereira, and M. Gidlund, “Analysis of LoRaWAN v1.1

security,” in Proceedings of the 4th ACM MobiHoc Workshop on
Experiences with the Design and Implementation of Smart Objects,
pp. 1–6, 2018.
[165] A. SEMTECH and M. Basics, “AN1200.22,” LoRa Modulation Basics,

vol. 46, 2015.
[166] S. M. Danish, A. Nasir, H. K. Qureshi, A. B. Ashfaq, S. Mumtaz,

and J. Rodriguez, “Network intrusion detection system for jamming
attack in lorawan join procedure,” in Proceedings of IEEE International
Conference on Communications (ICC), pp. 1–6, 2018.
[167] A. Fotouhi, H. Qiang, M. Ding, M. Hassan, L. G. Giordano, A. Garcia-

Rodriguez, and J. Yuan, “Survey on UAV cellular communications:
Practical aspects, standardization advancements, regulation, and secu-
rity challenges,” IEEE Communications Surveys & Tutorials, vol. 21,
no. 4, pp. 3417–3442, 2019.
[168] L. Gupta, R. Jain, and G. Vaszkun, “Survey of important issues in UAV

communication networks,” IEEE Communications Surveys & Tutorials,
vol. 18, no. 2, pp. 1123–1152, 2015.
[169] ATIS-I-0000060, “Unmanned aerial vehicle (UAV) utilization of cel-

lular services–enabling scalable and safe operation,” Alliance for
Telecommunications Industry Solutions, 2017.
[170] I. K. Azogu, M. T. Ferreira, J. A. Larcom, and H. Liu, “A new anti-

jamming strategy for VANET metrics-directed security defense,” in
Proceedings of IEEE Globecom Workshops (GC Wkshps), pp. 1344–
1349, 2013.
[171] O. Pu˜nal, A. Aguiar, and J. Gross, “In VANETs we trust? characterizing

RF jamming in vehicular networks,” in Proceedings of the ninth ACM
international workshop on Vehicular inter-networking, systems, and
applications, pp. 83–92, 2012.
[172] O. Punal, C. Pereira, A. Aguiar, and J. Gross, “Experimental char-

acterization and modeling of RF jamming attacks on VANETs,” IEEE
transactions on vehicular technology, vol. 64, no. 2, pp. 524–540, 2014.
[173] I. A. Sumra, I. Ahmad, H. Hasbullah, et al., “Behavior of attacker and

some new possible attacks in vehicular ad hoc network (VANET),”
in Proceedings of IEEE International Congress on Ultra Modern
Telecommunications and Control Systems and Workshops (ICUMT),
pp. 1–8, 2011.
[174] I. A. Sumra, H. B. Hasbullah, et al., “Effects of attackers and attacks on

availability requirement in vehicular network: a survey,” in Proceedings
of International Conference on Computer and Information Sciences
(ICCOINS), pp. 1–6, 2014.
[175] K. Hartmann and C. Steup, “The vulnerability of UAVs to cyber

attacks-an approach to the risk assessment,” in Proceedings of inter-
national conference on cyber conﬂict (CYCON), pp. 1–23, 2013.
[176] D. Rudinskas, Z. Goraj, and J. Stank¯unas, “Security analysis of UAV

radio communication system,” Aviation, vol. 13, no. 4, pp. 116–121,
2009.
[177] A. M. Malla and R. K. Sahu, “Security attacks with an effective

solution for dos attacks in VANET,” International Journal of Computer
Applications, vol. 66, no. 22, 2013.
[178] X. Lu, D. Xu, L. Xiao, L. Wang, and W. Zhuang, “Anti-jamming

communication game for UAV-aided VANETs,” in Proceedings of
IEEE Global Communications Conference, pp. 1–6, 2017.
[179] L. Xiao, X. Lu, D. Xu, Y. Tang, L. Wang, and W. Zhuang, “UAV relay

in VANETs against smart jamming with reinforcement learning,” IEEE
Transactions on Vehicular Technology, vol. 67, no. 5, pp. 4087–4097,
2018.
[180] D. Karagiannis and A. Argyriou, “Jamming attack detection in a pair

of RF communicating vehicles using unsupervised machine learning,”
Vehicular Communications, vol. 13, pp. 56–63, 2018.
[181] S. Kumar, K. Singh, S. Kumar, O. Kaiwartya, Y. Cao, and H. Zhou,

“Delimitated anti jammer scheme for Internet of vehicle: Machine
learning based security approach,” IEEE Access, vol. 7, pp. 113311–
113323, 2019.
[182] S. Lv, L. Xiao, Q. Hu, X. Wang, C. Hu, and L. Sun, “Anti-jamming

power control game in unmanned aerial vehicle networks,” in Proceed-
ings of IEEE Global Communications Conference, pp. 1–6, 2017.
[183] Y. Xu, G. Ren, J. Chen, L. Jia, and Y. Xu, “Anti-jamming transmission

in UAV communication networks: a Stackelberg game approach,” in
Proceedings of IEEE/CIC International Conference on Communica-
tions in China (ICCC), pp. 1–6, 2017.
[184] Y. Xu, G. Ren, J. Chen, Y. Luo, L. Jia, X. Liu, Y. Yang, and Y. Xu, “A

one-leader multi-follower Bayesian-Stackelberg game for anti-jamming

transmission in UAV communication networks,” IEEE Access, vol. 6,
pp. 21697–21709, 2018.
[185] Y. Xu, G. Ren, J. Chen, X. Zhang, L. Jia, Z. Feng, and Y. Xu, “Joint

power and trajectory optimization in UAV anti-jamming communica-
tion networks,” in Proceedings of IEEE International Conference on
Communications (ICC), pp. 1–5, 2019.
[186] J. Peng, Z. Zhang, Q. Wu, and B. Zhang, “Anti-jamming communi-

cations in UAV swarms: A reinforcement learning approach,” IEEE
Access, 2019.
[187] J. Zhang, S. C. Periaswamy, S. Mao, and J. Patton, “Standards for pas-

sive UHF RFID,” GetMobile: Mobile Computing and Communications,
vol. 23, no. 3, pp. 10–15, 2020.
[188] G. EPCglobal, “EPC radio-frequency identity protocols generation-2

UHF RFID; speciﬁcation for RFID air interface protocol for commu-
nications at 860 MHz–960 MHz,” EPCglobal Inc., November, 2013.
[189] Y. Fu, C. Zhang, and J. Wang, “A research on denial of service attack

in passive RFID system,” in IEEE International Conference on Anti-
Counterfeiting, Security and Identiﬁcation, pp. 24–28, 2010.
[190] A. Mitrokotsa, M. R. Rieback, and A. S. Tanenbaum, “Classifying

RFID attacks and defenses,” Information Systems Frontiers, vol. 12,
no. 5, pp. 491–505, 2010.
[191] Y. Oren, D. Schirman, and A. Wool, “RFID jamming and attacks on

israeli e-voting,” in Proceedings of VDE Smart SysTech; European
Conference on Smart Objects, Systems and Technologies, pp. 1–7,
2012.
[192] Y. Oren and A. Wool, “Attacks on RFID-based electronic voting

systems.,” IACR Cryptol. ePrint Arch., vol. 2009, p. 422, 2009.
[193] M. R. Rieback, B. Crispo, and A. S. Tanenbaum, “The evolution of

RFID security,” IEEE Pervasive Computing, no. 1, pp. 62–69, 2006.
[194] B. Danev, D. Zanetti, and S. Capkun, “On physical-layer identiﬁcation

of wireless devices,” ACM Computing Surveys (CSUR), vol. 45, no. 1,
pp. 1–29, 2012.
[195] J.-S. Cho, Y.-S. Jeong, and S. O. Park, “Consideration on the brute-

force attack cost and retrieval cost: A hash-based radio-frequency
identiﬁcation (RFID) tag mutual authentication protocol,” Computers
& Mathematics with Applications, vol. 69, no. 1, pp. 58–65, 2015.
[196] G. Wang, H. Cai, C. Qian, J. Han, S. Shi, X. Li, H. Ding, W. Xi, and

J. Zhao, “Hu-Fu: Replay-resilient RFID authentication,” IEEE/ACM
Transactions on Networking, vol. 28, no. 2, pp. 547–560, 2020.
[197] L. Avanco, A. E. Guelﬁ, E. Pontes, A. A. Silva, S. T. Kofuji, and

F. Zhou, “An effective intrusion detection approach for jamming attacks
on RFID systems,” in Proc. IEEE International EURASIP Workshop
on RFID Technology (EURFID), pp. 73–80, 2015.
[198] M. Karaim, Ultra-tight GPS/INS Integrated System for Land Vehicle

Navigation in Challenging Environments. PhD thesis, Queen’s Univer-
sity (Canada), 2019.
[199] O. Glomsvoll, “Jamming of GPS & GLONASS signals,” Department

of Civil Engineering, Nottingham Geospatial Institute, 2014.
[200] J. S. Warner and R. G. Johnston, “A simple demonstration that the

global positioning system (GPS) is vulnerable to spooﬁng,” Journal of
security administration, vol. 25, no. 2, pp. 19–27, 2002.
[201] T. E. Humphreys, B. M. Ledvina, M. L. Psiaki, B. W. O’Hanlon,

and P. M. Kintner, “Assessing the spooﬁng threat: Development of
a portable GPS civilian spoofer,” in Radionavigation laboratory con-
ference proceedings, 2008.
[202] B. Motella, M. Pini, M. Fantino, P. Mulassano, M. Nicola, J. Fortuny-

Guasch, M. Wildemeersch, and D. Symeonidis, “Performance assess-
ment of low cost GPS receivers under civilian spooﬁng attacks,” in
Proceedings of ESA Workshop on Satellite Navigation Technologies
and European Workshop on GNSS Signals and Signal Processing
(NAVITEC), pp. 1–8, 2010.
[203] Q. Zeng, H. Li, and L. Qian, “GPS spooﬁng attack on time synchroniza-

tion in wireless networks and detection scheme design,” in Proceedings
of IEEE Military Communications Conference (MILCOM), pp. 1–5,
2012.
[204] M. G. Kuhn, “An asymmetric security mechanism for navigation

signals,” in Proceedings of International Workshop on Information
Hiding, pp. 239–252, 2004.
[205] Y. Zhang, M. G. Amin, and A. R. Lindsey, “Anti-jamming GPS

receivers based on bilinear signal distributions,” in Proceedings of
IEEE MILCOM Proceedings Communications for Network-Centric
Operations: Creating the Information Force (Cat. No. 01CH37277),
vol. 2, pp. 1070–1074, 2001.
[206] Y.-R. Chien, “Design of GPS anti-jamming systems using adaptive

notch ﬁlters,” IEEE Systems Journal, vol. 9, no. 2, pp. 451–460, 2013.


## --- Page 39 ---

39

[207] M. J. Rezaei, M. Abedi, and M. R. Mosavi, “New GPS anti-jamming

system based on multiple short-time fourier transform,” IET Radar,
Sonar & Navigation, vol. 10, no. 4, pp. 807–815, 2016.
[208] Q. Li, W. Wang, D. Xu, and X. Wang, “A robust anti-jamming

navigation receiver with antenna array and GPS/SINS,” IEEE Com-
munications Letters, vol. 18, no. 3, pp. 467–470, 2014.
[209] N. Rezazadeh and L. Shafai, “A compact antenna for GPS anti-jamming

in airborne applications,” IEEE Access, vol. 7, pp. 154253–154259,
2019.
[210] L. Zhang, H. Wang, and T. Li, “Anti-jamming message-driven fre-

quency hopping—part i: System design,” IEEE Transactions on Wire-
less Communications, vol. 12, no. 1, pp. 70–79, 2012.
[211] W. Sun and M. G. Amin, “A self-coherence anti-jamming GPS re-

ceiver,” IEEE Transactions on Signal Processing, vol. 53, no. 10,
pp. 3910–3915, 2005.
[212] B. G. Agee, S. V. Schell, and W. A. Gardner, “Spectral self-coherence

restoral: A new approach to blind adaptive signal extraction using
antenna arrays,” Proceedings of the IEEE, vol. 78, no. 4, pp. 753–767,
1990.
[213] D. Lu, R. Wu, and H. Liu, “Global positioning system anti-jamming

algorithm based on period repetitive CLEAN,” IET Radar, Sonar &
Navigation, vol. 7, no. 2, pp. 164–169, 2013.
[214] U. Schwarz, “Mathematical-statistical description of the iterative beam

removing technique (method CLEAN),” Astronomy and Astrophysics,
vol. 65, p. 345, 1978.
[215] P. Gao, S. Sun, Z. Zeng, and C. Wang, “GNSS spooﬁng jamming

recognition based on machine learning,” in Proceedings of Interna-
tional Conference On Signal And Information Processing, Networking
And Computers, pp. 221–228, Springer, 2017.
[216] L. Xiao, Y. Li, C. Dai, H. Dai, and H. V. Poor, “Reinforcement learning-

based NOMA power allocation in the presence of smart jamming,”
IEEE Transactions on Vehicular Technology, vol. 67, no. 4, pp. 3377–
3389, 2017.
