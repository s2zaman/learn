**Daily commands**

**kubectl commands**
```
kubectl cluster-info
kubectl create deployment [name]
kubectl edit deployment [name]
kubectl delete deployment [name]
kubectl label namespace [name] istio-injection=enabled
kubectl get nodes | pod | services | replicaset | deployment
kubectl get events.   (Get cluster events)
kubectl logs [pod name]
kubectl exec -it [pod name] -- bin/bash
kubectl logs nginx-dep-5699968b79-pnb8c istio-proxy  | egrep -wi 'error|critical'
```


**linux commands**
```
telnet 35.123.456.78 443
telnet 35.123.456.78 80
netstat -ntlp
traceroute 35.123.456.78
```


**search specific word in a file or folder**
```
grep -i wordtosearch /opt/fileone
grep -i ‘wordtosearch’ /opt/fileone
grep -i wordtosearch /opt/*
```


**search multiple words in a file or folder**
```
egrep -i ‘wordtosearch|secondword|thirdword’ /opt/fileone
egrep -i ‘wordtosearch|secondword|thirdword’ /opt/*
```


**grep / cut / capture a portion of a file**
```
sed -n '/2021-09-15 05:40:00/,/2021-09-15 05:42:59/p' logfile
sed -n '/2021-09-15 05:40:00/,/2021-09-15 05:42:59/p' logfile > pod1.log
```


**download a file from Dropbox, via cmdline**

`curl -L -o projectghi.war https://www.dropbox.com/s/8udsfsfm6gsfi5rtsdf/projectghi.war?dl=1`


**create a gzip tar**

`tar -czvf file.tar.gz directory/abc/xyz/`


**create a gz tar , and exlude certain files with while creating this tar**
```
tar --exclude='*.gz' --exclude='*.jar' --exclude='*.war' --exclude='*.DS_Store' --exclude='*.jarBCKP' -czvf projectxy-prod.tar.gz projectxy-prod/
tar --exclude='*.gz' --exclude='*.jar' --exclude='*.war' --exclude='*.DS_Store' --exclude='*.jarBCKP' --exclude='projectxynodeserver' --exclude='V31-Prod-Build-09-08-2021' --exclude='checkin_api-main’ -czvf projectxy-prod.tar.gz projectxy-prod/
```


**unzip a gzip**
```
tar -xzvf file.tar.gz
tar -C /dir1/dir2 -xzvf file.tar.gz
```


**list the contents of a tar or tar.gz file**

`tar -ztvf projects.tar.gz`


**list contens of a WAR file**
```
jar -tvf projectghi_crons.jar
jar -tvf projectghi.war
```


**list contents of a JAR file**

`jar -tvf projectabc-0.0.1-SNAPSHOT.jar | grep -i bootstrap.yml`


**read a single file from inside a JAR, without extracting it**

`unzip -p projectabc-0.0.1-SNAPSHOT.jar BOOT-INF/classes/bootstrap.yml`


**find files recursively in a directory, then remove those files**

`find ./opt -name *BCKP | xargs rm`


**truncate a file. even large files**
```
truncate -s 0 path/to/the/file
‘-s means, set the size to zero’
```


**Display free disk space**

`df -h`


**estimate file or folder space usage**
```
du -sh dir/file
du -sh projectxyscheduler/
```


**Check who is logged-in**
```
who -H
w -H
```


**Replace a string from inside vim**
format

`:%s/current-old-string/new-string-value/g`

To do this;
- Press ESC
- :%s/namespace: projectxy-test/namespace: test-one/g
- Press ENTER
- DONE


———————————————————————————


**further findings**
```
ps -ef

kubectl logs nginx-dep-5699968b79-pnb8c istio-proxy  | egrep -wi 'error|critical'

ls -t /opt/apache-tomcat-7.0.57/logs | grep catalina | head -n1

ls -t /opt/apache-tomcat-7.0.57/logs | grep localhost | head -n1

ls -t /opt/apache-tomcat-7.0.57/logs | grep index | head -n1
```


and yet more to come !
