![](/logo.png)

# XMiner

GPU Miner for `ETH`

Be aware when you download XMiner binaries from other sources.

## 中文说明

[查看中文说明](/readme_zh.md)

## Download

[Download here](https://github.com/XMinerTech/XMiner/releases)

## Performance (stock settings)

| Algorithm             |  COIN   |  P106-100  |  P104-8G   |   1070ti   |  1080ti  |   2080   | RX580 2048sp |
| :--------------- | :-----: | :--------: | :--------: | :--------: | :------: | :------: | :----------: |
| ethash           |   ETH   |   21.2M   |   34.5M    |   26.9M    |   46M    |  35.5M   |     24M      |
| cuckatoo         | GRIN31  |     X      |    0.89    |    0.94    |   1.56   |   1.65   |      X       |
| cuckatoo32       | GRIN32  |   0.215    |    0.38    |    0.41    |   0.63   |   0.65   |      X       |
| cuckoo_ae        |   AE    |    3.35    |    5.5     |    5.15    |   7.9    |   8.75   |      X       |
| progpow_sero     |  SERO   |   10.3M    |   17.5M    |   13.3M    |  22.5M   |  25.8M   |     10M      |
| kawpow           |   RVN   |   10.3M    |   17.5M    |   13.3M    |  22.5M   |  25.8M   |     11M      |
| beamv3           |  BEAM   |    12.5    |    19.6    |    19.5    |    26    |   30.5   |      X       |
| octopus          |   CFX   |    5.5M    |    8.5M    |    9.8M    |  14.8M   |  48.5M   |     X     |
| ergo | ERGO | 42M | 68M | 53M | 64M | 74M | 64M(eth bios) |

## Features

* Support Windows & Linux.
* Support backup mining pool configuration.
* Support SSL connection to mining pools.
* Dev Fee: 
  * ethash etchash 1%
  * cuckatoo & cuckatoo32 & cuckoo_ae 2%
  * progpow_sero 2%
  * kawpow 2%
  * beamv3 2%
  * octopus 3%
  * ergo 2%

## Requirements

- **NVIDIA Driver version: >= 384**.
- Nvidia GPU Specific Requirements:

| Algorithm        |  Coin   | Compute Capability | Memory (Win7 & Linux) | Memory (Win10) |
| :--------------- | :-----: | :----------------: | :-------------------: | :------------: |
| ethash           |   ETH   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          5GB          |      6GB      |
| cuckatoo         | GRIN31  | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          8GB          |      10GB      |
| cuckatoo32 | GRIN32 | 6.0, 6.1, 7.0, 7.5 | 8GB | 10GB |
| cuckoo_ae        |   AE    | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          5GB          |      6GB       |
| progpow_sero     |  SERO   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          3GB          |      4GB      |
| kawpow           |   RVN   | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 |          3GB          |      4GB      |
| beamv3 | BEAM | 6.0, 6.1, 7.0, 7.5 | 3GB | 3GB |
| octopus | CFX | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 | 5GB | 6GB |
| ergo | ERGO | 6.0, 6.1, 7.0, 7.5, 8.0,8.6 | 3GB | 3GB |

- \* Compute Capability reference link: [wikipedia](<https://en.wikipedia.org/wiki/CUDA#GPUs_supported>)

## Sample Usages

#### ETH

- **ethermine:** nbminer -a eth -p stratum://0x12343bdgf.worker@asia1.ethermine.org:4444
- **sparkpool:** nbminer -a eth -p stratum://0x12343bdgf.worker@cn.sparkpool.com:3333
- **f2pool:** nbminer -a eth -p stratum://0x12343bdgf.worker@eth.f2pool.com:8008
- **beepool:** nbminer -a eth -p stratum://0x12343bdgf.worker@eth-pool.beepool.org:9530
- **nanopool:** nbminer -a eth -p stratum://0x12343bdgf.worker@eth-asia1.nanopool.org:9999
- **herominers:** nbminer -a eth -p stratum://0x12343bdgf.worker@ethereum.herominers.com:10201
- **nicehash:** nbminer -a eth -p stratum://0x12343bdgf.worker@daggerhashimoto.eu.nicehash.com:3353
- **miningpoolhub**: nbminer -a eth -p stratum://0x12343bdgf.worker@asia.ethash-hub.miningpoolhub.com:20535

## CMD options：

**XMiner -a algo -p protocol+socket_type://wallet_address.worker@pool_host:pool_port**

  * -h, --help    Displays this help.
  * -v, --version    Displays version information.
  * -c, --config \<config file path>    Use json format config file rather than cmd line options.
  * -a, --algo \<algo>    Select mining algorithm
  * --api  \<host:port>    The endpoint for serving REST API.
  * -o, --url \<url>    Mining pool url.
  * -u, --user \<user>    User used in Mining pool, wallet address or username.
  * -o1, --url1 \<url> url for backup mining pool 1.
  * -u1, --user1 \<user> username for backup mining pool 1.
  * -o2, --url2 \<url> url for backup mining pool 2.
* -u2, --user2 \<user> username for backup mining pool 2.
* -p,  --password \<password>  password for mining pool
* -p1,  --password1 \<password>  password for backup mining pool1
* -p2,  --password2 \<password>  password for backup mining pool2
* -d, --devices \<devices>    Specify GPU list to use. Format: "-d 0,1,2,3" to use first 4 GPU.
* -i, --intensity \<intensities>    Comma-separated list of intensities (1 -100).
* --strict-ssl    Check validity of certificate when use SSL connection.
* --proxy    Socks5 proxy used to eastablish connection with pool, E.g. 127.0.0.1:1080
* --cuckoo-intensity \<intensity>    Set intensity of cuckoo, cuckaroo, cuckatoo, [1, 12]. Smaller value means higher CPU usage to gain more hashrate. Set to 0 means autumatically adapt. Default: 0.
* --cuckatoo-power-optimize    Set this option to reduce the range of power consumed by rig when minining with algo cuckatoo. This feature can reduce the chance of power supply shutdown caused by overpowered. Warning: Setting this option may cause drop on minining performance.
* --temperature-limit, --tl \<temp-limit>    Set temperature limit of GPU, if exceeds, stop GPU.
* --temperature-start, --ts \<temp-start>    Set cool-down temperature target if GPU is stopped by `temperature-limit`, default to \<temp-limit> - 5.
* --log    Generate log file named `logs/log_<timestamp>.txt`.
* --log-file \<filename>    Generate custom log file. Note: This option will override `--log`.
* --no-nvml    Do not query cuda device health status.
* --fidelity-timeframe \<timeframe>    Set timeframe for the calculation of fidelity, unit in hour. Default: 24.
* --long-format    Use 'yyyy-MM-dd HH:mm:ss,zzz' for log time format.
* --verbose    Print communication data between miner and pool in log file.
* --device-info    Print device cuda information.
* --fee \<fee>    Change devfee in percentage, [0-5]. Set to '0' to turn off devfee with lower hashrate. Otherwise, devfee = max(set_value, def_value).
* --generate-config \<filename>    Generate a sample config json file.
* --no-watchdog    Disable watchdog process.
* --platform \<platform>    Choose platform，0: NVIDIA+AMD (default), 1: NVIDIA only, 2: AMD only
* --share-check \<value>    If \<value> minutes without share, reboot miner, set 0 to disable. Default: 30
* --no-interrupt    set this option will disable miner interrupting current GPU jobs when a new job coming from pool, will cause less power supply issue, but might lead to a bit higher stale ratio and reject shares.
* --enable-igpu    AMD igpu is disabled by default, set this option to enable.
* **--mt, --memory-tweak \<mode>    Memory timings optimize for Nvidia GDDR5 & GDDR5X gpus. range [1-6]. Higher value equals higher hashrate. Individual value can be set via comma seperated list. Power limit may need to be tuned up to get more hashrate. Higher reject share ratio can happen if mining rig hits high temperature, set lower value of `-mt` can reduce reject ratio. Under windows, a custom driver need to be installed when using `-mt`, can installed manually by option  `--driver`, or run nbminer.exe with admin privilege to perform auto-install. Under linux, admin priviledge is needed to run, `sudo ./nbminer -mt x`. `OhGodAnETHlargementPill` is not needed anymore if `-mt` is enabled when mining on 1080 & 1080ti GPUs.**
* **--driver \<action>    Windows only option, install / uninstall driver for `memory tweak`. Run with admin priviledge. install: `nbminer.exe --driver install`, uninstall: `nbminer.exe --driver uninstall`. **
* **-lhr \<value>    Partially unlock hashrate for Nvidia LHR GPUs. [-1, 100]. 0: auto, -1: off. Others: set to 60 means trying to reach 60% of nonlocked max hashrate.**

## API Reference

### Web Monitor

Open http://api_host:port/ in your browser to use web monitor.

### Request

GET http://api_host:port/api/v1/status

### Response

``` json
{"devices":[{"accepted":1,"coreClock":"1995.00MHz","efficiency":"248.55K","fanSpeed":"30%","gpuTemperature":"59C","hashRate":"73.51M","id":0,"invalid":0,"memoryClock":"1156.50MHz","name":"RTX 3080 Ti","powerUsage":"295.77W","powerUsageRaw":295.7659912109375,"rejected":0}],"totalAccepted":1,"totalHashRate":"73.51M","totalHashRateRaw":73513350.400137767,"totalInvalid":0,"totalPowerUsage":"295.77W","totalPowerUsageRaw":295.7659912109375,"totalRejected":0,"uptime":"0:00"}
```
