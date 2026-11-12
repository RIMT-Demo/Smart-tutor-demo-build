Abstract
Quantum computers represent a transformative frontier in computational technology,
promising exponential speedups beyond classical computing limits. IBM Quantum
has led significant advancements in both hardware and software, providing access to
quantum hardware via IBM Cloud® since 2016 and achieving a milestone with the
world’s first accessible quantum computer. This paper explores IBM’s journey in
quantum computing, focusing on its contributions to both hardware and software, as
well as the development of practical quantum computers. We trace the evolution of
IBM Quantum’s processors, from the early canary processors to the milestone of
surpassing the 1000-qubit barrier. In addition to these technological strides, we delve
into the practical applications of quantum computing, particularly within nine key
industries: airlines, banking, healthcare, electronics, life sciences, and more. We also
explore IBM Quantum’s case studies and strategic partnerships with organizations
such as Boeing, CERN, ExxonMobil, and Cleveland Clinic, which are helping to
bridge the gap between theoretical research and real-world applications. Further, we
examine the key challenges and solutions in scaling quantum systems and achieving
fault tolerance, highlighting IBM’s efforts toward building practical, fault-tolerant
quantum systems capable of addressing real-world problems.
Keywords IBM Quantum computers · The practical applications of
quantum computation · Superconducting quantum computers · Performance
of IBM’s quantum computers · 1000-qubit processor · Quantum hardware · Quantum
computing case studies · Heron · Condor · Qiskit · Boeing · CERN · ExxonMobil ·
Quantum supremacy
& Muhammad AbuGhanem
gaa1nem@gmail.com
1
Faculty of Science, Ain Shams University, Cairo 11566, Egypt
123
  687 
