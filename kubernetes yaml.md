# kubernetes YAML
**This document will be explain about how we create the objects in the kubbernetes using the yaml configuration input file**

### Yaml : 
 it is a key value pair where key and value were suppurated by the colloen(:) must have a **space** after the collen for the values

All the various templets yaml,xml,jason were used to represent the data. It could be a data of an org with employs and personal data.etc

Eg: 


Key value pair

Fruit: Apple

Vegetable: carrot

Liquid: Water

Meat: Chicken

List/Array: it will be represent as below – indicates it an element in a array.
~~~
Fruits:
-	Orange (element)
-	Apple
-	Banana
Vegetables: 
-	Carrot
-	Cauliflower
-	Tomato

~~~

### Explanation

-  Fruits: This is the key for the list.

-  - Orange, - Apple, - Mango: These are the items in the list, each preceded by a dash and a space. This indicates they are elements of the list under the Fruits key.

### Dictionary/map: 
It is a set of properties were grouped together under an item the blank indicates the all were belongs and aligned to one set where the keys were same but the values under were different.

> **Note**  the space in dictionary should be allied properly(equal no of space) if not the properties will change to next one. Which makes no sense.

Equal number of space will represent the key.
If there is difference will comes under syntax error where it won’t allow us if a key having the value.


> Must ensure there were in the right form to represent your data correctly.

example for wrong notation if we miss the spaces
~~~
Banana:
	Calories: 105
	Fat: 0.4 g
	Carbs: 27 g
Grapes: 
Calories: 62
	Fat: 0.2  g
	Carbs: 25  g

~~~
**Explanation**

•	Banana and Grapes: These are the keys for each fruit.

•	Calories, Fat, Carbs: These are the sub-keys, providing nutritional information for each fruit.

•	The values (e.g., 105, 0.4 g, 27 g) represent the nutritional content.
	
~~~
Servers: 
  -	Name: server1
    Owner : Sudheer
    Created: 16/07/2024
    Status: active
~~~

 ***

## Difference between dictionary vs list dictionary in a list

**Eg** we will take an example of car where it contains all the data of color price model transmission. Etc can be represent as dictionary. 
~~~
Dictonery
Color: Red
Model: seltos
Transmission : manual
Price: 12 l
~~~
If in case we need to describe the model further we can consider it as an example of dictionary in other  dictionary 

Now model will be replaced by small dictionary name and year.

Eg: 
~~~
Color: Red
Model: 
	Name: seltos
	Year: 2019
Transmission : manual
Price: 12 l

~~~

If we want to store the name of 6 cars by color and name of the car to store this we will use list or array as it is a multiple items of same types of object since we are stoting the name 

Then it will be a list of strings
~~~
- Blue seltos
- red seltos
- green seltos
- orange seltos
- grey seltos
- black seltos
~~~


if we want to further provide details of how we provided we can name It as list of dictionary.
~~~
- Color: Blue
Model: 
	Name: seltos
	Year: 2019
Transmission : manual
Price: 12 l

- Color: Red
Model: 
	Name: seltos
	Year: 2019
Transmission : manual
Price: 12 l

- Color: Green
Model: 
	Name: seltos
	Year: 2019
Transmission : manual
Price: 12 l

- Color: Orange
Model: 
	Name: seltos
	Year: 2019
Transmission : manual
Price: 12 l
~~~
> Dictionary/map is a n unorder collection, where list is an order collection
>
> Even we change the order the dictionary will be the same it doesn’t matter properties were in any order dictionary will still be the same.

~~~
Eg: Banana: 					
	Calories: 105
	Fat: 0.4 g                                
	Carbs: 27g 
Banana: 
	Calories: 105
	Carbs: 27g
	Fat: 0.4 g                                   
~~~

But in the list order of the item matter’s the below list were not same as the items were placed different.

## Array/list

Using arrays in YAML files allows you to define lists of values or objects, which can be very useful in various contexts such as configuration management and CI/CD pipelines. 

By leveraging arrays, you can create more flexible and dynamic configurations, simplifying the management of complex workflows. Whether you are processing the data in a script or using it to control a pipeline,

 YAML arrays provide a clean and human-readable way to organize your data.

