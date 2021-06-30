## This repo is having manifest to deploy coturn on kubernetes.

You can use args to make it work as stun also.

Note: For the smooth routing(by using LoadBalancer service type I was facing issues) I am using daemon set.

by using [tickle](https://webrtc.github.io/samples/src/content/peerconnection/trickle-ice/) you can test the running coturn

example:

```turn:x.x.x.x:3478```

```stun:x.x.x.x:3478```

(in general x.x.x.x would be your node's IP)

for username password you can use 

```
secret=mysecret && \
time=$(date +%s) && \
expiry=8400 && \
username=$(( $time + $expiry )) &&\
echo username:$username && \
echo password : $(echo -n $username | openssl dgst -binary -sha1 -hmac $secret | openssl base64)

```
