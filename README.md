# Required Ports

    `9091` Device Server
    `80/443`  Nginx Proxy - Device Server
    `9050-9060` Appium Android Live Streaming
    `49050-49060` Nginx Proxy - Appium Android Live Streaming
    `9061-9070`  Appium Ios Live Streaming
    `49061-49070`  Nginx Proxy - Appium Ios Live Streaming


### Update env.sh for environment

    export XPRESS_ENV="production"
    export DEVICE_SERVER_JAR_FILE="$ROOT_FOLDER/xpressDeviceService.jar"
    export WEBSERVER_SERVER_URL="https://webserver.xpress-labs.local/xpressWebService"
    export WEBSERVER_CLIENT_ID=''
    export WEBSERVER_CLIENT_SERCRET=''
    export JWT_SECRET="[YOUR JWT SECRET]"`
    RABBIT_MQ_HOST="localhost"
    RABBIT_MQ_PORT=5672
    RABBIT_MQ_USERNAME="admin"
    RABBIT_MQ_PASSWORD="Admin@123"
    RABBIT_MQ_SSL="false" 

# Install Dependencies 
> sh ./install.sh

# Start Server
> sh ./start.sh


# Update /etc/hosts
> `
127.0.0.1	device-server-01.xpress-labs.local
`


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
   
`/logs/console.log`

`/logs/device-server.log`

`/logs/spring-boot-logger.log`


> Http nginx server logs :

`/nginx/logs/`


# Upgrade new device agent

> sh ./upgrade.sh

START DEVICE AGENT
> ./start.sh
