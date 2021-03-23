# Robot Learning by Demonstration 
* Main principle is to teach robots without progeamming them for each and every case.
* Robot Learning from Demonstration (LfD) or Robot Programming by Demonstration (PbD) is also called as Imitation Learning.
* Human's perfomance is evaluted and then extended and adapted to novel solutions

## Principle
* The main principle of robot LfD-PbD is that end-users can teach robots new tasks without programming.
* When failures occur, the end-user needs only to provide more demonstrations

## Key Issues:
### What to Imitate and Evalutaion Metric
* relates to the problem of the determing which aspects of demostration should be imitated. As for certain task, some of the properties of the environment may be irrelevant and can be safly ignored. 
* what is imp and what is not is to be decide with the tasks in hand.
*  If the dimension of the data to be imitated is too high then such an approach may require large amount of training demos to converge to the appropiate solution.
### How to imitate. And Correspondance.
* this is the satge where we figure out how to imitate the metric we want to imitate which we found out in the "What to imitate problem"
* Robot cannot act in the same way as a human does, due to physical and the computational differences between the two.
* This question applies even when their is very high amount of co-relation between the way human and the robot does the task.
* The two ways in this states of the demonstrator and the imitator can said to corresponds is given by:
    1. **Perceptual Equivalence:**
        * due to differences in the human and robot sensory capabitlies the same scence will be different to both human and the robot.
        * Example: A human will see the world and get "perception" data from eyes, while the robot will have to work with a depth map and RGB colour space.
        * Another most imp. comparision is between the tactile sensing.
        * Many tactile sensors allow robot to sense forces and contact, but don't offer any information about the texture and temperature which the human skin can easily offer, thus causing loss off significant data.
        * the LfD and PbD approaches try to fill in this gap and correct it.
    2. **Physical Equivalnce:**
        * Due to the differences between the structures same task has to be done via differnet methods.
        * Example: A human will kick the robot, while the robot wil roll and puch the football.
        * This entire field is very task dependent.
## How to Teach
* now that we know what to teach and the limitations that it possess, the attention is to see how can we provide, gather and the transmit the data from  human to robot.
    
    1. **Directly Recording of the human motions:**
        * When we are solely intrested in the kinematics of the motion, one can use, motion tracking systems based on Vision(ViCon Motion Capture), or the methods of using exoskelton or other motion sensors.
        * This mthod will provide extremly accurrate measurment of the task by humans, but relies on the good correspodace solution
    2. **Kineshtic Teaching:**
        * Guiding the robot physically by humans.
        * zero correspondance is needed as the task is taught by the humans itself. 
        * one majior frawback is that majority of the times, human exahusts its DOF while trying to control all of robot's DOF
        * A possibility is to use teach incrementally and then add up the training. this is very cumbersome though.
    3. **Teleoperation Sceneraio**
        * Done using joystick, haptic devices, and other remote control decices.
        * One advnatage is that since even the human is restriced to the sensory capabilites of the robot, the problem choosing what to imitate is gratly reduced.
        * Other advantage is that the human can train the robot remotly.
    
## Ways to Solve LfD-PbD
Current approaches to encode skills can be classifies in two parts:
###  Low level Learning of indivisual motions
* The indvisual motions in a a big task, can be taught seperatly, and can be one-shot, or multi-shot learning. 
* The learning is generally done via a probility density functions, and analysed with non-linear regression techniques.
* Popular techniques are: Gaussuian Mixture Models(GMM) and Hidden Markaov Models(HMM)
#### Teaching Force-Control Tasks.
* most approches try to decouple the forces and kinematics of the task.
* mostly fueld by the advancements in the haptic devices and sensors.

### Learning High-Level Action Compostion.
* the ultimate aim of LfD-PbD.
* one of the main appraoches is to first learn the model of the indivisual motions indivisaully, and then find the suitable combination to imitate the complete tasks bu observing a human to do it.
* an alternate way is to watch human perfoem the complete task many time and then segemnt it into primarly motions. Advnatage here is the entire learnign is done in one pass.
*  but one main issue is that we don;t know the number of the primitive task present ans a possiblity of multiple possible primituve task should be considered at all times.

## Imitation Learning combined with Other Learning Techniques

* majority of work focuses on learning from the demonstration data. One way of combining imitation learning with Reinforment Learning which allows the robot to learn through trial and error
* in other ways the robot participates in an bidirectional teacging scenriao and learn like the way human learns from eah other.

### Imitation Learning and Reinforcemnet Learning
* RL allows the robot to discover new control policies through free exploration of the state-action space. 
* Imitation with RL guides the exploration done during the RL phase to find a improved control policy, and reducing the time to converge to a solution
*  Human demostration will be used to find an initial estimate of the control poilicy.


**Inverse RL and Imitation Learning**
* typically works that combine RL, assume that we have a reward function for the task that we have. 
* but in Inverse RL we determine the reward and the optimal control policy at the same time.
* one of the critical assumptions is that this assumes that all xperts optimize the same objectives. and this is being overcome in recent works
* 