İbrahim Halil Koyuncu CleverBit application
## Task 1

You can find two ımages files in link below.
https://hub.docker.com/repository/docker/12281404047


# Minicube updates
minikube start --driver=docker --memory=18000 --cpus=4 --extra-config=kubelet.housekeeping-interval=10s  #start k8s cluster via minikube 
minikube addons enable metrics-server # activate metrics server for kubernetes environment


# taken jwt token and its command

curl https://authority.cb-interview.com/token --resolve authority.cb-interview.com:443:10.96.7.65  --cacert authority.cb-interview.com.crt

eyJhbGciOiJSUzI1NiIsImtpZCI6IkRIRmJwb0lVcXJZOHQyenBBMnFYZkNtcjVWTzVaRXI0UnpIVV8tZW52dlEiLCJ0eXAiOiJKV1QifQ.eyJleHAiOjQ2ODU5ODk3MDAsImZvbyI6ImJhciIsImlhdCI6MTUzMjM4OTcwMCwiaXNzIjoidGVzdGluZ0BzZWN1cmUuaXN0aW8uaW8iLCJzdWIiOiJ0ZXN0aW5nQHNlY3VyZS5pc3Rpby5pbyJ9.CfNnxWP2tcnR9q0vxyxweaF3ovQYHYZl82hAUsn21bwQd9zP7c-LS9qd_vpdLG4Tn1A15NxfCjp5f7QNBUo-KC9PJqYpgGbaXhaGx7bEdFWjcwv3nZzvc7M__ZpaCERdwU7igUmJqYGBYQ51vr2njU9ZimyKkfDe3axcyiBZde7G6dabliUosJvvKOPcKIWPccCgefSj_GNfwIip3-SsFdlR7BtbVUcqR-yv-XOxJ3Uc1MI0tz3uMiiZcyPV7sNCU4KRnemRIMHVOfuvHsU60_GhGbiSFzgPTAa9WTltbnarTbxudb_YEOx12JiwYToeX0DCPb43W1tzIBxgm8NxUg

token payload: 
{
  "exp": 4685989700,
  "foo": "bar",
  "iat": 1532389700,
  "iss": "testing@secure.istio.io",
  "sub": "testing@secure.istio.io"
}

