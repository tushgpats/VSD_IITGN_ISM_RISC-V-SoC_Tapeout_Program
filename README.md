# VSD_IITGN_ISM_RISC-V-SoC_Tapeout_Program
This program is an joint initiative Between VSD and IIT-Gandginagar and supported by SCL chandigarh and C2S program of Misistry of Electronics and IT. This Program aims to takes 
participants through the full journey of SoC design, from RTL to GDSII, using open-source as well as Industry standard EDA tools in the course of 20 weeks.

Now before we dig deep, let us dive deep into the significance of Semiconductors and Opensource Tools and Open Standard specifications.

## Growth trends of Semiconductor Industry

The global semiconductor market was valued at over USD 681 billion in 2024 and is projected to exceed USD 2 trillion by 2032, growing at a Compound Annual Growth Rate (CAGR) of 
roughly 15.4%. Key growth drivers include the expanding use of semiconductors in areas like AI, cloud computing, and 5G technology, with the Asia Pacific region holding the largest 
market share. 


<img width="1600" height="1200" alt="global_semiconductor_market" src="https://github.com/user-attachments/assets/fca77293-ba92-4704-9851-e9d6f1b3c65a" />


India's semiconductor consumption market was USD 52 billion in 2024-25 and is projected to reach USD 103.4 billion by 2030 with a CAGR of Approximately 13%., 
driven by surging domestic demand in sectors like mobile, IT, and industrial applications.


<img width="1600" height="1200" alt="indian_semiconductor_market" src="https://github.com/user-attachments/assets/4bd6039a-d9cf-4dbf-a6e6-6f380690dbb4" />

## OpenSource and OpenStandard

The Terms Open Source and Open Standard are frequently used interchangeably, but there is a difference between the two.
Open source refers to software or hardware whose implementation is freely available to use, study, modify, and share, while 
open standard refers to a publicly available specification or protocol that anyone can implement to ensure compatibility and interoperability. 
In other words, open source is about the implementation being open, whereas open standard is about the rules or specifications being open. 
For example, the RISC-V ISA is an open standard, and tools like Yosys or Openlane are open source. The two often complement each other, but they are not the same.

## Implications of Open Source and Open Standard in IP Law

Open source and open standard are often confused, but this distinction carries big consequences in IP law.
Misunderstanding this difference can lead to situations where engineers assume that “open” automatically means “free of restrictions,” which is not true in law.
The case of RISC-V illustrates this risk. 
The RISC-V ISA itself is an open standard, but many optimized implementations of RISC-V cores are protected by patents or proprietary licenses. 
A company could use the standard legally, but if they copy or adapt a patented microarchitecture feature — like cache coherence, 
branch prediction, or low-power extensions — they may infringe on someone’s IP rights. This creates “hidden mines” where the boundary between open specifications and proprietary designs is easy to miss without careful due diligence.
Even open source projects come with obligations. While licenses like BSD or Apache 2.0 may feel permissive, 
they often require attribution, disclosure of modifications, or avoidance of patent claims.
In short, open standards and open source lower barriers, but neither guarantees complete freedom from IP risks — engineers and companies must conduct freedom-to-operate (FTO) checks to avoid costly surprises.


## More on RISC-V

RISC-V is an open-standard Instruction Set Architecture (ISA) that provides a free, modular, and extensible alternative to proprietary ISAs like ARM and x86. 
Its popularity stems from the fact that the specification is openly available, allowing companies, researchers, and startups to design processors without paying licensing fees or being locked into vendor ecosystems. 
The flexibility to customize RISC-V for AI, IoT, cloud, or automotive applications makes it attractive, while its open ecosystem fosters rapid innovation. 
Its key advantages include cost savings, transparency, academic accessibility, and freedom from vendor restrictions.
However, challenges remain: the ecosystem is still immature compared to ARM, with fewer robust software stacks, toolchains, and proven commercial-grade implementations. 
Additionally, concerns about long-term support and the lack of large-scale, standardized RISC-V IP libraries slow adoption in some industries.
Despite these hurdles, RISC-V is being adopted worldwide, particularly in regions wary of U.S. sanctions, such as China, where companies see it as a path to technological self-reliance.
By eliminating dependency on foreign-controlled IP, RISC-V empowers countries to design their own chips while staying compliant with global standards. 
This democratization of processor design opens the VLSI world to universities, startups, and emerging economies that previously couldn’t afford ARM or x86 licensing costs. 
In this sense, RISC-V is not just a technical innovation but also a geopolitical and economic force, redistributing access to advanced silicon design and enabling broader participation in the semiconductor ecosystem.

## Impact of Opensourse and Open Standard on Business and Commerece

