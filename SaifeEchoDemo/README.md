# Dependencies
[gson](https://github.com/google/gson) - gson-2.3.1.jar or newer

[SAIFE Endpoint Library](http://saifeinc.com/developers/libraries/) - version 2.0.1 or newer.  Contact SAIFE to obtain SAIFE Endpoint Library.

# Java 
All commands are relative to the java directory. 

### Build
<code>
~$ SAIFE_HOME=<path to java lib>; javac -d bin -cp $SAIFE_HOME/java-lib-2.0.1.jar:$SAIFE_HOME/simple-xml-2.3.2.jar:gson-2.3.1.jar src/com/saife/demo/SaifeEcho.java
</code>

### Run
<code>
~$ SAIFE_HOME=<path to java lib>; java -cp bin:$SAIFE_HOME/java-lib-2.0.1.jar:$SAIFE_HOME/guava-11.0.jar:gson-2.3.1.jar  -Djava.library.path=$SAIFE_HOME/lib com.saife.demo.SaifeEcho
</code>

# C++ 
All commands are relative to the cpp directory.

### Build
<code>
~$ SAIFE_HOME=<path to cpp lib>; g++ -std=c++11 -I$SAIFE_HOME/include -L$SAIFE_HOME/lib/saife -o SaifeEcho src/SaifeEcho.cpp -l saife -l CecCryptoEngine -l roxml
</code>

### Run
<code>
~$ LD_LIBRARY_PATH=<path to cpp lib>/lib/saife ./SaifeEcho
</code>

# Running
Edit the command lines below for appropriate paths.   The application will create the SAIFE keystore and exit after the first run. Contact SAIFE to connect your application instances to the SAIFE network.

1. Create directories for instances of the app. For example <p/>
<code>
~$ mkdir EchoServer <p/>
~$ mkdir EchoCli1 <p/>
~$ mkdir EchoCli2
</code>
2. Run the server.  <p/>
<code>
~$ cd EchoServer <p/>
~$ LD_LIBRARY_PATH=<path to cpp lib>/lib/saife .../SaifeEcho
</code>
3. Run a client that uses secure messaging. <p/>
<code>
~$ cd EchoCli1 <p/>
~$ LD_LIBRARY_PATH=<path to cpp lib>/lib/saife .../SaifeEcho -cEchoServer -msg one two three four five
</code>
4. Run a client that uses secure sessions. <p/>
<code>
~$ cd EchoCli2 <p/>
~$ LD_LIBRARY_PATH=<path to cpp lib>/lib/saife .../SaifeEcho -cEchoServer -sess six seven eight nine ten
</code>
