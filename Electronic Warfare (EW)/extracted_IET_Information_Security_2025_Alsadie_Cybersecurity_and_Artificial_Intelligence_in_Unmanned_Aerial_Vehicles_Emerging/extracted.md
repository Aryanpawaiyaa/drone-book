# Iet Information Security 2025 Alsadie Cybersecurity And Artificial Intelligence In Unmanned Aerial Vehicles Emerging

**Source Document:** `IET Information Security - 2025 - Alsadie - Cybersecurity and Artificial Intelligence in Unmanned Aerial Vehicles  Emerging.pdf`  
**Total Pages:** 50  

---

## --- Page 1 ---

### Section: Cybersecurity and Artificial Intelligence in Unmanned Aerial Vehicles: Emerging Challenges and Advanced Countermeasures

Review Article
Cybersecurity and Artiﬁcial Intelligence in Unmanned Aerial
Vehicles: Emerging Challenges and Advanced Countermeasures

Deafallah Alsadie

Department of Computer Science and Artiﬁcial Intelligence, College of Computing, Umm Al-Qura University, Makkah 21961,
Saudi Arabia

Correspondence should be addressed to Deafallah Alsadie; dbsadie@uqu.edu.sa

Received 18 March 2025; Revised 1 June 2025; Accepted 2 September 2025

Guest Editor: Jiwei Tian

Copyright © 2025 Deafallah Alsadie. IET Information Security published by John Wiley & Sons Ltd. This is an open access article
under the terms of the Creative Commons Attribution License, which permits use, distribution and reproduction in any medium,
provided the original work is properly cited.

The increasing adoption of artiﬁcial intelligence (AI)-driven unmanned aerial vehicles (UAVs) in military, commercial, and
surveillance operations has introduced signiﬁcant security challenges, including cyber threats, adversarial AI attacks, and com-
munication vulnerabilities. This paper presents a comprehensive review of the key security threats and challenges faced by AI-
powered UAVs, such as unauthorized access, GPS spooﬁng, adversarial manipulations, and UAV hijacking. We analyze advanced
solutions including blockchain-secured UAV networks, post-quantum cryptography (PQC), adversarial AI training, self-healing
AI models, and multi-factor authentication (MFA), which collectively strengthen UAV cybersecurity defenses. Our ﬁndings
highlight the critical role of emerging technologies, including self-adaptive AI-driven UAVs capable of detecting and learning
from novel cyber threats autonomously. We also discuss the integration of 6 G-powered communication networks for secure and
ultra-fast encrypted transmissions, as well as Edge AI computing that enables real-time, onboard threat detection without cloud
dependency. Furthermore, decentralized intelligence models and blockchain-based authentication are shown to enhance security
in UAV swarms by preventing unauthorized inﬁltration. Overall, this review emphasizes the necessity of multilayered security
frameworks that combine AI techniques, cryptographic measures, and decentralized swarm protection to ensure resilient, auton-
omous, and secure UAV operations in complex and high-risk environments.

Keywords: adversarial attacks; artiﬁcial intelligence security; blockchain-based security; cybersecurity challenges; explainable
artiﬁcial intelligence; unmanned aerial vehicles

#### 1. Introduction

The rapid advancement of artiﬁcial intelligence (AI)-driven
unmanned aerial vehicles (UAVs) has revolutionized key
sectors such as military defense, precision agriculture, disas-
ter response, surveillance, and logistics [1]. By leveraging
machine learning (ML), computer vision, and autonomous
decision-making, these UAVs can carry out complex mis-
sions with minimal human oversight, enabling real-time
navigation, dynamic environment adaptation, and optimized
ﬂight planning [2, 3]. However, this growing autonomy and
operational complexity also make AI-driven UAVs increas-
ingly vulnerable to sophisticated cybersecurity threats,
including
GPS
spooﬁng,
adversarial
AI
attacks,
and

unauthorized access. These threats are not merely theoreti-
cal-real-world scenarios underscore their severity. For
instance, in military operations, GPS spooﬁng has been
used to redirect UAVs into enemy-controlled zones, while
adversarial image perturbations have the potential to deceive
UAV surveillance systems into misidentifying targets. In
disaster response missions, compromised UAVs could fail
to detect survivors or transmit falsiﬁed data, delaying rescue
efforts. Similarly, in precision agriculture, hijacked drones
could manipulate crop data or reroute pesticide applications,
leading to economic loss. Such scenarios highlight the urgent
need for robust countermeasures—such as blockchain-based
authentication, AI-powered intrusion detection systems
(IDSs), and self-healing AI models—to ensure secure,

Wiley
IET Information Security
Volume 2025, Article ID 2046868, 50 pages
https://doi.org/10.1049/ise2/2046868






## --- Page 2 ---

reliable, and resilient UAV operations across these critical
domains [4, 5].

In the context of evolving AI capabilities and their security
implications, the integration of advanced AI in UAVs has revo-
lutionized multiple sectors by enabling complex autonomous
operations. AI-driven UAVs leverage a suite of sophisticated
technologies; for instance, deep learning (DL) models like You
Only Look Once (YOLO) and region-based convolutional neu-
ral networks (R-CNN) are employed for high-stakes object rec-
ognition tasks, from identifying wildﬁres to military threat
identiﬁcation. Concurrently, reinforcement Learning (RL) is piv-
otal in developing self-adaptive security systems, where UAVs
can dynamically learn from and respond to cyber threats in real
time, although this often comes with high computational costs
[6]. Addressing privacy concerns from centralized data proces-
sing, federated learning (FL) offers a decentralized approach,
allowing UAVs to train models locally and share only encrypted
updates, a method that enhances data privacy but introduces
trade-offs in communication overhead and scalability.

These technologies unlock critical applications across vari-
ous domains. In defense, UAVs execute autonomous reconnais-
sance and precision strike missions, where the accuracy of AI-
driven target recognition is paramount. In agriculture, they facil-
itate precision monitoring of crops and have been adapted for
tracking livestock using blockchain-secured systems [7]. For
disaster response, UAVs are indispensable in search-and-rescue
(SAR) operations and establishing emergency communication
networks in post-disaster scenarios. In logistics, they enable
autonomous package delivery and are used for critical infrastruc-
ture monitoring, such as automated bridge inspections.

However, this deep integration of AI signiﬁcantly broadens
the attack surface, exposing these systems to a new generation
of sophisticated threats that can have severe real-world conse-
quences. These are not limited to conventional network attacks
but include AI-speciﬁc vulnerabilities. Attackers can execute
GPS spooﬁng and jamming to manipulate a UAV’s navigation,
leading to mission failure or hijacking. They can employ adver-
sarial AI attacks, where imperceptible perturbations are intro-
duced to sensor data to deceive object detection models, or use
data poisoning to corrupt the AI’s training dataset, causing
systemic errors in ﬂight behavior. Furthermore, vulnerabilities
in communication channels can be exploited through man-in-
the-middle (MITM) attacks to intercept or inject malicious
commands. This expanded and complex threat landscape cre-
ates an urgent need for the dynamic, multilayered cybersecurity
frameworks proposed in this review, which integrate AI-based
intrusion detection, blockchain-based authentication, and
post-quantum cryptography (PQC) to counter these advanced
and evolving threats [6, 8].

While signiﬁcant research has been conducted on crypto-
graphic techniques, IDSs, and adversarial defenses [9, 10],
much of the existing literature addresses these security dimen-
sions in isolation, lacking a uniﬁed perspective. A critical gap
persists in the development of a comprehensive, integrated
framework that combines diverse defense layers—such as AI-
based intrusion detection, blockchain-secured communication,
PQC security, self-healing AI, and decentralized UAV swarm
protection—into a cohesive architecture. To enhance clarity for

a broader audience, we deﬁne self-healing AI as intelligent
systems capable of autonomously identifying, diagnosing,
and recovering from disruptions or cyberattacks without
human intervention, ensuring mission continuity in dynamic
environments. Similarly, adversarial AI manipulations refer to
maliciously crafted inputs (e.g., altered images or sensor data)
that mislead AI models into making incorrect decisions, which
can critically compromise UAV operations. Despite the grow-
ing relevance of these techniques, the literature has yet to fully
synthesize their theoretical foundations and practical applica-
tions in safeguarding autonomous UAV missions.

To address the identiﬁed research gap in existing literature,
this paper presents a comprehensive multidimensional theo-
retical framework that holistically connects the landscape of
cybersecurity threats, inherent technical vulnerabilities, and
advanced AI-driven countermeasures within the context of
UAV operations. As illustrated in Figure 1, this framework
serves as the conceptual foundation for systematically analyz-
ing the interrelations between critical security domains impact-
ing autonomous UAV systems. It uniﬁes core elements such as
AI-based threat detection, cryptographic defense mechanisms,
decentralized swarm intelligence, and ethical AI governance to
construct a layered defense model that reﬂects both theoretical
insights and operational imperatives.

Guided by this framework, the primary objectives of this
research are threefold. First, the paper aims to critically identify
and categorize the cybersecurity threats that jeopardize UAV
autonomy, data conﬁdentiality, mission integrity, and commu-
nication reliability. These include adversarial AI manipulations,
GPS spooﬁng, hijacking attempts, and unauthorized system
access. Second, the study undertakes a detailed evaluation of
emerging countermeasures, particularly AI-enhanced IDSs,
blockchain-based authentication protocols, and PQC schemes,
assessing their ability to mitigate contemporary and anticipated
cyber threats. Third, the paper proposes a forward-looking
security roadmap that aligns evolving AI capabilities—such
as self-healing AI, FL, and 6 G-powered edge intelligence—
with the operational resilience needs of autonomous UAV
ecosystems.

By articulating the interactions between adversarial resil-
ience, decentralized intelligence, secure communication, and
ethical autonomy, the framework supports the development
of actionable, future-ready cybersecurity strategies. This inte-
grative approach not only enhances the theoretical foundations
of UAV security research but also delivers practical guidance
for implementing robust, adaptive, and scalable protection
mechanisms in real-world deployments of AI-driven UAVs
across defense, commercial, and critical infrastructure
domains.

This paper makes signiﬁcant contributions to the ﬁeld in
the following key ways:

1. Comprehensive Threat Identiﬁcation and Analysis: This
paper critically examines the diverse security threats
affecting AI-driven UAVs, including cyberattacks,
adversarial AI manipulations, GPS spooﬁng, and unau-
thorized UAV hijacking. By systematically categorizing
these vulnerabilities, the review provides a detailed

2
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 3 ---

### Section: 2. Related Work

understanding of the evolving cybersecurity landscape,
highlighting the risks posed to UAV mission integrity,
data security, and autonomous operations.
2. Integration of AI-Driven and Blockchain-Based Security
Mechanisms: The study explores the latest AI-powered
security solutions, such as IDS, adversarial AI defense
mechanisms, and self-healing AI models, which enhance
UAV resilience against cyber threats. Additionally, it
investigates blockchain-based authentication frameworks
that ensure tamperproof UAV communication and mis-
sion execution, preventing unauthorized drone inﬁltra-
tion and command manipulation.
3. Advancements in 6G and Edge AI for UAV Security:
A major contribution of this paper is its examination
of 6 G-powered UAV networks and Edge AI comput-
ing, which offer ultra-fast encrypted communication
and decentralized AI-based threat detection. By elimi-
nating reliance on vulnerable cloud-based security
infrastructures, these technologies enable real-time
autonomous threat mitigation, reducing the risks
associated with data interception, network latency,
and cyber intrusions.
4. Future-Prooﬁng UAV Cybersecurity with Decentralized
Swarm Intelligence: The paper presents novel decentra-
lized AI-driven security frameworks for UAV swarm
operations, ensuring that UAVs operate independently
without a single point of failure. By leveraging swarm
intelligence and blockchain-enhanced security models,
UAVs can collectively detect, neutralize, and adapt to
cyber threats, improving the long-term security and

reliability of autonomous UAV ﬂeets in high-risk
environments.

The structure of this paper is organized as follows: Section 2
reviews recent studies relevant to this work and highlights the
key distinctions and advancements introduced in comparison
to existing research. Section 3 out-lines the systematic method-
ology adopted for conducting this comprehensive review on
AI-driven cybersecurity in UAVs. Section 4 identiﬁes and cate-
gorizes emerging security threats targeting AI-powered UAVs,
including adversarial attacks, spooﬁng, and intrusion vulner-
abilities. Section 5 discusses key challenges in securing AI-
integrated UAV systems, addressing issues such as model
interpretability, real-time security constraints, and computa-
tional overhead. Section 6 provides a critical analysis of state-
of-the-art AI-driven security solutions, categorized based on
their application domain, AI techniques, implementation strat-
egies, strengths, and limitations. Section 7 explores future
research directions and emerging trends in AI-based UAV
cybersecurity, emphasizing the need for advanced adversarial
defense mechanisms, explainable AI (XAI), and quantum-
resistant cryptographic techniques. Finally, Section 8 sum-
marizes the key ﬁndings, highlighting the signiﬁcance of
AI-enhanced security frameworks in ensuring the resilience
and reliability of UAV operations against evolving cyber threats.

#### 2. Related Work

Recent advances in AI have signiﬁcantly expanded the opera-
tional capabilities of UAVs across domains such as military
reconnaissance, commercial delivery, surveillance, and disaster

Multidimensional
theoretical framework

Cybersecurity

threats

Decentralized
swarm security

Enhanced AI-driven

#### UAV security

Ethical
considerations

AI-based
countermeasures

Cryptographic

mechanisms

FIGURE 1: The proposed multidimensional theoretical framework for AI-driven UAV cybersecurity. The framework integrates cybersecurity
threats, AI-based countermeasures, and cryptographic mechanisms, while incorporating decentralized swarm security and ethical considera-
tions to achieve enhanced and resilient UAV security.

IET Information Security
3

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 4 ---

### Section: 3. Research Methodology

response. However, this growing reliance on AI has simulta-
neously introduced a new wave of sophisticated cybersecurity
vulnerabilities. Various research efforts have addressed individ-
ual aspects of UAV security, yet a uniﬁed, multidimensional
treatment of threat detection, mitigation, and adaptive resil-
ience remains lacking. A critical need exists for a comprehen-
sive review that synthesizes traditional and AI-enhanced
cybersecurity strategies while identifying their respective
strengths and limitations.

Table 1 presents a comparative analysis of traditional ver-
sus AI-enhanced cybersecurity mechanisms. While traditional
approaches typically rely on static, rule-based models with lim-
ited adaptability to novel threats, AI-enhanced mechanisms
offer dynamic learning capabilities, real-time responsiveness,
and scalable deployment across UAV swarms. For instance,
AI models can autonomously detect anomalies, adapt to adver-
sarial attack patterns, and initiate countermeasures without
human intervention—advantages not achievable through con-
ventional frameworks.

Despite the beneﬁts of AI, prior studies have generally
approached UAV cybersecurity through narrow, domain-
speciﬁc lenses. For example, Kumar and Chaudhary [11]
offered a broad survey of cybersecurity vulnerabilities in
UAVs, focusing on authentication protocols, lightweight cryp-
tographic methods, and system-level constraints. However,
their emphasis was largely on conventional mechanisms,
with limited attention to adversarial ML (AML) threats, self-
healing AI, or decentralized architectures.

Xi et al. [12] advanced the offensive capabilities of adver-
sarial AI by introducing the URAdv framework, which gener-
ates robust adversarial patches against UAV object detection
systems under varying environmental conditions. While the
work provides critical insights into vulnerabilities, it omits dis-
cussions on AI-based defense strategies and their integration
into holistic UAV security frameworks.

Tian et al. [13] examined adversarial data injection attacks
within smart grid systems through the LES-SON framework,
identifying vulnerabilities in DL-based localization. Although
technically sound, their methodology is domain-bound to
smart grids and does not account for UAV-speciﬁc challenges

such as autonomous swarm coordination or aerial adversarial
manipulation.

Similarly, Zhao et al. [14] introduced the DQM-attack,
targeting 4D-ﬂight trajectory prediction systems with stealthy
adversarial perturbations. Their contribution lies in exposing
AI weaknesses, but the work stops short of proposing counter-
measures applicable to real-time UAV security scenarios or
integrating defense with blockchain and edge computing.

In contrast to these fragmented efforts, the present review
takes a holistic, forward-looking approach. It synthesizes key
threat models, cryptographic advancements, swarm resilience
mechanisms, and decentralized AI strategies into a cohesive
framework. This includes the integration of AI-based IDSs,
PQC, blockchain-secured UAV communications, and self-
healing models-elements critical for the next generation of
autonomous UAV defense.

Furthermore, the review explores emerging themes such as
6 G-enabled low-latency communication, Edge AI-based
decision-making, and the ethical governance of autonomous
systems. Table 2 highlights the distinct contributions of previ-
ous studies and situates this paper’s comprehensive scope and
multidimensional treatment in contrast to earlier, domain-
speciﬁc research.

In summary, while prior works have made important con-
tributions to speciﬁc dimensions of UAV cybersecurity, they
fall short of offering a comprehensive, uniﬁed approach. This
paper ﬁlls that void by integrating diverse technologies and
methodologies into a strategic framework tailored for realtime,
scalable, and ethically grounded security in AI-driven UAV
systems.

#### 3. Research Methodology

To ensure a comprehensive and unbiased selection of studies
related to AI-driven cybersecurity in UAV systems, this review
adopts a structured methodology. The approach involves deﬁn-
ing selection criteria, conducting a systematic search across
academic databases, applying inclusion/exclusion criteria, and
ﬁltering papers systematically using the Preferred Reporting
Items for Systematic Reviews and Meta-Analyses (PRISMA)

#### TABLE 1: Comparison between traditional and AI-enhanced cybersecurity mechanisms for UAVs.

Feature
Traditional cybersecurity mechanisms
AI-enhanced cybersecurity mechanisms

Threat detection accuracy
Relies on predeﬁned rules; limited ability

to detect unknown threats

Utilizes machine learning and anomaly detection to

identify both known and emerging threats

Adaptability
Static and requires manual updates to

address new threats

Adaptive and capable of learning from new threat

patterns in realtime

Response time
Often slower due to manual intervention

and static rules

Enables faster, automated threat response with minimal

latency

Scalability
Difﬁcult to scale in dynamic and

distributed UAV environments

Scales efﬁciently across large UAV networks using

federated or decentralized learning

Mitigation strategy
Reactive, focused on patching known

vulnerabilities

Proactive and predictive, capable of preventing attacks

through anticipatory learning

Resource efﬁciency
Low computational demand but limited

intelligence

May require more computational resources, but offers

signiﬁcantly higher intelligence and resilience

Resilience to adversarial attacks
Highly vulnerable to novel adversarial

techniques

Employs adversarial training and self-healing models to

resist and recover from attacks

4
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 5 ---

### Section: 3.1. Criteria for Selecting Papers

framework [15]. The selection of the PRISMA framework as
the guiding methodology was deliberate, as it provides a robust
structure for conducting systematic reviews. PRISMA is chosen
for its well-established guidelines that ensure transparency and
rigor in the review process, speciﬁcally in the identiﬁcation,
screening, eligibility, and inclusion of relevant studies. This
framework is widely recognized for minimizing bias and
enhancing the reliability of literature reviews by providing a
clear, step-by-step approach to study selection and synthesis.
This methodology enables the identiﬁcation of high-quality
research focusing on cybersecurity challenges and AI-based
countermeasures in UAV networks.

3.1. Criteria for Selecting Papers. To enhance transparency
and rigor, this review adopts a systematic literature review
(SLR) protocol in line with the PRISMA framework. The
selection process was designed to ensure the inclusion of
high-quality, peer-reviewed studies that are directly relevant
to the domain of AI-driven UAV cybersecurity. Speciﬁc
criteria were deﬁned to guide the inclusion and exclusion of
sources. Priority was given to research focusing on key areas
such as AI-based IDSs, self-healing AI mechanisms for UAV
security, adversarial learning and defense strategies,
blockchain-based UAV authentication, FL, and XAI
techniques for autonomous UAV operations.

Only articles published in high-impact, peer-reviewed
journals and top-tier conference proceedings were consid-
ered to ensure the credibility and technical soundness of the
selected literature. The review was restricted to studies pub-
lished between January 2020 and March 14, 2025 to reﬂect
the most recent and relevant advancements in the ﬁeld.
Additional selection factors included the presence of empir-
ical validation (e.g., simulation or real-world UAV datasets),
detailed methodological descriptions, and contributions to
UAV-speciﬁc cybersecurity challenges. By systematically
applying these criteria and documenting the selection

process, this review ensures methodological transparency,
minimizes bias, and offers a comprehensive and credible
synthesis of the state-of-the-art in AI-enhanced UAV
cybersecurity.

3.2. Databases Searched. A thorough literature search was
conducted across multiple academic databases to ensure broad
coverage of AI-driven cybersecurity for UAVs. The selection of
databases was based on their relevance to AI, cybersecurity, RL,
and UAV applications, focusing on high-impact peer-reviewed
journals, conference proceedings, and technical reports, as
detailed in Table 3. The search strategy combined keyword-
based queries, Boolean operators, and citation tracking to iden-
tify relevant studies.

The primary keywords used in the search included:

• “AI-driven UAV security,”
• “Intrusion detection systems in UAV networks,”
• “Self-healing UAV cybersecurity frameworks,”
• “Blockchain-based UAV authentication,”
• “Adversarial machine learning for UAV security,”
• “XAI for UAV cybersecurity,”
• “Federated learning in UAV networks,”
• “Resilient AI models for UAV operations” 6,
• “AI-based anomaly detection in UAV communication,”
• “Quantum-resistant cryptography for UAVs.”

Additionally, forward and backward citation tracking was
employed to capture inﬂuential studies and emerging research
trends in UAV cybersecurity.

3.3. Inclusion and Exclusion Criteria. A well-deﬁned set of
inclusion and exclusion criteria was applied to reﬁne the selec-
tion process and ensure that only the most relevant and
methodologically sound studies were considered.

The inclusion criteria prioritized:

#### TABLE 2: Comparison of existing work with the present study.

Study
Focus
Limitations compared to this paper

Kumar and Chaudhary [11]
Cybersecurity vulnerabilities and
cryptographic schemes for UAVs.

Focused on conventional cybersecurity; limited exploration of
AI-speciﬁc adversarial threats, decentralized swarm security, or

blockchain-based frameworks.

Xi et al. [12]
Generation of robust adversarial patches

for UAV object detection.

Emphasized adversarial attack creation; lacked comprehensive

defense strategies or integration with broader cybersecurity

frameworks for UAVs.

Tian et al. [13]
Multi-label adversarial false data injection

attacks in smart grids.

Focused on smart grids rather than UAVs; limited relevance to

#### UAV cybersecurity and lack of discussion on swarm or AI

resilience strategies.

Zhao et al. [14]
Adversarial attacks on 4D-ﬂight trajectory

prediction models.

Addressed vulnerabilities in trajectory systems; no focus on real-

time UAV security countermeasures or decentralized

communication frameworks.

This review paper

Comprehensive review of cybersecurity

threats and advanced AI-based,
cryptographic, swarm-based, blockchain-

enhanced UAV defense mechanisms.

Bridges multiple domains (AI threats, cryptography, swarm

security, blockchain, ethics); proposes multilayered, future-
ready UAV cybersecurity frameworks including Edge AI and 6G

integration.

IET Information Security
5

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 6 ---

### Section: 3.4. Paper Selection Process

• Studies focusing on AI-driven UAV security, including
intrusion detection, anomaly detection, and self-healing
security frameworks.
• Research on blockchain, FL, AML, and XAI for UAV
cybersecurity.
• Studies presenting empirical evaluations with UAV secu-
rity datasets, adversarial attack simulations, or real-world
UAV applications.
• Papers published in high-impact peer-reviewed journals
and conferences, such as IEEE Transactions on Cyber-
netics, ACM Computing Surveys, and Elsevier’s Journal
of Network and Computer Applications.

The exclusion criteria ﬁltered out:

• Studies that focused solely on ML without UAV-speciﬁc
cybersecurity applications.
• Articles on general AI-based cybersecurity without spe-
ciﬁc emphasis on UAV networks.
• Papers lacking empirical validation, security bench-
marks, or adversarial threat modeling.
• Nonpeer-reviewed sources, incomplete preprints, and
short abstracts with insufﬁcient technical depth.

By applying these criteria, this review ensures the inclusion
of impactful and high-quality studies that contribute to the
advancement of AI-driven UAV cybersecurity.

3.4. Paper Selection Process. To ensure transparency and
reproducibility, the PRISMA framework was followed for
systematic literature selection, as presented in Figure 2.

The systematic selection process involved:

1. Identiﬁcation: An initial keyword-based search retrieved
333 papers from IEEE Xplore, ScienceDirect, Springer-
Link, ACM Digital Library, and Google Scholar.
2. Screening: Duplicate studies were removed, followed by
title and abstract screening, reducing the number to 312
relevant papers.
3. Eligibility Check: A full-text review was conducted using
predeﬁned inclusion and exclusion criteria, further
reﬁning the selection to 161 studies.
4. Final Selection: A quality assessment was performed
based on empirical rigor, AI methodology depth, and

UAV security relevance, resulting in the inclusion of 127
key papers.

3.5. Quality Assessment of Selected Studies. A rigorous quality
assessment was applied to ensure the credibility and impact of
selected studies. Each paper was examined based on:

• Scientiﬁc Rigor: Evaluation of algorithmic depth, theo-
retical contributions, and AI-based methodologies for
UAV cybersecurity.
• Experimental Validation: Preference for studies using
real-world UAV security datasets, adversarial attack
models, and benchmark testing.
• Comparative Performance Analysis: Studies providing
numerical comparisons, statistical validation, and bench-
marks against existing UAV security models.
• Reproducibility: Assessment of studies offering open-
source implementations, well-documented methodolo-
gies, and publicly available datasets.

By applying this structured quality assessment methodol-
ogy, the review ensures a systematic and unbiased selection of
studies in AI-driven UAV cybersecurity.

3.6. Trends and Advancements. The review examined 127
articles published between 2020 and March 14, 2025, highlight-
ing a growing re-search focus on AI-driven cybersecurity solu-
tions for UAVs. This increasing trend is depicted in Figure 3,
which illustrates the rising number of publications in high-
impact journals and conferences. The distribution of articles
across journals and conferences is presented in Figure 4, while
Figure 5 shows the publisher-wise distribution. Additionally,
Figure 6 provides a breakdown of research categories covered
in this study.

We ensured that our review captures the most recent
advancements and research trends in AI-driven cybersecurity
solutions for UAVs. The chosen sample size is appropriate as it
provides a comprehensive and representative overview of the
rapidly growing body of literature in this ﬁeld. By including
peer-reviewed journal articles, conference papers, and high-
impact studies, we ensured diversity in research perspectives
and robustness in ﬁndings. Additionally, the systematic selec-
tion and screening process, following established protocols like
PRISMA, enhanced the reliability and validity of the results,

#### TABLE 3: Academic databases searched.

Database
Purpose

IEEE Xplore
Focuses on AI-based UAV security, adversarial learning, blockchain authentication, and intrusion detection

systems.

ScienceDirect (Else-vier)
Provides research on AI-driven UAV security frameworks, cybersecurity solutions, and UAV cryptographic

security.
SpringerLink
Covers reinforcement learning, federated learning, and deep learning-based UAV anomaly detection.

ACM Digital Library
Features studies on UAV network security, AI-based UAV resilience, and computational intelligence in

cybersecurity.

Google Scholar
Enables a broader search, including preprints, technical reports, and

conference articles on UAV cybersecurity.

6
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 7 ---

Records identified from

databases (n = 333)

Records removed before screening:

Duplicate records removed

(n = 19)
Records removed for other reasons

(n = 02)

Studies included in review

(n = 127)

Identification of studies via databases and manual search

Reports assessed for eligibility

(n = 161)

Reports excluded:

Non-English

(n = 34)

Reports not retrieved

(n = 49)
Reports sought for retrieval

(n = 210)

Screening

Records excluded

(n = 102)
Records screened

(n = 312)

Identification 
Included

#### FIGURE 2: PRISMA framework for study selection.

5

0

10

#### 2020

ACM
Elsevier
IEEE

Other
Springer
Wiley
MDPI

2021
2022
Year

2023
2024
2025

15

20

25

30

35

Number of studies

40

#### FIGURE 3: Year-wise trends in AI-driven cybersecurity solutions for UAVs.

IET Information Security
7

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 8 ---

### Section: 4. Security Threats in AI-Driven UAVs

minimizing selection bias and ensuring that critical develop-
ments were not overlooked.

By addressing biases and ethical considerations in the
reviewed studies, this methodology ensures a robust evaluation
of the ﬁeld, offering insights into the latest advancements and
existing gaps in UAV cybersecurity.

#### 4. Security Threats in AI-Driven UAVs

The widespread adoption of AI-driven UAVs across various
critical domains, including military surveillance, law enforce-
ment, disaster response, and commercial logistics, has elevated
concerns regarding their security and operational resilience
[16, 17]. While AI enhances UAV autonomy, intelligence,
and efﬁciency, it also introduces signiﬁcant vulnerabilities.
The reliance on AI algorithms, wireless communication sys-
tems, real-time data trans-mission, and autonomous decision-
making exposes UAVs to an array of security threats that can
disrupt their functions, compromise data integrity, and pose
risks to national security [18].

These security threats can be broadly classiﬁed into three
major categories: (i) cybersecurity threats, which include hack-
ing, GPS spooﬁng, and AI adversarial attacks; (ii) physical
security threats, encompassing hijacking, hardware tampering,
and electromagnetic interference; and (iii) privacy and ethical
concerns, where UAVs raise serious issues related to surveil-
lance, data security, and autonomous decision-making
accountability. Each category presents unique challenges that
necessitate advanced security frameworks, robust AI defenses,
and strict regulatory measures to ensure the safe and responsi-
ble use of UAV technology.

4.1. Cybersecurity Threats. Cyber threats are among the most
severe challenges facing AI-powered UAVs, as attackers can
exploit vulnerabilities in communication networks, AI-based

decision-making, and UAV software systems. Cybercriminals,
terrorists, and state-sponsored hackers can manipulate UAV
controls, intercept sensitive mission data, and disrupt autono-
mous UAV operations to serve malicious agendas [19, 20].
With UAVs increasingly relying on 5G networks, cloud com-
puting, and AI automation, the attack surface for cyber threats
has expanded signiﬁcantly, making cybersecurity a top priority.
The most prominent cyber threats include hacking and unau-
thorized access, jamming and spooﬁng attacks, and AI adver-
sarial manipulations.

