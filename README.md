İbrahim Halil Koyuncu CleverBit application
## Task 1

You can find two ımages files in link below.
https://hub.docker.com/repository/docker/12281404047


# Minicube updates
minikube start --driver=docker --memory=18000 --cpus=4 --extra-config=kubelet.housekeeping-interval=10s  #start k8s cluster via minikube 
minikube addons enable metrics-server # activate metrics server for kubernetes environment


### taken jwt token and its command (task-4 validation-1)

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


### task4 validation servicex request command
curl https://servicex.cb-interview.com/x --resolve servicex.cb-interview.com:443:10.110.124.181  --cacert servicex.cb-interview.com.crt --header "Authorization: Bearer eyJhbGciOiJSUzI1NiIsImtpZCI6IkRIRmJwb0lVcXJZOHQyenBBMnFYZkNtcjVWTzVaRXI0UnpIVV8tZW52dlEiLCJ0eXAiOiJKV1QifQ.eyJleHAiOjQ2ODU5ODk3MDAsImZvbyI6ImJhciIsImlhdCI6MTUzMjM4OTcwMCwiaXNzIjoidGVzdGluZ0BzZWN1cmUuaXN0aW8uaW8iLCJzdWIiOiJ0ZXN0aW5nQHNlY3VyZS5pc3Rpby5pbyJ9.CfNnxWP2tcnR9q0vxyxweaF3ovQYHYZl82hAUsn21bwQd9zP7c-LS9qd_vpdLG4Tn1A15NxfCjp5f7QNBUo-KC9PJqYpgGbaXhaGx7bEdFWjcwv3nZzvc7M__ZpaCERdwU7igUmJqYGBYQ51vr2njU9ZimyKkfDe3axcyiBZde7G6dabliUosJvvKOPcKIWPccCgefSj_GNfwIip3-SsFdlR7BtbVUcqR-yv-XOxJ3Uc1MI0tz3uMiiZcyPV7sNCU4KRnemRIMHVOfuvHsU60_GhGbiSFzgPTAa9WTltbnarTbxudb_YEOx12JiwYToeX0DCPb43W1tzIBxgm8NxUg"
Hello World! (response)

### task 4 validation 2 servicex logs
dbug: Microsoft.AspNetCore.Server.Kestrel.Connections[39]
      Connection id "0HN1GALBT9SJU" accepted.
dbug: Microsoft.AspNetCore.Server.Kestrel.Connections[1]
      Connection id "0HN1GALBT9SJU" started.
info: Microsoft.AspNetCore.Hosting.Diagnostics[1]
      Request starting HTTP/1.1 GET http://servicex.cb-interview.com/x - - -
dbug: Microsoft.AspNetCore.Routing.Matching.DfaMatcher[1001]
      1 candidate(s) found for the request path '/x'
dbug: Microsoft.AspNetCore.Routing.EndpointRoutingMiddleware[1]
      Request matched endpoint 'HTTP: GET /x'
info: Microsoft.AspNetCore.Routing.EndpointMiddleware[0]
      Executing endpoint 'HTTP: GET /x'
info: System.Net.Http.HttpClient.y.LogicalHandler[100]
      Start processing HTTP request GET http://servicey.servicey.svc.cluster.local/y
info: System.Net.Http.HttpClient.y.ClientHandler[100]
      Sending HTTP request GET http://servicey.servicey.svc.cluster.local/y
info: System.Net.Http.HttpClient.y.ClientHandler[101]
      Received HTTP response headers after 315.6788ms - 200
info: System.Net.Http.HttpClient.y.LogicalHandler[101]
      End processing HTTP request after 315.8206ms - 200
info: Microsoft.AspNetCore.Routing.EndpointMiddleware[1]
      Executed endpoint 'HTTP: GET /x'
dbug: Microsoft.AspNetCore.Server.Kestrel.Connections[9]
      Connection id "0HN1GALBT9SJU" completed keep alive response.
info: Microsoft.AspNetCore.Hosting.Diagnostics[2]
      Request finished HTTP/1.1 GET http://servicex.cb-interview.com/x - 200 - text/plain;+charset=utf-8 316.3167ms


### task 4 validation 2 servicey logs
info: Microsoft.AspNetCore.Routing.EndpointMiddleware[1]
      Executed endpoint 'HTTP: GET /y'
dbug: Microsoft.AspNetCore.Server.Kestrel.Connections[9]
      Connection id "0HN1GBLUT5L0A" completed keep alive response.
info: Microsoft.AspNetCore.Hosting.Diagnostics[2]
      Request finished HTTP/1.1 GET http://servicey.servicey.svc.cluster.local/y - 200 - text/plain;+charset=utf-8 100.6471ms




