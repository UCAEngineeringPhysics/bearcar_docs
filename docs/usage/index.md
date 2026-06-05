# Operating the BearCar

Once your hardware is assembled and the software is installed and tested, you are ready to collect data and train an autopilot.

The BearCar operates using a **Behavioral Cloning** pipeline. 
This means the car learns to drive autonomously by mapping your manual driving inputs to the images it sees through its camera. 
Because of this, operating the car always follows a three-step loop. 

Work through the following steps in order:

### [Step 1: Manual Driving & Data Collection](01-collect_data.md)
Learn how to start the vehicle service, arm the recording loop, and drive the car manually to capture high-quality training data. 

### [Step 2: Training the Autopilot](02-train_autopilot.md)
Transfer your captured images with paired steering and throttle values to a computation dedicated server, run the neural network training scripts, and generate your custom autopilot model.

### [Step 3: Autonomous Deployment](03-deploy_autopilot.md)
Load your newly trained model weights back onto the Raspberry Pi, and let the car drive itself. 

