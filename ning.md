# Ning: Session 3.1 PCW

## Roll-A-Ball

This activity was quite fun. It made me realize that there's a fair whack of documentation to read through to start building custom environments.

![alt text](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4c7351e0-85b6-4126-9103-9ecfeefec32c/Screenshot_2020-01-29_at_10.33.26.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=ASIAT73L2G45DS7NX6FU%2F20200129%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200129T024428Z&X-Amz-Expires=86400&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCmKS6nlfc3xWuc6L3me3FLSN4QLcChCx5S0Xl5g5bSLAIgXCvwv65yExbkH4VD%2BdAd33clJwBuGqB9Vu1ika%2BirkMqvQMIyv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgwyNzQ1NjcxNDkzNzAiDDj76VUMM9cORmGtmSqRA8C%2BLsegVLT84yiWMkeys%2BQtnsECl7PJMaYOw10fR1UOCXYsd0AykxI22DE9BHkX0lU4bO0oheEOqKxwa82yQp1IxFx64Dji%2FzdjkCakzFOtnZQhOzQomUG9xX%2B8eiYkhu3rxE8AsfQs5CEPLDrasVzc6PDiltjZvW%2B1sATTKrWP%2B1x8zsiQtc%2FeZv1gHzttCHKctDomBsisosTWl0DEduzK5Mueo64NSt5%2B%2BbPKfZ%2FpO1dMFAtb6MaCmlux21RmjCk534PmCUrCsOzc559sFSUM09okPznX1YVUHI%2Bkpka2%2BhrdVfpEo2yHtsWYlSpPQDrhCRdOxLn1UlSEwPjkZnYUcCPkIE4xdqHTWT%2Fgrq2LYIfa7b4%2BjUTTCTK%2FaiRQfLRArJE8Ljm6S7TTpH8tjSpzh0MW9t22WuC5g6eQg7ZFP0u4x0Batwu79mEO0l05bPsFn2YZ8P5%2BQ09N8Vlv9WWwBMLvbUwnqxSlrRf0F2QbRzhkOtfIpF%2FZkazHF19qiX4jwm7%2FNcldmCFrqsFxfFAlMIO7w%2FEFOusBuCga97kD2yo834K%2FAPEk0tKfv6vjL1MrSQlYSkQW90idEXR18NQXGTYlQocpbIO5XcmQzJRy6O4ngPnstFUSl2gDCRsOFEyNq7QE%2Fkzb4h%2FtlUphxRY2IFAqAncPo5wbHZI7%2FeVW0MFS1CJyue%2FL%2BhZ%2BizlyOOFGI0oLOvpDk0VQiq3MqKUs1uPOWrCiKFMXiPCG2u%2BFps0Q8I%2BdezHmF6k9xRLeVCDxUY72E9jb8Ewdfya7GnJ9CT4IsGbjn5zXtZ5qg6%2BhOlBCIB5CSAxIEtYKZ59N8lsbihi1ZKpwFPtkNJbQyEBcs82hNg%3D%3D&X-Amz-Signature=464ef05cf0059e6163f67b20fc9c8fa9f98dd723c8ee38945ea139e508bec866&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Screenshot_2020-01-29_at_10.33.26.png%22)

## Balance-Ball

While I trained the Proximal Policy Optimization (PPO) model on the balance ball environment for 50,000 steps, the model started to show convergence around the 300 second mark (step 21000), i.e. achieving a mean reward of 100.00 with a standard deviation of 0.00.

At the start, the cubes were moving erratically with a lot of jitter as the balls kept falling of the top surface. Towards the end of the training process, I noticed two different strategies being adopted to balance the ball:
- Cube would remain relatively stable with minimal movement. As expected, this keeps the ball stable.
- Cube would be in a constant "low jitter" mode in all directions so that the constant opposing forces end up balancing the ball.

