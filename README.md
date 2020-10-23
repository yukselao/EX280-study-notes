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

## authentication token ogrenme

```bash
oc whami -t
```

# get projects


# switch to project


# get status of project

# get events

# get deployment

# modify deployment 
oc edit depoyment/bla

# yeni bir uygulama yarat

oc new-app --name=mydb --image-stream=mysql:5.7 -e MYSQL_USER=dbuser -e MYSQL_PASSWORD=verysecret -e MYSQL_DATABASE=mydb

# uygulamaya ait env variable'ları config den okunacak hale getirmek amacıyla bir configmap ve secret yarat

oc create configmap db-config --from-literal user=dbuser --from-literal=database=mydb

oc create secret generic db-auth --from-literal=password=verysecret

oc set env dc/mydb --list  # mydb isimi uygulama ayağa kaldırırken verdiğimiz isimlendirme, mevcut environment variable'ları listeler

oc set env dc/mydb --from cm/db-config --prefix=MYSQL

oc set env dc/mydb --from cm/db-auth --prefix=MYSQL







