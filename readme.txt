(1) AIDL
1. �� IHelloService.aidl, IGoodbyeService.aidl ���� frameworks/base/core/java/android/os
2. �޸� frameworks/base/Android.mk  ���һ��
         core/java/android/os/IVibratorService.aidl \
+        core/java/android/os/IHelloService.aidl \
+        core/java/android/os/IGoodbyeService.aidl \

3. mmm frameworks/base

4. ��������: 
./out/target/common/obj/JAVA_LIBRARIES/framework_intermediates/src/core/java/android/os/IHelloService.java
./out/target/common/obj/JAVA_LIBRARIES/framework_intermediates/src/core/java/android/os/IGoodbyeService.java

(2) ����:
�ѳ���ŵ� /work/android-5.0.2/frameworks/testing/APP_0005_Binder_JAVA_App
ִ��:

cd /work/android-5.0.2
. setenv
lunch // ѡ�񵥰�

mmm frameworks/testing/APP_0005_Binder_JAVA_App
�������� TestServer.jar, TestClient.jar

�����ļ���NFSĿ¼
cp /work/android-5.0.2/out/target/product/tiny4412/system/framework/Test*.jar /work/nfs_root/android_fs/

(3) ����:
logcat TestServer:* TestClient:* HelloService:* *:S &
CLASSPATH=/mnt/android_fs/TestServer.jar app_process / TestServer &
CLASSPATH=/mnt/android_fs/TestClient.jar app_process / TestClient hello
CLASSPATH=/mnt/android_fs/TestClient.jar app_process / TestClient hello 100ask.taobao.com
CLASSPATH=/mnt/android_fs/TestClient.jar app_process / TestClient goodbye
CLASSPATH=/mnt/android_fs/TestClient.jar app_process / TestClient goodbye weidongshan

