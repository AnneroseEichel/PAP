# A Dataset for Physical and Abstract Plausibility and Sources of Human Disagreement (PAP)

This folder contains the dataset presented in the paper "A Dataset for Physical and Abstract Plausibility and Sources of Human Disagreement" at LAW-XVII 2023 at ACL 2023. 

We present two dataset versions with ```dataset.tsv```: including label aggregations based on annotation post-processing as described in §4.2.
Specifically, we provide (a) strict majority voting including a disagreement label ('unsure') for both multi-class and binary setups for 1,733 events.
Probabilistic aggregations using MACE (Hovy et al., 2013) include aggregated silver labels based on raw annotations without post-processing, i.e., labels for 2,160 events.

The file ```dataset.tsv```: contains the following information:
- event: the event target as presented to human annotators
- original_label: the original label based on dataset construction as described in §3 in the paper; events can either be ('plausible') or implausible ('implausible')
- abstractness_combination: the abstractness combination an event belongs to
- rating: raw, i.e., non-aggregated but post-processed plausibility ratings as provided by the annotators
- majority_multiclass: strict majority votings (>=70%) for a multi-class setup on a scale from 1 to 5 with 1 denoting implausibility, 5 referring to plausibility, and ratings of 3 used for filtering out invalid submissions; in case of no clear majority, a label denoting disagreement ('unsure') is assigned to reflect conflicting perspectives of annotators
- distribution_multiclass: class distributions for a multi-class setup on a scale from 1 to 5 with 1 denoting implausibility, 5 referring to plausibility, and ratings of 3 used for filtering out invalid submissions
- majority_binary: strict majority votings (70% and more) for a binary setup where 0 denotes implausibility and 1 denotes plausibility; in case of no clear majority, a label denoting disagreement ('unsure') is assigned to reflect conflicting perspectives of annotators
- distribution_binary: class distributions for a binary setup where 0 denotes implausibility and 1 denotes plausibility

The folder ```mace_aggregations```: contains the following files and information.

The file ```aggregated_predictions.tsv```: encompasses:
- event: the event target as presented to human annotators
- original_label: the original label based on dataset construction as described in §3 in the paper; events can be either plausible ('plausible') or implausible ('implausible')
- multi-class_prediction: predicted multi-class labels using MACE (Hovy et al., 2013) using standard parameters; labels range from 1 to 5 with 1 denoting implausibility, 5 referring to plausibility, and ratings of 3 used for filtering out invalid submissions
- binary_prediction: predicted binary labels using the MACE implementation by Hovy et al., 2013 using standard parameters; 0 denotes implausibility and 1 denotes plausibility

```4- and 2-class-dist.predictions```:
- contain distributions for a multi-class and binary setup
Distributions are provided per label with each row referring to distributions for one event.
Events are provided in the corresponding order in aggregated_predictions.csv.
An example is shown below with each column containing a predicted label and the corresponding distribution separated with a whitespace.

5.0 0.935000961509369	2.0 0.023182269455259166	4.0 0.02100019482697004	1.0 0.020816574208401856
