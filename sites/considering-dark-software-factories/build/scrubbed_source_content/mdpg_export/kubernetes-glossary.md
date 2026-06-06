

* addons
    * <span class="link-not-tracked">link not tracked</span>
* API Server
    * AKA apiserver
    * TODO - does this run in the cluster itself?
    * a RESTful API - has swagger support
    * "a number of processes that implement the Kubernetes API" - <span class="link-not-tracked">link not tracked</span>
    * installed using the **kubelet** - <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* annotation
    * TODO
    * from <span class="link-not-tracked">link not tracked</span> "Update the **annotation**s on a **resource**"
    * for non-identifying information... information would not be used for object selection and therefore doesn't belong in labels
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* autoscale (verb)
    * Things that can be autoscaled: **deployment**, **replica set**, or **replication controller**
* backend
    * TODO from <span class="link-not-tracked">link not tracked</span>
* claim
    * AKA **Persistent Volume Claim**
    * AKA **PVC**
    * <span class="link-not-tracked">link not tracked</span>
* cluster
    * From <span class="link-not-tracked">link not tracked</span> "A group of **nodes** firewalled from the internet, that are the primary compute resources managed by Kubernetes."
    * From <span class="link-not-tracked">link not tracked</span> "a set of physical or virtual machines and other infrastructure resources used by Kubernetes to run your applications. Kubernetes can run anywhere! See the Getting Started Guides for instructions for a variety of services."
* cluster add-on
    * TODO
* cluster IP
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* cluster manager
    * from <span class="link-not-tracked">link not tracked</span> "**kubectl** controls the Kubernetes **cluster manager**"
* cluster network
    * from <span class="link-not-tracked">link not tracked</span> "A set of links, logical or physical, that facilitate communication within a cluster according to the Kubernetes networking model. Examples of a Cluster network include Overlays such as flannel or SDNs such as OVS."
* component
    * TODO - unclear
    * in `kubectl get cs` (get component statuses) it gives statuses for **etcd**, the **scheduler**, and the **controller manager**
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* config maps
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* control plane
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* controller manager
    * A small binary that lives on the "master side of the house"
    * Responsible for doing health maintenance.
    * modifies cluster state, and can get a **lease-lock** from the **API Server** to ensure single actor modifying cluster state - <span class="link-not-tracked">link not tracked</span>
* CNI - Container Network Interface
    * TODO
* daemon set
    * <span class="link-not-tracked">link not tracked</span>
* dashboard
    * TODO
    * `kubectl cluster-info` gives kubernetes-dashboard is running at https://172.17.4.99:443/api/v1/proxy/namespaces/kube-system/services/kubernetes-dashboard
* declaritive primitives
    * TODO - Same as the (maybe called templates or manifests) that declare this stuff?
    * <span class="link-not-tracked">link not tracked</span>
* deployment
    * includes a **replication controller**
    * includes the setup for rollouts
* definition
    * <span class="link-not-tracked">link not tracked</span>
* data volume
    * Independent of the lifespan of the containers
* desired state
    * The declarative statement about what you'd like the world to look like
* edge router
    * From <span class="link-not-tracked">link not tracked</span> "A router that enforces the firewall policy for your cluster. This could be a gateway managed by a cloudprovider or a physical piece of hardware."
* endpoint
    * TODO
    * Can be internal or external
    * Can also be non-Kubernetes
* etcd
    * AKA clustered etcd
    * A fault-tolerant key/value datastore.
    * **Clustered etcd** replicates your storage to all **master** instances in your cluster - <span class="link-not-tracked">link not tracked</span>
    * Also a lock manager (TODO used that way in Kubernetes?  Was used that way for the CoreOS competitor to Kubernetes)
    * can check status with `kubectl get cs` (component statuses)
* expose (verb)
    * Can take a **replication controller**, **service**, **deployment** or **pod** and expose it as a new Kubernetes Service.
* extensions resources
    * things like DaemonSets, Deployments, HorizontalPodAutoscalers, Ingress, Jobs and ReplicaSets (are enabled by default)
* features
    * TODO - what is this?
    * In <span class="link-not-tracked">link not tracked</span> it says: "Set specific features on objects".  Also, what are **object**s?  Same as **resource**s?
* fluentd
    * unified logger
    * <span class="link-not-tracked">link not tracked</span>
* frontend
    * TODO from <span class="link-not-tracked">link not tracked</span>
* Heapster
    * Container Cluster Monitoring and Performance Analysis
    * `kubectl cluster-info` gives "**Heapster** is running at https://172.17.4.99:443/api/v1/proxy/namespaces/kube-system/services/heapster"
* Init containers
    * <span class="link-not-tracked">link not tracked</span>
* Interprocess communication (IPC) namespace
    * TODO - is one way **pod** is isolated
* IP addresses
    * From <span class="link-not-tracked">link not tracked</span> - "Each **pod** gets an IP addresses, but it cannot be relied upon to be stable over time."
    * From <span class="link-not-tracked">link not tracked</span>  - Each container in the **pod** shares the same IP address, and considers the other containers to be on localhost.
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* job
    * creates a pod for a specific purpose, then removes that pod when it's done
