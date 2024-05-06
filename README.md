# Update environment variable in update_properties.sh

### Update ->  Credentials (In Future we have to make it dynamic)
`WEBSERVER_SERVER_URL='http://localhost:9090'
WEBSERVER_CLIENT_SERCRET='[YOUR CLIENT SECRET]'
WEBSERVER_CLIENT_ID='[YOUR CLIENT ID]'
RABBIT_MQ_HOST="localhost"
RABBIT_MQ_PORT=5672
RABBIT_MQ_USERNAME="admin"
RABBIT_MQ_PASSWORD="Admin@123"
RABBIT_MQ_SSL="false"

JWT_SECRET=""`

# Install Dependencies 
sh ./install.sh

# Start Server
sh ./start.sh

`

# Port Config 

`9091` Device Server
`80/443`  Nginx Proxy - Device Server

`9050-9060` Appium Android Live Streaming
`49050-49060` Nginx Proxy - Appium Android Live Streaming

`9061-9070`  Appium Ios Live Streaming
`49061-49070`  Nginx Proxy - Appium Ios Live Streaming


# Required command files:

> /usr/local/bin/magick
> adb
> xcode
> idevice_id
> aapt
> pkill
> ps


# Appium Configuration
> Appium Directory
    > runTimeFolders -> appiumDevices -> appiumProj

> appium device folder 
    > runTimeFolders -> appiumDevices -> appiumProj -> {deviceId}

> appium device xcodeproject config for specific device
    > runTimeFolders -> appiumDevices -> appiumProj -> {deviceId} -> node_modules -> appium-webdriveragent -> WebDriverAgent.xcodeproj

    Update WebDriverAgent.xcodeproj for os version and team using xcode

# Logs
> Device Server Logs : 
   > app_running.log
   > /logs/device-server.log
   > /logs/spring-boot-logger.log

> Http nginx server logs
   > /nginx/logs/



# Upgrade new device agent

> download latest jar from github package
Development: 
https://github.com/lss-xpress/xpressrelease/packages/2139862

Production: 
https://github.com/lss-xpress/xpressrelease/packages/2139862

add device-agent-dev-1.0.3.jar in current device-agent directory
update env.sh -> DEVICE_SERVER_JAR_FILE
export DEVICE_SERVER_JAR_FILE="$ROOT_FOLDER/device-agent-dev-1.0.3.jar"


run below command:
./stop.sh
./start.sh

Notes:
- if there is any application properties changes then you have to add that support in env.sh and create_properties_files.sh