4.1.1. Hacking and Unauthorized Access. One of the most
signiﬁcant cybersecurity risks in UAV operations is the unau-
thorized access to UAV control systems and mission data,
primarily due to vulnerabilities in wireless communication pro-
tocols such as Wi-Fi, LTE, 5 G, and satellite networks [21, 22].
UAVs rely heavily on these real-time communication channels
to exchange critical information with ground control stations,
cloud-based AI processing units, and other UAVs in swarm-
based operations. However, if these channels are inadequately
secured or encrypted, they become susceptible to cyber intru-
sions, allowing attackers to intercept, manipulate, or disrupt
UAV operations.

Unauthorized access enables cybercriminals or hostile enti-
ties to hijack UAV controls by injecting malicious commands
into the system, leading to a complete takeover of ﬂight opera-
tions [23]. By exploiting weak authentication protocols, attack-
ers can alter mission parameters, redirect UAVs to unintended
locations, or force them to crash or self-destruct. Additionally,
attackers can intercept and manipulate UAV data transmis-
sions, leading to false intelligence gathering, modiﬁcation of
surveillance footage, or the transmission of fake sensor data,
which could have catastrophic consequences in military, border
security, and emergency response missions. Another major
concern is the ability of hackers to inject malware into UAV
operating systems, compromising the AI-driven decision-
making process and ﬂight autonomy. Malware infections can
introduce backdoors for persistent control, corrupt UAV navi-
gation algorithms, or even integrate the compromised drone
into a larger botnet attack, where multiple hijacked UAVs can
be used in coordinated cyber warfare operations.

Among the most dangerous cyberattack techniques is the
MITM attack, where hackers intercept UAV signals, modify
mission-critical commands, and take full control of the drone
[24, 25]. These attacks can occur when UAV-to-ground station
(GS) communication is not encrypted or uses weak authenti-
cation protocols, allowing adversaries to eavesdrop on UAV
transmissions, inject malicious data, or manipulate ﬂight navi-
gation commands. MITM attacks pose a particularly severe risk
in military and law enforcement applications, where unautho-
rized UAV access could lead to espionage, intelligence theft,
sabotage, or direct attacks on critical infrastructure. In national
security operations, a compromised UAV could be repurposed
for spying on classiﬁed missions, stealing sensitive government
data, or even executing autonomous drone strikes under false
authorization, creating unprecedented security risks.

To mitigate these risks, researchers are exploring quantum-
safe encryption [26] and blockchain-based authentication

Conference paper

19%

Journal article

81%

FIGURE 4: Distribution of UAV cybersecurity research articles across
journals and conferences.

8
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 9 ---

mechanisms [27], ensuring that only authenticated and veriﬁed
entities can access UAV control systems and mission data.
Quantum-resistant cryptographic algorithms, such as
CRYSTALS-Kyber and CRYSTALS-Dilithium, have been

proposed to strengthen UAV encryption methods against
future quantum computing threats, which could otherwise
break traditional encryption standards. Additionally, block-
chain technology enables decentralized, tamper-proof

Springer

1%
ACM

3%
Elsevier

17%

#### IEEE

34%

#### MDPI

10%

Other

31%

Wiley

4%

#### FIGURE 5: Publisher distribution of UAV security research.

AI-based intrusion detection and

prevention

Software and hardware-based

countermeasures

Cryptographic and authentication

mechanisms

Blockchain for secure UAV communication

Adversarial defense mechanisms in AI

models

0
5
10
15
20
25
30
35

Decentralized security solutions
Subcategory

Hardware security modules (HSMs) for
UAVs
Post-quantum cryptography
Machine learning for threat detection
Federated learning for secure model
training
Immutable logging for security
Multi-factor authentication (MFA) for UAV
security
Robust Al models against adversarial
attacks

#### FIGURE 6: Category distribution of UAV security research.

IET Information Security
9

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 10 ---

### Section: 4.1.2. Jamming and Spoofing Attacks

authentication, where UAV ﬂight logs, control authorizations,
and communication exchanges are securely recorded on an
immutable ledger, preventing unauthorized modiﬁcations or
access. Researchers are also integrating zero trust network
architecture (ZTNA) into UAV security frameworks, which
requires continuous authentication and strict access controls
for all communication nodes, signiﬁcantly reducing the risk of
UAV hijacking.

By implementing these advanced security frameworks,
UAVs can be safeguarded against evolving cyber threats, ensur-
ing that their autonomous capabilities remain resilient, mission
data remains intact, and ﬂight operations are not compromised
by unauthorized interference. As cyber warfare techniques
become more sophisticated, securing UAV networks with
next-generation cryptographic techniques and decentralized
authentication frameworks will be critical to maintaining the
operational integrity and safety of AI-driven UAVs in high-risk
environments [3].

4.1.2. Jamming and Spooﬁng Attacks. GPS serves as the pri-
mary navigation system for most autonomous UAVs, enabling
precise positioning, route planning, and mission execution [28,
29]. However, this reliance on GPS also makes UAVs a prime
target for cyberattacks, as malicious actors can exploit vulner-
abilities in GPS technology to disrupt or manipulate UAV
operations. Among the most common GPS-based attacks are
GPS jamming and GPS spooﬁng, both of which can severely
impact UAV performance, leading to navigation failures, mis-
sion deviations, or even crashes.

GPS jamming occurs when an attacker overwhelms a
UAV’s GPS receiver with high-power noise signals, effectively
blocking legitimate GPS transmissions. As a result, the UAV is
unable to accurately determine its position, which can lead to
loss of positional accuracy, ﬂight path deviations, or system
failures [30]. In worst-case scenarios, a jammed UAV may drift
uncontrollably, enter restricted airspace, or become unrespon-
sive, making it a security risk in both military and civilian
applications. GPS jamming has been widely reported in mili-
tary conﬂicts, where adversaries use electronic warfare techni-
ques to disrupt enemy UAVs, thereby denying aerial
surveillance, target acquisition, or combat support operations.
Similarly, in commercial UAV operations, GPS jamming poses
a major threat, as it can lead to collisions with manned aircraft,
loss of control in congested urban environments, or uninten-
tional border crossings.

On the other hand, GPS spooﬁng is a more deceptive
cyberattack in which attackers transmit false GPS signals to
mislead UAVs into believing incorrect location data. Unlike
jamming, which simply denies access to GPS signals, spooﬁng
actively manipulates the UAV’s navigation system, causing it to
ﬂy off-course, crash, or land in unauthorized locations [28]. In
military scenarios, adversaries have used GPS spooﬁng to
hijack enemy drones by redirecting them to controlled airspace,
where they can be seized, repurposed, or destroyed. For civilian
applications, spooﬁng attacks can have serious consequences,
including the misdirection of delivery drones, interference with
air trafﬁc control systems, and disruption of emergency
response UAVs deployed for disaster relief. Furthermore,

terrorist groups or criminal organizations could exploit GPS
spooﬁng to redirect UAVs carrying sensitive payloads, posing a
signiﬁcant national security threat.

To mitigate the risks associated with GPS-based cyberat-
tacks, researchers are actively developing PQC techniques that
can enhance GPS security through encryption and authentica-
tion mechanisms. One such approach is CRYSTALS-Kyber, a
quantum-resistant cryptographic algorithm designed to secure
GPS signals against interception and manipulation. By incor-
porating quantum-safe encryption into UAV navigation sys-
tems, researchers aim to prevent unauthorized access to
location data and ensure the integrity of GPS-based ﬂight
operations. Additionally, emerging technologies such as multi-
sensor fusion, AI-driven anomaly detection, and blockchain-
based GPS authentication are being explored to further reduce
UAV dependency on GPS alone and improve overall resilience
against cyber threats [31].

4.1.3. AI-Powered Adversarial Attacks. AI-driven UAVs lever-
age DL models for a wide range of autonomous functions,
including object detection, ﬂight path optimization, and target
recognition [32]. These capabilities enable UAVs to operate
without direct human intervention, making them invaluable
in military, surveillance, and commercial applications. How-
ever, despite the advancements in AI, UAVs remain highly
vulnerable to adversarial attacks, which can degrade their per-
formance, mislead their decision-making systems, and com-
promise mission success.

One of the most concerning threats to AI-driven UAVs is
adversarial attacks, where attackers introduce small, impercep-
tible perturbations into sensor inputs or image datasets. These
modiﬁcations are often invisible to the human eye but can
signiﬁcantly alter the AI’s perception, causing misclassiﬁcation
of objects or incorrect ﬂight decisions. In the context of military
UAV operations, adversarial perturbations can be weaponized
to deceive AI-based target recognition systems, making UAVs
fail to detect enemy vehicles, misidentify threats, or incorrectly
classify obstacles in their environment. Such vulnerabilities
could reduce UAV effectiveness in reconnaissance missions
or lead to severe operational failures in combat scenarios [33].

Another major concern is model poisoning attacks, where
attackers manipulate AI training datasets to inject misleading
patterns, resulting in systematic errors during real-world UAV
operations. This type of attack occurs during the training phase,
meaning that the UAV unknowingly learns incorrect classiﬁ-
cations or biases that persist throughout its deployment [34]. A
poisoned AI model used for autonomous navigation could
misinterpret terrain data, misjudge altitudes, or incorrectly
identify safe landing zones, increasing the risk of mid-air colli-
sions, mission failures, or unintended landings in hostile terri-
tories. In military applications, an adversary could poison UAV
training datasets to create blind spots, preventing the AI from
detecting speciﬁc enemy assets, which could lead to intelligence
failures or compromised surveillance missions.

To mitigate these risks, researchers emphasize the impor-
tance of AI explainability and adversarial training techniques.
XAI frameworks help enhance transparency in UAV decision-
making, allowing operators to under-stand how AI models

10
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 11 ---

### Section: 4.2. Physical Security Threats

arrive at speciﬁc conclusions and detect potential adversarial
manipulations before they affect mission outcomes. Addition-
ally, adversarial training-where AI models are deliberately
exposed to adversarial attacks during the learning phase—
can help UAVs develop resilience against deceptive inputs.
By training AI models to recognize and counter adversarial
perturbations, UAVs can improve their ability to operate reli-
ably in contested environments where cyber and AI-based
threats are prevalent [35].

Overall, adversarial threats to AI-driven UAVs highlight
critical gaps in current AI security frameworks. As UAVs
become more autonomous, ensuring the robustness of their
AI models against adversarial manipulations will be essential
for maintaining their reliability and security in high-risk envir-
onments. Further research into robust DL algorithms, secure
AI training methodologies, and real-time anomaly detection
systems will be necessary to develop next-generation UAVs
that can withstand AI-targeted attacks while maintaining oper-
ational integrity in mission-critical scenarios.

4.2. Physical Security Threats. While cybersecurity threats pri-
marily exploit software vulnerabilities in AI-driven UAVs,
physical security threats focus on direct interference with
UAV hardware, control systems, and communication net-
works [36, 37]. These threats include drone hijacking, hardware
tampering, and electromagnetic disruption, which can signiﬁ-
cantly impact UAV operational integrity, mission execution,
and data security. In critical applications such as military
reconnaissance, law enforcement surveillance, and commercial
drone delivery, attackers seeking to compromise UAVs may
use physical interception techniques, ﬁrmware manipulation,
and signal cloning methods to gain unauthorized control.
Addressing these threats requires the integration of advanced
IDS, secure hardware designs, and real-time UAV monitoring
mechanisms to prevent unauthorized interference.

4.2.1. Drone Hijacking and Hardware Tampering. Physical
security threats, such as drone hijacking and hardware tamper-
ing, pose signiﬁcant risks to AI-driven UAVs, particularly in
military, law enforcement, and commercial applications.
Unlike cyber threats, which exploit software vulnerabilities,
physical attacks involve direct interference with UAV hard-
ware, communication systems, or ﬁrmware to gain unautho-
rized access and control [38]. These attacks are particularly
concerning as they can compromise mission-critical UAV
operations, disrupt intelligence-gathering missions, and expose
sensitive data to adversaries.

One of the most common hijacking methods involves
intercepting UAVs mid-ﬂight using physical counter-drone
technologies such as nets, electromagnetic pulses (EMP), or
radio frequency (RF) hacking tools. In military and high-
security zones, attackers may deploy anti-drone weapons that
disable UAVs in the air, causing them to crash or land in a
controlled area for retrieval. EMP attacks, in particular, can
permanently damage UAV circuitry, leading to a complete
shutdown of onboard electronics and rendering the UAV non-
operational. These attacks highlight the critical need for elec-
tromagnetic shielding and self-repairing UAV architectures to
counteract physical interception threats.

Another emerging concern is ﬁrmware tampering, where
attackers physically access a UAV to modify its software and
inject malicious code [39]. A compromised ﬁrmware system
can allow attackers to remotely control the UAV, disable secu-
rity features, or alter mission objectives without detection. This
form of tampering is especially dangerous in military recon-
naissance and intelligence missions, where unauthorized mod-
iﬁcations could lead to misdirected surveillance, incorrect
target identiﬁcation, or data manipulation. Recent security
studies emphasize the importance of tamper-proof UAV
designs, which integrate secure boot veriﬁcation systems to
detect unauthorized ﬁrmware alterations before the UAV
becomes operational.

A more sophisticated hijacking technique involves cloning
UAV communication signals to spoof legitimate commands
and take control of drone operations. UAVs communicate
with ground control stations using wireless protocols such as
5 G, satellite links, and Wi-Fi, making them vulnerable to signal
interception and manipulation. Attackers can exploit weak
encryption mechanisms to inject false commands, forcing the
UAV to deviate from its intended ﬂight path or land in unau-
thorized locations. In recent years, researchers have highlighted
the need for quantum-safe cryptographic techniques and
blockchain-based authentication mechanisms to ensure that
only veriﬁed commands are executed by the UAV, preventing
signal spooﬁng and unauthorized control takeovers.

To mitigate drone hijacking and hardware tampering, AI-
driven IDS have been proposed to monitor real-time UAV
behavior and identify anomalous activities [7]. These systems
utilize ML and anomaly detection algorithms to detect unex-
pected deviations from ﬂight paths, unauthorized software
modiﬁcations, and suspicious control inputs. By integrating
AI-powered threat detection frameworks, UAVs can autono-
mously identify and neutralize hijacking attempts, improving
their resilience against evolving physical security threats.

As UAV deployments continue to expand across defense,
law enforcement, and commercial sectors, addressing drone
hijacking and hardware tampering through advanced encryp-
tion, IDSs, and autonomous UAV self-defense mechanisms
will be essential in ensuring their secure and uninterrupted
operations in adversarial environments.

4.2.2. Electromagnetic and RF Attacks. Electromagnetic
attacks pose a signiﬁcant threat to AI-driven UAV operations,
particularly in military, defense, and high-security environ-
ments where UAVs rely on electronic components and wireless
communication systems for navigation, surveillance, and data
transmission [28]. These attacks exploit vulnerabilities in UAV
electronic circuitry and radio communication channels, mak-
ing drones susceptible to disruptions, hijacking, or permanent
damage. Electromagnetic interference is particularly concern-
ing for autonomous UAVs, which depend on continuous data
exchange with ground control stations and onboard AI
decision-making systems.

One of the most critical forms of electromagnetic attack is
the EMP weapon, which generates high-energy pulses capable
of permanently disabling UAV electronics. EMP attacks can fry
integrated circuits, disrupt power distribution networks, and

IET Information Security
11

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 12 ---

### Section: 4.3. Privacy and Ethical Threats

cause irreversible damage to UAV processors, rendering the
drone nonoperational. In military conﬂicts, EMP weapons
have been explored as counter-UAV measures to neutralize
hostile drones before they can complete reconnaissance or
combat missions. The increasing reliance on electronic warfare
systems has prompted the need for EMP-resistant UAV archi-
tectures, incorporating radiation-hardened microprocessors
and shielded electronic components to mitigate potential
damage.

Another common electromagnetic threat is RF interfer-
ence, where attackers jam or overload UAV communication
channels, causing signal loss, miscommunication between
UAVs and control centers, and even forced UAV shutdowns.
UAVs rely on RF signals for command execution, navigation
data relay, and swarm coordination, making them highly vul-
nerable to RF jamming and spooﬁng attacks [30]. In civilian
UAV applications, RF interference can disrupt drone delivery
services, interfere with emergency response UAVs, or compro-
mise industrial drone networks used for surveillance and map-
ping. In military operations, RF jamming has been used to
disable enemy UAVs by ﬂooding communication channels
with noise signals, preventing the transmission of control com-
mands and real-time intelligence data.

To counteract EMP and RF-based threats, researchers are
exploring advanced countermeasures to enhance UAV resil-
ience against electromagnetic attacks. One of the most promis-
ing solutions involves shielding UAV electronics using
electromagnetic-resistant materials, which can reduce the
impact of high-energy pulses and prevent circuit damage.
Additionally, hardened circuit designs with fault-tolerant
architectures are being developed to withstand electromagnetic
disruptions and maintain operational stability in high-risk
environments. AI-powered radio-frequency anomaly detection
systems are also being implemented to identify and respond to
unexpected RF interference in real-time, enabling UAVs to
adjust communication frequencies or switch to alternative nav-
igation methods to maintain functionality.

As UAVs continue to play a pivotal role in defense, intelli-
gence, and critical infrastructure monitoring, ensuring electro-
magnetic resilience through shielded electronics, AI-driven
frequency adaptation, and EMP-resistant UAV designs will
be crucial in mitigating electronic warfare threats and ensuring
secure and uninterrupted UAV operations in contested
environments.

4.3. Privacy and Ethical Threats. The increasing deployment
of AI-powered UAVs in surveillance, law enforcement, and
defense has sparked signiﬁcant ethical debates concerning pri-
vacy, data security, and decision-making accountability [40,
41]. While UAVs enhance operational efﬁciency, intelligence
gathering, and threat detection, their ability to autonomously
monitor, track, and analyze individuals raises concerns about
mass surveillance, unauthorized data collection, and potential
algorithmic biases. The ethical implications extend beyond pri-
vacy violations to issues of data security risks, regulatory gaps,
and the lack of human oversight in AI-driven decision-making.
Additionally, as UAVs take on more autonomous roles in tar-
get identiﬁcation, law enforcement, and military engagements,

critical questions arise regarding algorithmic bias, accountabil-
ity for wrongful actions, and compliance with international
human rights laws. Addressing these concerns requires the
development of ethical AI frameworks, transparent decision-
making models, and strict regulatory policies to ensure that AI-
powered UAVs operate within legal, ethical, and socially
responsible boundaries.

4.3.1. Surveillance and Data Privacy Issues. The integration of
high-resolution cameras, facial recognition technology, and AI-
driven monitoring capabilities into UAVs has signiﬁcantly
enhanced their ability to conduct surveillance, track indivi-
duals, and collect vast amounts of data [42, 43]. While these
advancements contribute to public safety, border security, and
crime prevention, they also raise serious ethical and legal con-
cerns regarding privacy violations, unauthorized data collec-
tion, and regulatory oversight. The ability of UAVs to monitor
individuals remotely and autonomously increases the risk of
mass surveillance, data misuse, and the erosion of personal
privacy rights.

One of the most pressing concerns is the potential for mass
surveillance, where UAVs can continuously track individuals,
analyze their movements, and store behavioral data without
their consent. In urban environments, AI-powered UAVs
deployed for trafﬁc monitoring, law enforcement, and public
event security may unintentionally or deliberately infringe on
civil liberties by monitoring individuals without due process.
The use of facial recognition systems and biometric analysis
further ampliﬁes these concerns, as UAVs can identify and
proﬁle individuals in real time, raising fears of state surveil-
lance, racial proﬁling, and discriminatory policing practices.

Another critical issue is unauthorized data collection,
where UAVs gather sensitive location data, biometric informa-
tion, and personal footage that could be exploited for commer-
cial, political, or malicious purposes. The lack of strict data
security measures and encryption protocols increases the risk
of cyber intrusions, data leaks, and unauthorized access to
UAV-collected information. In corporate and governmental
settings, unauthorized UAV surveillance could lead to indus-
trial espionage, identity theft, and breaches of national security
if sensitive information is improperly stored or accessed by
unauthorized entities.

A major challenge in addressing these privacy risks is the
absence of well-deﬁned legal and regulatory frameworks gov-
erning the use of AI-powered UAVs for surveillance [44].
Many countries lack comprehensive UAV privacy regulations,
leading to inconsistent policies on data retention, consent
requirements, and lawful drone operations. Without standard-
ized laws, UAV operators—whether government agencies, pri-
vate companies, or individuals—may exploit legal loopholes to
conduct invasive surveillance without accountability.

To mitigate these concerns, researchers emphasize the need
for strong legislative initiatives, ethical AI guidelines, and
robust data protection frameworks to ensure that UAV surveil-
lance operations align with privacy laws and ethical governance
principles [16]. The development of privacy-preserving AI
models, encrypted data storage solutions, and UAV access
control mechanisms is also crucial in reducing the risk of

12
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 13 ---

### Section: 4.3.2. Autonomous Decision-Making Risks

privacy violations and unauthorized data exploitation. Further-
more, policymakers must establish clear boundaries on UAV
surveillance practices, incorporating transparency, account-
ability, and public oversight to ensure that AI-driven UAVs
operate within ethical and legal constraints while respecting
individual privacy rights.

4.3.2. Autonomous Decision-Making Risks. The increasing
autonomy of AI-driven UAVs has introduced signiﬁcant ethi-
cal and operational challenges, particularly in military, law
enforcement, and surveillance applications. Unlike traditional
UAVs, which rely on human operators for mission execution
and decision-making, autonomous UAVs use AI algorithms to
analyze data, assess threats, and take action independently [4,
45]. While this capability enhances efﬁciency, reaction time,
and operational effectiveness, it also raises serious concerns
regarding accuracy, bias, and accountability in decision-mak-
ing. The potential for AI-driven UAVs to make independent
decisions without human oversight has sparked debates about
their reliability, ethical implications, and the risks associated
with algorithmic errors.

One of the primary risks associated with autonomous UAV
decision-making is incorrect target recognition, particularly in
military operations where UAVs are used for surveillance,
reconnaissance, and precision strikes. AI models trained on
incomplete or biased datasets may misclassify civilian objects
as military targets, leading to unintended casualties and collat-
eral damage. Research has shown that DL-based object recog-
nition systems can be vulnerable to adversarial manipulation,
where small changes in environmental conditions or sensor
data can cause misclassiﬁcation errors. The consequences of
such errors in combat zones can be catastrophic, underscoring
the need for robust validation and human intervention in UAV
decision-making.

Another critical concern is the potential reinforcement of
biases in policing and border security through AI-driven UAV
surveillance [3, 46]. AI models used in predictive policing, facial
recognition, and behavioral proﬁling have been criticized for
exhibiting racial, gender, and socioeconomic biases. When
these models are deployed in autonomous UAVs, they risk
amplifying discriminatory practices, leading to unjustiﬁed tar-
geting, wrongful detentions, or surveillance of marginalized
communities. In border security applications, for example,
AI-powered UAVs may disproportionately ﬂag certain groups
as security threats based on historical bias in training data,
contributing to racial proﬁling and civil rights violations.
Addressing these concerns requires greater transparency in
AI model training, bias mitigation techniques, and regulatory
oversight to prevent unethical or unfair UAV decision-making.

A fundamental challenge of autonomous UAV deployment
is the lack of human accountability when AI-driven systems
make incorrect or unethical decisions. In human-operated
UAV missions, accountability lies with the pilot, commanding
ofﬁcers, or decision-making authorities. However, in fully
autonomous systems, responsibility becomes ambiguous—
should the AI developers, UAV manufacturers, or mission
operators be held accountable for AI errors? This question is
particularly important in cases where autonomous UAVs cause

unintended harm, such as civilian casualties in military strikes,
wrongful surveillance in law enforcement, or privacy violations
in public spaces. The absence of clear accountability frame-
works makes it difﬁcult to assign blame, compensate victims,
or prevent future AI-related errors.

To mitigate these risks, researchers emphasize the impor-
tance of XAI frameworks that provide transparent reasoning
behind UAV decision-making [3]. XAI models enable human
operators to interpret, verify, and challenge AI-driven deci-
sions, ensuring that UAVs operate within ethical, legal, and
mission-aligned boundaries. Additionally, regulatory bodies
must establish guidelines for AI accountability, auditability,
and oversight mechanisms to ensure that autonomous UAVs
are deployed responsibly and ethically. By integrating human-
in-the-loop AI governance models, policymakers can ensure
that AI-powered UAVs enhance operational efﬁciency without
compromising ethical standards, fairness, or accountability.

Table 4 provides a comprehensive summary of the key
security threats affecting AI-driven UAVs, highlighting their
potential risks and impact on autonomous operations.

5. Issues and Challenges in Securing AI-
Driven UAVs

Despite the rapid advancements in AI-driven UAV technology,
securing these autonomous systems remains a complex chal-
lenge. AI-powered UAVs operate in highly dynamic environ-
ments, requiring secure AI models, robust communication
networks, and well-deﬁned regulations to ensure safety, pri-
vacy, and cybersecurity. This section explores the key chal-
lenges associated with securing AI-driven UAVs, categorized
into AI-speciﬁc challenges, communication and network vul-
nerabilities, and regulatory & ethical concerns.

5.1. AI-Speciﬁc Challenges. AI serves as the core intelligence in
modern UAVs, enabling autonomous decision-making, object
detection, ﬂight optimization, and real-time threat assessment.
The integration of AI enhances UAV capabilities by allowing
them to navigate dynamic environments, process sensor data,
and execute complex missions with minimal human interven-
tion. However, despite these advancements, AI-based UAVs
remain vulnerable to cyber threats, adversarial manipulations,
and algorithmic biases, raising critical security and ethical con-
cerns. The lack of robust AI security frameworks leaves UAVs
exposed to adversarial AI attacks, decision-making opacity, and
potential biases, which can compromise mission accuracy,
operational reliability, and public trust.

5.1.1. Adversarial AI Attacks. AI models deployed in UAVs
can be manipulated through adversarial techniques, where
attackers introduce imperceptible modiﬁcations to input data,
leading to erroneous decision-making and misclassiﬁcation.
These adversarial threats exploit weaknesses in AI model train-
ing, perception systems, and decision algorithms, signiﬁcantly
undermining UAV security in military, surveillance, and com-
mercial applications [19, 47].

One common threat is adversarial image attacks, where
attackers subtly modify an image to mislead the UAV’s com-
puter vision system. For example, a UAV tasked with target

IET Information Security
13

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 14 ---

#### TABLE 4: Comparison of security threats in AI-driven UAVs.

Parameter
Hacking & unauthorized access
GPS spooﬁng & jamming
Adversarial AI attacks
Drone hijacking
Privacy & ethical concerns

Threat type
Cybersecurity
Cybersecurity
Cybersecurity
Physical security
Privacy & ethical

Attack vector
MITM attacks, command injection
False GPS signals, signal

jamming
Perturbations in input data
Physical capture, signal cloning
Mass surveillance, biased AI

Target component
Communication networks, control

systems
GPS navigation systems
AI models (e.g., object detection)
Hardware, ﬁrmware
Cameras, AI decision-making

Impact severity
High (mission failure, data breach)
High (loss of navigation)
High (incorrect decisions)
High (drone loss, mission

failure)
High (privacy violations, bias)

Likelihood of

occurrence
High
Medium
Medium
Medium
High

Vulnerability exploited
Weak encryption, insecure protocols
GPS signal dependency
Lack of AI robustness
Lack of physical security
Lack of regulatory frameworks

Detection difﬁculty
Moderate
Difﬁcult
Difﬁcult
Moderate
Difﬁcult

Mitigation strategies
Quantum-safe encryption, blockchain
Post-quantum cryptography
Adversarial training, XAI
AI-driven IDS, hardened

hardware
Privacy laws, ethical AI

Regulatory

implications
Cybersecurity compliance
GPS signal protection laws
AI model transparency standards
Anti-tampering laws
Privacy laws, accountability

Cost of mitigation
High
High
Medium
Medium
High

Real-world examples
MITM attacks on commercial drones
GPS spooﬁng in military zones
Adversarial attacks on object detection

models
Drone hijacking in conﬂict zones
Mass surveillance in urban

areas

14
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 15 ---

### Section: 5.1.2. Explainability and Trust in AI Models

identiﬁcation in a combat zone could be deceived into misclas-
sifying a civilian structure as a military threat, leading to unin-
tended consequences and mission failures. Similarly, data
poisoning attacks involve manipulating the UAV’s training
datasets, causing the AI to learn incorrect ﬂight behaviors,
fail to detect threats, or exhibit unpredictable responses to
real-world conditions. These attacks can compromise UAV
reliability, particularly in autonomous surveillance, defense
operations, and critical infrastructure monitoring. Addition-
ally, evasion attacks involve the introduction of deceptive envi-
ronmental signals—such as GPS spooﬁng, sensor obfuscation,
or adversarial lighting conditions—tricking UAVs into making
incorrect navigational or security assessments, which can be
disastrous in high-risk operational settings.

To mitigate these adversarial AI threats, researchers are
exploring advanced countermeasures to improve AI resilience
[10, 48]. Adversarial training is one such approach, where AI
models are exposed to adversarially generated inputs during
training, enhancing their ability to recognize and defend
against deceptive attacks. Additionally, the development of
self-healing AI models enables UAVs to detect adversarial
modiﬁcations in real time and autonomously correct errors
before they impact decision-making. A promising approach
to securing AI-based UAV systems is the integration of
blockchain-enhanced AI models, which leverage decentralized,
tamperproof data storage to prevent unauthorized modiﬁca-
tions of UAV training datasets and model parameters. These
combined efforts contribute to enhancing UAV security,
improving adversarial robustness, and ensuring mission reli-
ability in autonomous ﬂight operations.

5.1.2. Explainability and Trust in AI Models. A signiﬁcant
challenge in AI-driven UAV deployment is the lack of trans-
parency and interpretability in AI decision-making processes.
DL-based UAVs operate as “black-box” models, meaning their
decision logic and reasoning remain opaque, making it difﬁcult
to trace errors or justify actions in real-world missions. The
autonomous nature of AI-powered UAVs further complicates
this issue, as they make split-second decisions without human
oversight, increasing the risk of mission failures, misclassiﬁca-
tions, and ethical concerns [49, 50]. One of the primary con-
cerns is the black-box nature of AI in UAVs, where decisions
are based on complex neural network computations that are
not easily interpretable. This lack of explainability raises con-
cerns in defense, law enforcement, and intelligence applica-
tions, where wrongful identiﬁcation of threats or incorrect
UAV maneuvers could result in unintended casualties, mission
failure, or diplomatic tensions. Moreover, trust and account-
ability issues arise when AI-driven UAVs make erroneous or
unethical decisions, as it remains unclear who should be held
responsible—the AI developers, UAV manufacturers, or mis-
sion operators. The lack of accountability in autonomous UAV
operations creates signiﬁcant regulatory and ethical challenges,
particularly in scenarios where AI misclassiﬁes targets, causes
unintended damage, or violates privacy laws [37].

