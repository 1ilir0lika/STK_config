# Supertuxkart Server Setup Tutorial
Install dependencies:
```bash
sudo apt install wget git subversion make build-essential cmake pkg-config zlib1g-dev libcurl4-openssl-dev libssl-dev
```

Download the source code:
```
git clone https://github.com/supertuxkart/stk-code stk-code
```

Download assets:
```
svn co https://svn.code.sf.net/p/supertuxkart/code/stk-assets stk-assets
```

Create & enter the work directory for build process:
```
cd stk-code
mkdir cmake_build
cd cmake_build
```

Use this to build STK (You can add `-jX` to the make command to utilize X CPU cores)
```
cmake .. -DSERVER_ONLY=ON
make
```

Log in to SuperTuxKart Online:
```
./bin/supertuxkart --init-user --login="USERNAME" --password="PASSWORD"
```

Download template server config:
```
wget -O server.xml https://raw.githubusercontent.com/1ilir0lika/STK_config/main/server.xml
```

Run the server:
```
./bin/supertuxkart --server-config=server.xml --network-console
```
