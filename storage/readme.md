kubectl create namespace nfs


helm install nfs-subdir-external-provisioner -n nfs \
nfs-subdir-external-provisioner/nfs-subdir-external-provisioner \
--set nfs.server=172.16.50.3 \
--set nfs.path=/mnt/nfs \
--set storageClass.onDelete=true

kubectl label ns nfs pod-security.kubernetes.io/enforce=privileged