Open-source EDA tools like Yosys, GTKWave, Ngspice, and OpenLane, combined with open-standard ISAs like RISC-V, are reshaping the business and economic landscape of semiconductors.
For startups, the most obvious benefit is the drastic reduction in entry barriers: costly proprietary EDA licenses and IP royalties are often prohibitive, but open-source ecosystems allow small teams to prototype SoCs and ASICs with minimal upfront cost. 
This democratization encourages innovation, enabling startups, universities, and even individuals to participate in chip design. 
Moreover, the use of open-standard ISAs like RISC-V ensures global interoperability while allowing startups to customize processors for niche applications, giving them flexibility that ARM or x86 ecosystems traditionally restrict.
However, leveraging open tools comes with challenges. Startups face ecosystem immaturity, lack of comprehensive support, and difficulty integrating open-source tools into industrial-grade flows.
The way forward lies in building stronger collaborative ecosystems—government funding, consortium-backed development, and industry-academia partnerships can help mature open-source EDA stacks.

## Market Data Framework.

<img width="1400" height="1400" alt="tam_to_sam_pie" src="https://github.com/user-attachments/assets/baf412cc-b1ae-4a71-b8a9-325f1f48bbb6" />  <img width="1400" height="1400" alt="sam_to_som_pie" src="https://github.com/user-attachments/assets/9d0d77b3-b392-4ab5-9649-cb217cd41e9c" />


The TAM→SAM and SAM→SOM Pie Charts illustrate how startups can position themselves in the semiconductor ecosystem. While the Total Addressable Market (TAM) is massive at USD 681B+, the Serviceable Available Market (SAM) for open-source and RISC-V solutions is a smaller but fast-growing USD 2–3B. Within this, the Serviceable Obtainable Market (SOM) represents realistic capture opportunities of USD 100–300M for startups targeting IoT, AI, and niche applications.

## Impact of Opensourse and Open Standard on Geopolitics
Open-source EDA tools (Yosys, Ngspice, OpenLane) and open-standard ISAs like RISC-V have the potential to reshape geopolitics in the same way OPEC and crude oil shaped global power in the 1960s. 
In today’s world, semiconductors are the “new oil” — central to defense, AI, communications, and economic competitiveness. Traditionally, access to advanced semiconductor design was locked behind expensive proprietary tools (Synopsys, Cadence, Mentor) and proprietary ISAs (ARM, x86), both of which are controlled largely by U.S. and its allies with the exception of French republic which very frequently sides with its own strategic autonomy rather than being reticent to US Policies.
This has given the U.S. enormous leverage as seen in sanctions on China,Russia where restricting access to EDA software or processor IP can halt entire industries.
Open-source ecosystems weaken this monopoly and redistribute power. With tools like Yosys, OpenLane, and standards like RISC-V, countries under sanctions can still continue chip design without relying on U.S.-licensed IP.
This shifts the balance: instead of a few Western firms acting as gatekeepers, innovation is now democratized. 
For emerging economies, open ecosystems mean participation in the semiconductor supply chain without paying billions in licensing costs, reducing dependency and enabling sovereign design capability.


#### Thank you for bearing with me while i took a quick detour to touch on multiple aspects of Semiconductors that are generally overlooked by engineers. 
#### It is just that i strongly believe that the key problem in todays industry is not expertise but the ability to think in cross functional domains.
India’s semiconductor ecosystem is fractured by domain silos.
But here’s the deeper issue:
Engineers rarely understand the law.
Lawyers don’t understand semiconductors.
And neither group understands how international treaties, export controls, and geopolitical shifts shape supply chains, choke points, and fab location logic.
and while investors understand international treaties, Business Law and Geopolitics; they genrally don’t understand technology risk, semiconductor fabrication issues. 
Until we cultivate multi-disciplinary thinkers who understand chip design, semiconductor tech, IP law, finance, and geopolitical risk,
India will be assembling parts of a machine it doesn’t fully control.
We need systems thinkers who can move between disciplines and align them.

#### So without much Futher Ado Lets get down to Actual Engineering.

## Weekly Progress and Implementation

| Task | Description | Status |
|------|-------------|---------|
| [**Task 0**](Week0/Task0/README.md) | 🛠️ [Tools Installation](Week0/Task0/README.md) — Sucessfully Installed **Iverilog**, **Yosys**, and **gtkwave** | ✅ |


## 🙏 Acknowledgment

I would Like to acknowledge Kunal Ghosh and his team from VSD for the Opportunity to work on this Tapeout Program.

I would Also like to Thank Prof Rajat Moona and his Team From IIT Gandhinagar For their Support to this noble initiative.

I would also extend thanks to SCL Chandigarh and Chip Foundry for their immense Support for this endevour.