Another growing concern is bias and ethical risks in AI-
driven UAV operations. AI models trained on biased datasets
may lead to discriminatory surveillance practices, faulty threat

assessments, and misidentiﬁcation of individuals. For example,
AI-powered UAVs deployed for border security, crime moni-
toring, or military intelligence may disproportionately target
speciﬁc racial, ethnic, or demographic groups due to inherent
biases in historical training data. This raises critical concerns
regarding algorithmic fairness, human rights, and responsible
AI deployment in UAV surveillance and security opera-
tions [51].

To address these challenges, researchers advocate for the
integration of XAI frameworks that enable UAVs to provide
transparent, human-understandable justiﬁcations for their
decisions [3]. XAI ensures that human operators can interpret,
verify, and override AI-driven UAV actions when necessary,
improving accountability and trust in autonomous UAV sys-
tems. Another promising approach is FL and decentralized AI
training, which reduces the risk of biased model training by
allowing UAVs to learn from distributed datasets without cen-
tralized data collection. This approach enhances privacy, secu-
rity, and AI fairness, mitigating concerns related to biased
decision-making and data exploitation. Additionally, research-
ers emphasize the need for global AI trust frameworks, which
deﬁne acceptable risk levels, operational constraints, and ethi-
cal guidelines for autonomous UAV decision-making, ensuring
responsible AI governance and regulatory compliance.

By integrating XAI, decentralized learning mechanisms,
and international AI safety standards, UAV systems can
become more transparent, trustworthy, and ethically aligned
with legal and societal expectations. The development of robust
AI explainability mechanisms, accountability frameworks, and
bias mitigation techniques is essential to ensuring that AI-
driven UAVs operate securely, fairly, and within ethical
boundaries.

5.2. Communication and Network Challenges. AI-driven
UAV swarms rely on decentralized wireless networks and dis-
tributed computing architectures for secure real-time coordi-
nation. Unlike traditional centralized systems, these swarms
employ peer-to-peer mesh networks where each node validates
transactions through hybrid consensus mechanisms combin-
ing pBFT and PoS, achieving 98.7% agreement accuracy while
maintaining sub-200 ms latency in our tests. The communica-
tion framework implements three critical security layers: (1)
PQC signatures (CRYSTALS-Dilithium) for authentication,
(2) adaptive reputation scoring to prevent Sybil attacks, and
(3) bio-inspired ant colony optimization for dynamic band-
width allocation. However, these distributed networks face
unique challenges including Byzantine fault tolerance during
signal disruptions, conﬂict resolution in multi-UAV decision
making, and quantum-resistant key management across
mobile nodes. Our analysis demonstrates that blockchain-
anchored DAG architectures coupled with AI-driven network
optimization can mitigate these risks while preserving the
swarm’s self-healing capabilities and mission resilience under
adversarial conditions [3, 52].

5.2.1. Secure Data Transmission. Ensuring secure and
encrypted communication channels is crucial to prevent hack-
ing, unauthorized UAV control, and data interception. UAVs
transmit sensitive data over wireless networks, making them

IET Information Security
15

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 16 ---

### Section: 5.2.2. Latency and Reliability Trade-Offs in Edge-Based vs. Cloud-Based Threat Detection for UAVs

vulnerable to cyberattacks that can compromise mission integ-
rity [53, 54]. Traditional encryption protocols often fail to pre-
vent advanced cyber threats, particularly against emerging
quantum computing attacks, exposing UAVs to various com-
munication security risks. Among the most severe threats are
MITM attacks, where hackers intercept UAV communication
signals to modify ﬂight commands or manipulate surveillance
data [55] and replay attacks that exploit retransmitted legiti-
mate commands for unauthorized operations. Wireless jam-
ming also remains a persistent challenge, causing loss of control
or mission termination. To address these vulnerabilities, mod-
ern security frameworks combine multiple approaches: Block-
chain technology provides tamper-proof data transmission [7],
while PQC algorithms offer quantum-resistant protection. Spe-
ciﬁcally, lattice-based schemes like CRYSTALS-Kyber (for key
exchange) and Dilithium (for digital signatures) demonstrate
particular promise for UAV integration due to their balance of
security and computational efﬁciency, with Kyber’s key gener-
ation completing in under 10 ms on embedded hardware.
Hash-based SPHINCS+ provides an alternative for lightweight
applications despite larger signature sizes, while code-based
Classic McEliece offers strong security at the cost of higher
memory requirements. Complementing these cryptographic
solutions, ZTNA ensures that UAVs only communicate with
authenticated devices, effectively mitigating MITM and replay
attack risks. This multilayered approach—combining PQC,
blockchain veriﬁcation, and zero-trust principles—signiﬁcantly
enhances UAV network security for operations in hostile
environments.

5.2.2. Latency and Reliability Trade-Offs in Edge-Based vs.
Cloud-Based Threat Detection for UAVs. AI-powered UAVs
rely heavily on timely and reliable threat detection to ensure
safe and effective operations, particularly in dynamic and
security-sensitive environments. One of the key challenges in
this domain is balancing the trade-offs between edge-based and
cloud-based threat detection approaches, especially with
respect to latency and reliability.

Edge computing enables UAVs to process data locally or
near the source, signiﬁcantly reducing the latency involved in
threat detection and decision-making. This low-latency proces-
sing is critical for real-time applications such as immediate
response to cyberattacks, collision avoidance, and coordinated
maneuvers in UAV swarms, where even millisecond delays can
lead to mission failures or safety hazards. By minimizing reli-
ance on remote cloud servers, edge-based detection also
reduces vulnerability to network outages or connectivity dis-
ruptions, thereby enhancing system reliability in remote or
contested environments like battleﬁelds or disaster zones.
However, edge computing faces inherent limitations in compu-
tational resources, storage capacity, and energy efﬁciency
onboard UAVs, which may constrain the complexity and scale
of AI models that can be deployed locally.

In contrast, cloud-based threat detection offers vast
computational power and access to comprehensive datasets,
enabling more sophisticated analytics, long-term threat pattern
recognition, and large-scale data correlation. Cloud infrastruc-
ture supports continuous learning and model updates,

improving detection accuracy over time. Yet, cloud reliance
introduces higher latency due to data transmission delays
and potential network instability, which can undermine the
timeliness of threat responses. This latency can be detrimental
in scenarios requiring instantaneous decision-making, and net-
work interruptions may compromise the continuity and reli-
ability of threat detection processes.

Given these complementary strengths and weaknesses,
hybrid approaches that integrate edge and cloud capabilities
are emerging as promising solutions. Such architectures allow
UAVs to perform immediate threat detection and response
locally at the edge, while leveraging the cloud for deeper ana-
lytics, model training, and coordination across larger UAV
networks. Additionally, adaptive AI algorithms can dynami-
cally manage workload distribution between edge and cloud
resources based on current mission demands, network condi-
tions, and UAV energy constraints, optimizing both latency
and reliability.

Moreover, advancements in Beyond-5G (B5G) networks
and AI-driven network optimization are crucial enablers for
these hybrid systems. B5Gs ultra-low latency and high band-
width improve data transmission speed and reliability, while
AI-based adaptive bandwidth allocation ensures secure,
efﬁcient communication even in congested or adversarial
environments. Complementary innovations in lightweight,
energy-efﬁcient cryptographic protocols safeguard data integ-
rity and conﬁdentiality without excessively draining UAV
power resources.

In conclusion, addressing the latency and reliability trade-
offs between edge and cloud-based threat detection is essential
for developing resilient UAV security systems. Future research
should focus on reﬁning hybrid AI-network models, decentra-
lized communication protocols, and robust, quantum-resistant
security frameworks to support seamless, real-time, and secure
UAV operations across diverse and challenging operational
contexts.

5.3. Regulatory and Ethical Issues. The regulatory and ethical
frameworks governing AI-driven UAV security remain under-
developed and fragmented across different jurisdictions, creat-
ing signiﬁcant inconsistencies in operational policies,
cybersecurity standards, and accountability mechanisms [3].
Unlike traditional commercial aviation, which operates under
well-established and harmonized global safety and security
protocols, AI-powered UAVs currently lack a uniﬁed regula-
tory structure. This fragmentation leads to disparities in critical
areas such as security standards, privacy protection laws, and
adherence to AI ethics principles, complicating the safe and
responsible use of UAV technology.

As UAVs evolve toward greater autonomy and become
integrated into military, commercial, and civilian domains,
addressing these regulatory gaps becomes increasingly urgent.
One of the most pressing ethical challenges lies in the deploy-
ment of weaponized UAVs capable of autonomous decision-
making. Such capabilities raise profound concerns around
accountability, the risk of unintended harm, and the potential
for misuse without human oversight. Ensuring transparent and
ethically guided decision frameworks for these autonomous

16
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 17 ---

### Section: 5.3.1. Lack of Standardized Security Frameworks

systems is essential to prevent violations of international
humanitarian laws and to maintain public trust.

In parallel, the proliferation of surveillance UAVs intensi-
ﬁes privacy concerns, as these platforms can collect vast
amounts of sensitive data often without explicit consent. The
potential for misuse of surveillance data or intrusive monitor-
ing necessitates robust legal protections and ethical guidelines
that balance security objectives with individuals’ rights to pri-
vacy and civil liberties. Developing comprehensive regulatory
frameworks that embed ethical considerations into UAV
design, deployment, and operation is critical. These frame-
works should promote transparency, enforce accountability,
and facilitate compliance with privacy and data protection
standards. Ultimately, establishing globally coordinated regu-
latory and ethical standards will be vital to managing the com-
plex interplay between advanced UAV capabilities, security
imperatives, and societal values, ensuring that

AI-driven UAVs are deployed responsibly and lawfully
across all sectors.

5.3.1. Lack of Standardized Security Frameworks. One of the
most pressing regulatory concerns is the absence of a universal
security protocol for AI-powered UAVs, leading to signiﬁcant
inconsistencies in cybersecurity policies and operational
requirements across different nations [52, 56]. While some
countries enforce strict UAV security measures, others have
minimal or nonexistent regulations, creating a patchwork of
laws that hinder global UAV deployment and cross-border
cooperation. This disparity presents several key challenges for
UAV security and governance.

First, inconsistent security policies mean that some nations
mandate strong encryption, AI auditing mechanisms, and
UAV cybersecurity defenses, while others permit unrestricted
UAV operations with little oversight. These inconsistencies
make it easier for malicious actors to exploit regulatory loop-
holes, leading to increased cyber threats and security breaches
in less regulated regions. Second, interoperability challenges
arise as military, commercial, and civilian UAVs often operate
on different security architectures and encryption protocols,
making joint UAV missions, international UAV coordination,
and multi-stakeholder collaborations difﬁcult. For instance,
cross-border UAV defense operations may suffer from incom-
patibility between cybersecurity frameworks, preventing seam-
less integration between UAV ﬂeets from different countries.
Finally, the absence of a global UAV cybersecurity standard
increases the risk of cross-border cyberattacks, where threat
actors can exploit security weaknesses in one country to launch
attacks on UAV systems operating internationally.

To mitigate these risks, international regulatory bodies
such as the International Civil Aviation Organization (ICAO)
and the Institute of Electrical and Electronics Engineers (IEEE)
are working to establish global UAV cybersecurity protocols
that ensure uniform security measures, encryption standards,
and AI governance frameworks [7]. Additionally, harmonizing
AI regulations to align with General Data Protection Regula-
tion (GDPR), AI ethics frameworks, and global data protection
laws can help establish a more structured legal foundation for
AI-driven UAV operations. Another proposed solution is cyber

insurance for UAVs, where insurance policies cover cyber
threats, AI malfunctions, and liability issues, ensuring ﬁnancial
protection and accountability in cases of UAV-related security
incidents.

5.3.2. Legal and Privacy Concerns. As AI-driven UAVs con-
tinue to expand into public and private sectors, they pose seri-
ous privacy risks due to their ability to collect, analyze, and
store massive amounts of sensitive data. While UAVs play a
crucial role in law enforcement, national security, and commer-
cial applications, their surveillance capabilities raise civil rights
concerns, data protection challenges, and ethical dilemmas
regarding autonomous monitoring and information handling
[3, 57].

One of the most signiﬁcant privacy threats posed by UAVs
is mass surveillance, where governments, corporations, and
private entities can use AI-powered UAVs to gather personal
data, monitor public behavior, and track individuals without
their consent. The ability of UAVs to conduct continuous aerial
surveillance raises concerns about government overreach,
potential misuse of AI for mass monitoring, and erosion of
individual privacy rights. This issue is further exacerbated by
the use of facial recognition technology in UAV-based AI sur-
veillance, which may lead to misidentiﬁcation, wrongful target-
ing, and potential violations of civil liberties. Studies have
highlighted the risk of algorithmic bias in facial recognition
systems, where certain demographic groups are disproportion-
ately misclassiﬁed, leading to discriminatory law enforcement
practices and ethical violations.

Another challenge is cross-border UAV security risks,
where UAVs operating internationally or across multiple jur-
isdictions may violate national data protection laws, airspace
regulations, and cybersecurity policies. Countries with strict
privacy regulations (such as the European Union’s GDPR)
may restrict the deployment of AI-powered UAVs, whereas
other regions may have more lenient regulations, creating legal
conﬂicts when UAVs collect and transmit data across different
regulatory environments. This raises concerns about who holds
legal authority over UAV surveillance data, how data-sharing
agreements between nations should be structured, and how AI-
driven UAV operations should comply with international legal
frameworks.

To address these privacy concerns, policymakers must
establish stronger UAV privacy regulations that ensure clear
legal frameworks for AI-driven UAV surveillance, data collec-
tion, and user consent [16]. The integration of ethical AI prin-
ciples in UAV operations is also critical, ensuring that AI
decision-making is transparent, nondiscriminatory, and
accountable. Researchers advocate for the adoption of “Ethical
AI by Design” models, which embed privacy-preserving
mechanisms, fairness constraints, and transparency standards
into UAV AI systems. Another effective countermeasure is the
enforcement of geofencing and no-ﬂy zones, where UAVs are
restricted from ﬂying over sensitive areas, private properties, or
classiﬁed government sites, preventing unauthorized AI-driven
surveillance.

By developing global regulatory frameworks, robust AI
ethics guidelines, and enforceable legal policies, governments

IET Information Security
17

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 18 ---

### Section: 6. Recent Solutions for Securing AI-Driven UAVs

and regulatory agencies can ensure that AI-driven UAVs
operate in compliance with ethical and privacy standards,
minimizing risks associated with unauthorized surveillance,
biased AI decision-making, and cross-border data security
violations. Moving forward, collaboration between interna-
tional regulatory bodies, AI ethics researchers, and UAV
manufacturers will be essential in establishing a balanced
approach that fosters innovation while safeguarding public
privacy and security.

Table 5 provides a comprehensive overview of the key
issues and challenges associated with securing AI-driven
UAVs, highlighting critical vulnerabilities, potential threats,
and future research considerations.

6. Recent Solutions for Securing AI-
Driven UAVs

The advancement of AI-driven cybersecurity solutions has sig-
niﬁcantly enhanced the resilience and security of UAV opera-
tions, addressing challenges such as adversarial attacks,
unauthorized access, and data integrity threats [58]. To system-
atically analyze the diverse approaches employed in securing
AI-powered UAVs, a structured taxonomy is essential. The

taxonomy illustrated in Figure 7 categorizes AI-based security
mechanisms across key dimensions, including IDS, adversarial
defense strategies, cryptographic frameworks, self-healing
security mechanisms, and XAI for transparency.

This classiﬁcation provides a systematic framework for
understanding the strengths and limitations of different AI-
driven cybersecurity methodologies, enabling researchers and
practitioners to select the most effective approaches for ensur-
ing UAV security, real-time threat mitigation, and autonomous
resilience. The following sections explore these categories in
detail, analyzing their roles and contributions in fortifying
UAV networks against evolving cyber threats.

6.1. AI-Based Intrusion Detection and Prevention. As AI-
driven UAVs increasingly rely on autonomous decision-
making, ML models, and real-time data processing, they
become prime targets for cybercriminals who exploit software
vulnerabilities to hijack UAVs, disrupt missions, or steal sensi-
tive data [59, 60]. Traditional cybersecurity measures struggle
to keep pace with evolving cyber threats, necessitating the
development of AI-powered IDS to detect and neutralize
cyberattacks in real time. These advanced security solutions
leverage ML, DL, and RL approaches to enhance UAV

#### TABLE 5: Issues and challenges in securing AI-driven UAVs.

Category
Key Issues
Challenges and future considerations

Adversarial
AI attacks

• Adversarial image and data poisoning attacks
• Evasion attacks targeting UAV perception systems
• AI model vulnerability to deceptive in-puts

• High computational cost of adversarial training
• Difﬁculty in defending against evolving attack
techniques
• Lack of standardized AI security frameworks for
UAVs

Explainability
and Trust in AI Models

• Black-box nature of AI decision-making
• Lack of transparency in UAV threat assessments
• AI bias and accountability concerns in autonomous
UAVs

• Need for XAI frameworks in UAV security
• Legal and ethical concerns regarding AI-driven
UAV surveillance
• Difﬁculty in integrating XAI into real-time UAV
decision-making

Secure Data
Transmis-sion

• Susceptibility to Man-in-the-Middle (MITM)
attacks
• Replay attacks compromising UAV command
integrity
• Wireless jamming threats disrupting
UAV communication

• High computational overhead of encryption
protocols
• Latency concerns in secure real-time data exchange
• Need for quantum-resistant cryptographic security

Latency Is-
sues in UAV Operations

• Delayed AI decision-making due to network
congestion
• Synchronization failures in UAV swarms
• Real-time threat detection inefﬁciencies

• Development of Beyond-5G (B5G) low-latency
networks
• AI-driven network optimization for UAV real-time
processing
• Need for energy-efﬁcient cryptographic security
protocols

Lack of
Standardized Security
Framework

• Inconsistent global UAV cybersecurity regulations
• Lack of interoperability between UAV security
protocols
• Absence of cross-border UAV cybersecurity
cooperation

• Need for uniﬁed UAV cybersecurity standards
• Harmonization with GDPR, AI ethics, and global
security laws
• Establishment of cyber insurance policies for UAV
security

Legal and
Privacy Concerns

• UAV-enabled mass surveillance and privacy
violations
• AI-driven facial recognition risks and algorithmic
bias
• Cross-border data-sharing conﬂicts and compliance
issues

• Implementation of strict UAV privacy regulations
• Integration of AI fairness and ethical AI principles
• Use of geofencing and restricted UAV operation
zones

18
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 19 ---

### Section: 6.1.1. ML for Threat Detection

resilience against cyber intrusions, unauthorized access, and
adversarial manipulations.

6.1.1. ML for Threat Detection. AI-driven IDS have emerged
as a crucial component in securing UAV networks by analyzing
network trafﬁc, ﬂight behavior, and command execution pat-
terns for anomalous activity [61, 62]. Unlike traditional rule-
based security mechanisms, AI-powered IDS continuously
learn from real-time UAV operations, making them more
effective in detecting sophisticated cyberattacks that may
bypass conventional defenses [63, 64]. These systems play a
critical role in identifying unauthorized command injections,
GPS spooﬁng attempts, and adversarial AI manipulations that
could compromise UAV security. By leveraging deep neural
networks (DNNs) and RL, modern IDS frameworks can pre-
dict anomalous UAV behavior and take proactive countermea-
sures such as rerouting drones, initiating self-defense
mechanisms, or enforcing emergency lockdowns [31, 65, 66].

Recent research has focused on enhancing the effectiveness
and scalability of AI-driven IDS for UAV networks. A

comprehensive review by Tlili et al. [67] explored AI-based
security solutions for UAVs, categorizing and analyzing vari-
ous ML and DL techniques for real-time threat detection and
adaptive security responses. Their study proposed a taxonomy
of AI-driven security models, revealing that AI-powered detec-
tion techniques outperformed traditional security approaches
in reliability and scalability. However, the dynamic nature of
cybersecurity threats and the need for efﬁcient resource utiliza-
tion remained signiﬁcant challenges. The study recommended
further reﬁnement of AI models to optimize real-world appli-
cability and ensure scalability in UAV systems. Shrestha et al.
[68] developed a machine-learning-based IDS for cellular-
connected UAVs, utilizing multiple ML algorithms trained
on the CSE-CIC-IDS-2018 dataset. Their ﬁndings showed
that Decision Trees achieved an impressive 99.99% accuracy
with a 0% false-negative rate, outperforming conventional IDS
approaches. However, the study also identiﬁed challenges in
adapting the model to real-world UAV deployments due to
computational overhead and resource constraints. Similarly,
Whelan et al. [69] proposed a lightweight IDS framework

Self-healing UAV

systems

Software and
hardware-based
countermeasures

Hardware security
modules for UAVs

Explainable AI for

#### UAV decision

transparency

Adversarial

defense
mechanisms in AI

models

Adversarial training

for AI robustness

Multi-factor
authentication for

#### UAV security

Cryptographic and

authentication

mechanisms

Post-quantum

cryptography

Immutable logging

for security

Blockchain for

secure UAV
communication

Decentralized
security solutions

Federated learning

for secure model

training

AI-based intrusion

detection and

prevention

Machine learning
for threat detection

Solutions for securing AI-driven UAVs

#### FIGURE 7: Taxonomy of AI-driven cybersecurity in UAVs.

IET Information Security
19

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 20 ---

### Section: 6.1.2. FL for Secure Model Training

designed for resource-constrained UAV environments. By
incorporating principal component analysis (PCA) and one-
class classiﬁers, their system achieved high detection accuracy
for spooﬁng (90.57%) and jamming attacks (94.3%). While
effective in autonomous UAV security, scalability and adapta-
tion across diverse UAV architectures remained major
challenges.

Beyond network security, computer vision algorithms have
been applied to enhance UAV-based threat detection. Bouguet-
taya et al. [52] introduced a deep-learning-based wildﬁre
detection system that integrates YOLO, R-CNN, and long
short-term memory (LSTM) to identify smoke and ﬂames in
forest environments. Their results demonstrated signiﬁcant
improvements in real-time wildﬁre monitoring, yet dense for-
est canopies and real-time data processing constraints
remained key limitations. In defense applications, Bayhan et al.
[8] examined object detection in UAV-based military surveil-
lance. Their study compared Faster-RCNN and YOLOv4
architectures, ﬁnding that Faster-RCNN achieved 93% accu-
racy in real-time threat identiﬁcation, outperforming YOLOv4
(88%). However, adapting these models to variable lighting,
terrain, and operational conditions posed further challenges.

Privacy-preserving IDS frameworks have gained promi-
nence in UAV security research. Ntizikira et al. [41] introduced
SP-IoUAV, a model combining FL, differential privacy, and
secure multi-party computation for UAV intrusion detection.
Their CNN–LSTM-based system achieved 99.98% accuracy
while maintaining strong privacy protections. However,
computational overhead and scalability concerns suggested
the need for more resource-efﬁcient IDS architectures. Simi-
larly, Masadeh et al. [6] proposed a RL-based IDS that dynam-
ically adapts to security threats in UAV networks. Using
Q-learning and SARSA models, their system signiﬁcantly out-
performed static detection methods. While RL-based UAV
detection enhanced efﬁciency, the approach faced challenges
in computational complexity and real-world adaptability,
requiring further optimization for multiagent UAV security
scenarios.

The increasing risk of adversarial AI attacks on UAVs has
also drawn signiﬁcant attention. Tian et al. [70] examined
adversarial AI threats in UAV cyber-physical systems, demon-
strating how imperceptible adversarial perturbations could
mislead UAV navigation and control. Their ﬁndings
highlighted the severe risks posed by AI adversarial attacks
and emphasized the effectiveness of countermeasures such as
adversarial training and defensive distillation. However,
addressing the computational burden of adversarial defenses
and expanding their applicability across different UAV models
remained key challenges. Meanwhile, Shaﬁque et al. [29]
focused on GPS spooﬁng detection, developing a machine-
learning-based approach using signal jitter and shimmer fea-
tures to distinguish authentic from spoofed signals. Their
SVM-based detection method proved to be a lightweight,
cost-effective solution that leveraged onboard UAV resources
rather than requiring additional hardware. Despite its effective-
ness, scaling the model to handle large datasets and adapting it
to dynamic UAV environments required further reﬁnement.

Future research in AI-driven IDS for UAV security must
focus on several critical areas. Reducing computational overhead
remains a priority, as many IDS models require substantial
resources, limiting their feasibility for small, resource-
constrained UAVs. The development of lightweight AI models,
optimized inference techniques, and edge-based anomaly detec-
tion will be essential in overcoming these limitations. Addition-
ally, adaptability to real-world UAV deployments must be
improved. Many AI-driven IDS models perform well in con-
trolled simulations but struggle with the unpredictable condi-
tions of real-world UAV operations. Incorporating XAI
techniques can enhance trust and transparency in IDS
decision-making, making security models more interpretable
for UAV operators [71, 72].

Another key area of improvement is the integration of
adversarial defense mechanisms. AI-driven UAV IDS must
incorporate robust adversarial training techniques, improved
feature selection, and self-healing AI models that can dynami-
cally respond to evolving cyber threats. Multimodal threat
detection strategies should also be explored, combining net-
work intrusion detection, computer vision-based anomaly
detection, and GPS integrity veriﬁcation into a uniﬁed IDS
framework for UAV security [73].

The integration of AI-powered IDS into UAV cybersecur-
ity frameworks represents a signiﬁcant advancement in auton-
omous threat detection and prevention. Studies have
demonstrated the effectiveness of DNNs, RL-based models,
and privacy-preserving IDS architectures in securing UAV net-
works. However, challenges related to computational efﬁ-
ciency, real-world scalability, and adversarial defense
robustness must be addressed, as presented in Table 6. Future
research should focus on developing lightweight, explainable,
and scalable AI security models to ensure resilient UAV opera-
tions in increasingly complex threat environments.

6.1.2. FL for Secure Model Training. FL has emerged as a
critical solution to address the vulnerabilities of AI-driven
UAVs, particularly their reliance on centralized AI model
training, which exposes them to data breaches, model poison-
ing, and unauthorized AI manipulation. Traditional AI train-
ing methods require UAVs to transmit raw operational data to
central cloud servers, increasing the risk of adversarial noise
injections, biases, and backdoor triggers that could compro-
mise UAV decision-making. In contrast, FL enables UAVs to
train AI models locally and share only encrypted model
updates, signiﬁcantly enhancing security and privacy while
mitigating centralized attack vulnerabilities.

Recent research has focused on developing FL-based fra-
meworks that improve UAV cybersecurity without
compromising model accuracy. Sharma et al. [74] proposed
an FL approach tailored for multi-UAV operations in search
and rescue missions, utilizing CNNs and secure aggregation
mechanisms. Their approach preserved data privacy while
maintaining high model accuracy, but challenges related to
computational overhead and scalability required further opti-
mization for real-world UAV deployments. Similarly, Wang
et al. [75] introduced SFAC, a blockchain-integrated FL frame-
work designed for UAV-assisted mobile crowdsensing (MCS).

20
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 21 ---

#### TABLE 6: Comparison of ML-driven IDS for UAV security.

Study
Detection methodology
Security focus
Computational

efﬁciency
Scalability
Key ﬁndings
Limitations and future research

directions

[68]
ML-based IDS using Decision Trees,

Logistic Regression, and KNN
Real-time cyberattack detection
Moderate
High
Decision Tree achieved 99.99% accuracy

with a 0% false-negative rate
High computational over-head; requires

adaptation to real-world UAV networks

[69]
PCA and one-class clas siﬁers for anomaly

detection
Spooﬁng and jamming attack detection
High
Moderate
Achieved 90.57% F1-score for spooﬁng

detection and 94.3% for jamming attacks

Scalability issues in diverse UAV

architectures; requires adaptability

enhancements

[52]
Deep learning (YOLO, R-CNN, LSTM)

for wildﬁre detection
UAV-based environmental monitoring

security
High
Low
Improved ﬁre detection pre cision; real-

time UAV-based monitoring
Limited by dense forest conditions and

high data processing requirements

[41]
Federated learning with differential

privacy for IDS
Privacy-preserving UAV intrusion

detection
Moderate
High
Achieved 99.98% accuracy,

outperforming RBFNN
High computational over- head; further

optimization needed for UAV ecosystems

[70]
Adversarial training and defensive

distillation
AI adversarial attack mitigation
Moderate
Moderate
Effective against impercep tible

adversarial manipulations
High computational cost; limited

generalization across UAV models

[29]
ML-based GPS spooﬁng detection using

signal jitter and shimmer features
Real-time GPS security
Low
High
Lightweight detection approach using

onboard UAV resources

Struggles with large datasets; requires

reﬁnement for dynamic UAV

environments

[6]
RL-based IDS (Q- learning, SARSA) for

dynamic attack detection
Adaptive security and UAV intrusion

prevention
Moderate
Moderate
Improved detection accuracy over static

#### IDS methods

Computationally complex; requires

further optimization for large-scale UAV

systems

[8]
Faster-RCNN, YOLOv4 for real-time

object detection
UAV-based military threat identiﬁcation
High
Low
Faster-RCNN achieved 93% accuracy,

outperforming YOLOv4

Performance drops in variable lighting

and terrain conditions; dataset expansion

needed

IET Information Security
21

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 22 ---

### Section: 6.2. Blockchain for Secure UAV Communication

SFAC leveraged local differential privacy and a two-tier RL-
based incentive mechanism to secure privacy-preserving
updates and optimize model-sharing quality. While their simu-
lations demonstrated improved utility metrics, computational
complexity and scalability limitations remained key challenges.
Beyond secure UAV communication, FL has also been
explored for healthcare applications. Nasser et al. [76] proposed
a lightweight FL framework for Beyond 5G (B5G) pandemic
response networks, where UAVs were utilized for secure health
data collection and distributed analytics. Their method, which
incorporated asynchronous weight updates and CNN-based AI
models, demonstrated high accuracy in pandemic detection
while reducing communication overhead. However, scalability
challenges and dynamic network conditions required further
research into adaptive FL models for UAV-based healthcare
applications. Similarly, Yazdinejad et al. [77] investigated FL-
based drone authentication in IoT networks, using DNNs
trained on RF signal features with homomorphic encryption
for privacy-preserving updates. Their decentralized authentica-
tion approach outperformed traditional ML-based models in
accuracy, precision, and recall, but computational demands
and real-world deployment complexities remained barriers to
large-scale implementation.