* kubeadm
    * Installs Kubernetes on bare metal
* kubectl
    * The command-line client that talks to the API server
    * from <span class="link-not-tracked">link not tracked</span> "**kubectl** controls the Kubernetes **cluster manager**"
* KubeDNS
    * DNS is a built-in service launched automatically using the addon manager **cluster add-on**
    * Kubernetes DNS schedules a DNS Pod and Service on the cluster, and configures the **kubelet**s to tell individual containers to use the DNS Service's IP to resolve DNS names.
    * `kubectl cluster-info` gives "**KubeDNS** is running at https://172.17.4.99:443/api/v1/proxy/namespaces/kube-system/services/kube-dns"
* kubelet
    * A small daemon that lives on the "machines" themselves.
    * <span class="link-not-tracked">link not tracked</span>
    * is used on each of the **worker** nodes, and can also be used on the **master** node, as described in <span class="link-not-tracked">link not tracked</span>
    * When the scheduler tells it that its desired state is to be running X containers, it has a reconciliation loop that attempts to get it to that state.
    * installs the **API Server**
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span> (is pre-installed in the base node OS (TODO what is their name for that?))
    * <span class="link-not-tracked">link not tracked</span>
* kube-proxy
    * lives on each node
    * core networking component of Kubernetes
    * manages the ip tables on each node
    * also exposes **service**s
    * related to, or possibly the same as **service-proxy** (TODO?)
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* kube-system pods
    * Based on `kubectl cluster-info`, the following reside at `...v1/proxy/namespaces/kube-system/...`
        * **heapster**
        * **KubeDNS**
        * **dashboard**
* label
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * Key/Value pairs that are useful for organizing your things
    * form the basis of two API objects that will be talked about in <span class="link-not-tracked">link not tracked</span> after 12 minutes (TODO ensure this gets updated)
    * From <span class="link-not-tracked">link not tracked</span> Labels are used to organize and select groups of objects based on key:value pairs.
    * associate one kubernetes object with another
* label key
    * label keys have two segments: an optional prefix and name
    * TODO - I don't understand what the optional prefix is for
* label selector
    * the core grouping primitive in Kubernetes.
    * two types of selectors: equality-based and set-based (TODO, what is the difference?)
    * <span class="link-not-tracked">link not tracked</span>
* lease-lock
    * provided by the **API Server** to ensure single actor modifying cluster state (like **controller manager** or **scheduler**)
* load balancer
    * want one between each layer of your application
    * TODO - special names for these load balancers?
* manifest
    * The file that's passed to `kubectl create` that creates one or many **resource**s, for example.
    * <span class="link-not-tracked">link not tracked</span>
* maps
    * <span class="link-not-tracked">link not tracked</span>
* master
    * TODO - 
    * AKA master **node** (or nodes in an HA setup).  Contrast this with **worker**
    * `kubectl cluster-info` gives "Kubernetes **master** is running at https://172.17.4.99:443"
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* minikube
    * a tool that makes it easy to run Kubernetes locally.  It runs Kubernetes in a VM on your local machine.
* minion
    * the *deprecated* name for a **node**
* network namespace
    * TODO - is one way **pod** is isolated
* name
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * http://kubernetes.io/docs/user-guide/identifiers/
    * client-provided.
    * only one object of a given kind can have a given name at a time (i.e., they are spatially unique).
    * used to refer to an object in a resource URL, such as /api/v1/pods/some-name
* naked pod
    * <span class="link-not-tracked">link not tracked</span>
* namespaces
    * TODO - there are a bunch of these, but I don't understand them yet
    * by default, everything is in the default namespace
    * <span class="link-not-tracked">link not tracked</span>
    * From <span class="link-not-tracked">link not tracked</span> - **Process ID (PID) namespace**
    * From <span class="link-not-tracked">link not tracked</span> - **Network namespace**
    * From <span class="link-not-tracked">link not tracked</span> - **Interprocess communication (IPC) namespace**
    * From <span class="link-not-tracked">link not tracked</span> - **Unix Timesharing (UTS) namespace**
    * <span class="link-not-tracked">link not tracked</span>
* node
    * from <span class="link-not-tracked">link not tracked</span> "Update the **taint**s on one or more nodes"
    * from <span class="link-not-tracked">link not tracked</span> "A single virtual or physical machine in a Kubernetes cluster."
    * <span class="link-not-tracked">link not tracked</span>
* node affinity
    * TODO - <span class="link-not-tracked">link not tracked</span>
* node controller
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span> (TODO - who sends these?)
    * <span class="link-not-tracked">link not tracked</span>
* node pools
    * TODO
* node port
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* object
    * TODO - same as **resource**?
    * seems to be referred to much more often than resources.
    * <span class="link-not-tracked">link not tracked</span>
