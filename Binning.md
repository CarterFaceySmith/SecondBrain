# Binning

used in [[Data Preparation]]

binning is converting a continuous feature (ie stats on an effectively infinite spectrum) into categorical features (ie can be categorised you moron)

how to do this magical procedure:
- define a series of ranges (bins) that correspond to the levels of the new categorical feature
- binning types cos how you do this shit matters, more bins = more specific and less = you may lose data:
	- equal width binning: splits the range of feature vals into b bins each of size range/b
	- equal frequency binning: sorts continuous vals into ascending order then places equal num of instances into each bin from bin 1 (num of instances/b)