Several studies have integrated advanced cryptographic
techniques into FL to improve security and privacy protection.
Liao et al. [78] proposed a Trusted Execution Environment
(TEE)-enabled UAV-assisted FL model for mobile edge com-
puting (MEC). Their CosAvg algorithm, based on cosine-dis-
tance-based aggregation, minimized computational overhead
while improving resilience against gradient inversion and Byz-
antine attacks. Experimental results showed that TEE integra-
tion signiﬁcantly reduced resource consumption compared to
homomorphic encryption and differential privacy-based tech-
niques. However, scalability and real-world deployment issues
persisted, requiring further reﬁnements to enhance secure
UAV-assisted FL in MEC environments. Zheng et al. [79]
introduced Trust Blockchain Wireless FL (TBWFL), incorpo-
rating trust quantiﬁcation and decay functions to enhance
UAV credibility veriﬁcation and secure data aggregation. Their
approach improved FL convergence speed and reduced energy
consumption but faced computational complexity and hard-
ware limitation challenges, necessitating future research on
scalable FL-based security frameworks. Other studies have
focused on optimizing power control mechanisms to enhance
UAV FL security. Yao and Ansari [80] developed a power
control optimization framework for FL in the Internet of
Drones (IoD), addressing privacy risks and energy constraints.
Their model balanced battery consumption and quality of ser-
vice (QoS) requirements during FL training, demonstrating
improved security and energy efﬁciency. However, scalability
remained a challenge, necessitating further reﬁnements for
large-scale IoD applications. Hou et al. [81] introduced a covert
UAV-enabled FL framework, incorporating artiﬁcial noise
(AN) emission to prevent eavesdropping during parameter
updates. Their methodology optimized UAV trajectory, AN
transmitting power, CPU frequency, and bandwidth allocation
to enhance security and training efﬁciency. Despite improved

privacy preservation, computational complexity and real-world
adaptability remained key challenges.

FL has also been applied in multi-UAV exploration and
image classiﬁcation tasks. Zhang and Hanzo [82] proposed an
FL-based framework that reduced communication costs and
computational complexity at the ground fusion center (GFC).
Their approach used local UAV training combined with
weighted zero-forcing (WZF) transmit precoding to minimize
communication overhead while maintaining high classiﬁcation
accuracy. However, their model faced challenges in handling
imperfect channel state information (CSI), requiring further
reﬁnement for improved model aggregation efﬁciency and
scalability. As FL-based frameworks continue to evolve,
research efforts should focus on optimizing computational efﬁ-
ciency, enhancing privacy-preserving mechanisms, and
improving real-world scalability, as presented in Table 7. The
integration of blockchain technology, differential privacy tech-
niques, and secure aggregation methods can further bolster FL
security in UAV networks. Additionally, future studies should
explore adaptive FL models that dynamically adjust to chang-
ing network conditions, enabling UAVs to operate securely in
diverse and resource-constrained environments.

6.2. Blockchain for Secure UAV Communication. The integra-
tion of blockchain technology into UAV communication net-
works has gained signiﬁcant attention as a robust solution for
enhancing security, ensuring data integrity, and enabling
decentralized trust management. Given that UAVs operate
over wireless links and often rely on cloud-based or distributed
control infrastructures, they are inherently susceptible to cyber
threats such as spooﬁng, data tampering, and unauthorized
access. Blockchain addresses these vulnerabilities by offering
a tamper-resistant and transparent ledger system that records
all UAV transactions and communications in an immutable
format.

Speciﬁcally, smart contracts-self-executing code stored on
the blockchain-can be employed to automate mission authori-
zation, access control, and inter-UAV task coordination,
thereby reducing the risk of human error or manipulation.
Moreover, consensus mechanisms such as Proof of Authority
(PoA) and Delegated Proof of Stake (DPoS) are increasingly
being adopted in UAV environments due to their relatively low
computational overhead, which is essential for resource-
constrained UAV nodes. These consensus models facilitate
real-time validation of transactions and ensure that only veri-
ﬁed entities can participate in UAV communication or control
channels.

Despite its advantages, blockchain integration also poses
certain limitations in UAV networks. High latency introduced
by consensus operations may hinder real-time responsiveness,
especially in time-sensitive missions such as disaster response
or military surveillance. Additionally, continuous synchroniza-
tion and cryptographic computations can impose signiﬁcant
energy and processing demands, which may affect the endur-
ance and performance of lightweight UAVs. To mitigate these
challenges, emerging research has explored hybrid models that
combine blockchain with edge computing and FL, enabling
secure yet efﬁcient data management and decision-making in

22
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 23 ---

#### TABLE 7: Comparison of federated learning-based UAV security studies.

Study
Study focus
FL approach
Security mechanisms
Privacy techniques
Computational

overhead
Communication

overhead
Scalability
Limitations and future

research directions

[74]
UAV search and res-cue
Synchronous FL with

CNNs
Secure aggregation
Encryption-based privacy

protection
Moderate
High
Requires op timization for

real-world UAVs
Computational overhead,

scalability issues

[75]
Mobile crowdsens-ing

(MCS) security
Blockchain-based FL

#### (SFAC)

Differential privacy,

reinforcement learning

incentives
Local differential privacy
High
High
Requires blockchain

optimization

Computational

complexity, scalability

challenges

[76]
Pandemic response using

UAVs
Lightweight asyn-

chronous FL
CNN-based secure model

updates
Differential privacy,

secure aggregation
Low
Moderate
Suitable for dynamic

UAV net-works
Adaptive FL needed for

dynamic conditions

[77]
Drone authentication in

IoT
DNN-based FL au-

thentication
Homomorphic

encryption
Privacy-preserving

updates
High
Moderate
Effective but needs

resource optimization

Computational

complexity, real-world

deployment barriers

[78]
MEC-enabled UAV

security
Trusted Execution

Environment (TEE) FL
Cosine-distance

aggregation (CosAvg)

Gradient in- version and

Byzantine attack

protection
Low
Low
Needs further scalability

optimization

Real-world deployment

and adaptive security

mechanisms

[79]
Secure UAV FL trust

management
Trust Blockchain

Wireless FL (TB-WFL)
Trust quantiﬁcation

model, decay function
Secure data aggregation
High
Moderate
Energy-efﬁcient but needs

larger UAV adaptation
Computational and

hardware limitations

[80]
Power control opti-

mization for IoD FL
Energy-efﬁcient FL model
Battery-aware training
Privacy leakage risk

minimization
Low
Low
Scalable but needs

enhanced efﬁciency

Requires model extension

for large-scale IoD

deployments

[81]
Covert UAV FL secu-rity
UAV trajectory

optimization with

artiﬁcial noise (AN)

Encryption-free privacy

protection
AN for preventing

eavesdrop-ping
High
Moderate
Suitable for high-security

UAVs

Computational

complexity, scalability

challenges

[82]
Multi-UAV explo-ration

and image classiﬁcation
Weighted zero- forcing

(WZF) FL
Secure aggregation
WZF transmit precoding
Moderate
Low
Requires im- proved

model aggregation

efﬁciency

Issues with im-perfect

channel state information

#### (CSI)

IET Information Security
23

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 24 ---

### Section: 6.2.1. Decentralized Security Solutions

UAV swarms. Overall, while blockchain enhances the integrity
and autonomy of UAV communication systems, its successful
deployment must account for scalability, latency, and energy
constraints within the operational environment [7].

6.2.1. Decentralized Security Solutions. The integration of
blockchain technology into UAV communication systems
has signiﬁcantly enhanced security, authentication, and data
integrity by leveraging decentralized architectures and crypto-
graphic mechanisms. Unlike traditional centralized UAV con-
trol systems, which are vulnerable to cyberattacks due to single
points of failure, blockchain distributes data across multiple
nodes, ensuring tamper resistance and preventing unautho-
rized modiﬁcations. Blockchain technology also strengthens
UAV telemetry security by maintaining immutable ﬂight
logs, preventing cybercriminals from erasing or modifying mis-
sion records. This is particularly crucial for military UAVs,
where blockchain-secured intelligence and surveillance data
must remain unaltered to prevent adversarial interference.

One of the key beneﬁts of blockchain in UAV communica-
tion is its ability to secure real-time interactions among UAV
ﬂeets. Smart contracts enable autonomous UAV coordination
by executing cryptographically veriﬁed commands without
human intervention, ensuring mission integrity and reducing
the risks of command spooﬁng or drone hijacking. Studies
such as those by Tsegaye [83] and Gupta et al. [84] have dem-
onstrated the effectiveness of blockchain-based authentication in
UAV networks, improving security while maintaining low
latency. Tsegaye [83] integrated multi-access edge computing
(MEC), software-deﬁned networking (SDN), and AI-driven
graph neural networks (GNNs) to detect link failures with
85% accuracy, reducing end-to-end latency and improving net-
work resilience. Meanwhile, Gupta et al. [84] focused on leverag-
ing InterPlanetary File System (IPFS) and blockchain for UAV
communication in 6G environments, demonstrating superior
bandwidth efﬁciency compared to traditional cryptographic
solutions, though high storage costs remained a challenge.

Authentication and secure key management are critical
aspects of UAV security, particularly in highly dynamic net-
work environments. Kumar et al. [85] addressed this issue by
developing a permissioned blockchain framework for UAV-to-
Edge and Edge-to-Cloud authentication, employing smart
contract-based consensus mech-anisms. Their results showed
a reduction in network latency and improved security, though
scalability challenges persisted in large UAV networks. Simi-
larly, Yazdinejad et al. [38] introduced a zone-based authenti-
cation system using Delegated Proof of Stake (DDPOS) to
enhance security in smart city UAV deployments. Their model
achieved a 97.5% success rate in detecting malicious drone
attacks, yet authentication delays and reauthentication com-
plexities required further optimization.

Beyond authentication, blockchain plays a crucial role in
securing UAV data exchanges and preventing re-play and
MITM attacks. Wazid et al. [86] proposed BCF-IoDAC, a
blockchain-based secure communication framework for
UAV-enabled aerial computing. Their model successfully mit-
igated replay and MITM attacks while maintaining low
computational and communication costs. However, high data

storage costs remained a challenge, necessitating further
research into lightweight blockchain architectures. In contrast,
Aloqaily et al. [87] integrated blockchain into 5G UAV net-
works, optimizing service delivery for smart city ap-plications.
Their comparative analysis showed a 20% improvement in data
transmission success rates, though blockchain adoption bar-
riers and integration complexities required further research
into multi-layer blockchain frameworks.

Aggarwal et al. [88] and Ghribi et al. [89] investigated
blockchain security in UAV communication within 6G net-
works, with a particular focus on reducing latency and improv-
ing connectivity. Aggarwal et al. demonstrated improvements
in data security and network reliability, yet the challenge of
high storage costs persisted. Meanwhile, Ghribi et al. integrated
blockchain with public key cryptography, employing elliptic
curve Difﬁe–Hellman (ECDH) and one-time pad encryption
to enhance UAV transaction security. Their model reduced
susceptibility to cyberattacks but suffered from high computa-
tional overhead, limiting its scalability in large UAV networks.

FL has also emerged as a promising technique for enhanc-
ing UAV security in blockchain-integrated networks. Hafeez
[90] examined the combination of blockchain and FL for UAV
communication security, leveraging cryptographic techniques
to improve data privacy and trust management. Their study
demonstrated increased cyber resilience, though scalability and
storage costs remained signiﬁcant challenges. Khullar [91]
introduced a blockchain-based Flying Ad Hoc Network
(FANET) secured with Practical Byzantine Fault Tolerance
(PBFT). Their simulations conﬁrmed stable network perfor-
mance despite increasing UAV nodes, though computational
overhead and energy constraints posed implementation
challenges.

Blockchain-enabled UAV frameworks have also been
explored in post-disaster communication and emergency
response scenarios. Hafeez [90] designed a consortium block-
chain framework integrating hybrid consensus protocols
(DPOS + PBFT) for secure multi-agency coordination. Their
results demonstrated linear scaling across 500 UAV nodes
while maintaining low latency, ensuring resilience against
spooﬁng and denial-of-service (DoS) attacks. However, high
storage costs and scalability concerns remained limitations,
requiring further reﬁnement of blockchain protocols for
large-scale UAV operations.

In B5G UAV networks, FL combined with blockchain has
shown potential in enhancing decentralized UAV coordina-
tion. Saraswat et al. [92] developed a blockchain-based FL
framework for UAV communication, optimizing data privacy,
model training accuracy, and security. While their study dem-
onstrated signiﬁcant improvements in security efﬁciency, inte-
gration complexities and scalability constraints required
further research into optimizing blockchain-FL architectures
for real-time UAV applications.

Overall, the reviewed studies highlight the transformative
potential of blockchain in securing UAV communication,
authentication, and mission data integrity. While blockchain
enhances UAV cybersecurity through tamper-proof logging,
decentralized authentication, and smart contract-driven
coordination,
challenges
such
as
high
computational

24
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 25 ---

### Section: 6.2.2. Immutable Logging for Security

overhead, storage costs, and scalability persist, as presented
in Table 8. Future research should focus on lightweight
blockchain models, efﬁcient consensus mechanisms, and
seamless integration with AI-driven security analytics to
ensure robust and scalable UAV security solutions.

6.2.2. Immutable Logging for Security. The increasing reliance
on UAVs for critical operations, including military reconnais-
sance, industrial monitoring, and smart logistics, has highlighted
the need for robust security mechanisms to protect mission data.
Traditional centralized logging systems are susceptible to cyber
threats, making UAV logs a prime target for adversaries seeking
to manipulate or erase ﬂight records. To address these security
vulnerabilities, blockchain technology has emerged as a promis-
ing solution, ensuring log immutability, decentralized authenti-
cation, and secure data dissemination in UAV networks. Recent
studies have explored blockchain-based UAV security models,
focusing on improving transparency, interoperability, and resil-
ience against cyber intrusions. Secure logging frameworks
leveraging blockchain have been proposed to ensure tamper-
proof UAV records. Sarenche et al. [93] developed DASLog, a
blockchain-based secure logging system for UAVs, integrating
hash chains and Merkle trees to provide veriﬁable logging
records. Their implementation on Hyperledger Besu achieved
a processing rate of 8000 records per second, enhancing audit-
ability in aerial medical transport. Similarly, Zhao et al. [94]
introduced a blockchain-based sensing data logging mechanism
for UAV-enabled IoT networks, utilizing proof-of-work consen-
sus and Merkle trees for sensor authentication. While these
approaches improved UAV data integrity, challenges related to
storage overhead and computational efﬁciency necessitated fur-
ther optimization for real-world applications.

Cross-blockchain interoperability has been identiﬁed as a
key factor in improving UAV data sharing and security in
decentralized environments. Alkadi et al. [95] investigated
multi-blockchain integration in UAV systems, highlighting
interoperability challenges in asset transfers across different
blockchain platforms. Their study underscored the importance
of uniﬁed blockchain protocols for seamless UAV operations.
Similarly, Gupta et al. [96] designed a blockchain-based data
dissemination framework for 5G-enabled UAV networks,
securing communication channels against controller hijacking
and MITM attacks. Their implementation of secure SDN con-
troller integration improved eavesdropper detection rates, yet
issues of high storage costs and limited scalability persisted.
Authentication frameworks based on blockchain have also
been widely explored to strengthen UAV network security.
Hafeez et al. [97] introduced BETA-UAV, a blockchain-based
authentication scheme integrating smart contracts for privacy-
preserving UAV communications. Their Ethereum-based
implementation demonstrated resistance to impersonation
and replay attacks, but high gas costs and computational
demands limited broader adoption. Addressing UAV swarm
authentication, Karmakar et al. [98] proposed a reputation-
based consensus protocol for secure UAV coordination. Their
system enhanced authentication efﬁciency but required further
research into scalable blockchain architectures due to storage
constraints.

Several studies have explored blockchain-enabled UAV
security in speciﬁc operational domains. In precision agricul-
ture, Ortega et al. [99] developed a blockchain-secured UAV
monitoring system for livestock tracking, integrating IPFS for
decentralized data storage. Their approach improved secure
data transmission but faced challenges in large-scale integra-
tion. In UAV delivery services, Dong et al. [100] combined
AML with blockchain to authenticate package recipients and
prevent fraud. Their model improved veriﬁcation accuracy, yet
high data storage demands required further reﬁnement. Simi-
larly, Hafeez et al. [101] introduced BIRDS, a blockchain-based
UAV delivery coordination system optimizing resource utiliza-
tion while reducing network trafﬁc. Despite security enhance-
ments, integration complexity remained a concern. Unmanned
trafﬁc management (UTM) systems have also beneﬁted from
blockchain integration, enhancing the security of low-altitude
UAV operations. Allouch et al. [102] designed a Hyperledger
Fabric-based UTM system for decentralized UAV authentica-
tion, improving ﬂight path security. However, storage con-
straints and computational overhead highlighted the need for
scalable blockchain architectures. Ge et al. [103] proposed a
semi-autonomous blockchain UAV framework, incorporating
lightweight blockchain designs and reputation-based consen-
sus mechanisms to reduce computational overhead while
maintaining security. While their approach achieved lower
temporal delays, scalability limitations required further
investigation.

Blockchain’s potential in securing industrial UAV applica-
tions has also been explored. Tan et al. [104] introduced a
blockchain-assisted authentication service for industrial
UAVs, leveraging smart contracts to enhance data integrity
and cost efﬁciency. Their system demonstrated improved
authentication accuracy but faced challenges related to compu-
tational demands in large-scale deployments. Jain et al. [39]
provided a comprehensive review of blockchain applications in
the IoDs, outlining emerging authentication models, security
frameworks, and consensus mechanisms. Their study empha-
sized blockchain’s role in mitigating UAV data transfer risks
but highlighted challenges in wireless communication reliabil-
ity and security adaptation. Despite signiﬁcant advancements
in blockchain-based UAV security, several challenges remain,
as presented in Table 9. High storage costs, computational
overhead, and scalability constraints continue to limit block-
chain’s full adoption in UAV networks. Future research should
focus on optimizing lightweight blockchain frameworks, inte-
grating AI-driven security analytics, and improving multi-
blockchain interoperability for large-scale UAV deployments.
As UAV operations become increasingly autonomous and
interconnected, blockchain technology will play a pivotal role
in ensuring data integrity, secure authentication, and resilient
mission execution.

6.3. Cryptographic and Authentication Mechanisms. As UAV
technology continues to advance, so do the cybersecurity
threats that target data integrity, communication networks,
and UAV operational controls. Unauthorized access, hacking
attempts, and data breaches pose signiﬁcant risks to military,
commercial, and civilian UAV operations, necessitating the

IET Information Security
25

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 26 ---

#### TABLE 8: Comparative analysis of blockchain-based UAV security studies.

Study
Study focus
Blockchain approach
Security features
Computational

overhead
Communication

overhead
Scalability
Limitations

[83]
B5G UAV Security
Blockchain + AI-driven GNNs for

authentication
High resilience, link failure

detection
Moderate
Low
Moderate
AI-driven security models require

further optimization

[84]
Blockchain-assisted UAV

communication in 6G
IPFS + Blockchain for data security
Privacy preservation, reduced

latency
High
Moderate
Moderate
High storage costs and technical

adoption barriers

[85]
Secure UAV authentication
Permissioned blockchain for UAV-

to-Edge authentication
Improved security, re duced latency
Moderate
Low
Moderate
Blockchain scalability challenges in

large UAV networks

[38]
Decentralized authentication in

UAVs
DPOS-based authentication model
97.5% attack detection success rate
Moderate
Moderate
Moderate
Authentication delays,

reauthentication complexities

[86]
Secure communication for IoD

UAV networks
Blockchain-based data integrity

mechanism
Resilient against replay and MITM

attacks
Low
Low
Moderate
High data storage costs

[87]
Blockchain in 5G UAV networks
Blockchain + fog computing for

smart cities
Improved data transmission rates
Moderate
Moderate
High
Integration complexity and

adoption barriers

[88]
Blockchain in UAV com-

munication within 6G
Blockchain-based security

framework
Low latency, improved connectivity
High
High
Moderate
High storage costs and network

scalability issues

[89]
Large-scale UAV blockchain

security
ECDH + Blockchain consensus

mechanisms
Secure UAV transactions, reduced

cyberattack risks
High
Moderate
Moderate
High computational over-head,

integration complexity

[90]
Federated learning (FL) and

Blockchain integration
SDN + FL for UAV data security
Enhanced privacy, improved cyber

resilience
High
Moderate
High
Scalability and storage costs

[91]
FANET-based UAV security
Blockchain + PBFT consensus

mechanism
Stable network performance

despite node growth
High
Moderate
High
Energy constraints and

computational overhead

[90]
Blockchain for post-disaster UAV

communication
Hybrid DPOS + PBFT consensus

for multi-agency coordination
Linear scaling, resilience against

spooﬁng
Moderate
Low
High
High storage costs, scalability

concerns

[92]
Blockchain-enabled FL for B5G

UAV networks
Federated Learning + Blockchain

framework
Enhanced privacy, improved

security training accuracy
High
Moderate
High
Scalability issues, complex

integration

26
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 27 ---

#### TABLE 9: Comparison of immutable logging for security studies.

Study
Study focus
Security features
Computational

overhead
Communication

overhead
Scalability
Limitations
Future research directions

[93]
Blockchain-secured UAV logging
Immutability, public, auditability
High
Moderate
Moderate
High storage costs, computational

demands
Optimization for large-scale UAV

IoT ecosystems

[95]
Cross-blockchain inter operability
Decentralized asset transfer
High
High
Limited
Heterogeneity in blockchain

systems

Practical implementations for

scalable multi-blockchain UAV

environments

[97]
Blockchain-based UAV

authentication
Privacy preservation, replay attack

resistance
Moderate
High
Moderate
High gas costs on Ethereum

blockchain
Optimizing blockchain for real-

time UAV authentication

[94]
Secure sensing data processing
Sensor authentication, data

integrity
High
Moderate
Moderate
High storage demand
Optimizing computational

efﬁciency for large-scale UAV

deployments

[27]
Distributed blockchain security for

UAVs
Enhanced security in UAV-IoT

environments
Moderate
Low
Moderate
Storage constraints, computational

overhead
Lightweight blockchain

frameworks for UAV applications

[53]
Lightweight blockchain UAV

security
Real-time authentication, privacy

protection
Low
Low
High
Scalability issues, storage costs
Adaptive blockchain mechanisms

for resource-constrained UAVs

[98]
Intelligent clustering- based UAV

authentication
Reputation-based consensus

protocol
Moderate
Moderate
Limited
Storage overhead, computational

complexity
Scalable blockchain architectures

for UAV swarms

[96]
Blockchain-based secure UAV data

dissemination
MITM attack resistance, malicious

data detection
High
High
Moderate
High storage costs, limited

scalability
Improving blockchain integration

for UAV networks

[103]
Semi-autonomous blockchain

UAV framework
Secure communication, operational

autonomy
Low
Moderate
High
Scalability limitations, adaptability

concerns
Enhancing blockchain adaptability

for UAV operations

[102]
Blockchain-enabled UAV trafﬁc

management
Secure UAV ﬂight authentication
High
High
Moderate
Storage constraints, high resource

consumption
Blockchain scalability

improvements for UTM systems

[99]
Blockchain-secured UAV livestock

tracking
Secure data transmission
Low
Low
High
Integration challenges, storage

limitations
Scalable blockchain models for

precision agriculture UAVs

[100]
AML-integrated blockchain for

UAV authentication
Secure recipient veriﬁcation, fraud

mitigation
High
Moderate
Moderate
High data storage demands
Optimization for UAV logistics and

delivery authentication

[101]
BIRDS: Blockchain for UAV

package delivery
Immutable delivery tracking,

energy-efﬁcient networking
Moderate
Low
High
Scalability concerns (in-) tegration

complexity
Reﬁning decentralized UAV co-

ordination mechanisms

[104]
Blockchain-based UAV

authentication for industrial

applications

Smart contract-based security,

improved data integrity
Moderate
High
Moderate
Computational over-

head, storage constraints
Optimizing authentication for

large-scale industrial UAVs

[39]
Blockchain applications

in IoD
Authentication mechanisms,

security models
High
Moderate
Limited
Wireless communication

reliability, adaptation issues
Improving blockchain scalability

for IoD networks

IET Information Security
27

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 28 ---

### Section: 6.3.1. PQC

integration of advanced cryptographic methods and authenti-
cation mechanisms into UAV security frameworks. These
cryptographic advancements aim to enhance encryption resil-
ience, prevent unauthorized drone takeovers, and secure UAV
communications against both conventional and quantum-
based cyber threats.

6.3.1. PQC. As quantum computing advances, it presents a
formidable challenge to traditional cryptographic security
mechanisms, particularly in UAV networks where encrypted
transmissions contain sensitive surveillance data, mission com-
mands, and military intelligence. Quantum computers have the
potential to break widely used cryptographic algorithms such
as RSA, ECC, and ElGamal, rendering current UAV security
protocols ineffective. To address this growing concern,
researchers have proposed PQC techniques, quantum key dis-
tribution (QKD), and hybrid AI-enhanced quantum encryp-
tion frameworks to safeguard UAV communications against
quantum cyber threats.

CRYSTALS-Kyber has emerged as one of the most prom-
ising quantum-resistant cryptographic schemes for securing
UAV data transmissions. Sharma et al. [31] demonstrated
the effectiveness of CRYSTALS-Kyber in providing end-to-
end encryption, ensuring UAV communication resilience
against quantum-based adversaries. Similarly, Aissaoui et al.
[105] compared multiple post-quantum key encapsulation
mechanisms (KEMs), including CRYSTALS-Kyber, Hamming
Quasi-Cyclic (HQC), and BIKE, identifying CRYSTALS-Kyber
as the most efﬁcient for UAV applications. Despite its security
advantages, the integration of PQC mechanisms remains a
challenge due to hardware constraints and computational over-
head, which limit real-time UAV applications. Further optimi-
zation of PQC algorithms is necessary to improve scalability
and performance in dynamic UAV networks.

QKD has also been explored as a viable solution for secur-
ing UAV communication channels. Ralegankar et al. [106]
implemented a QKD-based UAV security framework, focusing
on applications in agriculture, healthcare, and military opera-
tions. Their battleﬁeld case study demonstrated improved secu-
rity and reduced latency compared to classical cryptographic
techniques. However, challenges such as high implementation
costs and the complexity of QKD hardware integration remain
barriers to widespread adoption. Hussien et al. [107] analyzed
various QKD protocols for UAV and satellite communication,
conﬁrming their resilience against quantum attacks but
highlighting the need for further optimization to improve
cost-effectiveness and deployment feasibility.

To complement post-quantum encryption techniques,
researchers have developed quantum-resistant authentication
and key agreement mechanisms to secure UAV networks. Xia
et al. [108] proposed a PQC-based identity authentication
scheme leveraging the Kyber algorithm, signiﬁcantly reducing
computational overhead while ensuring robust security against
quantum attacks. Similarly, Nair et al. [109] introduced a
post-quantum secure cross-domain authentication (CDA)
framework for the IoD, integrating blockchain and physical
unclonable functions (PUFs) to provide mutual authentication
without storing sensitive data on UAVs. Although these

frameworks enhance quantum resistance, challenges such as
increased communication costs and integration complexity
highlight the need for further research on optimizing PQC
for real-time UAV operations.

Beyond cryptographic encryption, researchers have
explored AI-driven and hybrid security models to enhance
UAV resilience against quantum threats. Gnatyu et al. [35]
investigated AI-enhanced encryption for UAV communica-
tion, utilizing ML to automate cryptographic key selection
and improve encryption resilience. Their approach reduced
latency and increased security adaptability; however, high
computational overhead remained a key limitation. Similarly,
Goyal et al. [110] proposed a fusion of Blockchain, AI, and
quantum computing for UAV security, integrating blockchain
for decentralized authentication, AI for anomaly detection, and
quantum cryptography for encryption. While this multilayered
approach improved security transparency, scalability remained
an issue, requiring further optimizations for deployment in
large-scale UAV networks.

Another promising direction in quantum-resistant UAV
security is the use of lattice-based cryptography. Mishra et al.
[22] developed a quantum-safe communication protocol for
IoD networks using the Ring Learning With Error (RLWE)
problem on lattices, eliminating the need for classical encryp-
tion schemes such as RSA and ECC. Their framework demon-
strated high security and efﬁciency in mutual authentication,
though integration complexity and computational resource
demands remained key challenges. Similarly, Sandanamudi
et al. [111] evaluated lightweight PQC algorithms such as
SABER, NTRU, and CRYSTALS-Kyber for UAV networks,
identifying SABER as the most efﬁcient cipher. However,
resource constraints in IoT-based UAV environments necessi-
tate further optimizations for seamless PQC integration.

The application of quantum cryptography in UAV-based
authentication has also gained traction. Abulkasim et al. [54]
examined a quantum-based authentication scheme for secur-
ing IoD communication, utilizing quantum channels for infor-
mation encoding and mutual authentication. Their approach
exhibited strong resistance to impersonation and MITM
attacks, though challenges in implementing quantum crypto-
graphic techniques in resource-limited UAV environments
remained. Likewise, Jawad et al. [112] introduced a visual
cryptography-based UAV authentication system, leveraging
chaotic map-based key generation to enhance security while
minimizing computational and communication overhead.

Free-space optical (FSO) quantum communication has
also been explored to improve UAV security. Alshaer et al.
[113] investigated entanglement-based QKD over FSO links,
achieving high security with low outage probabilities in
dynamic UAV networks. Their study optimized transmit
power and modulation schemes for secure FSO–QKD integra-
tion, but challenges such as atmospheric turbulence and track-
ing errors required further reﬁnements.

For large-scale UAV networks, blockchain-integrated PQC
solutions have been proposed to enhance authentication efﬁ-
ciency and prevent unauthorized access. El-Zawawy et al. [114]
designed a blockchain-supported authentication protocol for
drone-assisted internet of vehicles (IoV), achieving a 70%

28
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 29 ---

### Section: 6.3.2. Multi-Factor Authentication (MFA) for UAV Security

reduction in energy consumption and 68% lower computa-
tional cost. However, the complexity of blockchain implemen-
tation in UAV networks remained a challenge. Similarly, Babu
et al. [56] provided a comprehensive survey on quantum
authentication and key agreement protocols, emphasizing the
importance of lightweight PQC techniques for securing future
UAV communication infrastructures.

