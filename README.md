# How to deploy Ansible Automation Platform via the Operator on Code Ready containers

This is a quick how to deploy Ansible Automation platform locally on Code Ready Containers for a quick demo, or home lab.

## Definitions

[Red Hat CodeReady Containers aka CRC](https://developers.redhat.com/products/codeready-containers/overview) is a very easy to install local OpenShift cluster that runs on your laptop. This works for any operating system and can be downloaded from [here.](https://mirror.openshift.com/pub/openshift-v4/clients/crc/latest/)

## CRC Installation

Instructions to install crc are [here](https://access.redhat.com/documentation/en-us/red_hat_codeready_containers/1.35/html/getting_started_guide/installation_gsg)

TL;DR if you are on a mac you must be on 10.14 or above and you can just need to run crc binary you installed. (for Linux you will need to install libvirt via ```yum install virt-manager or apt if on debian``` and windows hyper-v must be enabled see install instructions above)

From terminal:

  ```shell
  crc setup
  ```

  ```shell
  crc config set cpus 6
  ```
  
  ```shell
   crc config set memory 12288
   ```

Then to run it:

```shell
crc run
```

Once it is installed it should give you information to log in, however you can always retrieve this with:

```shell
crc console --credentials
```

## Installing the Ansible Automation Platform Operator

---

## Login to the crc console as kubeadmin

  [https://console-openshift-console.apps-crc.testing](https://console-openshift-console.apps-crc.testing) (get password via ```crc console --credentials``` )

   ![crc_login](images/crc_login.png)

---

## Once logged into the CRC/Openshift local instance click on OperatorHub on the left

  ![choose_operators](images/choose_operators.png)

---

### Type Ansible into the filter window and choose Ansible Automation Platform

  ![choose_aap](images/choose_aap.png)

---

## Click install

  ![click_install](images/click_install.png)

---

## Allow all the defaults and click install again

  ![all_defaults](images/all_defaults.png)

---

## Once it is installed click view operator

  ![view_operator](images/view_oper.png)

---

## Click Create Instance in the Automation Controller box (third from left)

  ![create_controller](images/create_controller.png)

---

## Click Create (you can rename to whatever you want default is example)

  ![create_example](images/create-example.png)

---

## Click on instance you created

  ![click on instance](images/click_instance.png)

---

## Loging to AAP console (click on link on right password is in the Admin Password link)

  ![aap_login](images/login_aap.png)

## Add Subscription via your redhat login (if you dont have one click the request trial button at the top)
  
  ![subscription](images/subscription.png)

## Select the subscription (then next, next, submit)

  ![select_sub](images/select_sub.png)

Now you have a fully functional AAP instance to test with.
