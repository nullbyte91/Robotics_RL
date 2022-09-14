```bash
# Install the mujoco library
wget https://mujoco.org/download/mujoco210-linux-x86_64.tar.gz
mkdir /home/$USER/.mujoco
tar -xvf mujoco210-linux-x86_64.tar.gz
echo "export LD_LIBRARY_PATH=/home/$USER/.mujoco/mujoco210/bin" >> ~/.bashrc
source ~/.bashrc

# Test Mujoco
cd ~/.mujoco/mujoco210/bin
./simulate ../model/humanoid.xml

# Dep Install
sudo apt update
sudo apt-get install patchelf
sudo apt-get install python3-dev build-essential libssl-dev libffi-dev libxml2-dev  
sudo apt-get install libxslt1-dev zlib1g-dev libglew1.5 libglew-dev python3-pip

# Create a virtual environment
python3 -m venv /home/$USER/openai_env/
source /home/$USER/openai_env/bin/active

# Clone mujoco py and install
git clone https://github.com/openai/mujoco-py
cd mujoco-py
python3 -m pip install -r requirements.txt
python3 -m pip install -r requirements.dev.txt
python3 -m pip install -e . --no-cache

# Reboot machine
```

```bash
sudo apt install libosmesa6-dev libgl1-mesa-glx libglfw3
source /home/$USER/openai_env/bin/active
python3 -m pip install -U 'mujoco-py<2.2,>=2.1'

# Test mujoco installation
cd examples/
python3 setting_state.py

# Install OpenAI Gym
python3 -m pip install gym==0.20.0.0

# Test the OpenAI env
python3 openai_fetchRobot.py
```