Page 2 of 95
M. AbuGhanem
1 Introduction
Quantum computers represent a revolutionary approach to computation [1], lever
aging the principles of quantum mechanics [2, 3] to potentially solve problems that
are beyond the reach of classical computers [4–6]. The NISQ era [7] marks a pivotal
phase in quantum computing, characterized by rapid advancements and challenges in
achieving practical quantum applications [1].
Industry has been facilitating access to quantum computers for both academic and
commercial users. Companies such as IBM (2016), Rigetti Computing (2017), IonQ
(2020), Honeywell (2020), Google (2020), Xanadu (2020), Oxford Quantum Circuits
OQC (2021), PASQAL (2022), QuEra (2022), and Quandela (2022). While others
have adopted a reseller model through web-based services. As a result, research on
quantum computers has increased significantly. For instance, scientific papers
utilizing IBM Quantum’s quantum systems via cloud service have reached
approximately 2800 as of February 2024, with over 3 trillion circuits executed
through IBM Quantum platform [8].
IBM Quantum [9] has emerged as a key player in the quantum computing
landscape, leading efforts to advance both quantum hardware and software
capabilities. The development of scalable quantum processors based on supercon
ducting qubits has been central to IBM Quantum’s research and development efforts.
Over the years, IBM has made significant strides in increasing qubit counts,
improving qubit coherence times, and implementing error correction techniques
necessary for reliable quantum computation [10, 11]. These advancements have
positioned IBM Quantum as a leader in quantum computing research, with broad
implications ranging from computational chemistry and optimization to cryptography
and machine learning [10–13].
This paper explores IBM Quantum’s journey in quantum computing, highlighting
key technological achievements, current challenges, and future prospects. The study
aims to present a comprehensive review of detailed performance metrics across IBM
Quantum’s quantum computers, crucial for historical documentation within the NISQ
era literature. Metrics examined include relaxation times, qubit frequency and
anharmonicity, readout assignment errors and readout length, single-qubit gate errors,
connection errors, and gate times.
2 Design philosophy
This paper is structured as follows: Sect. 3 offers an overview of IBM Quantum’s
quantum computing initiative. Section 4 explores the practical applications of
quantum computing, focusing specifically on IBM Quantum’s quantum systems. In
this section, we examine how quantum technology is being adopted across nine
major industries: airlines, banking, chemicals, electronics, government, healthcare,
insurance, life sciences, and logistics. For each industry, we highlight three real
world use cases that demonstrate the transformative potential of quantum solutions.
In Sect. 5, we discuss three critical metrics-Scale, Quality, and Speed-that are
essential for assessing the performance of quantum computing systems. These
123
IBM quantum computers: evolution, performance, and future directions
Page 3 of 95  687 
metrics serve as vital benchmarks for evaluating progress in near-term hardware
capabilities. Section 6 traces the evolution of IBM Quantum’s hardware, from the
early 5-qubit Canary processor to the achievement of the 1000-qubit milestone with
the Condor processor. In Sect. 7, we summarize the performance and characteristics
of IBM Quantum’s quantum computers, reviewing both current systems and their
capabilities, as well as retired systems and simulators.
Moving to Sect. 8, the focus shifts to IBM Quantum’s software and tools,
examining key technologies such as Qiskit, Qiskit Patterns, and Qiskit Circuits,
alongside advanced features like quantum serverless computing and circuit design
tools. Section 9 delves into IBM Quantum’s strategic partnerships and use cases,
highlighting collaborations with major organizations such as Boeing, CERN,
ExxonMobil, Cleveland Clinic, E.ON, Mitsubishi Chemical, JSR, Keio University,
and Mercedes-Benz. These partnerships are crucial to advancing quantum computing
applications across a range of industries and bringing us closer to achieving a
quantum advantage.
While IBM Quantum’s contributions are undeniably significant, they represent
just one facet of the broader and rapidly evolving quantum landscape. To gain a fuller
perspective, Sect. 10 explores the efforts of other leading companies and research
institutions in the field, such as Google Quantum AI, Rigetti Computing, IonQ,
Quantinuum, Xanadu, Oxford Quantum Circuits, QuEra, Quandela Cloud, Micro
soft, Alibaba Quantum, Intel Quantum, UST China, and TU Delft. By examining
these developments, we deepen our understanding of the global push toward
scalable, fault-tolerant quantum systems.
Section 11 outlines IBM Quantum’s Technology Roadmap and its ongoing
initiatives to make practical quantum computing a reality (Sect. 11.1). This includes a
focus on quantum safety, along with a detailed look at IBM Quantum’s Hardware
Development Roadmap: Milestones (2016 2033þ) in Sect. 11.3. Each milestone is
presented in three parts: (1) Strategy Overview, (2) Significance for clients and
society, and (3) Innovations that will drive progress, with an emphasis on the delivery
of solutions to clients and partners.
Despite IBM Quantum’s significant progress, challenges remain in developing
fault-tolerant quantum systems (Sect. 12), particularly concerning issues like noise,
error correction, qubit connectivity, and scalability. Section 12.1 discusses these
scalability challenges in detail, while Sect. 12.2 explores IBM Quantum’s strategies
for addressing them. These strategies include a combination of hardware innovations,
modular architectures, and advanced error correction techniques [14].
IBM Quantum’s long-term vision for quantum computing-particularly using
superconducting qubits-highlights both the complexity of these challenges and the
approaches required to overcome them [15]. To achieve a computational advantage,
substantial advancements in quantum error correction will be necessary to address
issues such as noise and qubit connectivity, along with other hardware limitations [7].
Section 12.3 discusses IBM Quantum’s work on quantum error mitigation and
quantum error correction (QEC), while Sect. 12.4 explores IBM Quantum’s plans for
building fully fault-tolerant quantum systems that can address real-world problems.
123
  687 