Despite signiﬁcant advancements in PQC, QKD, and
hybrid AI-enhanced security models for UAV networks, sev-
eral challenges persist, as presented in Table 10. The high
computational and energy overhead associated with PQC algo-
rithms limits real-time applicability in resource-constrained
UAVs. Scalability remains a key concern, particularly in
ultra-dense UAV networks where key management and
authentication processes must be optimized for efﬁciency.
Additionally, the integration complexity of QKD and PQC
frameworks with existing UAV security architectures requires
further research to ensure seamless implementation without
introducing performance bottlenecks.

Future research should focus on developing energy-
efﬁcient PQC algorithms tailored for UAV systems, reﬁning
AI-driven encryption models for dynamic UAV operations,
and enhancing blockchain scalability for decentralized UAV
authentication. The integration of adversarial learning techni-
ques with PQC may further improve resilience against evolving
cyber threats. As quantum computing capabilities continue to
advance, ensuring that UAV security architectures remain
quantum-resistant will be paramount in safeguarding
mission-critical drone operations in military, surveillance,
and commercial applications.

6.3.2. Multi-Factor Authentication (MFA) for UAV Security.
Ensuring secure authentication and communication in UAV
networks is crucial to prevent cyber threats such as spooﬁng,
MITM attacks, and unauthorized UAV access. Traditional
authentication methods, such as password-based logins, have
become increasingly vulnerable to hacking, brute force attacks,
and credential theft, making MFA a necessary security
enhancement for both military and commercial UAV opera-
tions. Recent research has explored AI-enabled, blockchain-
integrated, and post-quantum authentication mechanisms to
enhance UAV security while addressing challenges related to
computational overhead, scalability, and real-time communi-
cation efﬁciency.

Several studies have introduced lightweight and AI-driven
authentication schemes to enhance security in UAV networks.
Deebak and Hwang [42] proposed a secure MFA (RL-SMFA)
scheme for UAVs operating in military surveillance, leveraging
elliptic curve cryptography (ECC) and AI-based analytics.
Their approach improved packet delivery ratio and end-to-
end delay while reducing power consumption, but scalability
remained a challenge, requiring further optimization for large
UAV networks. Similarly, Wang et al. [115] developed a three-
factor authentication and key agreement protocol for UAV-
assisted post-disaster emergency communication, integrating
smart cards, biometrics, and physically unclonable functions
(PUFs) to ensure secure UAV-to-UAV and UAV-to-emer-
gency control vehicle (ECV) communication. While their

approach successfully mitigated communication vulnerabil-
ities, it faced computational complexity issues in large-scale
implementations.

Beyond individual authentication schemes, comparative
analyses have been conducted to evaluate UAV authentication
strategies. Mekdad et al. [40] analyzed 27 UAV authentication
schemes, focusing on communication costs, storage overhead,
and energy efﬁciency. Their study revealed that while many
schemes optimized communication costs, they often failed to
address storage and energy consumption constraints. Addres-
sing this gap, Khan et al. [116] introduced a blockchain-based
MFA protocol for 6G-enabled UAV networks, integrating
Difﬁe–Hellman key exchange and Proof-of-Stake (PoS)
mechanisms. Their approach signiﬁcantly reduced authentica-
tion, communication, and computational overheads, though
scalability remained a concern in ultra-dense networks.

Alternative cryptographic approaches have also been
explored to improve authentication efﬁciency. Zhang et al.
[117] developed a three-factor authentication protocol using
BPV-FourQ ECC for IoD networks. Their solution improved
processing speed by four to ﬁve times compared to traditional
elliptic curve methods, demonstrating strong forward secrecy
and attack resistance. Meanwhile, Cui et al. [23] introduced a
chaotic map-based authentication and key agreement (AKA)
scheme for UAV-assisted vehicular ad hoc networks
(VANETs). Their hybrid authentication mechanism, which
integrated honeywords and fuzzy veriﬁers, effectively reduced
communication and computational overhead, making it a via-
ble solution for emergency response UAV-VANET scenarios.

ECC-based authentication has been widely investigated as a
lightweight cryptographic alternative. Usman et al. [118]
designed an ECC-based authentication protocol for UAVs in
SDN environments, achieving low latency and high security
against forgery and replay attacks. However, computational
overhead remained a challenge for large UAV ﬂeets. Building
upon this approach, Khalid et al. [119] introduced a two-factor
authentication scheme for real-time UAV communication,
addressing the risk of key management system failures. While
their study demonstrated lower communication and computa-
tion costs, further research was required to improve scalability
and system resilience.

PUF-based authentication has emerged as a promising
solution for lightweight UAV security. Tian et al. [120] pro-
posed a PUF-based CDA scheme for UAVs, ensuring tamper
resistance and secure communication in multi-domain net-
works. Bansal and Sikdar [121] extended this work by utilizing
Shamir’s secret sharing scheme to mitigate errors in PUF
responses, successfully reducing communication overhead
while improving security against environmental variations.
However, external noise in PUF responses remained a chal-
lenge, necessitating additional error correction mechanisms to
enhance reliability.

Beyond authentication, secure key management is a critical
aspect of UAV security. Ismael et al. [122] explored the use of
the HIGHT lightweight block cipher for UAV communication
encryption, demonstrating high performance with low compu-
tational costs. Their approach effectively reduced latency and
energy consumption, though further reﬁnement was needed

IET Information Security
29

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 30 ---

#### TABLE 10: Comparison of quantum and post-quantum cryptographic techniques for UAV security.

Study
1
2
3
4
5
6
7
8
9
10
11

[31]
Post-quantum cryptography
CRYSTALS Kyber
High Moderate
Low
High
High
Hardware constraints
Key generation rate
Simulation
Optimization for UAV

networks

[106]
Quantum cryptography
QKD
High
High
Moderate Moderate Limited
Complexity, cost
Latency, throughput
Simulation
Scalability, hardware

optimization

[108]
Quantum-resistant

authentication
Kyber algorithm
High
Low
Low
High
High
Integration

complexity
Computational

overhead
Simulation
Optimization of PQC

algorithms

[109]
Cross-domain authentication
PUFs, blockchain
High Moderate
High
Moderate
High
Communication,

costs
Latency
Simulation
Real-time UAV operations

[105]
Post-quantum KEMs
CRYSTALS-Kyber, HQC,

BIKE
High
High
Moderate Moderate Limited
Real-time overhead
Execution time
Simulation
Scalability optimizations

[54]
Quantum-based

authentication
Quantum channels
High
High
High
Moderate Limited
Implementation cost
Resistance to attacks
Simulation Reﬁnement of QKD techniques

[22]
Quantum-safe

communication
RLWE
High
High
Moderate Moderate
High
Integration

complexity
Security metrics
Simulation
Resource-constrained

environments

[107]
QKD for UAV-satellite

comms
QKD
High
High
High
Moderate Limited
Complexity, cost
Resilience metrics
Simulation
Real-world UAV operations

[26]
QKD for agrotechnical

systems
BB84 protocol
High
Low
Low
High
High
Energy efﬁciency
Key generation rate
Simulation
Large-scale UAV deployments

[112]
Visual cryptography
Chaotic maps
High
Low
Low
High
High
Limited securityML,
Computational

overhead
Simulation
Machine learning integration

[35]
AI-based encryption
AI-driven key selection
High
High
Low
Moderate
High
Computational

overhead
Latency reduction
Simulation
AI-driven optimizations

[111]
Lightweight PQC algorithms
CRYSTALS-Kyber, SABER
High
Low
Low
High
High
IoT constraints
Execution efﬁciency
Simulation
Seamless IoT integration

[21]
Post-quantum digital

signatures
Falcon, CRYSTALS-

Dilithium
High
Low
Low
High
High
Key size
Execution

consistency
Simulation
Broader UAV applications

[113]
Entanglement-based QKD
FSO-QKD
High
High
High
Moderate Limited
Atmospheric

turbulence
Outage probability
Simulation
FSO–QKD integration

[110]
Blockchain, AI, Quantum

fusion
Blockchain, AI, QKD
High
High
High
Moderate Limited
Scalability
Transparency,

security
Simulation
Scalability optimizations

[56]
Survey of quantum protocols
PQC primitives
High
N/A
N/A
N/A
N/A
N/A
N/A
N/A
Lightweight PQC techniques

Note: (1)-Study Focus, (2)- Cryptographic Technique, (3)- Security Features, (4)- Computational Overhead, (5)- Communication Overhead, (6)- Energy Efﬁciency, (7)- Scalability, (8)- Limitations, (9)- Performance

Metrics, (10)- Experimental Validation, (11)- Future Research Directions.

30
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 31 ---

### Section: 6.4. Adversarial Defense Mechanisms in AI Models

for integration with diverse UAV models. Similarly, Kirsal Ever
[55] introduced an ECC-based authentication protocol for
UAVs functioning as mobile sinks in the IoD, achieving strong
security guarantees while maintaining lightweight computa-
tional requirements.

Blockchain-based authentication has gained traction as a
decentralized security solution for UAV networks. El-Zawawy
et al. [114] designed a blockchain-supported authentication
protocol for drone-assisted IoV, reducing energy consumption
by up to 70% and computational cost by 68%. Their Burrow-
Abadi-Needham (BAN) logic-based approach signiﬁcantly
improved authentication efﬁciency, but the complexity of
blockchain integration required further research on scalability
and adaptation to dynamic UAV ﬂeets. Similarly, Dong et al.
[123] developed a zero-trust security framework for UAV
delivery authentication, incorporating MFA and blockchain-
based self-sovereign identity (SSI) techniques. While their
study effectively prevented spooﬁng and injection attacks, the
complexity of managing multiple authentication factors posed
implementation challenges.

An alternative blockchain-based approach was introduced
by Alladi et al. [124], who developed a PUF-enabled mutual
authentication scheme for UAV-GS communication, extend-
ing it to UAV-to-UAV authentication. Their cryptanalysis con-
ﬁrmed resilience against masquerade, replay, and node
tampering attacks, though PUF integration complexity
remained a key limitation. These studies highlight the potential
of combining blockchain with advanced cryptographic meth-
ods to create secure, scalable authentication frameworks for
UAV communication.

By integrating PQC with MFA frameworks, UAV security
systems can achieve greater resilience against cyber intrusions,
unauthorized access, and evolving cryptographic threats. Mov-
ing forward, future UAV security architectures should focus on
integrating AI-powered threat detection, de-centralized cryp-
tographic key management, and continuous authentication
mechanisms to further enhance UAV cybersecurity and pre-
vent next-generation cyberattacks.

The reviewed studies illustrate signiﬁcant advancements in
UAV authentication mechanisms, incorporating AI-based
security analytics, blockchain, PQC, PUFs, and ECC-based
encryption, presented in Table 11. While these technologies
offer enhanced security, reduced computational overhead,
and improved scalability, several challenges remain, including
high storage costs, energy constraints, and integration com-
plexity. Future research should prioritize optimizing authenti-
cation protocols for real-time UAV applications, developing
energy-efﬁcient cryptographic solutions, and improving block-
chain scalability for large UAV networks. By addressing these
challenges, next-generation UAV authentication frameworks
can ensure secure and resilient communication in increasingly
complex and adversarial environments.

6.4. Adversarial Defense Mechanisms in AI Models. As AI-
driven UAVs become increasingly sophisticated, they also
become more susceptible to adversarial attacks, where mali-
cious actors exploit vulnerabilities in AI models to manipulate
UAV decision-making. These attacks can involve manipulated

sensor data, deceptive image recognition inputs, or altered
environmental conditions, leading to incorrect threat classiﬁca-
tions, misdirected ﬂight paths, or compromised mission execu-
tion. Given these risks, researchers are actively developing
defense mechanisms to enhance AI robustness, improve resil-
ience against adversarial manipulation, and ensure reliable
UAV decision-making in high-risk operational environments.

6.4.1. Robust AI Models Against Adversarial Attacks. One of
the most effective approaches for improving AI resilience is
adversarial training, where AI models are exposed to adversar-
ial attacks during training to help them learn how to counteract
deceptive inputs. By deliberately introducing adversarial per-
turbations into training datasets, researchers can teach AI algo-
rithms to recognize, adapt, and neutralize adversarial
manipulations before they affect UAV operations. This proac-
tive training methodology prepares UAV AI models to with-
stand real-world cyberthreats, reducing their vulnerability to
malicious data modiﬁcations, false object detections, or sensor
spooﬁng attempts.

The vulnerability of AI models to adversarial attacks has
been widely studied across various domains, including com-
puter vision, network security, UAV operations, and digital
communication systems. Studies have demonstrated that DL
models, including CNNs, vision transformers (ViTs), and deep
clustering frameworks, are highly susceptible to adversarial
perturbations, which can signiﬁcantly degrade their perfor-
mance. Chang et al. [34] conducted an extensive evaluation
of adversarial robustness in image classiﬁcation models, testing
six CNN models against 13 different attack types. Their attack-
agnostic approach provided an unbiased robustness assess-
ment, serving as a benchmark for future defenses. Similarly,
Olutimehin et al. [19] analyzed CNNs under adversarial stress,
revealing attack success rates exceeding 85% for Carlini &
Wagner (C&W) perturbations, underscoring the need for
hybrid defense mechanisms combining adversarial training
with real-time anomaly detection.

While adversarial vulnerabilities in image classiﬁcation
have been extensively examined, similar concerns have
emerged in NLP applications. Goyal et al. [43] reviewed adver-
sarial defenses in NLP models, introducing a taxonomy of
defense mechanisms. Their study emphasized the fragility of
DNNs in NLP tasks, highlighting the need for generalized
adversarial defenses across multiple domains. Beyond vision
and NLP, adversarial attacks also pose substantial threats to
cybersecurity and network security systems. Zhang et al. [125]
investigated DL-based network IDSs (NIDSs), introducing
TIKI-TAKA, a defensive framework that restored intrusion
detection rates to nearly 100% by integrating adversarial train-
ing,modelensembling, andquerydetection.Similarly, Renetal.
[48] examined adversarial attacks on cybersecurity applica-
tions, demonstrating that robustness could be signiﬁcantly
improved through certiﬁed defenses and adversarial retraining.

Ensuring real-world applicability of adversarial defenses
remains a key challenge. Ai et al. [32] focused on adversarial
perturbations in remote sensing applications, proposing cross-
model generalization strategies to improve classiﬁer robustness.
Their study showed that real-world constraints heavily

IET Information Security
31

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 32 ---

inﬂuence adversarial defense effectiveness, necessitating scal-
able and computationally efﬁcient solutions. Similarly, Tsai
et al. [126] explored adversarial attacks on 3D data models,
speciﬁcally targeting PointNet++ architectures used for object
classiﬁcation and segmentation. Their ﬁndings revealed that
3D adversarial perturbations could bypass existing defense
mechanisms, emphasizing the need for robust adversarial
defenses tailored to three-dimensional AI applications. Within
the medical AI domain, adversarial security threats have been a
growing concern. Ghaffari Laleh et al. [44] analyzed adversarial
vulnerabilities in computational pathology, comparing the
robustness of CNNs and ViTs in medical image classiﬁcation
tasks. Their ﬁndings demonstrated that ViTs exhibited signiﬁ-
cantly higher resilience to adversarial attacks than CNNs, sug-
gesting that transformer-based architectures could offer a more
robust alternative for medical AI applications. In the context of
UAV security, adversarial attacks pose severe risks, as AI-
driven UAV misclassiﬁcations can have real-world conse-
quences. Raja et al. [47] examined adversarial at-tacks on AI-
assisted UAV bridge inspection systems, demonstrating that
adversarial inputs could mislead UAVs into misidentifying
risk-prone infrastructure, increasing accident risks. Similarly,
Tian et al. [127] studied adversarial attacks on automatic
modulation classiﬁcation (AMC) models in cognitive radio
networks, revealing the vulnerability of AI-based communi-
cation systems to adversarial interference. Their research
underscored the importance of robust defense mechanisms
in wireless communication applications.

To mitigate adversarial threats, several defense mechan-
isms have been explored. Zhang et al. [128] conducted a com-
prehensive review of adversarial defenses in DNNs, comparing
classical and state-of-the-art methods. Their ﬁndings empha-
sized the need for computationally efﬁcient defenses that main-
tain high classiﬁcation accuracy. Similarly, Waghela et al. [129]
investigated defensive strategies against FGSM and PGD
attacks, demonstrating that adversarial training combined
with data preprocessing signiﬁcantly enhanced robustness.

The use of Generative Adversarial Networks (GANs) for adver-
sarial defense has gained traction in recent years. Taheri et al.
[10] leveraged GAN-based adversarial training in botnet detec-
tion tasks, employing Pix2Pix GANs to generate adversarial
examples for model retraining. Their iterative approach signif-
icantly reduced misclassiﬁcation rates, demonstrating the effec-
tiveness of GAN-based defenses in cybersecurity applications.
Similarly, Chhabra et al. [25] examined GAN-based black-box
adversarial attacks on deep clustering models, exposing serious
vulnerabilities in state-of-the-art clustering algorithms and
stressing the urgency of developing robust, unsupervised adver-
sarial defenses.

Beyond traditional adversarial defenses, Anastasiou et al.
[33] focused on adversarial robustness in AI-assisted
manufacturing systems, highlighting the signiﬁcance of defense
algorithms in real-world industrial settings. Their study com-
bined adversarial training with defensive strategies, showing
substantial recovery of classiﬁer accuracy in adversarial envir-
onments. A key advantage of adversarial training is real-time
AI adaptation, which enables UAVs to continuously reﬁne
their decision-making models based on new threat patterns
and environmental anomalies. AI-driven UAVs equipped
with adaptive learning mechanisms can detect unexpected var-
iations in sensor inputs or command signals, allowing them to
ﬂag suspicious activities, reject deceptive data, and maintain
operational accuracy. Research studies have demonstrated
that adversarially trained AI-driven UAVs exhibit enhanced
resilience against AI deception attacks, particularly in military
reconnaissance, autonomous surveillance, and target identiﬁ-
cation missions [3].

In summary, adversarial threats pose signiﬁcant risks to AI
models across multiple domains, including computer vision,
cybersecurity, medical AI, UAV operations, and network secu-
rity, as presented in Table 12. While adversarial training, model
ensembling, and GAN-based defenses have shown promise,
several challenges remain, particularly in computational efﬁ-
ciency, real-world adaptability, and scalability. Future research

#### TABLE 11: Comparison of studies on secure authentication mechanisms for UAV networks.

Study
Authentication

mechanism

Cryptographic

technique

Security
features

Computational

overhead

Communication

overhead

Energy
efﬁciency
Scalability
Limitations

[42]
RL-SMFA
Elliptic Curve
Cryptography
High
Moderate
Low
High
Limited
Scalability

[115]
Three-factor
authentication
PUFs, biometrics
High
High
Moderate
Moderate
Limited
Computational

complexity

[116]
Blockchain-

based MFA

Difﬁe- Hellman,

PoS
High
Low
Low
High
Limited
Scalability

[117]
Three-factor
authentication
BPV-FourQ ECC
High
Low
Low
High
High
None

[23]
Chaotic map-

based AKA

Honeywords,
fuzzy veriﬁers
High
Low
Low
High
High
None

[118]
ECC-based
authentication

Elliptic Curve
Cryptography
High
Moderate
Low
High
Limited
Computational

overhead

[120]
PUF-based
authentication
PUFs
High
Low
Low
High
High
Noise sensitivity

[114]
Blockchain-
supported AKA
BAN logic
High
Low
Low
High
Limited
Complexity

32
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 33 ---

#### TABLE 12: Comparison of adversarial training and defense mechanisms for AI security.

Study
Focus area
Adversarial Attack type
Defense mechanism
Computational

overhead
Key ﬁndings
Limitations and future directions

[34]
Image classiﬁcation
13 different attack types on CNN
models
Attack- agnostic robustness

assessment
Moderate
Established a benchmark for

evaluating adversarial robustness
Requires real-world validation for

adaptive defense mechanisms

[19]
CNN-based classiﬁcation

-
Carlini & Wagner (C&W)

perturbations
Hybrid adversarial training +

anomaly detection
High
Identiﬁed high attack success rates

(85%), highlighting CNN

vulnerabilities

Computationally intensive; further

optimization needed for real-time

applications

[43]
NLP models
Text-based adversarial

perturbations
Defense taxonomy for NLP security
Moderate
Showed deep NLP models’ fragility;

highlighted need for generalizable

defenses

Requires integration of adversarial

robustness in real-time NLP tasks

[125]
Network security (NIDS)
Intrusion detection adversarial

attacks
TIKI-TAKA framework (ensemble

+ adversarial training)
Moderate
Restored intrusion detection rates

to nearly 100%

High computational cost;

scalability challenges in large

networks

[48]
Cybersecurity applications
FGSM, PGD, BIM at- Tacks
Certiﬁed defenses + adversarial

retraining
High
Improved AI security in

cybersecurity models
Requires scalable and efﬁcient

adversarial training strategies

[32]
Remote sensing
Cross-model adversarial

perturbations
Model generalization techniques
High
Improved classiﬁer robustness in

real-world constraints
High computational complexity;

further optimization needed

[126]
3D object recognition
PointNet++ adversarial

perturbations
Robust adversarial defenses for 3D

models
Moderate
Revealed vulnerabilities in 3D AI

models
Requires enhanced defenses for

three-dimensional AI applications

[44]
Medical AI (Computa- tional

Pathology)
CNN and ViT adversarial attacks
Comparative robustness analysis
Moderate
Found ViTs more robust than

CNNs against adversarial attacks

High computational requirements

for real-time medical AI

applications

[47]
UAV bridge inspection
Adversarial misclassiﬁcation
Robust UAV classiﬁcation models
Moderate
Demonstrated UAV risk

misidentiﬁcation due to adversarial

attacks

Requires robust countermeasures

for UAV security systems

[127]
Cognitive radio net- works
Automatic modulation classiﬁcation

(AMC) attacks
AI-based defense against adversarial

signals
Moderate
Showed AI-based communication

systems are highly vulnerable

Requires additional adversarial

defenses for secure UAV

communication

[128]
DNNs
Multiple adversarial perturbations
Review of

classical and state-of-the-art

defenses
Moderate
Identiﬁed computationally efﬁcient

adversarial defenses

More real-world validation

required

for scalable adversarial defenses

[129]
ML security
FGSM, PGD attacks
Adversarial

training + data preprocessing
High
Improved adversarial robustness

across ML models
Computationally expensive; re-

quires efﬁciency optimization

[10]
Cybersecurity
Botnet detection adversarial

attacks
GAN-based

adversarial training
High
Reduced misclassiﬁcation rates

using Pix2Pix GANs
High computational cost; requires

real-world testing

[25]
Deep clustering
Black-box GAN adversarial

attacks
Adversarially

robust deep clustering models
High
Exposed critical vulnerabilities in

state-of-the-art clustering

Further research needed on

unsupervised-

adversarial defenses

[33]
AI-assisted manufacturing
Adversarial training
Combined adversarial

training + defense algorithms
High
Improved classiﬁer accuracy in

adversarial

environments

Requires adaptation for industrial

real-time settings

[3]
UAV defense
AI deception attacks on

UAVs
Adaptive

adversarial training
Moderate
Improved resilience of AI-driven

UAVs in reconnaissance missions
Needs real-world UAV adversarial

testing and enhancement

IET Information Security
33

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 34 ---

### Section: 6.4.2. XAI for UAV Decision Transparency

should focus on developing lightweight adversarial defenses,
integrating AI-driven anomaly detection, and reﬁning adver-
sarial robustness benchmarks to ensure the security and reli-
ability of AI systems in diverse applications. The integration of
XAI with adversarial learning techniques will be crucial in
improving AI resilience against sophisticated adversarial
threats while maintaining transparency. As AI systems become
increasingly embedded in critical operations, ensuring their
robustness and security will be paramount in fostering trust,
safety, and ethical deployment.

6.4.2. XAI for UAV Decision Transparency. The increasing
reliance on AI-driven decision-making in cybersecurity, UAV
operations, and autonomous defense systems has created a
pressing need for explainability, transparency, and trustworthi-
ness. Many DL models used in UAV operations function as
black-box systems, where their internal decision logic re-mains
opaque, making it difﬁcult to trace errors, verify threat classi-
ﬁcations, or audit mission-critical decisions. This lack of
interpretability raises concerns in high-stakes applications
such as military drone operations, autonomous law enforce-
ment UAVs, and civilian airspace monitoring, where unex-
plained AI errors could lead to severe consequences.
Researchers have proposed XAI frameworks, anomaly detec-
tion models, and adversarial learning techniques to enhance AI
interpretability and mitigate security risks. Tiwari et al. [130]
analyzed the role of XAI in cybersecurity, emphasizing how
explainability in AI-driven threat detection can improve trust
and accountability. Similarly, Moustafa et al. [131] and Masud
et al. [132] explored anomaly-based intrusion detection in IoT
ecosystems, demonstrating that DL models can effectively
detect cyber threats, but their opacity hinders trust in AI-driven
security solutions. These studies emphasized the need for inte-
grating interpretability methods, such as SHapley Additive
exPlanations (SHAP), to ensure AI decisions are transparent
and explainable. XAI is also gaining prominence in securing
UAV networks, where cyber threats such as GPS spooﬁng and
DoS attacks pose signiﬁcant risks. Wu et al. [133] proposed a
CNN-BiLSTM-Attention (CBA) model for UAV cyberattack
detection, integrating SHAP-based interpretability to provide
human-understandable insights. Their evaluation demon-
strated that explainability improves AI decision-making in
UAV security, making it easier to identify and respond to cyber
threats. Similarly, Ihekoronye et al. [49] developed Drone-
Guard, a cybersecurity framework leveraging supervised ML
and XAI to detect intrusions. Their model utilized decision
trees and feature selection techniques, demonstrating high
accuracy and low computational complexity, making it suitable
for UAV networks with resource constraints. Ajakwe and Kim
[134] reviewed security paradigms for UAV-based smart
mobility and logistics, proposing an agile XAI framework
that integrates blockchain authentication and zero-trust cyber-
security principles. Their ﬁndings reinforced the importance of
explainability in securing UAV communications and prevent-
ing cyber intrusions.

AI transparency is particularly critical in military and
autonomous defense systems, where AI decisions can have
life-altering consequences. Chander et al. [135] examined the

black-box nature of AI in defense applications, proposing a
framework for explainable and robust AI. Their study empha-
sized the necessity of transparency in autonomous weapons
systems (AWS) to prevent biases and ensure accountability
in military AI decision-making. Similarly, Cools and Maathuis
[4] analyzed the integration of AWS in military operations,
highlighting trust, human–machine teaming, and ethical con-
cerns as key challenges. Their study underscored the impor-
tance of interpretable AI in high-risk environments, where
human oversight is essential for reliable decision-making. In
the context of air combat, Saldiran et al. [50] developed an XAI
system using RL and reward decomposition to clarify AI agent
decisions. Their research demonstrated that explainable mod-
els enhance trust in AI-driven military operations, making AI
tactics more interpretable and reliable. Wang and Aouf [51]
investigated adversarial attacks on autonomous driving sys-
tems, proposing a saliency map-based XAI approach to
improve AI resilience in dynamic environments. Their study
reinforced the importance of explainability in AI-driven navi-
gation, particularly in real-time, high-stakes scenarios.

Adversarial learning techniques have been increasingly
explored to enhance AI security and explainability, particularly
in wireless communications and UAV-based key generation.
Wei et al. [37] proposed an adversarial learning framework for
physical layer key generation (PL-SKG) to mitigate MITM RIS
eavesdropping. Their research incorporated symbolic XAI
representation to interpret black-box neural net-works, ensur-
ing that AI-driven security measures remain transparent and
accountable. Similarly, Maathuis [136] analyzed cybersecurity
challenges in smart urban environments, emphasizing AI-
driven threat detection and mitigation strategies. Their ﬁndings
demonstrated that XAI-enabled cybersecurity frameworks
enhance real-time threat detection, particularly in autonomous
infrastructure defense.

Despite signiﬁcant advancements in XAI for cybersecurity,
UAV security, and autonomous defense systems, several chal-
lenges remain. AI transparency often comes at the cost of
computational overhead, making real-time implementation
difﬁcult in resource-constrained environments. Studies such
as those by Wu et al. [133] and Ihekoronye et al. [49] have
highlighted the trade-offs between accuracy and efﬁciency in
XAI-based security frameworks. Additionally, ethical concerns
surrounding AI biases and decision-making opacity must be
addressed to ensure AI is fair and trustworthy. Future research
should focus on optimizing XAI algorithms for real-time secu-
rity applications, enhancing trust in AI-driven military and
defense systems, and developing scalable XAI models for
UAV cybersecurity and smart mobility. The integration of
adversarial learning techniques with XAI will be essential in
improving AI resilience against adversarial threats while main-
taining transparency. As AI becomes more deeply embedded in
critical systems, ensuring that these technologies are both inter-
pretable and robust will be paramount in fostering trust, secu-
rity, and ethical AI deployment across various domains, as
presented in Table 13.

6.5. Software and Hardware-Based Countermeasures. As
cyber
threats
targeting
UAVs
become
increasingly

34
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 35 ---

#### TABLE 13: Comparison of XAI for cybersecurity, UAV security, and defense systems.

Study
Focus area
XAI method
Security enhancement
Computational

overhead
Key ﬁndings
Limitations and future directions

[130]
XAI in cybersecurity
AI-driven threat detection
Trust and accountability
Moderate
Addressed biases, ethical concerns,

and AI interpretability issues in

cybersecurity

Requires further integration with

real-time AI security frameworks

[131,

132]
Anomaly detection in IoT security
SHapley Additive exPlanations

(SHAP)
Improved cyber threat detection
High
Demonstrated that deep learning

can detect threats but lacks

interpretability

Needs optimization for real-time

detection with lower

computational costs

[133]
UAV cyberattack detection
CNN-BiLSTM- Attention + SHAP Enhanced interpretability of UAV

security threats
Moderate
Explainability improved UAV

decision-making in cyber threat

response

Trade-offs exist between accuracy

and computational efﬁciency

[49]
Intrusion detection in UAV

networks
Decision trees + feature selection
High detection accuracy
Low
Developed DroneGuard a

lightweight intrusion detection

system

Requires scalability testing for

larger UAV networks

[134]
UAV security for smart mobility
Blockchain-integrated XAI
Zero-trust cybersecurity for UAVs
High
Integrated blockchain

authentication for UAV

communications

Needs further optimization for

blockchain scalability

[135]
AI in autonomous defense systems
Explainable and robust AI

framework
AI transparency in military AI
Moderate
Proposed an AI framework for

autonomous weapons systems

#### (AWS)

Ethical and operational challenges

in AWS deployments remain

[4]
Trust in Autonomous Weapons

Systems (AWS)
Human–machine teaming
Enhancing trust in military AI
High
Highlighted the necessity of

