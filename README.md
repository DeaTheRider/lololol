
Install with pip:
```
cd GRIT
pip install -e .
```

Extract the [inD](https://www.ind-dataset.com/) and [rounD](https://www.round-dataset.com/) datasets into the `GRIT/data` directory.

Apply patches to the lanelet2 maps:

```
cd lanelet_map_patches
python patch_lanelet_maps.py
```

Preprocess the data and Extract features:

```
cd ../core
python data_processing.py
```

Train the decision trees:

```
cd ../decisiontree
python train_decision_tree.py
```

Calculate evaluation metrics on the test set:

```
cd ../evaluation/
python evaluate_models_from_features.py
```

Show animation of the dataset along with inferred goal probabilities:

```
python run_track_visualization.py --scenario heckstrasse --goal_recogniser trained_trees
```

## References
[1] C Brewitt, B Gyvenar, S Garcin, SV Albrecht, "GRIT: Fast, Interpretable, and Verifiable Goal Recognition with Learned Decision Trees for Autonomous Driving", in IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 2021

[2] SV Albrecht, C Brewitt, J Wilhelm, B Gyvenar, F Eiras, M Dobre, S Ramamoorthy, "Integrating planning and interpretable goal recognition for autonomous driving", in Proc. of the IEEE International Conference on Robotics and Automation (ICRA), 2021
