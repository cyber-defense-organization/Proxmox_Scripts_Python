# Start Up or Shut Down all Vms in a pool

Use this script to start up or shut down all VMs in a pool. This script was tested on 3.7, it is unknown if this script runs on other versions of Python.

## Installation
git clone https://github.com/jlm9/Proxmox_Scripts.git  
chmod +x startstop.py  
sudo apt-get install jq  
There is no requirements.txt since Proxmox has these packages in by default.
## Usage
There are two mandatory arguments:  
-a action    
-p pool  
  
And there are two optional arguments that were added to prevent shell crashes:  
-i iterations (after how many vms started/stop do you want the script to temporarily stop after. I recommend 3-4 but play around with it)  
-s sleep (how long do you want the script to stop for in seconds. I recommend 5 seconds but play around with it)

possible actions are:   
start    
stop

Example usage: sudo ./startstop.py -p test_pool -a start -i 3 -s 5  
This example would start all of the VMs in test_pool and would take a 5 second break for every 3 VMs started.  
For help use the -h option  
  
Some optional print statements are commented out. Caution: It gets noisy with all of the print statements
  
 Recommendation: You can install screen (apt-get install screen) and run the script using screen. Then press ctrl-a then the d key to detach the screen session after all inputs have been completed. Then you can log out and it will still run.
 
Functionality I hope to get working: organize json output by vmids so that the script could just grab all vmids by index. I had to circumvent the issue because the json would be randomly ordered. Stay tuned!