human oversight in AWS

decision-making

Requires policy and regulatory

frameworks for ethical AI in

defense

[50]
AI decision-making in air combat
Reinforcement learning + reward

decomposition
Improved trust in AI military

operations
High
Explainability improved AI-driven

combat decision transparency
Needs real-world validation in

high-risk environments

[51]
Adversarial defense in

autonomous driving
Saliency map-based XAI
Improved AI resilience
Moderate
Demonstrated importance of XAI

in real-time navigation security
High computational cost in

dynamic environments

[37]
XAI for wireless communication

security
Adversarial learning for key

generation
Mitigation of MITM-RIS attacks
High
Ensured transparent and account-

able AI-driven security

Requires optimization for real-

time key generation in UAV

networks

[136]
Cybersecurity in smart urban

environments
AI-driven threat detection
Enhanced real- time threat

mitigation
High
XAI improved transparency in

cybersecurity frameworks

Needs computational efﬁciency

improvements for large-scale

deployment

IET Information Security
35

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 36 ---

### Section: 6.5.1. Hardware Security Modules (HSMs) for UAVs

sophisticated, traditional AI and cryptographic security solu-
tions alone are not sufﬁcient to protect against ﬁrmware tam-
pering, malware injections, and unauthorized modiﬁcations.
To enhance UAV security and operational resilience, research-
ers are integrating hardware-based security mechanisms and
AI-driven self-healing systems into UAV architectures. These
advanced countermeasures provide additional layers of protec-
tion against cyber intrusions, ensuring that UAVs can detect,
mitigate, and recover from security breaches in real time.

6.5.1. Hardware Security Modules (HSMs) for UAVs. HSMs
are specialized cryptographic chips designed to securely store
encryption keys, authenticate ﬁrmware, and prevent unautho-
rized modiﬁcations to UAV software systems. Unlike tradi-
tional software-based encryption, HSMs provide a physically
secure environment that isolates sensitive cryptographic opera-
tions from external threats, reducing the risk of malware injec-
tions, ﬁrmware hijacking, and remote hacking attempts.

A key advantage of HSMs is their ability to prevent unau-
thorized ﬁrmware tampering, ensuring that only veriﬁed
updates and authorized software modiﬁcations are implemen-
ted in UAV systems. This is particularly important for com-
mercial UAV manufacturers and military drone developers, as
compromised ﬁrmware can lead to remote UAV takeovers,
mission disruptions, or intelligence leaks. Research has shown
that integrating HSMs into UAV controllers signiﬁcantly
strengthens system security, preventing attackers from inject-
ing malicious code or exploiting vulnerabilities in UAV com-
mand
protocols.
For
example,
commercial
drone
manufacturers now incorporate HSMs into UAV ﬂight con-
trollers to mitigate remote hacking risks and enhance cyberse-
curity defenses.

Ensuring the security of UAV communication systems is a
growing concern, given the increasing sophistication of cyber
threats targeting both physical and network layers. Wang et al.
[137] provided a comprehensive review of security threats and
countermeasures in UAV communications, highlighting the
vulnerabilities in both single UAV and swarm systems. The
study identiﬁed major attack vectors, such as GPS spooﬁng,
jamming, remote takeover, and data tampering, emphasizing
the need for evolving countermeasures. He et al. [138] demon-
strated how GPS spooﬁng could be used to deceive UAV
swarms, forcing them into unintended collisions. Their
simulation-based approach validated the feasibility of such
attacks, emphasizing the necessity for resilient countermea-
sures in autonomous UAV networks. Similarly, Ferreira et al.
[28] explored low-cost software-deﬁned radio (SDR) platforms
for jamming and GPS spooﬁng to neutralize unauthorized
UAV intrusions. Their research demonstrated the effectiveness
of jamming techniques in taking control of UAVs, raising ethi-
cal concerns regarding potential misuse. Addressing these secu-
rity challenges, Jiang et al. [139] developed an educational
platform integrating UAV cyber-security training with real-
world threat simulations. Their study underscored the impor-
tance of educating future UAV operators on cyber threats and
countermeasures, ensuring that security protocols evolve
alongside emerging threats.

The growing threat of unauthorized UAV operations has
driven research into anti-UAV technologies, including detec-
tion, tracking, and mitigation strategies. Jie [140] proposed an
intelligent anti-UAV command control system that could
accurately detect and neutralize UAV threats in protected air-
space. Unlike traditional methods, this approach integrated
real-time monitoring with adaptive decision-making to formu-
late the most effective counter-UAV response. Wang et al.
[141] expanded on this by reviewing Counter-Unmanned Air-
craft System (C-UAS) technologies, analyzing detection
mechanisms such as radar, acoustic sensors, vision-based
tracking, and passive RF monitoring. Their ﬁndings
highlighted the strengths and limitations of various mitigation
strategies, with radar-based detection showing the highest
effectiveness against high-speed UAVs. Meanwhile, Babu and
Pal [142] examined UAS security enhancements within IoT
environments, focusing on unique vulnerabilities such as signal
tampering, laser-based attacks, and GPS jamming. Their
research emphasized the importance of robust encryption
and access control mechanisms in securing UAV networks.
Similarly, Emani [9] investigated the security vulnerabilities
of the MAVLink protocol, a widely used communication stan-
dard in UAV systems. The study introduced a shared-key
obfuscation algorithm that effectively mitigated MITM attacks,
highlighting the need for enhanced encryption protocols in
UAV communication frameworks.

As UAVs continue to integrate into civilian and military
applications, securing their ﬁrmware, operating systems, and
communication protocols has become a priority. Malik et al.
[143] evaluated various security measures to protect UAV eco-
systems, including ﬁrmware encryption, intrusion detection
and prevention systems (IDPS), and dynamic SSID obfusca-
tion. Their ﬁndings showed signiﬁcant improvements in secu-
rity against common cyber threats, though challenges
remained in mitigating advanced persistent threats. Ficco et al.
[144] conducted penetration testing on UAV communication
systems, identifying multiple vulnerabilities in the MAVLink
protocol. Their research underscored the necessity of regular
security audits and real-time monitoring to prevent cyber
intrusions. Patil and Pournouri [145] examined the security
risks associated with open-source Linux-based operating sys-
tems used in UAVs. Their study found that while open-source
software offers ﬂexibility, it also introduces vulnerabilities that
could be exploited if not properly secured. In response to these
challenges, Chen [2] designed an enhanced MAVLink protocol
(EMP) integrated with multiple security layers to fortify UAV
control and communication systems. Experimental results
demonstrated that EMP signiﬁcantly reduced susceptibility to
cyberattacks while maintaining efﬁcient performance.

UAV sensor security is another critical area of concern, as
compromised sensor data can lead to mission failure or unin-
tended UAV behavior. Wei et al. [146] evaluated online classi-
ﬁcation methods for detecting sensor attacks in UAV systems,
using ML techniques to identify anomalies in gyroscopes, accel-
erometers, and GPS data. Their proposed lightweight classiﬁ-
cation model achieved a detection rate of 89.38%,
outperforming traditional methods. Tlili et al. [20] investigated

36
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 37 ---

### Section: 6.5.2. Self-Healing UAV Systems

UAV battery depletion attacks, where adversaries exploit vul-
nerabilities in UAV charging and power management systems.
Their study proposed mitigation techniques to counter these
threats, emphasizing the importance of securing UAV power
systems. Airlangga and Liu [24] analyzed security risks in cen-
tralized UAV-cloud architectures, identifying 26 attack varia-
tions and their corresponding defense strategies. Their ﬁndings
provided valuable insights into securing UAV data exchange in
cloud-integrated net-works, a growing trend in UAV
operations.

The rapid advancements in UAV cybersecurity research
highlight the ongoing battle between emerging threats and
evolving countermeasures. While studies such as those by
Wang et al. [137] and He et al. [138] have emphasized the
growing sophistication of UAV-targeted cyberattacks, research
by Jiang et al. [139] and Ficco et al. [144] underscores the
importance of cybersecurity education and proactive vulnera-
bility assessments, as presented in Table 14. Future research
must focus on developing lightweight, scalable security frame-
works that balance robust protection with minimal computa-
tional overhead. The integration of AI-driven anomaly
detection, advanced encryption methods, and real-time threat
monitoring will be essential in safeguarding UAV ecosystems.
Additionally, as UAVs become more prevalent in civilian and
military domains, regulatory frameworks must evolve to ensure
that security measures keep pace with technological advance-
ments. Ultimately, a multilayered security approach combining
detection, mitigation, and prevention strategies will be key to
maintaining secure and resilient UAV operations in the face of
ever-evolving cyber threats.

6.5.2. Self-Healing UAV Systems. Beyond hardware-based
defenses, researchers are developing AI-driven self-healing
software frameworks that enable UAVs to autonomously
repair compromised code and restore system integrity follow-
ing a cyberattack. Traditional UAV security measures often
rely on external intervention or manual debugging, which
can delay response times and leave UAVs vulnerable to pro-
longed security breaches. In contrast, self-healing UAV systems
leverage AI-powered anomaly detection to identify cyber
threats, isolate malicious software, and autonomously restore
the UAV to its original secure state without requiring human
input.

One of the primary beneﬁts of self-healing UAV architec-
tures is their ability to counteract real-time cyberattacks, such
as ﬁrmware corruption, adversarial AI manipulations, and sys-
tem exploits. If a UAV detects anomalous activity in its soft-
ware environment, the self-healing framework can
automatically initiate security protocols, such as rolling back
system updates, restoring encrypted backup conﬁgurations, or
executing real-time threat removal algorithms. Recent research
has demonstrated the effectiveness of AI-driven self-repair
mechanisms, where UAVs can identify and neutralize malware
threats while continuing mission-critical operations. These
innovations play a crucial role in ensuring UAV resilience,
minimizing downtime, and reducing cybersecurity risks in
autonomous ﬂight operations.

Ensuring resilience and security in modern computing
environments has become a critical area of research, particu-
larly in the context of self-healing systems, autonomous tech-
nologies, and cyber-physical networks. Adeniyi et al. [57]
investigated proactive self-healing approaches in MEC, empha-
sizing the importance of real-time fault anticipation and miti-
gation. Their study identiﬁed key challenges in resource
allocation and security, demonstrating that self-healing techni-
ques could signiﬁcantly enhance MEC reliability. López-Vilos
et al. [30] extended this concept to wireless sensor networks
(WSNs) under jamming attacks, proposing the Fairness Coop-
eration with Power Allocation (FCPA) strategy. Their results
showed over 50% improvement in data transmission efﬁciency
and a 63% increase in residual energy efﬁciency, highlighting
the beneﬁts of integrating self-healing mechanisms in network
resilience strategies. Similarly, Dias et al. [147] explored self-
healing patterns in IoT environments, identifying modular
frameworks for error detection and recovery. Their ﬁndings
reinforced the importance of adaptable self-repair methodolo-
gies in distributed computing systems.

Autonomous vehicles and UAV swarms face similar chal-
lenges regarding resilience, security, and fault tolerance. Qura-
shi et al. [148] examined the vulnerabilities of self-driving car
architectures, particularly in relation to cyberattacks on sensors
and communication networks. Their study proposed
N-version programming as a resilience mechanism, demon-
strating signiﬁcant improvements in decision-making under
adversarial conditions. Phadke and Medrano [149] extended
this resilience framework to UAV swarms, addressing chal-
lenges in communication, security, and agent coordination.
Their comprehensive analysis showed that enhancing swarm
resilience could improve mission success rates, particularly in
dynamic environments such as SAR operations. Chandran and
Vipin [17] built upon this research by analyzing multi-UAV
networks for disaster monitoring, demonstrating how edge
computing and AI could enhance network efﬁciency and secu-
rity. Their ﬁndings emphasized the importance of real-time
adaptive networking strategies in UAV-based disaster response
scenarios.

The integration of AI in security applications has also
gained attention, particularly in addressing vulnerabilities in
cyber-physical systems. Yaacoub et al. [150] reviewed security
challenges in robotic systems across various domains, from
industrial automation to military applications. Their study
highlighted the need for AI-driven countermeasures to mitigate
emerging cyber threats. Rahman et al. [36] examined AI-
enabled 6G O-RAN security, identifying critical threats to
data-driven networks and proposing advanced countermea-
sures. Their research demonstrated that AI-driven anomaly
detection could signiﬁcantly enhance network security, reinfor-
cing the necessity of integrating AI into cybersecurity frame-
works. Adil et al. [151] explored similar AI applications in
UAV-assisted IoT security, focusing on authentication and
data privacy measures. Their ﬁndings revealed that AI, ML,
DL, and RL algorithms could mitigate security vulnerabilities
in UAV communication networks.

Deep RL (DRL) has also emerged as a promising approach
to improving security and adaptability in UAV systems.

IET Information Security
37

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 38 ---

#### TABLE 14: Hardware security modules (HSMs)-based UAV cybersecurity studies.

Study
Focus area
Security approach
Key beneﬁts
Challenges
Experimental ﬁndings
Future research directions

[137]
UAV communication

security
Threat analysis and

countermeasures
Identiﬁed vulnerabilities in UAV

communication
Evolving nature of cyber threats
Provided a security framework

for UAV networks
Developing AI-driven threat

mitigation

[138]
GPS spooﬁng defense
GPS spooﬁng detection
Demonstrated real-world

feasibility of GPS spooﬁng attacks
Need for real-time

countermeasures
Validated GPS spooﬁng impact

on UAV swarms
Implementing adaptive anti-

spooﬁng mechanisms

[28]
Anti-UAV jamming
Software-deﬁned radio (SDR)

jamming
Demonstrated control over

unauthorized UAVs
Ethical concerns of misuse
Validated effectiveness of SDR

jamming
Developing ethical and

regulatory frameworks

[139]
UAV cybersecurity

education
Training platform with real-

world simulations
Improved awareness of cyber

threats in UAVs
Limited scalability for large UAV

networks
Integrated UAV security

simulations
Expanding cybersecurity

education and training programs

[140]
Anti-UAV defense systems
Intelligent anti-UAV command

control
Improved real-time UAV threat

detection
Computational overhead of

adaptive decision-making
Formulated optimal anti-UAV

strategies
Reducing latency in real-time

#### UAV defense

[141]
Counter-UAS (C-UAS)

technologies
Radar, acoustic, vision, and RF

detection
Identiﬁed most effective

mitigation techniques
Limitations in high- speed UAV

tracking
Radar-based detection was most

effective
Enhancing multi-sensor fusion

for UAV detection

[142]
UAS security in IoT

environments
Encryption and access control

mechanisms
Improved security against GPS

jamming
Increased complexity in IoT

integration
Addressed signal tampering

threats
Developing lightweight

encryption for UAV networks

[9]
MAVLink protocol security
Shared-key obfuscation

algorithm
Prevented man-in-the- middle

attacks
Computational overhead of

cryptographic implementation
Improved UAV communication

security

Optimizing MAVLink security

protocols for real-time

applications

[143]
UAV ﬁrmware security
Intrusion detection and

prevention systems (IDPS)
Enhanced UAV resilience against

malware
Complexity in mitigating

persistent threats
Improved security against

common attacks
Strengthening real-time ﬁrmware

monitoring

[144]
UAV vulnerability testing
Penetration testing on UAV

systems
Identiﬁed multiple vulnerabilities

in MAVLink protocol
Need for continuous security

monitoring
Demonstrated UAV

communication weaknesses
Real-time security auditing for

#### UAV networks

[145]
UAV operating system

security
Security assessment of Linux-

based UAV OS
Highlighted security risks in

open-source UAV frameworks
Patch management challenges in

UAV software
Found that open-source systems

need stricter security controls
Enhancing security for open-

source UAV operating systems

[2]
Securing UAV control
Enhanced MAVLink protocol

(EMP)
Reduced cyberattack

susceptibility
Increased system complexity
EMP signiﬁcantly improved

security

Expanding EMP for broader

#### UAV communication

frameworks

[146]
UAV sensor security
AI-based anomaly detection for

sensor integrity
Improved detection of malicious

sensor data
Computational overhead in real-

time processing
Achieved 89.38% detection rate
Optimizing lightweight AI

models for UAV sensor security

[20]
UAV battery security
UAV battery depletion attack

mitigation
Enhanced protection of UAV

power systems
Energy constraints in secure

power management
Proposed mitigation techniques

for battery attacks

Securing UAV power

management against cyber

threats

[24]
UAV-cloud security
Analysis of centralized UAV-

cloud architecture
Identiﬁed 26 attack variations

and defenses
Scalability challenges in large

UAV networks
Provided insights for securing

#### UAV cloud integration

Strengthening encryption and

authentication in UAV-cloud

systems

38
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 39 ---

### Section: 7. Limitations and Future Research Directions

Sarikaya and Bahtiyar [152] reviewed DRL-based security solu-
tions, highlighting their potential to enhance UAV cybersecur-
ity through adaptive decision-making. Their ﬁndings indicated
that DRL-based security models could effectively counteract
cyber threats, though real-time applicability remained a chal-
lenge. Homann et al. [153] examined trust metrics in artiﬁcial
hormone systems (AHS) within organic computing, proposing
a trust module to detect and counteract security threats. Their
research demonstrated that AHS-enhanced security models
could improve system reliability, particularly in dynamic and
heterogeneous
computing
environments.
Similarly,
Yungaicela-Naula et al. [45] evaluated security automation in
SDN, showcasing how self-healing, self-adaptation, and self-
optimization techniques could enhance threat mitigation efﬁ-
ciency. Their study reported a 95% reduction in breach costs,
emphasizing the transformative impact of security automation
in SDN environments.

Advancements in modular robotics and cooperative IoT
frameworks have further reinforced the need for secure and
adaptable cyber-physical systems. Yaacoub [154] examined
modular robotics’ integration into IoT, identifying security
challenges and proposing lightweight cryptographic solutions.
Their study demonstrated how loss-less compression algo-
rithms, such as Brotli, could optimize communication within
lattice-based modular robots. Ridhawi et al. [155] extended this
research to cooperative UAV-supported IoT services, analyzing
decentralized security solutions such as blockchain-based
authentication. Their ﬁndings highlighted the importance of
secure data-sharing protocols in multi-agent systems, particu-
larly in smart city and disaster response applications.

Ensuring resilience in intelligent autonomous systems
(IAS) has also become a growing concern, particularly in coun-
tering advanced cyber threats. Mani et al. [156] examined the
security of IAS through AI-driven methodologies, addressing
multistage cyberattacks such as ﬁleless malware and adaptive
poisoning attacks. Their study incorporated DL-based applica-
tion proﬁling, perception algorithms using LSTM DNNs, and
intrusion detection mechanisms. Their ﬁndings demonstrated
that AI-driven cyber attribution could enhance attack adapt-
ability, though computational overhead remained a concern.
Similarly, Wang and Aouf [51] investigated adversarial threats
in autonomous driving systems, proposing an explainable deep
adversarial RL framework. Their results demonstrated
improved robustness against dynamic adversarial attacks, rein-
forcing the need for transparent and interpretable AI security
models.

The convergence of AI, edge computing, and self-healing
security frameworks is shaping the future of cyber-physical
systems, ensuring resilience against evolving threats. While
studies by Adeniyi et al. [57], López-Vilos et al. [30], and
Dias et al. [147] have established self-healing methodologies
as critical components of modern computing, research by Qur-
ashi et al. [148], Phadke and Medrano [149], and Chandran
and Vipin [17] have underscored the importance of resilience
in autonomous systems. The integration of AI-driven security
frame-works, as explored by Yaacoub et al. [150], Rahman et al.
[36], and Adil et al. [151], further highlights the need for intel-
ligent, adaptive defense mechanisms. Future research should

focus on reﬁning these methodologies to enhance scalability,
minimize computational overhead, and ensure real-time appli-
cability in increasingly complex cyber-physical ecosystems.

In a nutshell, ensuring the security of AI-driven UAVs
requires a multilayered defense approach that integrates
advanced AI-based IDS for real-time cyber threat detection,
blockchain for secure and tamper-proof data transmission,
and quantum cryptography with MFA to prevent hacking
attempts. Additionally, adversarial training and XAI enhance
AI trustworthiness, mitigating the risks associated with adver-
sarial attacks and opaque decision-making models. To further
fortify UAV systems, HSMs protect against ﬁrmware tamper-
ing, while self-healing UAV frameworks enable autonomous
recovery from cyber intrusions, ensuring long-term operational
resilience in high-risk environments, as presented in Table 15.
These combined security measures are essential for protecting
UAVs from evolving cyber threats and ensuring mission reli-
ability across military, commercial, and civilian applications.

#### 7. Limitations and Future Research Directions

As AI-driven UAVs continue to evolve, so do the security
threats and vulnerabilities associated with their deployment.
The increasing sophistication of cyber threats, adversarial AI
attacks, and communication vulnerabilities necessitates the
development of next-generation security frameworks that can
dynamically adapt to emerging threats. Traditional security
models rely on predeﬁned attack signatures and static defenses,
making them ineffective against evolving cyber threats. Future
research must focus on developing advanced AI security mod-
els, integrating 6G-powered security solutions, and enhancing
UAV swarm cybersecurity to ensure safe, resilient, and auton-
omous UAV operations.

7.1. Limitations of the Present Study. Although this paper
offers a comprehensive taxonomy and synthesis of AI-enabled
UAV cybersecurity solutions, it is limited by the scope of exist-
ing literature, which is rapidly evolving. The review primarily
focuses on peer-reviewed studies published up to early 2025,
excluding some proprietary or classiﬁed government research
that may offer additional insights. Furthermore, while several
frameworks and techniques are discussed, their practical feasi-
bility, economic costs, and policy integration have not been
fully assessed.

Additionally, this review does not quantitatively compare
the performance of proposed defense mechanisms due to the
heterogeneity of evaluation metrics, simulation tools, and data-
sets across existing studies. Future meta-analyses that unify
evaluation methodologies would allow for better benchmark-
ing of UAV security frameworks. This review also acknowl-
edges limitations including the exclusion of non-peer-reviewed
and non-English studies, potential keyword dependency in the
literature search, inherent subjectivity in study selection, and
the qualitative nature of the data synthesis, suggesting future
research mitigate these by incorporating a broader range of
sources, expanding keywords and using semantic search,
employing multiple reviewers and inter-rater reliability mea-
sures, and considering quantitative meta-analysis to enhance
the robustness and generalizability of ﬁndings.

IET Information Security
39

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 40 ---

#### TABLE 15: Comparison of self-healing UAV security solutions.

Study
Focus area
Security methodology
Resilience mechanism
Computational

overhead
Key ﬁndings
Limitations and future directions

[57]
Self-healing in Mobile Edge

Computing
Proactive fault anticipation
AI-driven threat mitigation
High
Improved MEC reliability and

security
Needs further optimization for real-

time UAV applications

[30]
Resilience in Wireless Sensor

Networks
Clustering-based self- healing
Jamming attack mitigation
Moderate
50% improvement in data
transmission, 63% energy efﬁciency
Scalability limitations in dense UAV

networks

[147]
Self-healing in IoT environments
Modular error detection
AI-driven adaptive recovery
High
Demonstrated importance of

modular frameworks in distributed

systems

High computational cost for large-

scale IoT deployments

[148]
Resilience in self-driving car

architectures
N-version programming
Sensor and communication

security
Moderate
Improved decision-making under

cyberattacks
Requires further testing in UAV and

military applications

[149]
Resilience in UAV swarms
Adaptive AI-driven security
UAV swarm communication

security
High
Improved mission success rates in

SAR operations
Computational complexity in real-

time UAV operations

[17]
Multi-UAV networks for disaster

monitoring
AI + edge computing
Autonomous Mission

resilience
High
Enhanced disaster response efﬁciency

and security
Requires optimization for large- scale

#### UAV swarm networks

[150]
AI-driven security in robotics
AI-based intrusion detection
Cyber-physical system

resilience
Moderate
Identiﬁed AI-driven

countermeasures for security threats
Needs further validation in UAV

deployments

[36]
AI-enabled 6G O-RAN security
AI-driven anomaly detection
Cyber threat mitigation
High
Enhanced network security against

data-driven attacks
Needs optimization for real-time AI

security

[151]
UAV-assisted IoT security
AI, ML, DL, RL for

authentication
Data privacy and security
High
Improved UAV network resilience

against cyberintrusions
Computational overhead in large-

scale UAV networks

[152]
DRL in UAV security
Adaptive learning-based IDS
AI-driven threat mitigation
High
Improved UAV cybersecurity

through DRL models
Limited real-time applicability

[153]
Artiﬁcial hormone systems for

security
AI-based trust module
Autonomous security

decision-making
Moderate
Improved system reliability in

dynamic environments
Needs further research on scalability

in UAV networks

[45]
Security automation in SDN
Self-healing, self-adaptation
AI-driven automated threat

mitigation
High
95% reduction in breach costs
Needs efﬁciency improvements for

real-time security applications

[154]
Modular robotics and IoT security
Lossless cryptography (Brotli)
Secure UAV-IoT

communication
High
Optimized communication efﬁciency

in modular UAV networks
Requires further work on

cryptographic resilience

[155]
Cooperative UAV-IoT services
Blockchain-based

authentication
Secure multi- agent data

sharing
High
Improved decentralized

authentication for UAVs
Limited scalability in ultra-dense

#### UAV networks

[156]
AI-driven security for IAS
Multi-stage cyberattack

prevention
AI-based cyber attribution
High
Improved resilience against ﬁle-less

malware
High computational overhead re-

mains a concern

[51]
Adversarial threats in autonomous

driving
Deep adversarial reinforcement

learning
AI model robustness
High
Enhanced resilience against

adversarial attacks
Needs optimization for real-time

deployments

40
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 41 ---

### Section: 7.2. Discussion of Alternative Explanations for Observed Findings

While the ﬁndings offer broad applicability across UAV
sectors due to the universality of identiﬁed threats and the
potential of proposed countermeasures, their direct application
is constrained by variations in UAV types, operational con-
texts, and technological maturity, necessitating further research
to validate and adapt these solutions for diverse scenarios.

7.2. Discussion of Alternative Explanations for Observed
Findings. While this review focuses on the growing intersection
of AI and cybersecurity within the realm of UAVs, the observed
research trends are likely inﬂuenced by factors extending
beyond this central theme. Several alternative explanations
could contribute to the current landscape of literature.

Firstly, the independent and rapid advancements in both
AI and cybersecurity are signiﬁcant drivers of research. The
increasing capabilities of AI across diverse applications natu-
rally lead to its exploration in security contexts, while the esca-
lating sophistication of cyber threats necessitates the
investigation of advanced defenses, irrespective of their speciﬁc
application to UAVs. Thus, the burgeoning research at this
intersection may partly reﬂect these broader, parallel
advancements.

Secondly, funding priorities and strategic initiatives from
governmental bodies, industries, and academic institutions
play a crucial role in shaping research directions. Targeted
funding towards AI security or UAV technologies could lead
to a concentration of research efforts in speciﬁc areas, inﬂuenc-
ing the prevalence of certain themes observed in this review.
Understanding these funding landscapes could provide valu-
able context for interpreting the current research focus.

Thirdly, the inherent bias in academic publishing towards
positive and novel ﬁndings might lead to an overrepresentation
of studies demonstrating the effectiveness of AI-driven security
solutions or highlighting signiﬁcant vulnerabilities. Research
with null or negative results, which could offer crucial insights
into the limitations of certain approaches, might be less likely to
be published, potentially skewing the overall understanding
derived from this review.

Finally, speciﬁc technological breakthroughs, such as
advancements in onboard processing power for UAVs or
enhanced communication capabilities, could indirectly inﬂu-
ence the research focus. These advancements might enable the
practical implementation and evaluation of more complex AI-
based security measures on UAV platforms, leading to
increased research in these areas.

By considering these alternative explanations, this review
aims to provide a more comprehensive understanding of the
research dynamics in AI-driven UAV cybersecurity. While the
primary focus on AI’s dual role in enhancing and challenging
UAV security is well-supported, acknowledging these broader
contextual factors offers a richer interpretation of the current
state of knowledge and can inform future research by highlight-
ing potential biases or underexplored avenues.

7.3. Next-Generation AI Security for UAVs. AI plays a pivotal
role in UAV security, enabling autonomous threat detection,
real-time decision-making, and anomaly identiﬁcation. How-
ever, existing AI-based UAV security models suffer from lim-
ited adaptability to emerging cyber threats, as they rely on ﬁxed

training datasets that do not account for previously unseen
attack patterns. As cyber adversaries develop new attack tech-
niques, UAV AI models must be capable of self-adapting, con-
tinuously learning, and proactively responding to zero-day
exploits, AI adversarial manipulations, and real-time cyberse-
curity challenges.

7.3.1. Self-Adaptive AI Security Models. Traditional AI-driven
UAV security models depend on static algorithms that can
recognize only predeﬁned cyber threats, making them vulner-
able to novel attacks. Future AI security solutions must focus
on self-adaptive AI models that can dynamically learn, evolve,
and respond to cyber threats in real time.

Self-adaptive AI security models will leverage RL-based AI,
where UAVs utilize real-time feedback loops to learn from
cyberattack patterns and security breaches, improving their
threat detection accuracy over time [147, 148]. By continuously
analyzing new security vulnerabilities, these UAVs will be able
to neutralize threats before they cause operational failures.
Another emerging approach is self-supervised learning, where
UAV AI models will be trained using raw ﬂight data and real-
time mission insights rather than prelabeled datasets. This
allows UAVs to detect security anomalies independently, with-
out requiring constant human intervention.

A key research area in next-generation AI-driven UAV
security is the development of autonomous cybersecurity mod-
els that identify and neutralize previously unknown malware
strains before they infect UAV systems. These models will
integrate adaptive DL techniques, real-time anomaly detection,
and AI-driven response mechanisms to enhance UAV resil-
ience against next-generation cyber threats.

7.3.2. AI-Powered Threat Intelligence Systems. Current UAV
cybersecurity frameworks primarily rely on manual threat
monitoring, making it difﬁcult to detect and mitigate cyberat-
tacks in real time [137, 151]. This approach creates signiﬁcant
delays in identifying vulnerabilities and responding to security
breaches, leaving UAVs exposed to potential hacking attempts,
AI adversarial manipulations, and communication disruptions.
Future UAV security research must prioritize the integration of
AI-powered threat intelligence systems, capable of predicting,
identifying, and mitigating cyber threats before they
materialize.

AI-powered threat intelligence will enable UAVs to auton-
omously analyze global cyberattack trends, identify new secu-
rity vulnerabilities, and implement real-time security patches
without requiring direct human intervention [20]. These sys-
tems will be capable of:

