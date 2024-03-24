# DRS_Parsing_with_SRL
Code and data for paper "Improving DRS Parsing with Separately Predicted Semantic Roles" at CSTFRS workshop https://aclanthology.org/2021.cstfrs-1.3.pdf 

Since the backbone of the DRS notation is basically an SRL annotation of the underlying predicats, we suggest that predicting the SRL labels separately might improve the parsing performance. 

An advantage of our approach is that it is very flexible: it can be applied
on top of any DRS parsing model without having to alter or retrain the model itself.

### Convert the gold DRSs to SRL labels in order to train them separately

In the first step, you have to convert DRSs to SRL labels.

There are two ways of converting DRSs to SRL. We described both in our [workshop paper](https://aclanthology.org/2021.cstfrs-1.3.pdf)

#### Syntax-agnostic DRS-to-SRL conversion based on DRS notations

For a syntax-agnostic conversion, please check the instructions in this repository:

https://github.com/texttheater/tbsp

#### Syntax-aware DRS-to-SRL conversion based on the CCG derivations

This conversion is trickier than the syntax-agnostic one. Please contact [Gosse Minnema](https://github.com/gossminn) to help you with the conversion.

### Train a neural network to predict SRLs

You can use any model of your choice to train an SRL labeler. We have showed in our paper that the performance of the SRL labeling system is the bottleneck of our approach. Thus it can be helpful to use the most recent neural model to get the best SRL results.

You can find our data split in the folder [data](https://github.com/TaniaBladier/DRS_Parsing_with_SRL/tree/main/data)

### Use predicted SRLs for your DRS parser

Once you have predicted the SRLs, you can try to use them for the output of your DRS parser. This might improve your parsing results. Please follow the steps described in this repository:

https://github.com/RikVN/SRL-DRS