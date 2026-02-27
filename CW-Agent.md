## cloudwatch monitoring 
### cloudwatch dashboard
 - Grafical representation of metrics

### Metrics
 - Data points that are collected from AWS resources and services
 - Numerical data 
    - Examples: CPU utilization, disk I/O, network traffic
- metrcal data --> numerical values


### Alarms
 - Notifications based on metric thresholds
 - Trigger actions when certain conditions are met
   - Examples: sending notifications, cpu utilization exceeds --%

---
## lanch an Ec2 instance and attach IAM role to it with policy
<img width="1233" height="581" alt="Screenshot 2026-02-27 at 12 43 14 PM" src="https://github.com/user-attachments/assets/b279862c-5f0e-47ae-8442-faca53d5a363" />

## cloudwatch 
## cloudwatch agent 
Step 1: Download and install the CloudWatch agent 
```bash
wget https://amazoncloudwatch-agent.s3.amazonaws.com/ubuntu/amd64/latest/amazon-cloudwatch-agent.deb
```
step 2: install the package with dpkg:
```bash
sudo dpkg -i -E ./amazon-cloudwatch-agent.deb
```
step 3: Configure the agent
```bash
cd /opt/aws/
cd amazon-cloudwatch-agent/
cd bin/
./amazon-cloudwatch-agent-config-wizard
```
- Log file path:
```
/var/1og/syslogs
```
- log group name
```
syslogs
```
step 4: start an agent
```
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json

 ```
```
sudo systemctl status amazon-cloudwatch-agent
```
