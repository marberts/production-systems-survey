# Research Plan

**Authors**:

-   Collin Brown (@collinbrown95)
-   Steve Martin (@marberts)

**Overview**: The purpose of this document is to articulate the research questions we plan to answer with the contents of `survey-questions.md`. Additionally, this document can serve as a "checklist" to make sure we are collecting sufficient data to answer these questions.

## Section 2: Archetype Survey Questions

### Question 1: Monolithic or Modular

-   One of our hypotheses is that **stream aligned teams** *should* cut across GSBPM steps, but **systems** *should not* cut across GSBPM steps.
    -   The rationale for this is that systems being siloed represents **low coupling** which **improves maintainability**, whereas teams that are siloed creates **communication overhead** due to **lack of shared context**.

### 1.1 Approximately how many **distinct** systems exist for each GSBPM step?

-   Are certain GSBPM steps prone to centralizing the system implementation in a small number of systems (or the opposite)?

#### 1.2: For **any** of your systems, is it the case that the **same system** handles more than one GSBPM step?

-   Do systems try to handle many distinct GSBPM concerns or do they try to do "one thing really well".

#### 1.2.1 `(if 1.2== 'yes')` In the event that systems handle more than one GSBPM step, please indicate which GSBPM steps are handled by the same system.

-   If systems cut across GSBPM steps, which steps do they tend to cut across?

#### 1.2.2 `(if 1.2 == 'yes')` As measured by total expenditure weight, approximately what share of your outputs are handled by **all** of the systems in 1.2.1?

-   Do systems that cut across GSBPM steps account for a large share of the CPI output?

#### 1.3 Fraction of Cases Handled

-   If one system handles the majority of cases, this represents a central bottleneck in the GSBPM flow. One of our hypotheses is that points of centralization are correlated with slower lead time.

### Question 2: Corporate IT or DIY

#### 2.1 For each GSBPM step, how many systems are maintained by each of the following teams?

-   Is it the case that domain-aligned teams tend to maintain systems for certain GSBPM steps, whereas other teams (e.g., corporate IT) tend to maintain systems for other GSBPM steps?

### Question 3: Analysis of a Group of Systems

-   Questions 1 and 2 can only be analyzed independently. This question tries to jointly ask qustions about system topology **and** team topology **for a representative group of systems**.

#### 3.0 Selection a "representative system"

-   This is important because how the respondent interprets the meaning of a "representative system group" defines the kind of inferences we can make from this.

#### 3.1 System boundary crossing for your representative system group

#### 3.2 Team maintenance for your representative system group

We can't perfectly re-create the NSO's systems diagram from the questions alone, but we can characterize several important details about the joint team/system topology for a representative system in the NSO.

![gsbpm-highlight](./diagrams/gsbpm-systems-3-highlight.drawio.svg)

For the example answers to questions 3.1 and 3.2, we know the system group can be characterized as shown below.

![gsbpm-recreate](./diagrams/gsbpm-recreate.drawio.svg)

We aren't able to infer the cardinality of inputs, the exact count of system groups that have more than one system, or the edges that connect system groups with more than one system.

However, we **can** infer:

-   The existence of single large systems.
-   The team who **maintains** each system group.
-   Situations where one system feeds many systems or many systems feed one system.
-   Points of centralization/decentralization in the GSBPM flow.
-   Cases where **systems** do or do not cross GSBPM boundaries.
-   Cases where **teams** do or do not cross GSBPM boundaries.

### Question 4: Open Source Data Science Tools

-   One of our hypotheses is that domain aligned teams who develop systems within the open source data science tooling ecosystem are able to deliver faster.

#### 4.1 For any of the GSBPM steps in this survey, do you use any open source libraries for making price indexes as part of your system?

-   One of our hypotheses is that there is not a standard price index methods package for production use because of system integration challenges.

#### 4.1.1 `(if 4.2 == 'no')` For what reason(s) do you not use any open source libraries?

#### 4.2 For each GSBPM step, are your system(s) made in-house or do you use commercial off the shelf (COTS) software?

