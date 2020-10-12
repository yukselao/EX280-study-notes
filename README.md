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


## ClusterOperators Listeleme

```bash
oc get co
oc get clusteroperators
```

## Log görüntüleme

```bash
oc adm node-logs -u crio master01
oc adm node-logs -u kubelet master01
oc adm node-logs master01
```


## node'a uzaktan erisim saglama

```bash
oc debug node/master01

```

## deployment'a uzaktan erisim saglama

```bash
oc debug deployment/my-deployment-name --as-root
```

## pod'a uzaktan erisim saglama

```bash
oc rsh my-pod-name
```

## dosya kopyalama

```bash
oc cp localfile my-pod-name:/remotefile
```

## tcp tunnel olusturma

```bash
oc port-forward my-pod-name local-port:remote-port
```

## increase log level

```bash
oc get pod --loglevel 10
```




