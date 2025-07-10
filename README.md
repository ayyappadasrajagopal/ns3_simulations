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