-   Are certain GSBPM steps prone to adopting COTS vs. in house software?

#### 4.3 For each GSBPM Step, which programming languages and statistical tools do you use in your system implementation?

#### 4.3.1 **Version Control** Tools

-   Since these teams are effectively maintaining software products, are they following software development best practices? E.g., it is extremely difficult to maintain production software without version control tooling.

#### 4.3.2 **Project Management Software**

-   Do teams use specialized software for managing complex projects? Is this correlated with slow/fast lead times?

#### 4.3.3 **Programming Languages**

-   This question gives a hint about whether systems are developed within the data science ecosystem, the "corporate" eceosystem, or a particular COTS ecosystem like SAS or Stata.

#### 4.3.4 **Open Source Packages**

#### 4.3.5 **Commercial Software**

#### 4.3.6 **Cloud Provider/Infrastructure**

-   Curious if organizations that adopt cloud have better or worse outcomes, or if this doesn't really play a role in outcomes.

### Question 5: New or Well-Established

-   One of our hypotheses is that older "legacy" systems are more challenging to maintain, whereas newer systems are likely easier to maintain.
    -   We expect to see this being correlated with certain business outcomes like faster lead times.

#### 5.1 Age of System

#### 5.2 Frequency of Updates

-   A system could be updated frequently either because it's very easy to make changes, or it's always broken.
-   A system could be updated infrequently either because it rarely needs to change, or it's extremely difficult and time consuming to make changes.

### Question 6: Team Structures

-   One of our hypotheses is that either too many or too few individuals participating in system changes will lead to poor outcomes.
    -   If too many people need to participate, this leads to an "everyone needs to talk to everyone about every change" problem, which creates a ton of communication overhead and slows things down.
    -   If too few people are involved (e.g., one person in the extreme), this could be correlated with poor outcomes too, such as lack of capacity/expertise/things breaking often because there's not enough people to maintain systems.

#### 6.1 Approximately how many individuals need to participate in a **small change** to the system?

-   We expect that high performing teams should not need to involve too many people in small system changes.

#### 6.2 Approximately how many individuals need to participate in a **large change** to the system?

-   We expect that high performing teams probably need to involve a few more people in large changes than small changes, but this number should still not be too large in order to prevent too much communication overhead.

## Section 3: Business Outcomes

-   These questions represent the "dependent variables" of our analysis, they are the outcomes we want to correlate with the archetypes we define in Section 2.

### Question 1: Adoption of Alternative Data

-   This is generally considered a "good" outcome in contrast to using entirely field collected data.

#### 1.1 Do you currently make use of alternative data in **any** of your production systems?

#### 1.1.1 `(1.1 == "No")` Do you intend/want to make use of alternative data in the future?

-   Curious if any NSOs just don't need to bother with this, and if so, how many?

#### 1.1.2 `(1.1 == "Yes") or (1.1.1 == "Yes")` What are the main challenges you face in adopting alternative data?

-   What archetypes are correlated with each kind of challenge?

#### 1.2 `(1.1 == "Yes")` Approximately what share of your price statistic by expenditure weight **is currently** comprised of alternative data?

#### 1.2.1 `(1.1 == "Yes")` Approximately what share of your price statistic by expenditure weight **would you like to be** comprised of alternative data in your target state?

-   1.2.1 minus 1.2 defines an **implementation gap**. Which archetypes are **correlated with a high implementation gap**?

#### 1.2.2 `(1.1 == "Yes")` Approximately what share of your alternative data price statistics are comprised of each of the following methodologies?

### Question 2: Flexible or Rigid (Lead Time)

#### 2.1 How long do changes take?

-   This is probably the main DORA metric that applies to price statistics systems. Put simply: "How long does it take to get stuff done?"

#### 2.1.1 Small Changes

#### 2.1.2 Large Changes

### Question 3: Challenges in Developing Production Systems

-   The purpose of this question is to see if there is any correlation between certain archetypes and certain kinds of system development/maintenance challenges.