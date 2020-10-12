# EX280-study-notes

## Giriş

```bash
export KUBECONFIG=INSTALL_DIR/auth/kubeconfig
oc login -u kubeadmin -p my-secure-password-{-_-}

## Cluster sürüm bilgisi öğrenme

```bash
oc get clusterversion
```   


## Node'ları listele 

```bash
oc get node
oc adm top nodes
```   

## Kullanıcı yarat

```bash
oc create user aliokan
oc create user --full-name="Ali Okan Yuksel"
```
## Kullanıcıları listele

```bash
oc get user
```

## Sistemde authenticate olmuş olan tüm kullanıcılardan self-provisioner rolünü çıkar

```bash
oc adm policy remove-cluster-role-from-group self-provisioner system:authenticated:oauth
```