Page 4 of 95
M. AbuGhanem
Finally, Sect. 13 presents the conclusion, synthesizing the key findings and their
implications for the future of IBM Quantum technology.
3 IBM quantum
3.1 Overview
IBM Quantum is a leading provider of quantum computing resources, offering access
to top-of-the-line quantum hardware that is built with the latest technology to meet
the needs of researchers, industry professionals, and developers.
IBM Quantum operates the most sophisticated collection of quantum systems
globally, currently featuring seven utility-scale systems, with additional systems in
development. These systems are known for their exceptional reliability, boasting over
95% uptime collectively. They also demonstrate remarkable stability, with minimal
fluctuations in two-qubit gate errors, which do not exceed 0.001 over periods
spanning several months (median 2-qubit gate errors measured across all accessible
Eagle processors from July 20 to September 20, 2023) [16].
In 2023, IBM has introduced its latest quantum computing milestone with the
unveiling of Condor, a quantum processor featuring 1121 superconducting qubits
arranged in a honeycomb configuration [17]. This follows the pattern set by earlier
record-breaking machines such as Eagle, a 127-qubit chip launched in
2021 [16, 18], and Osprey, a 433-qubit processor announced November 2022
[19]. As part of its strategy, IBM also introduced a new quantum chip named
Heron, boasting 133 qubits and achieving a remarkable record-low error rate that is
three times lower than that of IBM’s previous quantum processor. This achievement
marks a departure from IBM’s previous strategy of doubling qubit counts annually,
signaling a shift toward prioritizing enhanced error resistance over further qubit
scalability [11, 17].
IBM Quantum offers a wide range of hardware and software resources that
support learning, experimentation, and collaboration in the field of quantum
computing, as detailed in this paper, with promising implications for accelerating
scientific discovery, enhancing computational efficiency, and addressing complex
real-world problems.
3.2 Breaking the 1000-qubit barrier
IBM Quantum has introduced IBM Condor, a quantum processor with 1121
superconducting qubits based on IBM Quantum’s cross-resonance gate technol
ogy [17]. Condor sets new standards in chip design (see Fig. 1), featuring a 50%
increase in qubit density, enhancements in qubit fabrication and laminate size, and
over a mile of high-density cryogenic flex I/O wiring within a single dilution
refrigerator.
Moving to high performing quantum processors, IBM Quantum introduced the
first IBM Quantum Heron processor on the ibm_torino quantum system. Featuring
123
IBM quantum computers: evolution, performance, and future directions
Page 5 of 95  687 
Fig. 1 IBM’s latest quantum
processor Condor, unveiled in
2023,
features
1121
superconducting qubits arranged
in a honeycomb configuration.
(Credit: Ryan Lavine, IBM)
133 fixed-frequency qubits with tunable couplers. Heron delivers significant
improvements in device performance (a 3-5x improvement in device performance)
compared to IBM Quantum’s previous flagship 127-qubit Eagle processors [16, 18],
while virtually eliminating cross-talk. With Heron, IBM Quantum has developed
qubit and gate technology that forms the foundation of IBM Quantum’s hardware
roadmap moving forward.
3.3 IBM quantum’s system two
IBM Quantum System Two serves as the foundation for scalable quantum
computation and is currently operational at the IBM lab in Yorktown Heights, NY.
Housing three IBM Quantum Heron processors, integrating cryogenic infrastructure
with third-generation control electronics and classical runtime servers (see Fig. 2).
IBM Quantum System Two features a modular architecture designed to facilitate
parallel circuit executions, which are essential for achieving quantum-centric
supercomputing [15].
4 The practical applications of quantum computation
Quantum computing offers transformative potential for industries by solving
complex problems more efficiently, cost-effectively, and with greater precision than
classical systems. The true power of quantum computing lies in its ability to
complement and enhance classical computing, creating a synergy that can unlock
new possibilities. As advancements in quantum hardware, software, and algorithms
converge, industries can expect significant breakthroughs that go beyond the
capabilities of traditional systems [1]. This section explores how quantum computing
is being adopted across various sectors, including airlines, banking, healthcare, and
more, highlighting industry-specific use cases and insights. While the path to
achieving “Quantum Advantage” may take time, businesses can already begin to
benefit from the exponential progress and learning that quantum computing
promises.
123
  687 
Page 6 of 95
M. AbuGhanem
Fig. 2 IBM Quantum System Two, unveiled at the IBM Quantum Summit 2023, represents IBM’s first
modular quantum computer and serves as a foundational element in IBM’s quantum-centric
supercomputing architecture. (Image source: IBM Quantum)
4.1 Airline
Quantum computing is revolutionizing the airline industry by addressing complex
operational challenges and enhancing customer experiences. As global travel
recovers from the COVID-19 pandemic, airlines are leveraging quantum technolo
gies to tackle inefficiencies in operations, improve personalization, and optimize
planning. The computational power of quantum systems provides faster decision
123
IBM quantum computers: evolution, performance, and future directions
Page 7 of 95  687 
making and more advanced algorithms, enabling the industry to remain competitive
in an increasingly dynamic environment.
Use Cases Quantum computing helps airlines manage Irregular Operations
(IROPS) by enabling integrated recovery models and enhancing customer
satisfaction with rapid solutions [20]. It also enhances personalized customer
services by analyzing multidimensional data to refine customer segmentation and
improve marketing strategie [21]. Additionally, quantum systems optimize global
network planning by unifying fleet, crew, fuel, and revenue management into a
single model, ensuring cost-effective and efficient operations. These advancements
position airlines to offer streamlined and customer-focused services while boosting
profitability [22].
4.2 Banking and financial markets
Quantum computing holds the potential to revolutionize the banking and financial
markets by tackling complex challenges such as market uncertainty, constrained
system optimization, and profitable opportunity identification. This technology
enhances traditional financial models, enabling faster and more accurate assessments
of market risks, responses to volatility, and utilization of behavioral data for superior
customer engagement. While widespread applications may take time, financial
institutions are already exploring quantum computing to transform operations like
client management, trading, asset management, and compliance, offering a
competitive edge in an increasingly dynamic market [20].
Use Cases Quantum computing aids financial institutions in targeting and
prediction by improving data modeling for personalized services, fraud detection,
and customer acquisition [23]. It enhances risk profiling by accelerating scenario
simulations and refining compliance with regulatory standards like Basel III.
Additionally, quantum algorithms optimize trading by enabling more effective
portfolio diversification, rebalancing, and scenario analysis, reducing costs and
boosting portfolio performance. Together, these advancements streamline operations
and position financial institutions to better navigate market complexities and
customer demands.
4.3 Chemicals and petroleum
Quantum computing is set to transform the chemicals and petroleum industries by
addressing challenges such as complex molecular modeling, optimizing refining
processes, and improving resource extraction. These industries, crucial to the global
economy (contributing approximately 5.7 trillion to global GDP and supporting over
120 million jobs [24]), face computational bottlenecks when simulating molecular
behaviors or managing supply chain logistics. For instance, the simple hydrocarbon
Naphthalene (C10 H8) can be simulated using approximately 116 qubits. In contrast,
a classical computer would need around 1034 bits to perform the same simula
tion [25]. To put this into perspective, 1034 bits is roughly 7.1 billion times the
amount of data expected to be stored electronically by 2025, which is estimated to be
123
  687 
