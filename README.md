# Demo
## Dependencies
Part of the needed dependencies for DeepXplore, DLFuzz, and DeepHunter are listed as below for the experiment

### DeepXplore
```
python 2.7.13
h5py 2.7.1
keras 2.1.3
numpy 1.11.1
opencv-python 3.1.0.0
pandas 0.20.3
pillow 5.0.0
scipy 1.2.3
tensorflow-cpu 2.2.1
```

### DLFuzz
```
python 2.7.13
h5py 2.7.1
keras 2.1.3
numpy 1.11.1
opencv-python 3.1.0.0
pandas 0.20.3
pillow 5.0.0
scipy 1.2.3
tensorflow-cpu 2.2.1
```

### DeepHunter
```
python 3.6.2
h5py 2.10.0
imageio 2.9.0
keras 2.1.6
numpy 1.15.5
opencv-python 4.5.2.52
pandas 0.20.3
pillow 8.2.0
scipy 1.2.1
tensorflow 1.5.0
```

## Usage
Anaconda is used to manage the dependencies of DeepXplore, DLFuzz, and DeepHunter.
### DeepXplore
```
Using TensorFlow backend.
usage: gen_diff.py [-h] [-t {0,1,2}] [-sp START_POINT]
                   [-occl_size OCCLUSION_SIZE]
                   {light,occl,blackout} weight_diff weight_nc step seeds
                   grad_iterations threshold log_path

Main function for difference-inducing input generation in MNIST dataset

positional arguments:
  {light,occl,blackout}
                        realistic transformation type
  weight_diff           weight hyperparm to control differential behavior
  weight_nc             weight hyperparm to control neuron coverage
  step                  step size of gradient descent
  seeds                 number of seeds of input
  grad_iterations       number of iterations of gradient descent
  threshold             threshold for determining neuron activated
  log_path              the path of file recorded the log info

optional arguments:
  -h, --help            show this help message and exit
  -t {0,1,2}, --target_model {0,1,2}
                        target model that we want it predicts differently
  -sp START_POINT, --start_point START_POINT
                        occlusion upper left corner coordinate
  -occl_size OCCLUSION_SIZE, --occlusion_size OCCLUSION_SIZE
                        occlusion size
```

### DLFuzz
```
usage: gen_diff.py [-h] [-t {0,1,2}]
                  number_mutation target_dir {0,1,2,3} threshold log_path

Main function for DLFuzz strategy

positional arguments:
  number_mutation       the number of mutation for a seed
  target_dir            the dir that saves the generated adversarial inputs
  {0,1,2,3}             the strategy of selecting neurons
  threshold             threshold for determining neuron activated
  log_path              the path of file recorded the log info

optional arguments:
  -h, --help            show this help message and exit
  -t {0,1,2}, --target_model {0,1,2}
                        target model that we want it predicts differently
```
### DeepHunter
```
usage: gen_diff.py [-h] [-g GAMMA] [-p P_MIN] [-a ALPHA] [-b BELTA]
                  [-t {0,1,2}]
                  number_mutation target_dir coverage threshold log_path
                  save_path {random,probability}

Main function for DeepHunter strategy

positional arguments:
  number_mutation       the number of mutation for a seed
  target_dir            the dir that saves the generated adversarial inputs
  coverage              the coverage metric
  threshold             threshold for determining neuron activated
  log_path              the path of file recorded the log info
  save_path             the dir that saves the adversarial inputs
  {random, probability}  the selecting seed strategy

optional arguments:
  -h, --help            show this help message and exit
  -g GAMMA, --gamma GAMMA
                        the probabilities adjusting factor
  -p P_MIN, --p_min P_MIN
                        the minimum probability for selecting a seed
  -a ALPHA, --alpha ALPHA
                        a mutation constraint parameter
  -b BELTA, --belta BELTA
                        a mutation constraint parameter
  -t {0,1,2}, --target_model {0,1,2}
                        target model that we want it predicts differently
```
## File structure
- DeepXplore: the dir that saves the Implemented scripts
-seeds: the dir that saves the images of seed queue
-generated_inputs: the dir that saves the adversarial inputs
- DLFuzz: the dir that saves the Implemented scripts
-seeds: the dir that saves the images of seed queue
-generated_inputs: the dir that saves the adversarial inputs
- DeepHunter: the dir that saves the Implemented scripts
-seeds: the dir that saves the images of seed queue
-generated_inputs: the dir that saves the adversarial inputs

