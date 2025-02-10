# Meeting Log

## Date
February 5, 2025

## Video Recording
[Zoom Recording](https://kyoto-u-edu.zoom.us/rec/share/KV5yTnCsJfEVOlG_5zSLDd9_3NZqXBJnfUY7GHJB0aZ8hbd3_qDyNXlXT7kRIK85.aGNvk-dGSXeLBoeU)
(Passcode shared via email)

## Participants
- S. Han (SH)
- R. Akutsu (RA)
- Y. Hayato (YH)
- K. Okumura (KO)
- B. Xu (BX)

## Comments by Akutsu-san

### Uncertainty in Hadron-Nucleus Inelastic Interaction Cross-Section
**RA**: Geant4 uses a common hadron-nucleus inelastic cross-section dataset, but the draft does not seem to address its uncertainty. Given the absence of relevant data in the energy region for oxygen, the uncertainty may be significant.

**SH**: I believe we have at least two cross-section datasets in the SI models: 
1. Bertini/HETC/CALOR table.
2. Geant4's Barashenkov table. 

This should provide some coverage of the inelastic interaction cross-section uncertainty, but I will further investigate which inelastic cross-sections are used in the SI models and determine how to assign uncertainty to them.

### Why Does Geant4 Precompound Predict Fewer Neutron Ejections?
**RA**: What do you mean by "data-driven" in the context of Geant4 Precompound?

**SH**: The Geant4 Precompound model claims to use a nucleon absorption cross-section parameterization fitted to more recent experimental data, which was unavailable when Bertini's native de-excitation model (Dostrovsky, 1958) was developed.

**RA**: The Fermi breakup process should be called more often (even for a 100 MeV KE neutron projectile) compared to the statistical evaporation process in question. Additionally, level density parameters significantly affect nucleon emission and should be worth mentioning in the paper.

**SH**: Understood. I will check these points and include them in the paper.

### Why Is the Measured Slope in SK6 Larger Than in SK4/5?
**RA**: Differences in prompt lepton selection efficiencies between SK4/5 and SK6 might explain the discrepancy.

**SH**: I reviewed SK4/5 and SK6 selection criteria, including PID, NRing, etc., and found no significant differences. X-axis errors might be contributing factors; I will investigate further.

## Comments by Hayato-san

### Energy Range Where INCL Deviates from Data
**YH**: It would be useful to analyze which particles, at what momenta, contribute most to the total neutron prediction. This will help us decide which model is appropriate for each particle and momentum range.

**SH**: Agreed. My current understanding is that INCL's neutron production prediction from pion-nucleus interactions primarily drives the observed multi-ring deviation from data. I have contacted Jean-Christophe David, one of the developers, for clarification. (A later discussion with Abe-san suggests that INCL uses a smaller pion absorption cross-section than Bertini. The reason for this is unclear.)

## Comments by Benda

### Geant4 Error on Hydrogen Thermal Motion and Its Effect in Pure Water
**BX**: Can the impact of this error be observed through the neutron capture time distribution in pure water for SK4/5?

**SH**: This error has minimal impact in pure water since no competing element is present. It becomes relevant only for intermediate Gd concentrations (0.01w%), where captures on H and Gd occur on the same scale. This effect is negligible in other Gd-loaded experiments with 0.1 w%. While we have AmBe data in SK4/5, the limited number of measurements results in large uncertainties, making it difficult to discern hydrogen thermal motion effects. Additionally, our pure water simulations use Geant3/skdetsim, which neglects nuclear thermal motion altogether.

## Proposed Timeline
- **Feb 12 - Feb 16**: 2nd committee circulation (4 days)
- **Feb 17 - Feb 24**: 1st ATMPD circulation (1 week)
- **Feb 27 - Mar 13**: 1st SK circulation (2 weeks)
- **Mar 17 - Mar 24**: 2nd SK circulation (1 week)
- **By Mar 31**: Final draft update, upload to arXiv, submit to PRD