# lego-loam-mc
source code of the papre: An Improved Simultaneous Localization and Mapping Method base on LeGO-LOAM and Motion Compensation
# how to use
1.download ./ws_lego_loam_mc_github.rar and unzip it to your ros workspace
2.change the traj output directory in LeGO-LOAM/src/mapOptimation.cpp at line 830 to your own directory
3.catkin_make this package
4.source devel/setup.bash
5.roslaunch lego_loam run.launch
#note!
1.The number of true values of kitti's path data is inconsistent with the number of frames. You need to manually change the number of paths automatically exported by the code. For example, there are 4541 ground truth values in the 00 sequence. Set trajNum=4541 at line 53 of the LeGO-LOAM/src/mapOptimation.cpp.
2.Note that in the last closed loop of the 00 sequence (returning to the starting point), the path ends without being updated in time, which may cause the last few values of the estimated path to be wrong. Please delete the wrong data manually, and then Replace them with the last correct value.