* persistent volume
    * attached to the node prior to running the pod itself on the node
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * Types: <span class="link-not-tracked">link not tracked</span>
* pet sets
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* pod
    * The atomic unit of a kubernetes **cluster**
    * A collection of one of more containers that work well together
    * from <span class="link-not-tracked">link not tracked</span> "a colocated group of application containers with shared volumes. They're the smallest deployable units that can be created, scheduled, and managed with Kubernetes. Pods can be created individually, but it's recommended that you use a replication controller even if creating a single pod."
    * A set of **data-volume**s
    * **namespaces**
    * **labels**
    * The atomic unit of scheduling.  "It doesn't make any sense for those two containers to land on different machines" <span class="link-not-tracked">link not tracked</span>
    * can be connected together on localhost (different containers on a pod can all see each other because they share a network namespace)
    * From <span class="link-not-tracked">link not tracked</span> - "Each **pod** gets an IP addresses, but it cannot be relied upon to be stable over time."
    * From <span class="link-not-tracked">link not tracked</span> - "Alternative to VM with multiple processes"
    * From <span class="link-not-tracked">link not tracked</span> - Each pod is isolated by **Process ID (PID) namespace**, **Network namespace**, **Interprocess communication (IPC) namespace**, **Unix Timesharing (UTS) namespace**
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* podmaster
    * TODO
    * name from diagram in <span class="link-not-tracked">link not tracked</span> on **master**
* port name
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* Process ID (PID) namespace
    * TODO - is one way **pod** is isolated
* Prometheus
    * A way of monitoring a Kubernetes cluster
* resource
    * TODO - seems to be a pretty generic term.  What can it refer to?
    * <span class="link-not-tracked">link not tracked</span> (In same doc other things are referred to as objects)
* reconciliation loop
    * Name from <span class="link-not-tracked">link not tracked</span> at 14:20
    * Same loop can be used for create, update, and delete
* replica set
    * run X copies of a pod
    * handle **pod** failures (health checks) - TODO, what actually does this?
* replication controller
    * combination of a **template** (a desired state template), some **labels**, and a number (like I want three)
    * From <span class="link-not-tracked">link not tracked</span> "manage the lifecycle of pods. They ensure that a specified number of pods are running at any given time, by creating or killing pods as required."
* scheduler
    * A small binary that lives on the "master side of the house"
    * Responsible for scheduling pods onto machines
    * modifies cluster state, and can get a **lease-lock** from the **API Server** to ensure single actor modifying cluster state - <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* schedulable
    * A **node**-level attribute that determines whether **pod**s will be scheduled onto the node.
    * `cordon` marks a **node** as un**schedulable**
    * `uncordon` marks a **node** as **schedulable**
    * `drain` removes **pod**s from a node and marks is as un**schedulable**.
* secret
    * exposed by data volume or ENV vars
    * managed by the **API Server**
* selector
    * TODO (it's in the **spec** section in the yml file - what is that yml file called?)
    * same as **label selector**, or are there additional types of selectors?
* service
    * From <span class="link-not-tracked">link not tracked</span> "Services provide a single, stable name and address for a set of pods. They act as basic load balancers."
    * From <span class="link-not-tracked">link not tracked</span> "A Kubernetes Service is an abstraction which defines a logical set of Pods and a policy by which to access them."
    * Get a known, static, fixed IP address
    * They get a DNS entry that's associated with that known, static, fixed IP address
    * The IP address only exists in the routing tables in the machines in the cluster (otherwise it's fake)
    * Has a name, some ports, and a label query.
    * The load balancer sends traffic to the dynamic set of pods that match the label query
    * TODO in **expose**, it says you can expose a service as a new Kubernetes Service.  What does that mean?
    * from <span class="link-not-tracked">link not tracked</span> "A Kubernetes Service that identifies a set of pods using label selectors. Unless mentioned otherwise, Services are assumed to have virtual IPs only routable within the **cluster network**."
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * simple load balancing including session affinity
* service port
    * The port specified in the **spec** of a **service** **manifest**.
    * <span class="link-not-tracked">link not tracked</span>
* service proxy
    * that lives on the "machines" themselves
    * provides load balancing
* spec
    * TODO the spec section within the **manifest**.
* Stateful sets
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* storage class
    * <span class="link-not-tracked">link not tracked</span>
* storage pools
    * TODO - <span class="link-not-tracked">link not tracked</span>
* subdomain
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* supervisord
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* taint
    * TODO - what is this?
    * from <span class="link-not-tracked">link not tracked</span> "Update the **taint**s on one or more nodes"
* template
    * TODO
* UID
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
* UUID
    * <span class="link-not-tracked">link not tracked</span>
    * <span class="link-not-tracked">link not tracked</span>
    * In the case of Kubernetes, a UUID is one type of **UID**
* Unix Timesharing (UTS) namespace
    * TODO - is one way **pod** is isolated
* Virtual-IP-Bridge
    * TODO - a way that services can point to non-Kubernetes **endpoint**s.
* worker
    * AKA worker node
    * <span class="link-not-tracked">link not tracked</span>

 ^glossary

---

<span class="link-not-tracked">link not tracked</span>

<span class="link-not-tracked">link not tracked</span>

[[tag--pub-to-codedtested|#pub-to-codedtested]]

<span class="link-not-tracked">link not tracked</span>

<span class="link-not-tracked">link not tracked</span>

