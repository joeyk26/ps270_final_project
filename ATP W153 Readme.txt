PEW RESEARCH CENTER
Wave 153 American Trends Panel 
Dates: Aug. 26 - Sept. 2, 2024
Mode: Web and CATI
Sample: Full panel
Language: English and Spanish
N=9,720

***************************************************************************************************************************
NOTES

This dataset contains the variables corresponding to questions asked in the survey. It also contains administrative data, such as the main production weight and completion date. There are several types of additional variables that we can typically provide upon request, if they were created for published reporting: 
(1) Researcher-created variable(s) reflecting how we categorized responses to open-ended questions. We do not release verbatim answers to open-ended questions, in the interest of protecting panelist anonymity.
(2) Researcher-created variables needed to replicate published analysis (e.g., an index using several questions).
(3) Special weights needed to replicate published analysis. The main production weight is included in the public dataset. Special weights refer to those used for unusual, bespoke analysis. We can provide existing special weights upon request so long as the analysis they support does not pose a risk to panelist anonymity.

For a small number of respondents with high risk of identification, certain values have been randomly swapped with those of lower risk cases with similar characteristics.

VOTEGEN24
In the dataset, VOTEGEN24_W151 is filtered on those who say they are registered to vote (F_REG=1).

HORSE_W153
The W153 dataset contains the HORSE_W153 created variable indicating 2024 presidential vote preference based on registered voters.

VALVOTE2016_W78/VOTECHOICE2016_VAL_W78
The W153 dataset contains two variables from W78 indicating validated voter turnout and vote choice in the 2016 election. 

F_VALVOTE2020
The W153 dataset contains the F_VALVOTE2020 variable measuring validated voter turnout in the 2020 election. For details on how this variable was created and instructions for its use, please refer to this essay: https://medium.com/pew-research-center-decoded/validating-2020-voters-in-pew-research-centers-survey-data-ddb2e2a3c50. 

PARTY/PARTYLN/PARTYSTR/PARTYLNCLOSE
PARTY, PARTYLN, PARTYSTR, and PARTYLNCLOSE can be found in the W149 dataset with an “F_” preceding the question name.

SNSUSE
SNSUSE was asked on W153 as a filter for follow up questions about social media use. For the Center's official estimates about social media use in the U.S., please refer to the National Public Opinion Reference Survey (NPORS) Social Media Fact Sheet: https://www.pewresearch.org/internet/fact-sheet/social-media/

***************************************************************************************************************************
WEIGHTS 


WEIGHT_W153 is the weight for the sample. Data for all Pew Research Center reports are analyzed using this weight.
WEIGHT_W78_W153 is a specialty longitudinal weight that should be used to replicate findings from the report, “In Tied Presidential Race, Harris and Trump Have Contrasting Strengths, Weaknesses.” 


***************************************************************************************************************************
Releases from this survey:

September 9, 2024, "In Tied Presidential Race, Harris and Trump Have Contrasting Strengths, Weaknesses"
https://www.pewresearch.org/politics/2024/09/09/in-tied-presidential-race-harris-and-trump-have-contrasting-strengths-weaknesses/

September 17, 2024. “Americans view Walz more positively than Vance, but many aren’t familiar with either VP nominee.” 
https://www.pewresearch.org/short-reads/2024/09/17/americans-view-walz-more-positively-than-vance-but-many-arent-familiar-with-either-vp-nominee/

September 19, 2024. “Americans in both parties are concerned over the impact of AI on the 2024 presidential campaign.” 
https://www.pewresearch.org/short-reads/2024/09/19/concern-over-the-impact-of-ai-on-2024-presidential-campaign/ 

September 25, 2024. “How Voters Expect Harris’ and Trump’s Policies to Affect Different Groups in Society.” https://www.pewresearch.org/politics/2024/09/25/how-voters-expect-harris-and-trumps-policies-to-affect-different-groups-in-society/ 

September 25, 2024. “Majority of Americans continue to favor moving away from Electoral College.” 
https://www.pewresearch.org/short-reads/2024/09/25/majority-of-americans-continue-to-favor-moving-away-from-electoral-college/

September 30, 2024. “Military veterans remain a Republican group, backing Trump over Harris by a wide margin.” 
https://www.pewresearch.org/short-reads/2024/09/30/military-veterans-remain-a-republican-group-backing-trump-over-harris-by-wide-margin/ 

October 17, 2024. “Key facts about union members and the 2024 election.” 
https://www.pewresearch.org/short-reads/2024/10/17/key-facts-about-union-members-and-the-2024-election/ 

***************************************************************************************************************************

SYNTAX

SYNTAX FOR COMPUTING HORSE_W153: 

compute HORSE_W153 = $sysmis.
do if F_REG=1.
if (VOTEGEN24_W153=1 or VOTEGEN24_LEAN_W153=1) HORSE_W153 = 1.
if (VOTEGEN24_W153=2 or VOTEGEN24_LEAN_W153=2) HORSE_W153 = 2.
if (VOTEGEN24_LEAN_W153=4) HORSE_W153 = 4.
if (VOTEGEN24_LEAN_W153=99) HORSE_W153 =99.
end if.
VARIABLE LABELS HORSE_W153 'Combined horserace variable for W153'.
VALUE LABELS HORSE_W153 1 'Trump/Lean Trump' 2 'Harris/Lean Harris' 4 'Lean toward none' 99 'Refused VOTEGEN24_LEAN'.
EXECUTE.




