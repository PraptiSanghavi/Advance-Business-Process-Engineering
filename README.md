# Advance-Business-Process-Engineering
INFO 7374: Business Process Engineering II is an entry-level course focused on product management, supply chain, and modern delivery methods that provides students with an integrated view of how products are conceived, built, and delivered in today’s fast-paced business environment. The course begins with the fundamentals of product management, exploring the role of the product manager, the product lifecycle, and strategies for identifying and validating customer needs. Students learn to conduct market analyses, craft compelling product visions, and build roadmaps aligned with business goals. Practical exercises in feature prioritization, Agile simulation, and metrics development help students bridge strategy with execution. Importantly, no prior coursework in process modeling or INFO 7260 is required, making this course accessible to those new to product or process management.

The course then shifts focus to the broader value chain, examining how modern supply chains are designed, optimized, and disrupted by emerging technologies. Students analyze real-world case studies on digitally enabled logistics, AI-driven predictive analytics, and global supply chain risk management. The final module explores modern delivery strategies, introducing Agile, Lean, DevOps, and CI/CD practices to illustrate how high-performing organizations accelerate value delivery. By combining product management, supply chain strategy, and digital delivery methods, this course equips students with the knowledge and skills to drive innovation from concept to customer across diverse industries.

Instructor Name: Mr. Shannon Pettiford, M.S., PMP, PMI-ACP\
Instructor E-mail: s.pettiford@northeastern.edu  

## Instructor's Profile:
Shannon Pettiford, M.S., PMP, PMI-ACP is a seasoned professional with expertise in program and project management, business process improvement, and operations management. His career spans decades, managing global projects and programs are focused on digital marketing, information technology, human resources, finance, and strategic initiatives.  

He is a member of the Project Management Institute (PMI.org) and holds the Project Management Professional (PMP), Agile Certified Practitioner (PMI-ACP), and Certified Scrum Master (CSM) certifications. He obtained his undergraduate degree in Computer Science from East Tennessee State University and earned his master's degree in Project Management from Northeastern University, with a concentration in program and portfolio management. His continued research focuses on risk management, business process development, strategic initiatives, and business relationship management. 
 
Mr. Pettiford's career spans various positions in the information technology field as a web developer, software programmer, systems analyst, and business analyst. His experience working in cross-functioning roles in Fortune 500 organizations provides him with keen insights and lessons learned in finance, information technology, marketing, and logistics. He works full-time at Boston Consulting Group as an IT Program Manager focused on office expansions, M&A, business acquisitions, and business engagement models globally. With a successful track record in program and project management, Mr. Pettiford delivers on organizational performance improvement, cost reduction methodologies, and business transformation.
 
Mr. Pettiford also teaches graduate-level courses in project management at Northeastern University, the University of Kansas, and the Harvard Extension School.


# CHEE 5397/6397 Homework 5 Solution

## 1. Fundamentals of Steam Methane Reforming

### a. Independent Reactions

We considered the following three reactions:
1. $CH_4 + H_2O \rightarrow CO + 3H_2$
2. $CH_4 + 2H_2O \rightarrow CO_2 + 4H_2$
3. $CO + H_2O \rightarrow CO_2 + H_2$

**Atomic Matrix Approach:**
The atomic matrix (Rows: C, H, O; Cols: $CH_4, H_2O, CO, H_2, CO_2$) has a rank of 3.
Number of species = 5.
Number of independent reactions = $N_{species} - Rank = 5 - 3 = 2$.

**Stoichiometric Matrix Approach:**
The stoichiometric matrix constructed from the three reactions has a rank of 2.
Thus, there are **2 independent reactions**.

### b. Standard Heat of Reactions (298.15 K)

Using standard enthalpies of formation calculated from NIST Shomate coefficients:
- $\Delta H_{f, CH_4}^\circ = -74.87$ kJ/mol
- $\Delta H_{f, H_2O}^\circ = -241.83$ kJ/mol
- $\Delta H_{f, CO}^\circ = -110.52$ kJ/mol
- $\Delta H_{f, CO_2}^\circ = -393.53$ kJ/mol
- $\Delta H_{f, H_2}^\circ = 0$ kJ/mol

