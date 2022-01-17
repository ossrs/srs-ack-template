# srs-ack-template

![](http://ossrs.net/gif/v1/sls.gif?site=github.com&path=/tmpl/k8s/ack/ossrs/srs-ack-template)
[![](https://github.com/ossrs/srs-ack-template/actions/workflows/alibabacloud.yml/badge.svg)](https://github.com/ossrs/srs-ack-template/actions/workflows/alibabacloud.yml)

Template repository for deploying SRS to [ACK(Alibaba Cloud Container Service for Kubernetes)](https://www.alibabacloud.com/product/kubernetes).

## Usage

**Step 1:** Create ACK cluster and user:

1. Create a K8s cluster by [ACK](https://cs.console.aliyun.com), check by command `kubectl get namespace`
1. Create a new [RAM user](https://ram.console.aliyun.com/users), with access <kbd>AliyunCSFullAccess</kbd>
1. Click the <kbd>ACK</kbd> > <kbd>Authorize</kbd> > <kbd>Modify Permissions</kbd> to set user as Administrators.

**Step 2:** Click the <kbd>Use this template</kbd> to create your repository, then set the [secrets](https://github.com/ossrs/srs-ack-template/settings/secrets/actions):

1. `ACCESS_KEY_ID` is the AccessKey ID of [RAM user](https://ram.console.aliyun.com/users).
1. `ACCESS_KEY_SECRET` is the AccessKey Secret of [RAM user](https://ram.console.aliyun.com/users).
1. `ACK_CLUSTER_ID` is the ACK K8s cluster ID at <kbd>ACK</kbd> > <kbd>Basic Information</kbd>.

**Step 3:** Run <kbd>Actions</kbd> to deploy to your K8s, for example, if your external IP is `28.170.32.118`:

* Website is http://28.170.32.118:8080
* Publish RTMP to rtmp://28.170.32.118/live/livestream
* Play RTMP from rtmp://28.170.32.118/live/livestream
* Play HTTP-FLV from http://28.170.32.118:8080/live/livestream.flv
* Play HLS from http://28.170.32.118:8080/live/livestream.m3u8

Try to motify the [srs.yaml](srs.yaml), then push to your repository, your K8s will be updated automatically.

