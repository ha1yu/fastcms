
# Fastcms system has a zip package directory traversal vulnerability that allows for arbitrary file writing. And gain server privileges

**Project Address**

https://github.com/my-fastcms/fastcms



**This interface has a zip package directory traversal vulnerability that allows for arbitrary file writing.**

/fastcms/admin/template/install

com/fastcms/cms/controller/admin/TemplateController.java
![image](https://user-images.githubusercontent.com/59911588/220809426-166b1f73-1717-4304-a7bb-b4e75cac28dd.png)

**The install method of DefaultTemplateService invoked the unzip method of FileUtils.**

com/fastcms/core/template/DefaultTemplateService.java
![image](https://user-images.githubusercontent.com/59911588/220809507-1e079228-3f20-4069-9ba1-dcc00fddcec4.png)

**The unzip method of FileUtils did not do any logical judgment on the decompressed zip package.**

com/fastcms/common/utils/FileUtils.java
![image](https://user-images.githubusercontent.com/59911588/220809549-cff3055e-6803-4f1d-9de2-06cd992deace.png)

**Create a zip package；**

![image](https://user-images.githubusercontent.com/59911588/220809566-207ae606-5b1e-4f18-9d93-d75869c64f7b.png)

**Uploading a zip package;**

![image](https://user-images.githubusercontent.com/59911588/220809578-441a96ba-2aa1-4aa1-afc1-997ca6782191.png)

**Successfully logged in to ssh, successfully wrote the public key to the root/.ssh/authorized_keys file.**

![image](https://user-images.githubusercontent.com/59911588/220809594-2e6fbb1a-fe04-469b-97d3-731125d6d80c.png)