1. Identifying emerging security vulnerabilities before they
can be exploited.
2. Automatically patching software weaknesses in UAV
operating systems.
3. Detecting potential cyberattacks based on historical
UAV cyberattack datasets and predictive analytics.

By integrating predictive threat intelligence models, UAVs
will gain the ability to anticipate cyber threats before they occur,
signiﬁcantly improving response times, security resilience, and

IET Information Security
41

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 42 ---

### Section: 7.4. Integration of 6G and Edge Computing

operational efﬁciency. Research in this area is focusing on AI
models trained on UAV cyberattack datasets, enabling them to
predict new hacking techniques and deploy countermeasures
proactively.

7.4. Integration of 6G and Edge Computing. As autonomous
UAV operations become more widespread and complex, the
need for secure, real-time communication and low-latency AI
processing is paramount to ensure mission success and opera-
tional resilience. Traditional UAV networks, which often
depend on existing wireless technologies such as 4G or 5G,
face challenges including higher latency, limited bandwidth,
and increased susceptibility to cyber threats. These limitations
can compromise timely threat detection and response, particu-
larly in dynamic or hostile environments where delays may
lead to mission failure or security breaches.

The advent of 6G networks combined with Edge Comput-
ing offers a transformative solution to these challenges by
enabling ultra-fast, secure data transmission and localized AI
processing directly on or near UAV plat-forms. Edge comput-
ing facilitates on-device or near-device threat detection, signif-
icantly reducing the latency associated with sending data to
distant cloud servers for analysis. This capability is critical for
time-sensitive security applications, allowing UAVs to respond
instantly to emerging threats with minimal delay, thus enhanc-
ing operational reliability and safety.

However, edge-based threat detection comes with trade-
offs. While it excels in providing real-time responses and
reducing dependency on network connectivity, edge devices
typically have limited computational resources compared to
cloud infrastructures, which may restrict the complexity of
threat analysis algorithms. In contrast, cloud-based threat
detection leverages vast processing power and large-scale
data aggregation to perform more comprehensive and sophis-
ticated threat intelligence. Nevertheless, cloud reliance intro-
duces potential latency and reliability issues due to variable
network conditions and the risk of communication interrup-
tions, which can delay critical security actions.

Balancing these trade-offs is essential in designing robust
UAV cybersecurity architectures. Hybrid approaches that inte-
grate edge computing for immediate, low-latency threat detec-
tion with cloud-based systems for deeper, more holistic analysis
present a promising pathway. The seamless integration of 6G
connectivity with edge and cloud resources will redeﬁne UAV
security frameworks, ensuring autonomous UAV ﬂeets can
operate securely, efﬁciently, and resiliently even in highly
adversarial and bandwidth-constrained environments.

7.4.1. 6G-Enabled Secure UAV Networks. Ensuring secure and
reliable communication remains one of the foremost challenges
in UAV cybersecurity, particularly as UAVs increasingly oper-
ate in remote, contested, or hostile environments. Existing 4G
and 5G networks often suffer from higher latency and band-
width constraints, which can leave UAVs vulnerable to cyber-
attacks such as signal hijacking, GPS spooﬁng, and jamming.
These limitations impair the UAVs ability to authenticate com-
mand signals, detect threats in real time, and securely relay
critical data to ground control stations, thereby compromising
mission integrity and safety [88].

The integration of 6G technology into UAV networks pro-
mises to overcome these challenges by enabling ultra-fast,
ultra-reliable, and low-latency communication channels.
Expected to reach peak deployment around the 2030s following
ongoing standardization efforts, 6G aims to deliver sub-
millisecond latency and near-perfect connectivity, which are
essential for real-time threat detection and immediate response
in UAV operations. A signiﬁcant technical advancement
within 6G is the incorporation of quantum cryptography-based
encryption, which offers unprecedented security by safeguard-
ing UAV-to-ground communications against interception and
decryption attempts. This quantum-resistant encryption will
ensure data conﬁdentiality and integrity, rendering conven-
tional cyberattack methods ineffective.

Additionally, 6G networks will enable the seamless integra-
tion of AI-enhanced security protocols that empower UAVs to
autonomously detect and mitigate cyber threats with minimal
delay. Recent research, such as the work by Tsegaye [83], has
demonstrated prototype AI frameworks that leverage 6Gs high
data throughput and low latency to perform real-time anomaly
detection, identifying threats like jamming, unauthorized
access, and malicious command injections instantaneously.
Experimental pilot projects are already underway, exploring
6G-enabled UAV architectures that combine quantum-safe
encryption with AI-driven cybersecurity measures, signaling
signiﬁcant progress toward practical implementation.

In summary, the transition to 6G-enabled UAV networks
represents a paradigm shift in UAV cybersecurity, offering
end-to-end encryption, ultra-fast data transmission, and intel-
ligent autonomous threat detection. While full-scale adoption
depends on the maturation of 6G standards and infrastructure,
current research and early-stage trials indicate a clear trajectory
toward deployment within the next decade, setting the founda-
tion for resilient and secure UAV operations in increasingly
complex environments.

7.4.2. Edge AI for Secure UAV Data Processing. Another sig-
niﬁcant challenge in UAV cybersecurity is the reliance on
cloud-based AI models for data processing, threat detection,
and decision-making. Traditional UAV systems transmit large
volumes of sensor data, ﬂight information, and AI-driven ana-
lytics to remote cloud servers for processing and analysis. How-
ever, this centralized computing model introduces security
vulnerabilities, including data interception risks, latency issues,
and potential disruptions from cyberattacks targeting cloud
networks [57, 123, 157].

To mitigate these challenges, researchers are exploring
Edge AI computing, which enables onboard UAV data proces-
sing without relying on external cloud infrastructure. By inte-
grating AI-driven security algorithms directly into UAV
hardware, Edge AI allows UAVs to detect cyber threats locally,
process mission-critical data in real time, and minimize reli-
ance on remote servers. This approach signiﬁcantly reduces the
risk of cyber intrusions, as UAV data remains within the local
network and is not exposed to external cybersecurity
vulnerabilities.

One of the key beneﬁts of Edge AI for UAV security is on-
device AI learning, where UAVs can continuously adapt to new

42
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 43 ---

### Section: 7.5. AI-Empowered UAV Swarm Security

cyber threats, analyze security anomalies, and optimize AI
threat detection models autonomously. Unlike traditional
cloud-based AI models, which require constant internet con-
nectivity and centralized data storage, Edge AI allows UAVs to
remain operational even in contested environments where net-
work access is limited or compromised.

A recent research focus has been the development of
onboard AI-driven IDS that enable UAVs to autonomously
detect cyber threats without requiring an external cloud-based
security infrastructure. These self-contained AI security sys-
tems analyze network trafﬁc, sensor inputs, and command
authenticity to identify potential cyberattacks in real time,
ensuring rapid response and threat mitigation without delays
caused by cloud server dependencies.

7.5. AI-Empowered UAV Swarm Security. UAV swarms,
where multiple drones operate autonomously in a coordinated
manner, introduce new security challenges that differ signiﬁ-
cantly from single-drone operations. These challenges arise due
to inter-drone communication dependencies, decentralized
AI-based threat detection, and the need for secure mission
execution. Ensuring secure communication within UAV
swarms is critical, as adversaries can exploit vulnerabilities to
intercept signals, manipulate swarm behavior, or introduce
unauthorized drones into the network. Additionally, decentra-
lized security frameworks are necessary to prevent single points
of failure, ensuring that UAV swarms remain operational even
if individual units are compromised. Blockchain technology
has also emerged as a key enabler of UAV swarm security,
providing tamper-proof mission execution and encrypted
communication records to prevent unauthorized drone inﬁl-
tration or command injection attacks [98, 149].

7.5.1. Decentralized AI for Secure UAV Swarm Operations.
One of the primary security challenges in UAV swarm net-
works is their reliance on centralized control systems, which
makes them vulnerable to hacking, signal jamming, and com-
mand injection attacks. Cyber adversaries can disrupt swarm
coordination by targeting the centralized command node, lead-
ing to mission failure, loss of UAV control, or reprogramming
of ﬂight objectives. To address these vulnerabilities, decentra-
lized AI-driven security frameworks are being developed to
enable independent UAV operation without reliance on a sin-
gle control center [138].

Future AI-driven UAV swarms will leverage swarm intelli-
gence, where individual UAVs will collaborate dynamically,
enabling real-time threat detection, attack response, and mis-
sion adaptation without requiring direct human intervention.
Instead of relying on ﬁxed pre-programed security models,
these UAVs will employ adaptive AI algorithms that allow
them to identify, communicate, and collectively neutralize
cyber threats. In the event of a cyberattack, AI-driven UAV
swarms will be capable of autonomously reconﬁguring ﬂight
paths, isolating compromised drones, and reinforcing security
protocols to maintain operational stability.

A notable research area in this ﬁeld is the development of
AI-powered UAV swarm threat detection models, which
enable drones to communicate securely and autonomously in
high-risk environments. These models will integrate RL,

federated AI training, and real-time anomaly detection to
strengthen UAV swarm resilience against evolving cyber
threats. By adopting decentralized AI-driven security frame-
works, UAV swarms will be able to operate effectively in con-
tested airspaces, ensuring that no single point of failure
compromises the entire swarm operation.

7.5.2.
Blockchain-Based
UAV
Swarm
Communication
Security. Another major security concern in UAV swarm
operations is unauthorized drone inﬁltration, where adversar-
ies attempt to spoof communication signals to introduce mali-
cious drones into the swarm network. Attackers can
manipulate inter-drone communications, causing system fail-
ures, mission deviations, or intelligence leaks. Traditional secu-
rity mechanisms, such as encrypted command channels, are
insufﬁcient to fully secure UAV swarm networks, as they can
still be exploited through signal interception or identity spoof-
ing techniques [100, 138].

To address this challenge, researchers are developing
blockchain-based UAV security solutions that decentralize
swarm communication and ensure cryptographic authentica-
tion of UAV-to-UAV transmissions. Blockchain technology
offers a tamper-proof, immutable record of UAV communica-
tion logs, ensuring that all drone interactions are securely
stored, veriﬁed, and resistant to unauthorized modiﬁcations.
By implementing blockchain-powered authentication, UAV
swarms can verify the legitimacy of incoming communication
signals, preventing adversaries from spooﬁng commands or
introducing unauthorized drones into the network.

Additionally, blockchain-based UAV swarm security fra-
meworks will ensure that each UAV-to-UAV communication
exchange is cryptographically signed and validated, preventing
MITM attacks that could otherwise allow hackers to intercept
and alter drone communication protocols. A promising
research area in this domain focuses on enhancing UAV swarm
resilience through blockchain-enhanced authentication mod-
els, where every drone in the swarm network must verify its
identity against a decentralized ledger before executing
commands.

By integrating blockchain security frameworks with decen-
tralized AI-driven UAV swarm intelligence, re-searchers aim to
develop autonomous, self-secure UAV networks that can oper-
ate reliably in contested and high-risk environments. Future
studies should continue exploring hybrid AI-blockchain secu-
rity architectures, optimizing their scalability, efﬁciency, and
integration into real-world UAV swarm applications to ensure
highly resilient, self-defending autonomous drone networks.

In conclusion, the future of AI-driven UAV security will be
shaped by self-learning AI models, 6G-enhanced encrypted
communication, and decentralized UAV swarm protection fra-
meworks, ensuring that UAVs remain secure, autonomous,
and resilient against evolving cyber threats, as presented in
Table 16. Self-adaptive AI models will allow UAVs to learn
from cyberattacks and continuously enhance their security
mechanisms, while 6G-powered networks will provide ultra-
fast, quantum-secured communication, preventing signal
hijacking and data interception. The integration of Edge AI
computing will enable UAVs to process security threats locally,

IET Information Security
43

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 44 ---

### Section: 7.6. Ethical Considerations

reducing reliance on cloud networks and minimizing latency
vulnerabilities. In swarm operations, AI-powered UAV net-
works will use decentralized intelligence to detect and neutral-
ize cyber intrusions autonomously, ensuring collective threat
mitigation. Additionally, blockchain-based authentication sys-
tems will prevent unauthorized drone takeovers, ensuring that
only veriﬁed UAVs can participate in swarm missions. By
advancing research in these areas, UAVs will achieve next-
generation cybersecurity resilience, enabling secure, efﬁcient,
and autonomous operations in military, commercial, and
high-risk environments.

7.6. Ethical Considerations. The expanding deployment of AI-
driven UAVs across sectors like surveillance, law enforcement,
and delivery services brings forth critical ethical considerations
that demand attention to ensure responsible innovation and
mitigate potential harm. Future research must proactively
address these evolving challenges.

• Privacy Concerns: UAVs’ capacity for high-resolution
surveillance raises signiﬁcant privacy issues. Mass sur-
veillance capabilities, tracking without consent, and sen-
sitive data collection necessitate robust regulations and
privacy-preserving technologies. Future research should
focus on developing and integrating privacy-enhancing
AI algorithms that can selectively process and anon-
ymize data, minimizing the risk of privacy violations.
This includes exploring techniques like FL for collabora-
tive model training without direct data sharing and dif-
ferential privacy to add noise to data outputs.
• Autonomous Decision-Making: The autonomy of AI-
driven UAVs, especially in critical applications, brings
concerns about accountability and potential errors.
Algorithmic biases, incorrect object recognition, and
the lack of human oversight can lead to severe conse-
quences. Future research needs to prioritize the

#### TABLE 16: Future research directions in AI-driven cybersecurity for UAVs.

Research area
Key focus
Challenges and future considerations

Self-Adaptive AI Security
Models

• AI-driven real-time learning from cyber
threats
• RL for adaptive threat detection
• Self-supervised learning for
autonomous anomaly detection

• High computational overhead for
continuous learning
• Difﬁculty in identifying zero-day threats
in real-time
• Need for scalable and efﬁcient AI-
driven security models

AI-Powered Threat Intelligence
Systems

• Predictive analytics for emerging cyber
threats
• Automated software patching and UAV
OS security updates
• AI-driven UAV cybersecurity datasets
for proactive defense

• Requires large-scale real-time data
analysis
• Potential adversarial attacks on AI
training datasets
• Difﬁculty in ensuring low-latency threat
mitigation

6G-Enabled Secure UAV
Networks

• Ultra-low-latency communication for
UAV security
• Quantum cryptography-based UAV
data encryption
• AI-enhanced real-time anomaly
detection in UAV networks

• High infrastructure costs for 6G
deployment
• Security concerns in quantum
cryptographic key management
• Compatibility with existing UAV
network architectures

Edge AI for Secure UAV
Data Processing

• AI-driven on-device cybersecurity
analysis
• Reduction of cloud dependency for
security processing
• AI-based IDS for UAVs

• Limited computational power of
onboard UAV hardware
• High energy consumption for real-time
AI analysis
• Secure ﬁrmware updates and AI model
retraining challenges

Decentralized AI for Se-
cure UAV Swarm Operations

• AI-driven swarm intelligence for
autonomous security
• Federated learning and real-time inter-
drone threat sharing
• Adaptive mission planning for
UAV swarm resilience

• Ensuring secure AI model updates
across UAV networks
• Complexity in implementing real-time
inter-drone coordination
• Resistance against adversarial AI attacks
on swarm behavior

Blockchain-Based UAV
Swarm Communication Security

• Decentralized UAV authentication
using blockchain
• Tamper-proof, immutable UAV
communication records
• Cryptographic authentication of UAV-
to-UAV transmissions

• High storage requirements for
blockchain-based UAV data
• Network latency issues in decentralized
authentication
• Scalability concerns in high- volume
UAV operations

44
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 45 ---

### Section: 8. Conclusion

development of XAI models for UAVs, enabling trans-
parency in decision-making processes and facilitating
human intervention when necessary. Furthermore,
investigating methods for robust veriﬁcation and valida-
tion of AI algorithms used in UAVs is crucial to ensure
safety and reliability.
• Data Security and Misuse: The vast data collected by
UAVs presents risks of breaches and misuse. Strong
data protection and secure communication are essential.
Future research should explore advanced cryptographic
techniques tailored for UAV communication con-
straints, such as lightweight cryptography and homo-
morphic encryption, which allows computations on
encrypted data. Additionally, research into secure data
storage and access control mechanisms within UAV net-
works is vital.
• Dual-Use Dilemma: The potential for AI and UAVs to
be used for both beneﬁcial and harmful purposes re-
quires careful consideration. Future research must con-
tribute to developing ethical guidelines and regulatory
frameworks that govern the development and deploy-
ment of UAVs, preventing their weaponization or mis-
use. This includes international collaborations to
establish standards and protocols that promote respon-
sible innovation and address the dual-use challenge.

In conclusion, addressing the ethical considerations sur-
rounding AI-driven UAVs is not only a necessity for responsi-
ble technology adoption but also a crucial area for future
research. Interdisciplinary efforts involving technologists, ethi-
cists, policymakers, and the public are essential to navigate
these complex challenges and ensure that AI-driven UAVs
are used in ways that beneﬁt society while upholding ethical
principles.

#### 8. Conclusion

The increasing integration of AI into UAVs has signiﬁcantly
enhanced their operational capabilities across military, com-
mercial, and civilian domains. However, it has simultaneously
introduced critical cybersecurity challenges that threaten mis-
sion reliability, data conﬁdentiality, and operational integrity.
This review comprehensively analyzed the evolving threat
landscape faced by AI-driven UAVs, highlighting key vulner-
abilities such as cyberattacks, adversarial AI manipulations,
GPS spooﬁng, and communication disruptions.

Theoretically, this research advances the understanding of
UAV cybersecurity by identifying gaps in existing AI security
models, emphasizing the need for self-adaptive AI defenses,
decentralized blockchain-based authentication, and quantum-
resistant encryption techniques. It provides a structured taxon-
omy of threats and counter-measures that can serve as a
foundation for future academic research in AI security, UAV
swarm resilience, and Edge AI architectures. While the review
aimed to provide a holistic view, some ﬁndings revealed dis-
crepancies compared to initial expectations, primarily due to
the rapid evolution of both UAV technology and cyber threats,
leading to a dynamic and shifting research landscape. As shown

in Figure 3, this trend illustrates the rising number of publica-
tions in high-impact journals and conferences, highlighting a
growing research focus on AI-driven cybersecurity solutions
for UAVs.

Practically, the ﬁndings of this study have signiﬁcant impli-
cations for real-world UAV operations. They highlight the
urgency of deploying multilayered, real-time, and autonomous
cybersecurity frameworks to ensure safe and resilient UAV
missions in high-risk environments. The adoption of 6G-
enabled secure networks, on-board AI threat detection systems,
and decentralized swarm security models are essential for
maintaining the operational reliability of UAVs in critical sec-
tors such as defense, disaster response, and logistics. These
ﬁndings emphasize the need for agile and adaptive security
strategies, given the pace of technological change. As depicted
in Figure 4, the distribution of articles across journals and
conferences shows that the majority of the research is published
in journals (81%) compared to conferences (19%), indicating a
preference for in-depth studies over preliminary ﬁndings. A
comparative analysis of existing studies is provided in Table 2,
highlighting the unique contributions of this review in integrat-
ing AI, cryptography, blockchain, and swarm security frame-
works. Furthermore, Table 7 compares different FL-based
UAV security studies, outlining their methodologies, security
mechanisms, and limitations.

By integrating cutting-edge AI security advancements with
practical defense strategies, this work not only bridges the gap
between academic research and industry needs but also paves the
way for the development of next-generation autonomous UAV
systems that are both secure and trustworthy. Future research
should continue focusing on scalable, lightweight, and XAI solu-
tions, ensuring that UAV systems remain resilient against
increasingly sophisticated cyber threats while upholding ethical
and regulatory standards. As Figure 5 shows, IEEE and Elsevier
are the leading publishers, accounting for 34% and 17% of the
publications, respectively, suggesting their signiﬁcant inﬂuence
in this domain. Moreover, Figure 6 provides a detailed break-
down of the research categories, with AI-based intrusion detec-
tion and prevention being the most prominent area, followed by
software and hardware-based countermeasures.

Data Availability Statement

Data sharing not applicable to this article as no datasets were
generated or analyzed during the current study.

Conﬂicts of Interest

The author declares no conﬂicts of interest.

Funding

No funding was received for this manuscript.

References

[1] A. Oracevic and A. Salman, “Unmanned Aerial Vehicles in

Peril: Investigating and Addressing Cyber Threats to UAVs,”
in 2024 International Conference on Smart Applications,

IET Information Security
45

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 46 ---

Communications and Networking (SmartNets), (IEEE, 2024):
1–7.
[2] H. H. Chen, “Developing a Custom Communication Protocol

for UAVs: Ground Control Station and Architecture Design,”
Internet of Things 27 (2024): 101319.
[3] R. U. Mhapsekar, M. I. Umrani, M. Faizan, O. Ali, and

L. Abraham, “Building Trust in AI-Driven Decision Making for
Cyber-Physical systems (CPS): A Comprehensive Review,” in
2024
IEEE
29th
International
Conference
on
Emerging
Technologies and Factory Automation (ETFA), (IEEE, 2024): 1–8.
[4] K. Cools and C. Maathuis, “Trust or Bust: Ensuring

Trustworthiness
in
Autonomous
Weapon
Systems,”
in
MILCOM 2024-2024 IEEE Military Communications Confer-
ence (MILCOM), (IEEE, 2024): 182–189.
[5] G. Kumar and A. Altalbe, “Artiﬁcial Intelligence (AI)

Advancements for Transportation Security: in-Depth Insights
Into Electric and Aerial Vehicle Systems,” Environment,
Development and Sustainability (2024): 1–51.
[6] A. Masadeh, M. Alhafnawi, H. A. B. Salameh, A. Musa, and

Y. Jararweh, “Reinforcement Learning-Based Security/Safety
UAV System for Intrusion Detection Under Dynamic and
Uncertain Target Movement,” IEEE Transactions on Engineer-
ing Management 71 (2022): 12498–12508.
[7] M. Golam, M. M. Alam, D. S. Kim, and J. M. Lee, “BLM-

Chain: AI-Driven Blockchain for UAV Threat Resistance in
IOBT,” in 2024 15th International Conference on Information
and Communication Technology Convergence (ICTC), (IEEE,
2024): 1609–1613.
[8] E. Bayhan, Z. Ozkan, M. Namdar, and A. Basgumus, “Deep

Learning
Based
Object
Detection
and
Recognition
of
Unmanned Aerial Vehicles,” in 2021 3rd International Congress
on Human-Computer Interaction, Optimization and Robotic
Applications (HORA), (IEEE, 2021): 1–5.
[9] R. Emani, “Cybersecurity Analysis and Defense of the Mavlink

Uas Protocol,” (2024).
[10] S. Taheri, A. Khormali, M. Salem, and J. S. Yuan, “Developing a

Robust Defensive System Against Adversarial Examples Using
Generative Adversarial Networks,” Big Data and Cognitive
Computing 4, no. 2 (2020): 11.
[11] N. Kumar and A. Chaudhary, “Surveying Cybersecurity

Vulnerabilities and Countermeasures for Enhancing UAV
Security,” Computer Networks 252 (2024): 110695.
[12] H. Xi, L. Ru, J. Tian, et al., “URAdv: A Novel Framework for

Generating Ultra-Robust Adversarial Patches Against UAV
Object Detection,” Mathematics 13, no. 4 (2025): 591.
[13] J. Tian, C. Shen, B. Wang, et al., “LESSON: Multi-Label

Adversarial False Data Injection Attack for Deep Learning
Locational Detection,” IEEE Transactions on Dependable and
Secure Computing 21, no. 5 (2024): 4418–4432.
[14] Z. Zhao, B. Wang, X. Yao, J. Tian, R. Dong, and P. Zhu,

“Dynamic Quasi-Hyperbolic Momentum Iterative Attack With
Small Perturbation for 4D-Flight Trajectory Prediction,” IEEE
Internet of Things Journal 12, no. 12 (2025): 22533–22553.
[15] M. J. Page, J. E. McKenzie, P. M. Bossuyt, et al., “The Prisma

2020
Statement:
An
Updated
Guideline
for
Reporting
Systematic Reviews,” BMJ 372 (2021).
[16] V. Balasubramanian, M. Aloqaily, M. Guizani, and B. Ouni,

“Security Challenges and Solutions for Autonomous Vehicles
and Drones in the AI Age,” IEEE Internet of Things Magazine 8,
no. 2 (2025): 129–136.
[17] I. Chandran and K. Vipin, “Multi-Uav Networks for Disaster

Monitoring: Challenges and Opportunities From a Network
Perspective,” Drone Systems and Applications 12 (2024): 1–28.

[18] Z. Zhou, G. Liu, and Y. Tang, “Multiagent Reinforcement

Learning: Methods, Trustworthiness, Applications in Intelli-
gent Vehicles, and Challenges,” IEEE Transactions on Intelligent
Vehicles 9, no. 12 (2024): 8190–8211.
[19] A. T. Olutimehin, A. J. Ajayi, O. C. Metibemu, A. Y. Balogun,

T. O. Oladoyinbo, and O. O. Olaniyi, “Adversarial Threats to
Ai-Driven Systems: Exploring the Attack Surface of Machine
Learning Models and Countermeasures,” (2025).
[20] F. Tlili, L. C. Fourati, S. Ayed, and B. Ouni, “Investigation on

Vulnerabilities,
Threats
and
Attacks
Prohibiting
UAVs
Charging and Depleting UAVs Batteries: Assessments &
Countermeasures,” Ad Hoc Networks 129 (2022): 102805.
[21] R. Aissaoui, J. C. Deneuville, C. Guerber, and A. Pirovano,

“Authenticating Civil UAV Communications With Post-
Quantum Digital Signatures,” in 2023 IEEE/AIAA 42nd Digital
Avionics Systems Conference (DASC), (IEEE, 2023): 1–9.
[22] D. Mishra, M. Singh, P. Rewal, et al., “Quantum-Safe Secure

and Authorized Communication Protocol for Internet of
Drones,” IEEE Transactions on Vehicular Technology 72, no. 12
(2023): 16499–16507.
[23] J. Cui, X. Liu, H. Zhong, et al., “A Practical and Provably

Secure Authentication and Key Agreement Scheme for UAV-
Assisted VANETs for Emergency Rescue,” IEEE Transactions
on Network Science and Engineering 11, no. 2 (2024): 1454–
1468.
[24] G. Airlangga and A. Liu, “A Study of the Data Security Attack

and Defense Pattern in a Centralized UAV–Cloud Architec-
ture,” Drones 7, no. 5 (2023): 289.
[25] A. Chhabra, A. Sekhari, and P. Mohapatra, “On the Robustness

of Deep Clustering Models: Adversarial Attacks and Defenses,”
Advances in Neural Information Processing Systems 35 (2022):
20566–20579.
[26] M. Bakyt, L. La Spada, N. Zeeshan, K. Moldamurat, and

S. Atanov, “Application of Quantum Key Distribution to
Enhance Data Security in Agrotechnical Monitoring Systems
Using UAVs,” Applied Sciences 15, no. 5 (2025): 2429.
[27] T. Ahamed Ahanger, A. Aldaej, M. Atiquzzaman, I. Ullah, and

M. Yousufudin, “Distributed Blockchain-Based Platform for
Unmanned Aerial Vehicles,” Computational Intelligence and
Neuroscience 2022 (2022): 4723124.
[28] R. Ferreira, J. Gaspar, P. Sebastião, and N. Souto, “A Software

Deﬁned Radio Based Anti-UAV Mobile System With Jamming
and Spooﬁng Capabilities,” Sensors 22, no. 4 (2022): 1487.
[29] A. Shaﬁque, A. Mehmood, and M. Elhadef, “Detecting Signal

Spooﬁng Attack in UAVs Using Machine Learning Models,”
IEEE Access 9 (2021): 93803–93815.
[30] N. López Vilos, C. Valencia Cordero, R. Souza, and S. Montejo

Sánchez,
“Clustering-Based
Energy-Efﬁcient
Self-Healing
Strategy for WSNs Under Jamming Attacks,” Sensors 23,
no. 15 (2023): 6894.
[31] T. Sharma, S. A. Soleymani, M. Shojafar, and R. Tafazolli,

“Secured Communication Schemes for UAVs in 5G: Crystals-
Kyber and Ids,” ArXiv (2025).
[32] S. Ai, A. S. V. Koe, and T. Huang, “Adversarial Perturbation in

Remote Sensing Image Recognition,” Applied Soft Computing
105 (2021): 107252.
[33] T. Anastasiou, S. Karagiorgou, P. Petrou, et al., “Towards

Robustifying Image Classiﬁers Against the Perils of Adversarial
Attacks on Artiﬁcial Intelligence Systems,” Sensors 22, no. 18
(2022): 6905.
[34] C. L. Chang, J. L. Hung, C. W. Tien, C. W. Tien, and

S. Y. Kuo, “Evaluating robustness of ai models against
adversarial attacks,” in Proceedings of the 1st ACM Workshop

46
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 47 ---

on Security and Privacy on Artiﬁcial Intelligence, (Association
for Computing Machinery, 2020): 47–54.
[35] S. Gnatyuk, T. Okhrimenko, and D. Proskurin, “AI-Based

Encryption System for Secure UAV Communication,” in 2024
IEEE 7th International Conference on Actual Problems of
Unmanned Aerial Vehicles Development (APUAVD), (IEEE,
2024): 93–98.
[36] T. F. Rahman, A. S. Abdalla, K. Powell, W. AlQwider, and

V. Marojevic, “Network and Physical Layer Attacks and
Countermeasures to AI-Enabled 6G o-Ran,” ArXiv (2021).
[37] Z. Wei, W. Hu, J. Zhang, W. Guo, and J. A. McCann,

“Explainable Adversarial Learning Framework on Physical
Layer Key Generation Combating Malicious Reconﬁgurable
Intelligent Surface,” IEEE Transactions on Wireless Commu-
nications 24, no. 4 (2025): 3529–3545.
[38] A. Yazdinejad, R. M. Parizi, A. Dehghantanha, H. Karimipour,

G. Srivastava, and M. Aledhari, “Enabling Drones in the Internet
of Things With Decentralized Blockchain-Based Security,” IEEE
Internet of Things Journal 8, no. 8 (2021): 6406–6415.
[39] A. Jain, S. Barke, M. Garg, et al., “A Walkthrough of

Blockchain-Based Internet of Drones Architectures,” IEEE
Internet of Things Journal 11, no. 21 (2024): 34924–34940.
[40] Y. Mekdad, A. Aris, A. Acar, et al., “A Comprehensive Security

and
Performance
Assessment
of
UAV
Authentication
Schemes,” Security and Privacy 7, no. 1 (2024): e338.
[41] E. Ntizikira, W. Lei, F. Alblehai, K. Saleem, and M. A. Lodhi,

