# Blue/Green Deploy on Kubernetes

## Manual

In manual folder you can found a manual method to switch from a
blue deployment of an application to a green version changing  the deploy pointer on blue-green-service.yaml

## Gateway-Istio

In gateway-istio you can found a method to blue/green deploy on
kubernetes that can route the requests from on to another
version using variable tag $COLOR_TEST, but this tag throws an
error when trying to use it. For this ethod is necesary to
enable Istio on Kubernetes. The thrown error is:

~~~bash
* metadata.labels: Invalid value: "$COLOR_TEST": a valid label must be an empty string or consist of alphanumeric characters, '-', '_' or '.', and must start and end with an alphanumeric character (e.g. 'MyValue',  or 'my_value',  or '12345', regex used for validation is '(([A-Za-z0-9][-A-Za-z0-9_.]*)?[A-Za-z0-9])?')
* spec.selector.matchLabels: Invalid value: "$COLOR_TEST": a valid label must be an empty string or consist of alphanumeric characters, '-', '_' or '.', and must start and end with an alphanumeric character (e.g. 'MyValue',  or 'my_value',  or '12345', regex used for validation is '(([A-Za-z0-9][-A-Za-z0-9_.]*)?[A-Za-z0-9])?')
* spec.selector: Invalid value: v1.LabelSelector{MatchLabels:map[string]string{"app":"reviews-backend", "color":"$COLOR_TEST"}, MatchExpressions:[]v1.LabelSelectorRequirement(nil)}: invalid label selector
~~~
