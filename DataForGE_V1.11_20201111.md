## Data For GE

- Q1: Architecture Graph：哪些指令会通过P2P 通道传输？哪些指令通过HTTPS 传输？

  A1: 对于一些控制设备的指令会通过P2P通道传输，如云台控制的翻转，上、下、左、右方位的切 换等； 对于通过HTTPS传输的指令，比如说报警、视频上传等，均以此协议方式； 

- Q2: Interaction graph：提供以下过程的时序图

  1. 添加新设备；

​          2. Live stream（已提供）；

​		  3. 事件上报；

​		  4. 固件升级；

​		A2: 1）添加设备时序图

![image-20201112134448215](/Users/dee.huang/Library/Application Support/typora-user-images/image-20201112134448215.png)

​			2）昨天已提供（done）

​			3）事件上报时序图

​				![image-20201112134612142](/Users/dee.huang/Library/Application Support/typora-user-images/image-20201112134612142.png)

​			4）固件升级 因为这个纯属内部操作，不涉及到与第三方的交互，所以经沟通，暂时pending。

- Q3: System architecture graph: 需细化下云服务的部署，哪些部署在wasabi？哪些部署在AWS？相互间的联系？（如下午解释，1. 我们关注云端会使用到哪些平台（如Ali云我们不能使用），2.我们以前有过把不同云服务部署在不同平台上的经历，发生过不少延时时间长，连接不稳定等问题，所以想重点看下云部署的系统设计）

  A3: 关于服务部署这块，包含应用服务部署、对象存储、文件等。具体的细节，从技术层面来说， 集成方不必太过于关注我们这边的实现细节，因为我们对外提供的都是稳定的SDK加API访问接口 （具有一定的封装性和对外扩展性），同时我们会针对合作方的需求提供专业、可靠、安全、稳定 的云解决方案。