~~~
Fruits: 
-	Orange
-	Mango
-	Apple
Fruits: 
-	Orange 
-	Apple
-	Mango
~~~
The above 2 lists were different as the apple and mango order was different.

Any line that begins with # will be considered as comment in yaml.
~~~
# Below is the list which is talking about fruits.
Fruits: 
-	Orange
-	Mango
-	Apple
~~~

---
### Questions : 


Update the food.yml file to add a list of Vegetables - Carrot, Tomato, Cucumber
~~~
Fruits:
  - Apple
  - Banana
  - Orange
Vegetables:
    - Carrot
    - Tomato
    - Cucumber

~~~


## Yaml basic for kube controller
~~~
pod.yml
-------------
 
apiVersion: v1
kind: Pod
metadata:
name: nginx
labels:
  app: nginx
spec:
containers:
  - name: first-container
    image: nginx
    ports:
    - containerPort: 80
 ~~~ 

> command:
kubectl apply –f xxx.yml
	


### replica controller:
 
yaml file:
~~~ 
apiVersion: v1
kind: ReplicationController
metadata:
  name: nginx
spec:
  replicas: 3
  selector:
    app: nginx
  template:
    metadata:
      name: nginx
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
~~~
### replica set:
 
 ~~~
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: guestbook
    tier: frontend
spec:
  # modify replicas according to your case
  replicas: 3
  selector:
    matchLabels:
      tier: frontend
  template:
    metadata:
      labels:
        tier: frontend
    spec:
      containers:
      - name: php-redis
        image: gcr.io/google_samples/gb-frontend:v3
 
~~~

~~~
 Employee:
  Name: Jacob
  Sex: Male
  Age: 30
  Title: Systems Engineer
~~~


## POD with YAML


**Yaml in Kubernetes** : we will use yaml file in the Kubernetes as an input file for creation of pods,services,replicas,deployemnts.

All will follow the same top level or root level fields and those are must required fields in any of the objects mentioned above.

~~~
Pod-definition.yml – configuration file
apiVersion:
kind:
metadata:
	name: myapp-pod
	lables:
		app: myapp
spec:
~~~

**apiVersion**: it is the version of k8’s api that we will use to create object.

POD: V1

Services:V1

Deployments: Apps/V1

Replicaset: Apps/V1

**Kind**: it will define the type of the object we are going to create.
pods,  services, replicas, deployments


**metadata**: it will define the object that we are creating consist of name, labels as we could observe  the properties will be children of metadata 
> the space should be same as they were siblings.
~~~
metadata:
	name: myapp-pod
	lables:
		app: myapp
		type: front-end
~~~
under metadata name is a string where labels are dictionary it can have any key-value pair as our wish.

If there are 100 of pods were running for front-end and 100 for back-end we can filter them by types under the labels once we deploy it will be difficult to segregate.

> **Note**: under the metadata we need to provide the name or labels or anything else that Kubernetes expects , we can use user defined properties.

But under the labes we can use any key-value pairs that the suites the templet.


**SPEC**: 

Till now we have mention the kind and name fewer details but we didn’t mention any where in spec where we would provide additional information to Kubernetes pertaining to that object.

This is going to be different for different objects so it's important to understand or refer to the document before creating object.

Spec is a dictionary and we will update the other details as list.

Container will comes as list/array as we can have multiple container with in them

before name  “-“ since we plan to have only a single container in the part that - right before the name indicates that this is the first item in the list the item in the list is a dictionary.

Eg: 
spec:
  containers: 
    - name: nginx-container
      image: nginx

		
once we configure the file we will run the kubectl command to create  pod.
~~~
Kubectl create -f <file_name>.yml
Kubectl get pods
Kubectl describe pod myapp-pod

Yamel exercise:

apiVersion: v1
kind: Pod
metadata:
  name: postgres
  labels:
    tier: db-tier
spec:
  containers:
    - name: postgres
      image: postgres
      env:
        - name: POSTGRES_PASSWORD
          value: mysecretpassword
~~~