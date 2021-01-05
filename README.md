# Centralization of all backups. 

This repository allows us to centralize all our saved weights, entire models and training history.

------

## Requierements

This repository having rather heavy elements (more than 100 mo) it is necessary to use git lfs to make modifications. The clone can be done without problems with a classics git. 

-----

## Organisation and man

This repo contains 4 directory :

> *In the given pieces of code tensorflow is simplified to tf and numpy to np.*

* history : all the history object of a model training. Save in numpy format (.npy). To load use `np.load('historique.npy', allow_pickle='TRUE').item()`.

* FullModels : Format to save all the characteristics of a model : architecture, weigths, optimiser, loss. To load use `tf.keras.models.load_model(path)`.

* Weights : Format to save only the weigths of a model (as .h5 keras format). To use it you must built or use exactly the same model as us. Use `tf.keras.load_weigths(path)` to load.

* Features : For the pre-trained model we have mostly used the extraction features method and and in order to be able to test several dense networks on a single pre-training model we did the extraction in a first step and store the features to be able to reuse them several times. The format is the numpy save format so to use it `np.load(path)`.