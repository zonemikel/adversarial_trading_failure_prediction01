In trying to use lstm I had several problems. 
1.) forecasting is more of a regression problem and not a classification problem, regression problems art not well supported in ART.

0.) Accuracy was very low on real data

2.) Even after making it a classification problem when using lstm as the first layer I was able to achive high accuracy but ART was still unable to create attacks against a model with lstm layers. This can be seen in proj_lstm_attack_failed.ipynb
InvalidArgumentError: Node 'gradients/lstm_10/while_grad/lstm_10/while_grad': Connecting to invalid output 101 of source node lstm_10/while which has 101 outputs. Try using tf.compat.v1.experimental.output_all_intermediates(True).

After using a pure DNN it was required the outputs be one hot encoded, as ART would not accept sparce categorical values

references:
http://diva-portal.org/smash/get/diva2:1213449/FULLTEXT01.pdf