Page 8 of 95
M. AbuGhanem
around 175 zettabytes [26]. Quantum algorithms offer a scalable and efficient
solution, enabling precise molecular simulations, refined operations, and innovative
methods for expanding resource production. This technology has the potential to
reduce costs, enhance efficiency, and drive sustainable innovations across the value
chain.
Use Cases Quantum computing accelerates chemical product development by
enabling accurate simulations for catalysts and surfactants, revolutionizing product
design and emissions reduction efforts [27]. It optimizes feed-stock routing and
refining processes, reducing inefficiencies such as octane giveaways, which cost
billions annually [28]. Additionally, it enhances reservoir production by modeling
molecular-scale subsurface interactions, improving resource extraction efficiency and
boosting profitability [25]. These applications demonstrate the profound impact of
quantum computing on operational efficiency and industry sustainability.
4.4 Electronics
The electronics sector, a linchpin of modern technology and the global economy,
faces mounting challenges, including the escalating costs of semiconductor
manufacturing, plateauing advancements in product performance, and inefficiencies
in design and production processes. As Moore’s Law slows, traditional approaches to
driving innovation and efficiency are becoming less effective. Quantum computing
presents a groundbreaking alternative, offering solutions to complex problems in
materials science, product design, and manufacturing optimization. By leveraging its
computational advantages, quantum technology can help the industry overcome
current barriers, ensuring continued progress and competitiveness.
Use Cases Quantum computing holds transformative potential for the electronics
industry across materials development, product design, and manufacturing. It can
revolutionize materials research by accurately simulating molecular interactions,
enabling breakthroughs like more efficient displays and eco-friendly manufacturing
chemicals [29]. In product design, quantum optimization accelerates development by
solving complex challenges, such as optimizing chip layouts and enhancing bug
detection, reducing time-to-market and improving reliability [30]. For manufactur
ing, quantum-enhanced AI significantly improves defect detection accuracy, reducing
false positives and minimizing financial losses, while optimizing production
processes sustainably [31, 32]. Together, these capabilities position quantum
computing as a pivotal driver of innovation and efficiency in electronics.
4.5 Government
Governments are under growing pressure to address complex challenges, such as
climate change, social program sustainability, and transportation infrastructure strain,
while balancing limited resources. Quantum computing offers a transformative
solution by enabling more efficient problem-solving, accelerating decision-making,
and reducing costs. With the ability to tackle intricate simulations and optimization
tasks, quantum computing holds the promise of enhancing public services, improving
123
IBM quantum computers: evolution, performance, and future directions
Page 9 of 95  687 
emergency responses, and supporting sustainable development across various
sectors.
Use Cases Quantum computing can revolutionize government operations through
enhanced emergency preparedness, transportation management, and fraud detection.
It can optimize disaster response by improving real-time analysis and resource
allocation, as seen in wildfire evacuation planning [33]. In transportation, quantum
algorithms can streamline traffic management, reducing congestion and enhancing
flow efficiency, leading to significant economic benefits [25, 34]. For social
programs, quantum-enhanced machine learning can improve fraud detection, saving
billions annually while ensuring resources are directed to those in need [35]. These
advancements demonstrate quantum computing’s potential to elevate government
efficiency and service delivery