Calculated Heats of Reaction:
1. $\Delta H_{rxn,1}^\circ = 204.11$ kJ/mol (Endothermic)
2. $\Delta H_{rxn,2}^\circ = 162.24$ kJ/mol (Endothermic)
3. $\Delta H_{rxn,3}^\circ = -41.86$ kJ/mol (Exothermic)

### c. Temperature-dependent Specific Heat ($C_p$)

The temperature-dependent heat capacities were obtained using the Shomate equation from NIST Webbook:
$C_p^\circ(T) = A + B t + C t^2 + D t^3 + E/t^2$ where $t = T/1000$.
Coefficients were sourced from NIST for all species ($CH_4, H_2O, CO, H_2, CO_2$).

### d. Temperature Variation of Standard Heat of Reaction

The heat of reaction at temperature T was calculated using:
$\Delta H_{rxn}(T) = \Delta H_{rxn}^\circ(298.15) + \int_{298.15}^T \Delta C_p^\circ dT$

![Heat of Reaction vs Temperature](heat_of_reaction.png)

**Observation:**
- Reaction 1 (SMR) and Reaction 2 are strongly endothermic throughout the range.
- Reaction 3 (WGS) is moderately exothermic.

### e. Equilibrium Constants

The equilibrium constant $K^{eq}$ is defined as:
$K^{eq}(T) = \exp\left(\frac{-\Delta G^\circ(T)}{RT}\right)$

In terms of activities $a_i$:
$K^{eq} = \prod a_i^{\nu_i}$

Assuming ideal gas behavior ($a_i = y_i P/P^\circ$), the equilibrium constant in terms of mole fractions $K_y^{eq}$ is:
$K_y^{eq} = K^{eq} P^{-\Delta \nu}$

For Reaction 1 ($\Delta \nu = 2$):
$K_{y,1}^{eq} = \frac{y_{CO} y_{H_2}^3}{y_{CH_4} y_{H_2O}} = K_1^{eq} P^{-2}$

---

## 2. Single Reaction Equilibrium (Eq. 1)

We determined the equilibrium conversion of methane for the reaction $CH_4 + H_2O \rightarrow CO + 3H_2$ under different conditions.

**Conditions:**
- Temperature: 400 - 1200 K
- Feed: Methane and Steam in ratio 1:W

![Equilibrium Conversion Problem 2](problem_2_conversion.png)

**Analysis:**
- **Effect of Temperature:** Conversion increases with temperature for all cases. This is consistent with Le Chatelier's principle for an endothermic reaction ($\Delta H > 0$).
- **Effect of Pressure (Case a vs c):** Comparing W=3 at 30 bar (Case a) vs 10 bar (Case c), conversion is higher at lower pressure (10 bar). This is expected as the reaction produces more moles of gas ($\Delta \nu = +2$).
- **Effect of Steam Ratio (Case a vs b):** Comparing P=30 bar with W=3 (Case a) vs W=1 (Case b), conversion is higher with excess steam (W=3). Adding a reactant shifts equilibrium to the right.

---

## 3. Multi-Reaction Equilibrium (Eq. 1 & 2)

We solved for the simultaneous equilibrium of:
1. $CH_4 + H_2O \rightarrow CO + 3H_2$
2. $CH_4 + 2H_2O \rightarrow CO_2 + 4H_2$

**Conditions:**
- P = 30 bar
- W = 3 (Feed ratio $H_2O:CH_4$)

![Multi-Reaction Equilibrium Problem 3](problem_3_multireaction.png)

**Results:**
- **Total Methane Conversion:** Approaches 100% at high temperatures (>1000 K).
- **Product Distribution:**
    - At lower temperatures (< 800 K), $CO_2$ is the dominant carbon product (via Reaction 2 or WGS).
    - At higher temperatures (> 1000 K), $CO$ yield increases significantly while $CO_2$ yield decreases. This is because the Water-Gas Shift reaction ($CO + H_2O \leftrightarrow CO_2 + H_2$) is exothermic, so higher temperatures favor the reverse reaction (production of CO).