![alt text](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/56fc10dc-f59f-475a-9adc-99ae1d4e7eb9/Screenshot_2020-01-27_at_14.14.25.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=ASIAT73L2G45B3GLC6PO%2F20200129%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200129T023838Z&X-Amz-Expires=86400&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDEaCXVzLXdlc3QtMiJIMEYCIQDwWcyf3KdJD2f88Hac5ouATmT%2Br8n%2BwPWP8GGgAHkV0QIhAIkuZBLF19RkQchtbiVNEcC7eiB6gAEC1l7wVpXvalcXKr0DCMr%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEQABoMMjc0NTY3MTQ5MzcwIgzl58UfBtMGXJyL%2FKAqkQOR0AojD0vQrE%2FWg74e%2F0ZtWlad6Y4ZHLjuds1DsKT5MviYU8CWnHyoTPKgg6zFutp7lTzN1043kMtEjwImXrEHNj8fMbqOA0KxCmfgD6Fxe13bnw%2F8lm%2BjLNVg%2B9YD6ODiEVRTDbBQQmoh3T9u47SheArM%2F8RfxP9Fbu34FjP2YvXkRcdXs8H8FFqkrH8vDj0uA49TvCMr6tk58LAfGED7mp%2BI2CqCUXREo5tXNOy3zxoaE3thyB0WoDqSKCWgCRu4x%2BL%2BKdrC8kOoJA100mZViCmSYRFejKuxdZ9hiAOXz7eudHcbhQ0SMUGViM%2FvfhDeX%2FNNG%2BmK7h34NRgd%2F0krj6GS7X3eiJRfV67YjFL11cZ8W4UqPNiT0Vn73jJfztt1o%2BbjCEsXfusrea49EJlU4DTo%2FFSpBQ2F7BAbcIkGuWj%2BbDSdTwzewzW5RYjH49uJ3dXNR9nP1lUUo0L5ABbtScSBbIQhwR%2F4ZOP1Ncy1sTv%2FqHIYLLXNcBgQgoPP%2BoBaoL2qAFxbmf7Bpdr5T3EvrzDVscPxBTrqAaE5MTd%2FGgeZ0xFktkUartM5IUbMuCkFGdZSSMVu2b5tRcgTkqd1MoXLHoI2eT5lyXWy1vSk9hhXyZwR%2Bg0qaQ3apYlOLOi%2FQGCITTfPhY2lHzPIWJYmZYx36urw2ssnxLNcUHJQxLwPUIevqmynNHYhN3O9m0sF4T0%2BIQw8UwZ%2F7Sw%2Fq1yfNyD%2Bfom7U%2BuUyxNKSD9SbDAV%2FtLrYz6NHfmk%2F6d%2FN6d41Y1lWKbq%2BWuiGul9irC8Gj3ndEQna34iLlrue7xiIgVXwNhJ2aEPnmNCw%2F9XvamyXQCN4UkdVgp3YYA0wJ6lw8NwPQ%3D%3D&X-Amz-Signature=2ea4459e4a0cfc26a17578b59cb4fc13473f39bc32dcacda5c4b6b099fdd4621&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Screenshot_2020-01-27_at_14.14.25.png%22)