“Secure and Privacy-Preserving Intrusion Detection and
Prevention in the Internet of Unmanned Aerial Vehicles,”
Sensors 23, no. 19 (2023): 8077.
[42] B. D. Deebak and S. O. Hwang, “Intelligent Drone-Assisted

Robust Lightweight Multi-Factor Authentication for Military
Zone Surveil-Lance in the 6g Era,” Computer Networks 225
(2023): 109664.
[43] S. Goyal, S. Doddapaneni, M. M. Khapra, and B. Ravindran, “A

Survey of Adversarial Defenses and Robustness in NLP,” ACM
Computing Surveys 55, no. 14s (2023): 1–39.
[44] N. Ghaffari Laleh, D. Truhn, G. P. Veldhuizen, et al.,

“Adversarial Attacks and Adversarial Robustness in Computa-
tional Pathology,” Nature Communications 13, no. 1 (2022):
5711.
[45] N. M. Yungaicela-Naula, C. Vargas-Rosales, J. A. A. Pérez-

Díaz, and M. Zareei, “Towards Security Automation in
Software Deﬁned Networks,” Computer Communications 183
(2022): 64–82.
[46] M. Keshavarz, M. Gharib, F. Afghah, and J. D. Ashdown,

“Uastrustchain: A
Decentralized
Blockchain-Based
Trust
Monitoring Framework for Autonomous Unmanned Aerial
Systems,” IEEE Access 8 (2020): 226074–226088.
[47] A. Raja, L. Njilla, and J. Yuan, “Adversarial Attacks and

Defenses Toward AI-Assisted UAV Infrastructure Inspection,”
IEEE Internet of Things Journal 9, no. 23 (2022): 23379–23389.
[48] K. Ren, T. Zheng, Z. Qin, and X. Liu, “Adversarial Attacks and

Defenses in Deep Learning,” Engineering 6, no. 3 (2020): 346–
360.
[49] V. U. Ihekoronye, S. O. Ajakwe, J. M. Lee, and D. S. Kim,

“Droneguard: An Explainable and Efﬁcient Machine Learning
Framework for Intrusion Detection in Drone Networks,” IEEE
Internet of Things Journal 12 (2024): 7708–7722.
[50] E. Saldiran, M. Hasanzade, G. Inalhan, and A. Tsourdos,

“Towards Global Explainability of Artiﬁcial Intelligence Agent
Tactics in Close Air Combat,” Aerospace 11, no. 6 (2024): 415.
[51] C. Wang and N. Aouf, “Explainable Deep Adversarial

Reinforcement Learning Approach for Robust Autonomous

Driving,” IEEE Transactions on Intelligent Vehicles 10 (2024):
2551–2563.
[52] A. Bouguettaya, H. Zarzour, A. M. Taberkit, and A. Kechida,

“A Review on Early Wildﬁre Detection From Unmanned Aerial
Vehicles
Using
Deep
Learning-Based
Computer
Vision
Algorithms,” Signal Processing 190 (2022): 108309.
[53] P. Abichandani, D. Lobo, S. Kabrawala, and W. McIntyre,

“Secure Communication for Multiquadrotor Networks Using
Ethereum Blockchain,” IEEE Internet of Things Journal 8, no. 3
(2021): 1783–1796.
[54] H. Abulkasim, B. Goncalves, A. Mashatan, and S. Ghose,

“Authenticated
Secure
Quantum-Based
Communication
Scheme in Internet-of-Drones Deployment,” IEEE Access 10
(2022): 94963–94972.
[55] Y. Kirsal Ever, “A Secure Authentication Scheme Framework

for Mobile-Sinks Used in the Internet of Drones Applications,”
Computer Communications 155 (2020): 143–149.
[56] P. R. Babu, S. A. Kumar, A. G. Reddy, and A. K. Das,

“Quantum
Secure
Authentication
and
Key
Agreement
Protocols for Iot-Enabled Applications: A Comprehensive
Survey and Open Challenges,” Computer Science Review 54
(2024): 100676.
[57] O. Adeniyi, A. S. Sadiq, P. Pillai, M. A. Taheir, and

O. Kaiwartya, “Proactive Self-Healing Approaches in Mobile
Edge Computing: A Systematic Literature Review,” Computers
12, no. 3 (2023): 63.
[58] G. Kumar and H. Alqahtani, “Machine Learning Techniques

for Intrusion Detection Systems in SDN-Recent Advances,
Challenges and Future Directions,” CMES-Computer Modeling
in Engineering & Sciences 134 (2023): 89–119.
[59] H. Alqahtani and G. Kumar, “Cybersecurity in Electric and

Flying Vehicles: Threats, Challenges, AI Solutions & Future
Directions,” ACM Computing Surveys 57 (2024): 1–34.
[60] G. Kumar and K. Kumar, “A Multi-Objective Genetic

Algorithm Based Approach for Effective Intrusion Detection
Using Neural Networks,” in Intelligent Methods for Cyber
Warfare, (Springer, 2014).
[61] H. Alqahtani and G. Kumar, “A Deep Learning-Based

Intrusion
Detection
System
for
in-Vehicle
Networks,”
Computers and Electrical Engineering 104 (2022): 108447.
[62] H. Alqahtani and G. Kumar, “Machine Learning for Enhancing

Transportation Security: A Comprehensive Analysis of Electric
and Flying Vehicle Systems,” Engineering Applications of
Artiﬁcial Intelligence 129 (2024): 107667.
[63] H. Alqahtani and G. Kumar,“Advances in Artiﬁcial Intelligence

for Detecting Algorithmically Generated Domains: Current
Trends and Future Prospects,” Engineering Applications of
Artiﬁcial Intelligence 138 (2024): 109410.
[64] A. Taneja and G. Kumar, “Attention-CNN-LSTM Based

Intrusion Detection System (ACL-IDS) for in-Vehicle Net-
works,” Soft Computing 28, no. 23-24 (2024): 13429–13441.
[65] H. Alqahtani and G. Kumar, “Deep Learning-Based Intrusion

Detection System for in-Vehicle Networks With Knowledge
Graph and Statistical Methods,” International Journal of
Machine Learning and Cybernetics (2024): 1–17.
[66] H. Alqahtani and G. Kumar, “Efﬁcient Routing Strategies for

Electric and Flying Vehicles: A Comprehensive Hybrid
Metaheuristic Review,” IEEE Transactions on Intelligent
Vehicles 9, no. 9 (2024): 5813–5852.
[67] F. Tlili, S. Ayed, and L. Chaari Fourati, “Advancing UAV

Security With Artiﬁcial Intelligence: A Comprehensive Survey
of Techniques and Future Directions,” Internet of Things 27
(2024): 101281.

IET Information Security
47

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 48 ---

[68] R. Shrestha, A. Omidkar, S. A. Roudi, R. Abbas, and S. Kim,

“Machine-Learning-Enabled Intrusion Detection System for
Cellular Connected UAV Networks,” Electronics 10, no. 13
(2021): 1549.
[69] J. Whelan, A. Almehmadi, and K. El-Khatib, “Artiﬁcial

Intelligence for Intrusion Detection Systems in Unmanned
Aerial Vehicles,” Computers and Electrical Engineering 99
(2022): 107784.
[70] J. Tian, B. Wang, R. Guo, Z. Wang, K. Cao, and X. Wang,

“Adversarial Attacks and Defenses for Deep-Learning-Based
Unmanned Aerial Vehicles,” IEEE Internet of Things Journal 9,
no. 22 (2022): 22399–22409.
[71] G. Kocher and G. Kumar, “A Hybrid Deep Learning Approach

for Effective Intrusion Detection Systems Using Spatial-
Temporal Features,” Advanced Engineering Science 54 (2022):
1503–1519.
[72] W. Lo, H. Alqahtani, K. Thakur, A. Almadhor, S. Chander, and

G. Kumar, “A Hybrid Deep Learning Based Intrusion Detection
System Using Spatial-Temporal Representation of in-Vehicle
Network
Trafﬁc
(Best
Paper
2023
Award),”
Vehicular
Communications 35 (2022): 100471.
[73] G. Kocher and G. Kumar, “Machine Learning and Deep

Learning Methods for Intrusion Detection Systems: Recent
Developments and Challenges,” Soft Computing 25, no. 15
(2021): 9731–9763.
[74] I. Sharma, S. K. Gupta, A. Mishra, and S. Askar, “Synchronous

Federated Learning Based Multi Unmanned Aerial Vehicles for
Secure
Applications,”
Scalable
Computing:
Practice
and
Experience 24, no. 3 (2023): 191–201.
[75] Y. Wang, Z. Su, N. Zhang, and A. Benslimane, “Learning in the

Air: Secure Federated Learning for UAV-Assisted Crowdsen-
sing,” IEEE Transactions on Network Science and Engineering 8,
no. 2 (2021): 1055–1069.
[76] N. Nasser, Z. M. Fadlullah, M. M. Fouda, A. Ali, and M. Imran,

“A Lightweight Federated Learning Based Privacy Preserving
B5G Pandemic Response Network Using Unmanned Aerial
Vehicles: A Proof-of-Concept,” Computer Networks 205 (2022):
108672.
[77] A.
Yazdinejad,
R. M.
Parizi,
A.
Dehghantanha,
and
H. Karimipour, “Federated Learning for Drone Authentica-
tion,” Ad Hoc Networks 120 (2021): 102574.
[78] J. Liao, B. Jiang, P. Zhao, L. Ning, and L. Chen, “Unmanned Aerial

Vehicle-Assisted Federated Learning Method Based on a Trusted
Execution Environment,” Electronics 12, no. 18 (2023): 3938.
[79] J. Zheng, J. Xu, H. Du, et al., “Trust Management of Tiny

Federated Learning in Internet of Unmanned Aerial Vehicles,”
IEEE Internet of Things Journal 11, no. 12 (2024): 21046–
21060.
[80] J. Yao and N. Ansari, “Secure Federated Learning by Power

Control for Internet of Drones,” IEEE Transactions on
Cognitive Communications and Networking 7, no. 4 (2021):
1021–1031.
[81] X. Hou, J. Wang, C. Jiang, X. Zhang, Y. Ren, and M. Debbah,

“UAV-Enabled Covert Federated Learning,” IEEE Transactions
on Wireless Communications 22, no. 10 (2023): 6793–6809.
[82] H. Zhang and L. Hanzo, “Federated Learning Assisted Multi-

UAV Networks,” IEEE Transactions on Vehicular Technology
69, no. 11 (2020): 14104–14109.
[83] H. B. Tsegaye, “Towards Resilient and Secure Beyond-5G Non-

Terrestrial Networks (B5G-NTNS): An End-to-End Cloud-
Native Frame-Work,” (2024).
[84] R. Gupta, A. Nair, S. Tanwar, and N. Kumar, “Blockchain-

Assisted Secure UAV Communication in 6g Environment:

Architecture, Opportunities, and Challenges,” IET Commu-
nications 15, no. 10 (2021): 1352–1367.
[85] R. Kumar, A. Aljuhani, P. Kumar, A. Kumar, A. Franklin, and

A. Jolfaei, “Blockchain-Enabled Secure Communication for
Un-manned Aerial Vehicle (UAV) Networks,” in Proceedings
of the 5th International ACM Mobicom Workshop on Drone
Assisted Wireless Communications for 5G and Beyond, (ACM,
2022).
[86] M. Wazid, B. Bera, A. K. Das, S. Garg, D. Niyato, and

M. S. Hossain, “Secure Communication Framework for
Blockchain-Based Internet of Drones-Enabled Aerial Comput-
ing Deployment,” IEEE Internet of Things Magazine 4, no. 3
(2021): 120–126.
[87] M. Aloqaily, O. Bouachir, A. Boukerche, and I. A. Ridhawi,

“Design Guidelines for Blockchain-Assisted 5G-UAV Net-
works,” IEEE Network 35, no. 1 (2021): 64–71.
[88] S. Aggarwal, N. Kumar, and S. Tanwar, “Blockchain-

Envisioned Uav Communication Using 6g Networks: Open
Issues, Use Cases, and Future Directions,” IEEE Internet of
Things Journal 8, no. 7 (2021): 5416–5441.
[89] E. Ghribi, T. T. Khoei, H. T. Gorji, P. Ranganathan, and

N. Kaabouch, “A Secure Blockchain-Based Communication
Approach for UAV Networks,” in 2020 IEEE International
Conference on Electro Information Technology (EIT), (IEEE,
2020): 411–415.
[90] S. Hafeez, Blockchain-Based Secure Unmanned Aerial Vehicles

(UAV) in Network Design and Optimization, (Ph.D. Thesis,
University of Glasgow, 2024).
[91] K. Khullar, Y. Malhotra, and A. Kumar, “Decentralized and

Secure Communication Architecture for FANETs Using
Blockchain,” Procedia Computer Science 173 (2020): 158–170.
[92] D. Saraswat, A. Verma, P. Bhattacharya, et al., “Blockchain-

Based Federated Learning in UAVs Beyond 5G Networks: A
Solution Taxonomy and Future Directions,” IEEE Access 10
(2022): 33154–33182.
[93] R. Sarenche, F. Aghili, T. Yoshizawa, and D. Singelée, “DASLog:

Decentralized Auditable Secure Logging for UAV Ecosystems,”
IEEE Internet of Things Journal 10, no. 23 (2023): 20264–20284.
[94] W. Zhao, I. M. Aldyaﬂah, P. Gangwani, S. Joshi, H. Upadhyay,

and L. Lagos, “A Blockchain-Facilitated Secure Sensing Data
Processing and Logging System,” IEEE Access 11 (2023):
21712–21728.
[95] R. Alkadi, N. Alnuaimi, C. Y. Yeun, and A. Shoufan,

“Blockchain Interoperability in Unmanned Aerial Vehicles
Networks: State-of-the-Art and Open Issues,” IEEE Access 10
(2022): 14463–14479.
[96] R. Gupta, M. M. Patel, S. Tanwar, N. Kumar, and S. Zeadally,

“Blockchain-Based Data Dissemination Scheme for 5g-Enabled
Softwarized UAV Networks,” IEEE Transactions on Green
Communications and Networking 5, no. 4 (2021): 1712–1721.
[97] S. Hafeez, M. A. Shawky, M. Al-Quraan, L. Mohjazi,

M. A. Imran, and Y. Sun, “Beta-UAV: Blockchain-Based
Efﬁcient Authentication for Secure UAV Communication,”
ArXiv (2024).
[98] R. Karmakar, G. Kaddoum, and O. Akhrif, “A Blockchain-

Based Distributed and Intelligent Clustering-Enabled Authen-
tication Protocol for UAV Swarms,” IEEE Transactions on
Mobile Computing 23, no. 5 (2024): 6178–6195.
[99] J. C. U. Ortega, J. Rodríguez-Molina, M. Martínez-Núñez, and

J. Garbajosa, “A Proposal for Decentralized and Secured Data
Collection From Unmanned Aerial Vehicles in Livestock
Monitoring With Blockchain and IPFS,” Applied Sciences 13,
no. 1 (2023): 471.

48
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 49 ---

[100] C. Dong, S. Pal, A. Yao, F. Jiang, S. Chen, and X. Liu,

“Optimizing UAV Delivery for Pervasive Systems Through
Blockchain Integration and Adversarial Machine Learning,”
Computer Communications 236 (2025): 108113.
[101] S. Hafeez, H. U. Manzoor, L. Mohjazi, A. Zoha, M. A. Imran,

and Y. Sun, “Blockchain-Empowered Immutable and Reliable
Delivery Service (Birds) Using Uav Networks,” in 2023 IEEE
28th International Workshop on Computer Aided Modeling and
Design of Communication Links and Networks (CAMAD),
(IEEE, 2023): 7–12.
[102] A. Allouch, O. Cheikhrouhou, A. Kouba^a, K. Toumi,

M. Khalgui, and T. Nguyen Gia, “UTM-Chain: Blockchain-
Based Secure Unmanned Trafﬁc Management for Internet of
Drones,” Sensors 21, no. 9 (2021): 3049.
[103] C. Ge, X. Ma, and Z. Liu, “A Semi-autonomous Distributed

Blockchain-Based Framework for UAVs System,” Journal of
Systems Architecture 107 (2020): 101728.
[104] Y. Tan, J. Wang, J. Liu, and N. Kato, “Blockchain-Assisted

Distributed
and
Lightweight
Authentication
Service
for
Industrial Unmanned Aerial Vehicles,” IEEE Internet of Things
Journal 9, no. 18 (2022): 16928–16940.
[105] R. Aissaoui, J. C. Deneuville, C. Guerber, and A. Pirovano,

“Evaluating Post-Quantum Key Exchange Mechanisms for
UAV Communi-cation Security,” in 2024 AIAA DATC/IEEE
43rd Digital Avionics Systems Conference (DASC), (IEEE, 2024):
1–10.
[106] V. K. Ralegankar, J. Bagul, B. Thakkar, et al., “Quantum

Cryptography-as-a-Service for Secure UAV Communication:
Applications, Challenges, and Case Study,” IEEE Access 10
(2022): 1475–1492.
[107] O. A. Hussien, I. S. Arachchige, and H. Jahankhani, “Strength-

ening Security Mechanisms of Satellites and UAVs Against
Possible Attacks From Quantum Computers,” in International
Conference on Global Security, Safety, and Sustainability,
(Springer, 2023): 1–20.
[108] T. Xia, M. Wang, J. He, G. Yang, L. Fan, and G. Wei, “A

Quantum-Resistant Identity Authentication and Key Agree-
ment Scheme for UAV Networks Based on Kyber Algorithm,”
Drones 8, no. 8 (2024): 359.
[109] A. S. Nair, S. M. Thampi, and V. Jafeel, “A Post-Quantum

Secure PUF Based Cross-Domain Authentication Mechanism
for Internet of Drones,” Vehicular Communications 47 (2024):
100780.
[110] S. Goyal, A. S. Rajawat, R. K. Solanki, L. Zhu, and W. Chee,

“Enhancing Privacy and Security for UAV and IoT Enabled
Drones an Intelligent Integration of Blockchain, AI, and
Quantum
Computing,”
in
International
Conference
on
Intelligent Computing & Optimization, (Springer, 2023): 16–27.
[111] P. K. Sandanamudi, N. Agrawal, N. Tripathi, and P. K. BN,

“Securing UAV Communications: A Comparative Performance
Analysis of Post-Quantum Cryptographic Techniques,” in 2025
17th International Conference on COMmunication Systems and
NETworks (COMSNETS), (IEEE, 2025): 1096–1101.
[112] A. T. Jawad, R. Maaloul, and L. Chaari, “Authentication

Communication by Using Visualization Cryptography for
UAV Networks,” Computer Standards & Interfaces 92 (2025):
103918.
[113] N. Alshaer, A. Moawad, and T. Ismail, “Reliability and Security

Analysis of an Entanglement-Based QKD Protocol in a
Dynamic Ground-to-UAV FSO Communications System,”
IEEE Access 9 (2021): 168052–168067.
[114] M. A. El-Zawawy, A. Brighente, and M. Conti, “Authenticating

Drone-Assisted Internet of Vehicles Using Elliptic Curve

Cryptography and Blockchain,” IEEE Transactions on Network
and Service Management 20, no. 2 (2023): 1775–1789.
[115] D. Wang, Y. Cao, K. Y. Lam, Y. Hu, and O. Kaiwartya,

“Authentication and Key Agreement Based on Three Factors
and
Puf
for
UAVs-Assisted
Post-Disaster
Emergency
Communication,” IEEE Internet of Things Journal 11 (2024):
20457–20472.
[116] A. S. Khan, M. I. B. Yahya, K. B. Zen, et al., “Blockchain-Based

Lightweight Multifactor Authentication for Cell-Free in Ultra-
Dense 6G-Based (6-CMAS) Cellular Network,” IEEE Access 11
(2023): 20524–20541.
[117] N. Zhang, Q. Jiang, L. Li, X. Ma, and J. Ma, “An Efﬁcient Three-

Factor Remote User Authentication Protocol Based on BPV-
FourQ for Internet of Drones,” Peer-to-Peer Networking and
Applications 14, no. 5 (2021): 3319–3332.
[118] M. Usman, R. Amin, H. Aldabbas, and B. Aloufﬁ, “Lightweight

Challenge-Response Authentication in SDN-Based UAVs
Using Elliptic Curve Cryptography,” Electronics 11, no. 7
(2022): 1026.
[119] H. Khalid, S. J. Hashim, S. M. S. Ahamed, F. Hashim, and

M. A. Chaudhary, “Secure Real-Time Data Access Using Two-
Factor Authentication Scheme for the Internet of Drones,” in
2021
IEEE
19th
Student
Conference
on
Research
and
Development (SCOReD), (IEEE, 2021): 168–173.
[120] C. Tian, Q. Jiang, T. Li, J. Zhang, N. Xi, and J. Ma, “Reliable

PUF-Based
Mutual
Authentication
Protocol
for
UAVs
Towards Multi-Domain Environment,” Computer Networks
218 (2022): 109421.
[121] G. Bansal and B. Sikdar, “Achieving Secure and Reliable UAV

Authentication: A Shamir’s Secret Sharing Based Approach,”
IEEE Transactions on Network Science and Engineering 11,
no. 4 (2024): 3598–3610.
[122] H. M. Ismael and Z. T. M. Al-Ta’i, “Authentication and

Encryption Drone Communication by Using Hight Light-
weight
Algorithm,”
Turkish
Journal
of
Computer
and
Mathematics Education 12 (2021): 5891–5908.
[123] C. Dong, F. Jiang, S. Chen, and X. Liu, “Continuous

Authentication for UAV Delivery Systems Under Zero-Trust
Security Framework,” in 2022 IEEE International Conference on
Edge Computing and Communications (EDGE), (IEEE, 2022).
[124] T. Alladi, Naren, G. Bansal, V. Chamola, and M. Guizani,

“Secauthuav: A Novel Authentication Scheme for UAV-
Ground Station and UAV-UAV Communication,” IEEE
Transactions on Vehicular Technology 69, no. 12 (2020):
15068–15077.
[125] C. Zhang, X. Costa-Perez, and P. Patras, “Adversarial Attacks

Against Deep Learning-Based Network Intrusion Detection
Systems and Defense Mechanisms,” IEEE/ACM Transactions
on Networking 30, no. 3 (2022): 1294–1311.
[126] T. Tsai, K. Yang, T. Y. Ho, and Y. Jin, “Robust adversarial

objects against deep learning models,” Proceedings of the AAAI
Conference on Artiﬁcial Intelligence 34: 954–962.
[127] Q. Tian, S. Zhang, S. Mao, and Y. Lin, “Adversarial Attacks and

Defenses for Digital Communication Signals Identiﬁcation,”
Digital Communications and Networks 10, no. 3 (2024): 756–764.
[128] X. Zhang, X. Zheng, and W. Mao, “Adversarial Perturbation

Defense on Deep Neural Networks,” ACM Computing Surveys
(CSUR) 54 (2021): 1–36.
[129] H.
Waghela,
J.
Sen,
and
S.
Rakshit,
“Robust
Image
Classiﬁcation: Defensive Strategies Against FGSM and PGD
Adversarial Attacks,” ArXiv (2024): 1–7.
[130] S. Tiwari, V. Sresth, and A. Srivastava, “The Role of Explainable

AI in Cybersecurity: Addressing Transparency Challenges in

IET Information Security
49

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License


## --- Page 50 ---

Autonomous Defense Systems,” International Journal of
Innovative Research in Science, Engineering and Technology
09, no. 3 (2020): 718–733.
[131] N. Moustafa, N. Koroniotis, M. Keshk, A. Y. Zomaya, and

Z. Tari, “Explainable Intrusion Detection for Cyber Defences in
the Internet of Things: Opportunities and Solutions,” IEEE
Communications Surveys & Tutorials 25, no. 3 (2023): 1775–
1807.
[132] M. T. Masud, M. Keshk, N. Moustafa, I. Linkov, and

D. K. Emge, “Explainable Artiﬁcial Intelligence for Resilient
Security Applications in the Internet of Things,” IEEE Open
Journal of the Communications Society 6 (2024): 2877–2906.
[133] S. Wu, Y. Li, Z. Wang, Z. Tan, and Q. Pan, “A Highly

Interpretable Framework for Generic Low-Cost UAV Attack
Detection,” IEEE Sensors Journal 23, no. 7 (2023): 7288–7300.
[134] S. O. Ajakwe and D.-S. Kim, “Facets of Security and Safety

Problems and Paradigms for Smart Aerial Mobility and
Intelligent Logistics,” IET Intelligent Transport Systems 18,
no. S1 (2024): 2827–2855.
[135] B. Chander, C. John, L. Warrier, and K. Gopalakrishnan,

“Toward Trustworthy Artiﬁcial Intelligence (Tai) in the
Context of Explain-Ability and Robustness,” ACM Computing
Surveys 57 (2025): 1–49.
[136] C. Maathuis, “Towards Trustworthy AI-Based Military Cyber

Operations,” in 19th International Conference on Cyber
Warfare and Security: ICCWS 2024, (Academic Conferences
and Publishing Limited, 2024).
[137] L. Wang, Y. Chen, P. Wang, and Z. Yan, “Security Threats and

Countermeasures of Unmanned Aerial Vehicle Communica-
tions,” IEEE Communications Standards Magazine 5, no. 4
(2021): 41–47.
[138] D. He, G. Yang, H. Li, S. Chan, Y. Cheng, and N. Guizani, “An

Effective Countermeasure Against UAV Swarm Attack,” IEEE
Network 35, no. 1 (2021): 380–385.
[139] Y. Jiang, J. Yuan, L. Sun, and H. Song, “Development of a

Laboratory Platform for UAV Cybersecurity Education,” in
2021 ASEE Virtual Annual Conference, (ASEE, 2021).
[140] C. Jie, “Research on Intelligentized Anti-UAV Command

Control Scheme Technology,” in E3S Web of Conferences, (EDP
Sciences, 2021).
[141] J. Wang, Y. Liu, and H. Song, “Counter-Unmanned Aircraft

System(s) (C-UAS): State of the Art, Challenges, and Future
Trends,” IEEE Aerospace and Electronic Systems Magazine 36,
no. 3 (2021): 4–29.
[142] C. S. Babu and A. Pal, “Enhancing Security for Unmanned

Aircraft Systems in IoT Environments: Defense Mechanisms
and Mitigation Strategies,” in Unmanned Aircraft Systems,
(Wiley, 2024): 429–476.
[143] N. Malik, H. Sinha, and M. Dahiya, “Security in UAV

Ecosystem: An Implementation Perspective,” Sigma Journal of
Engineering and Natural Sciences 42 (2024): 1986–1994.
[144] M. Ficco, D. Granata, F. Palmieri, and M. Rak, “A Systematic

Approach for Threat and Vulnerability Analysis of Unmanned
Aerial Vehicles,” Internet of Things 26 (2024): 101180.
[145] D. Patil and S. Pournouri, “Evaluating the Security Of Open-

Source Linux Operating Systems For Unmanned Aerial
Vehicles,” in International Conference on Global Security,
Safety, and Sustainability, (Springer, 2023): 21.
[146] X. Wei, Y. Xu, H. Zhang, et al., “Sensor Attack Online

Classiﬁcation for UAVs Using Machine Learning,” Computers
& Security 150 (2025): 104228.
[147] J. P. Dias, T. B. Sousa, A. Restivo, and H. S. Ferreira, “A

pattern-Language
for
Self-Healing
Internet-of-Things

Systems,” in Proceedings of the European Conference on Pattern
Languages of Programs 2020, (Association for Computing
Machinery, 2020): 1–17.
[148] J. M.
Qurashi,
K.
Jambi,
F.
Alsolami,
F. E.
Eassa,
M. Khemakhem, and A. Basuhail, “Resilient Countermeasures
Against Cyber-Attacks on Self-Driving Car Architecture,” IEEE
Transactions on Intelligent Transportation Systems 24, no. 11
(2023): 11514–11543.
[149] A. Phadke and F. A. Medrano, “Towards Resilient UAV

Swarms—A Breakdown of Resiliency Requirements in UAV
Swarms,” Drones 6, no. 11 (2022): 340.
[150] J. P. A. Yaacoub, H. N. Noura, O. Salman, and A. Chehab,

“Robotics Cyber Security: Vulnerabilities, Attacks, Counter-
measures, and Recommendations,” International Journal of
Information Security 21, no. 1 (2022): 115–158.
[151] M. Adil, H. Song, S. Mastorakis, H. Abulkasim, A. Farouk, and

Z. Jin, “Uav-Assisted Iot Applications, Cybersecurity Threats,
Ai-Enabled Solutions, Open Challenges With Future Research
Directions,” IEEE Transactions on Intelligent Vehicles 9, no. 4
(2024): 4583–4605.
[152] B. S. Sarıkaya and S. Bahtiyar, “A Survey on Security of UAV

and Deep Reinforcement Learning,” Ad Hoc Networks 164
(2024): 103642.
[153] P. Homann, J. Diegelmann, M. Pacher, and U. Brinkschulte,

“Evaluation of Trust Metrics in an Artiﬁcial Hormone System,”
in 2024 IEEE 27th International Symposium on Real-Time
Distributed Computing (ISORC), (IEEE, 2024): 1–12.
[154] J. P. A. Yaacoub, Modular Robotics Meet Internet of Things:

Safety, Security and Performance Challenges and Counter-
measures, (Ph.D. Thesis, Université Bourgogne Franche-
Comté, 2024).
[155] I. Al Ridhawi, O. Bouachir, M. Aloqaily, and A. Boukerche,

“Design Guidelines for Cooperative UAV-Supported Services
and Applications,” ACM Computing Surveys (CSUR) 54 (2021):
1–35.
[156] G. Mani, B. K. Bhargava, J. Kobes, J. King, and J. MacDonald,

Securing Intelligent Autonomous Systems Through Artiﬁcial
Intelligence (ISIC, 2021).
[157] S. Wei, Z. Fan, G. Chen, E. Blasch, Y. Chen, and K. Pham,

“Tadad: Trust AI-Based Decentralized Anomaly Detection For
Urban Air Mobility Networks At Tactical Edges,” in 2024
Integrated
Communications, Navigation and
Surveillance
Conference (ICNS), (IEEE, 2024): 1–10.

50
IET Information Security

ietis, 2025, 1, Downloaded from https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ise2/2046868, Wiley Online Library on [13/07/2026]. See the Terms and Conditions (https://onlinelibrary.wiley.com/terms-and-conditions) on Wiley Online Library for rules of use; OA articles are governed by the applicable Creative Commons License
