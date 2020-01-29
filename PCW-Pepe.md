# List of issues

+ First issue I encountered was not finding the Project folder. To solve so, I simply downloaded the master branch rather than the latest release with the following command:
```
git clone --branch latest_release https://github.com/Unity-Technologies/ml-agents.git
```
+ Afterwards, I had some issues running the program because it told me there was no place to save the results. I resolved it by creating a summaries folder as it said that's where it is supposed to be saved.
+ I realized I hadn't properly installed the ml-agents and ml-agents-env packages because I hadn't set up properly the current directory.

### Roll-a-ball:
![image](https://drive.google.com/file/d/1rn7yfHeVZ9zw_aWru5eh08Z9xxDThv3a/view?usp=sharing)

### Balance Training

Video: https://drive.google.com/file/d/1nLS_ok7IAiNfVDUaA0_ggJzmyDM35DXe/view?usp=sharing

Training output:
```
Version information:
  ml-agents: 0.14.0.dev0,
  ml-agents-envs: 0.14.0.dev0,
  Communicator API: API-14-dev0,
  TensorFlow: 1.13.1
INFO:mlagents_envs:Listening on port 5004. Start training by pressing the Play button in the Unity Editor.
INFO:mlagents_envs:Connected new brain:
3DBall?team=0
INFO:mlagents.trainers:Hyperparameters for the PPOTrainer of brain 3DBall: 
	trainer:	ppo
	batch_size:	64
	beta:	0.001
	buffer_size:	12000
	epsilon:	0.2
	hidden_units:	128
	lambd:	0.99
	learning_rate:	0.0003
	learning_rate_schedule:	linear
	max_steps:	5.0e5
	memory_size:	256
	normalize:	True
	num_epoch:	3
	num_layers:	2
	time_horizon:	1000
	sequence_length:	64
	summary_freq:	12000
	use_recurrent:	False
	vis_encode_type:	simple
	reward_signals:	
	  extrinsic:	
	    strength:	1.0
	    gamma:	0.99
	summary_path:	firstRun_3DBall
	model_path:	./models/firstRun/3DBall
	keep_checkpoints:	5
2020-01-29 23:32:36.992120: I tensorflow/core/platform/cpu_feature_guard.cc:141] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
INFO:mlagents.trainers: firstRun: 3DBall: Step: 12000. Time Elapsed: 13.570 s Mean Reward: 2.254. Std of Reward: 0.691. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 24000. Time Elapsed: 27.375 s Mean Reward: 2.383. Std of Reward: 0.757. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 36000. Time Elapsed: 41.477 s Mean Reward: 2.552. Std of Reward: 0.933. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 48000. Time Elapsed: 57.686 s Mean Reward: 3.062. Std of Reward: 1.321. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 60000. Time Elapsed: 75.666 s Mean Reward: 3.938. Std of Reward: 2.627. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 72000. Time Elapsed: 106.355 s Mean Reward: 7.020. Std of Reward: 5.403. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 84000. Time Elapsed: 125.801 s Mean Reward: 10.097. Std of Reward: 7.747. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 96000. Time Elapsed: 145.333 s Mean Reward: 22.549. Std of Reward: 23.439. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 108000. Time Elapsed: 162.491 s Mean Reward: 55.300. Std of Reward: 38.476. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 120000. Time Elapsed: 177.712 s Mean Reward: 60.530. Std of Reward: 37.366. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 132000. Time Elapsed: 192.498 s Mean Reward: 78.327. Std of Reward: 27.354. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 144000. Time Elapsed: 207.606 s Mean Reward: 94.892. Std of Reward: 17.665. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 156000. Time Elapsed: 222.123 s Mean Reward: 97.467. Std of Reward: 8.402. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 168000. Time Elapsed: 237.011 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 180000. Time Elapsed: 250.952 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 192000. Time Elapsed: 265.306 s Mean Reward: 96.092. Std of Reward: 13.537. Training.
```