Training output:
```
Version information:
  ml-agents: 0.13.1,
  ml-agents-envs: 0.13.1,
  Communicator API: API-13,
  TensorFlow: 1.13.1
INFO:mlagents.trainers:CommandLineOptions(debug=False, num_runs=1, seed=-1, env_path=None, run_id='firstRun', load_model=False, train_model=True, save_freq=50000, keep_checkpoints=5, base_port=5005, num_envs=1, curriculum_folder=None, lesson=0, no_graphics=False, multi_gpu=False, trainer_config_path='config/trainer_config.yaml', sampler_file_path=None, docker_target_name=None, env_args=None, cpu=False, width=84, height=84, quality_level=5, time_scale=20, target_frame_rate=-1)
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
	max_steps:	5.0e4
	memory_size:	256
	normalize:	True
	num_epoch:	3
	num_layers:	2
	time_horizon:	1000
	sequence_length:	64
	summary_freq:	1000
	use_recurrent:	False
	vis_encode_type:	simple
	reward_signals:	
	  extrinsic:	
	    strength:	1.0
	    gamma:	0.99
	summary_path:	firstRun_3DBall
	model_path:	./models/firstRun-0/3DBall
	keep_checkpoints:	5
2020-01-27 13:35:07.647165: I tensorflow/core/platform/cpu_feature_guard.cc:141] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
INFO:mlagents.trainers: firstRun: 3DBall: Step: 1000. Time Elapsed: 70.363 s Mean Reward: 1.119. Std of Reward: 0.702. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 2000. Time Elapsed: 82.466 s Mean Reward: 1.236. Std of Reward: 0.795. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 3000. Time Elapsed: 94.836 s Mean Reward: 1.453. Std of Reward: 0.986. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 4000. Time Elapsed: 107.929 s Mean Reward: 2.134. Std of Reward: 1.630. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 5000. Time Elapsed: 119.345 s Mean Reward: 3.217. Std of Reward: 2.542. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 6000. Time Elapsed: 131.041 s Mean Reward: 5.395. Std of Reward: 4.742. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 7000. Time Elapsed: 143.265 s Mean Reward: 9.832. Std of Reward: 8.732. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 8000. Time Elapsed: 155.125 s Mean Reward: 19.871. Std of Reward: 22.828. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 9000. Time Elapsed: 167.927 s Mean Reward: 43.352. Std of Reward: 34.250. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 10000. Time Elapsed: 179.652 s Mean Reward: 84.353. Std of Reward: 32.211. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 11000. Time Elapsed: 191.509 s Mean Reward: 83.715. Std of Reward: 32.718. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 12000. Time Elapsed: 203.413 s Mean Reward: 87.740. Std of Reward: 26.675. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 13000. Time Elapsed: 215.060 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 14000. Time Elapsed: 226.529 s Mean Reward: 93.954. Std of Reward: 20.944. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 15000. Time Elapsed: 235.816 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 16000. Time Elapsed: 247.304 s Mean Reward: 93.015. Std of Reward: 24.195. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 17000. Time Elapsed: 258.603 s Mean Reward: 92.708. Std of Reward: 25.261. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 18000. Time Elapsed: 269.821 s Mean Reward: 92.777. Std of Reward: 25.021. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 19000. Time Elapsed: 281.132 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 20000. Time Elapsed: 292.654 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 21000. Time Elapsed: 304.073 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 22000. Time Elapsed: 315.568 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 23000. Time Elapsed: 326.889 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 24000. Time Elapsed: 338.616 s Mean Reward: 93.315. Std of Reward: 23.156. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 25000. Time Elapsed: 349.879 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 26000. Time Elapsed: 361.291 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 27000. Time Elapsed: 372.764 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 28000. Time Elapsed: 384.462 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 29000. Time Elapsed: 395.970 s Mean Reward: 97.233. Std of Reward: 9.176. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 30000. Time Elapsed: 407.662 s Mean Reward: 99.900. Std of Reward: 0.332. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 31000. Time Elapsed: 419.305 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 32000. Time Elapsed: 428.908 s Mean Reward: 98.075. Std of Reward: 6.385. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 33000. Time Elapsed: 442.786 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 34000. Time Elapsed: 455.995 s Mean Reward: 99.308. Std of Reward: 2.294. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 35000. Time Elapsed: 469.114 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 36000. Time Elapsed: 484.281 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 37000. Time Elapsed: 501.459 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 38000. Time Elapsed: 516.388 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 39000. Time Elapsed: 529.452 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 40000. Time Elapsed: 542.281 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 41000. Time Elapsed: 554.202 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 42000. Time Elapsed: 567.081 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 43000. Time Elapsed: 579.478 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 44000. Time Elapsed: 591.635 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 45000. Time Elapsed: 602.759 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 46000. Time Elapsed: 614.210 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 47000. Time Elapsed: 625.594 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 48000. Time Elapsed: 637.161 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers: firstRun: 3DBall: Step: 49000. Time Elapsed: 648.681 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers:Saved Model
INFO:mlagents.trainers: firstRun: 3DBall: Step: 50000. Time Elapsed: 660.260 s Mean Reward: 100.000. Std of Reward: 0.000. Training.
INFO:mlagents.trainers:Saved Model
INFO:mlagents.trainers:List of nodes to export for brain :3DBall?team=0
INFO:mlagents.trainers:	is_continuous_control
INFO:mlagents.trainers:	version_number
INFO:mlagents.trainers:	memory_size
INFO:mlagents.trainers:	action_output_shape
INFO:mlagents.trainers:	action
INFO:mlagents.trainers:	action_probs
Converting ./models/firstRun-0/3DBall/frozen_graph_def.pb to ./models/firstRun-0/3DBall.nn
IGNORED: Cast unknown layer
IGNORED: StopGradient unknown layer
GLOBALS: 'is_continuous_control', 'version_number', 'memory_size', 'action_output_shape'
IN: 'vector_observation': [-1, 1, 1, 8] => 'sub_2'
IN: 'epsilon': [-1, 1, 1, 2] => 'mul_1'
OUT: 'action', 'action_probs'
DONE: wrote ./models/firstRun-0/3DBall.nn file.
INFO:mlagents.trainers:Exported ./models/firstRun-0/3DBall.nn file
```
