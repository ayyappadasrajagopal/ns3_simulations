# ns3_simulations


https://www.nsnam.org/releases/ns-3-45/

https://www.nsnam.org/docs/installation/html/quick-start.html#installing-ns-3


## Installation

### Downloading
$ wget https://www.nsnam.org/releases/ns-allinone-3.45.tar.bz2
$ tar xfj ns-allinone-3.45.tar.bz2
$ cd ns-3.45
  or cd ns-allinone-3.43

if errro happens wget from https://www.nsnam.org/releases/ns-3.45.tar.bz2
or ns3-allinone 3.43 from https://www.nsnam.org/releases/ns-allinone-3.43.tar.bz2

### Installation
$ ./ns3 configure --enable-examples --enable-tests


If erros happen ns3 all in one and ns3 folder 
https://www.nsnam.org/docs/tutorial/html/getting-started.html
Chnage to ns3 3.43 folder and do the following

### Building with the ns3 CMake wrapper

$ ./ns3 clean
$ ./ns3 configure --build-profile=optimized --enable-examples --enable-tests

### Now go ahead and switch back to the debug build that includes the examples and tests.

$ ./ns3 clean
$ ./ns3 configure --build-profile=debug --enable-examples --enable-tests

The build system is now configured and you can build the debug versions of the ns-3 programs by simply typing:
$ ./ns3 build


### Install
./ns3 configure --prefix=/opt/local

#### Clean

./ns3 clean --dry-run
./ns3 clean


### Youtube Video
https://www.youtube.com/watch?v=0OKn9e1Gg48

✅ Step-by-Step: Install NS-3 (All-in-One)
🧱 Prerequisites (Ubuntu/Debian):

Install required packages first:

sudo apt update
sudo apt install -y \
  gcc g++ python3 python3-dev python3-pip cmake ninja-build \
  git mercurial qt5-qmake qtbase5-dev \
  libgtk-3-dev libsqlite3-dev \
  libxml2-dev libgsl-dev libgmp-dev \
  libboost-all-dev \
  libssl-dev \
  pkg-config \
  unzip curl

⬇️ Step 1: Download the NS-3 All-in-One Package

mkdir -p ~/ns3
cd ~/ns3
git clone https://gitlab.com/nsnam/ns-3-allinone.git
cd ns-3-allinone
./download.py -n ns-3.41   # Replace with your desired version

    This downloads NS-3 core and all required packages.

    You can run ./download.py -l to list available versions.

🏗️ Step 2: Build NS-3

./build.py

    This compiles the simulator and examples.

▶️ Step 3: Run NS-3 Example

Once built, go into the simulator directory:

cd ns-3.41   # or whatever version was downloaded
./waf --run hello-simulator

To run examples with parameters:

./waf --run "first --verbose=1"

🧪 Step 4: Enable and Run Tests (Optional)

./waf configure --enable-examples --enable-tests
./waf build
./test.py

📁 Directory Structure After Install:

~/ns3/ns-3-allinone/
├── ns-3.41/          ← Main NS-3 source directory
├── netanim-...       ← NetAnim (optional visualization)
├── bake/             ← For advanced builds

✅ Done! NS-3 is now installed.




## Installation of ns 3 in ubuntu 24.04

https://releases.ubuntu.com/noble/

https://www.nsnam.org/releases/ns-3-44/
https://www.nsnam.com/2024/06/installation-of-ns3-in-ubuntu-ubuntu.html

## Steps 

$ sudo apt update && sudo apt upgrade -y

$ sudo apt install g++ python3 cmake ninja-build git gir1.2-goocanvas-2.0 python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython3 tcpdump wireshark sqlite3 libsqlite3-dev qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools openmpi-bin openmpi-common openmpi-doc libopenmpi-dev doxygen graphviz imagemagick python3-sphinx dia imagemagick texlive dvipng latexmk texlive-extra-utils texlive-latex-extra texlive-font-utils libeigen3-dev gsl-bin libgsl-dev libgslcblas0 libxml2 libxml2-dev libgtk-3-dev lxc-utils lxc-templates vtun uml-utilities ebtables bridge-utils libxml2 libxml2-dev libboost-all-dev ccache python3-full python3-pip

$ wget https://www.nsnam.org/releases/ns-allinone-3.44.tar.bz2

$ tar -xjf ns-allinone-3.44.tar.bz2

$ cd ns-allinone-3.44

$ ./build.py --enable-examples --enable-tests

$ cd ns-3.44

$ ./ns3 run first


If successful, you’ll see output indicating a simple point-to-point network simulation, something like:

At time 2s client sent 1024 bytes to 10.1.1.2 port 9

https://blogger.googleusercontent.com/img/a/AVvXsEjH3ajT9LIzEPlTLJkxX674mIrnSe6-7Ztn9JVyikWMrZQuzAHsoJAxuXc7gsMN5kTV62zutr00JGCWJoEtuKQXtULf_wMf4R5us1B8pDCvpPVRiTSa4tTifEzZqWtU0FPW2psfAWw0082KIqQ0I-dAjbmxfHCRQTZCtacc9SsOXC4hg8o2fJtCPEkcrL8=w640-h360-rw

ns3
Network Simulator 3

### (Optional) Configure Python Bindings

If you plan to use Python for scripting NS-3 simulations, enable Python bindings during the build process. Install the Python development package if not already installed

$ sudo apt install -y python3-dev python3-pip
$ pip install pygccxml pygraphviz cppyy

$ cd ns-allinone-3.44/ns-3.44/

$ ./ns3 configure --enable-python-bindings
$ ./ns3 build


### Install vSCode

# 1. Update package index
sudo apt update

# 2. Install dependencies
sudo apt install software-properties-common apt-transport-https wget gpg -y

# 3. Import Microsoft GPG key
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
rm packages.microsoft.gpg

# 4. Enable VS Code repository
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/packages.microsoft.gpg] \
https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

# 5. Install VS Code
sudo apt update
sudo apt install code -y

🔹 Install Python IDLE
For Python 3 (recommended):
sudo apt update
sudo apt install idle3 -y

✅ Option 2: Use a Python virtual environment (best practice)

Create a virtual environment in your home directory:
python3 -m venv ~/pyenv

Activate it:
source ~/pyenv/bin/activate

Now install your packages:
pip install pygccxml pygraphviz cppyy

When you’re done, deactivate with:
deactivate

# Install venv if not present (before creating the virtual environment)
sudo apt install python3-venv -y

if pygraohics error occurs Fix for pygraphviz build error
Install Graphviz development libraries:
sudo apt install graphviz graphviz-dev -y
