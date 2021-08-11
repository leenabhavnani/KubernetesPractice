### Pod-to-pod networking

- Each pod in a Kubernetes node gets assigned a dedicated IP address with a dedicated namespace.
- Pods on a node can communicate with all pods on all nodes without NAT.
- Agents on a node (system daemons, kubelet) can communicate with all the pods on that specific node.

#### Communication between pods in the same node -
<br><br>
<img src="https://user-images.githubusercontent.com/61199820/128997429-bd4d063a-0697-4e5c-98ed-09daab22562a.png" align="left" height="348" width="348" >

<br><br><br><br><br><br><br><br><br><br><br><br><br><br> <br><br>


#### Communication between pods in different nodes -
<br><br>
<img src="https://user-images.githubusercontent.com/61199820/128999648-311e93bd-19c7-447c-8f71-28ad424b5966.png" align="left" height="448" width="548" >
<br><br><br><br><br><br><br><br><br><br><br><br><br><br> <br><br><br><br><br><br>




