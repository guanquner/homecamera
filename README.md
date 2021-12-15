# homecamera
家庭摄像头推流方案


构建SRS


选择环境CentOS8.4,安装有基本的环境。由于我对Docker内再编译不是很熟悉，故选择编译安装。


git clone -b 4.0release https://gitee.com/ossrs/srs.git


cd srs/trunk


./configure


make


git checkout feature/gb28181 &&


./configure --with-gb28181 && 


make clean && make


#配置服务器端push.gb28181.conf


#只需要把Hosts和CANDIDATE改掉（支持WebRtc)


然后./objs/srs -c conf/push.gb28181.conf


（candidate就是服务器的候选地址，客户端可以连接的地址ip:port。）


然后登陆摄像头后台开启GB28181协议主动推流。
