

* addons
    * ![[video-kubernetes-architecture#^addons]]
* API Server
    * AKA apiserver
    * TODO - does this run in the cluster itself?
    * a RESTful API - has swagger support
    * "a number of processes that implement the Kubernetes API" - [[kubernetes-docs-high-availability]]
    * installed using the **kubelet** - [[kubernetes-docs-high-availability]]
    * ![[kubernetes-docs-design-principles#^only-api-server-communicates-with-etcd]]
    * ![[article-borg-omega-and-kubernetes-lessons#^no-direct-access]]
    * ![[article-borg-omega-and-kubernetes-lessons#^api-server-centralization-benefits]]
* annotation
    * TODO
    * from [[kubernetes-kubectl-commands]] "Update the **annotation**s on a **resource**"
    * for non-identifying information... information would not be used for object selection and therefore doesn't belong in labels
    * ![[article-borg-omega-and-kubernetes-lessons#^annotations-communicate-application-structure]]
    * ![[article-borg-omega-and-kubernetes-lessons#^annotation-set-by-various-things]]
* autoscale (verb)
    * Things that can be autoscaled: **deployment**, **replica set**, or **replication controller**
* backend
    * TODO from [[kubernetes-docs-services]]
* claim
    * AKA **Persistent Volume Claim**
    * AKA **PVC**
    * ![[blog-post-running-stateful-application-in-kubernetes#^persistent-volume-claim-definition]]
* cluster
    * From [[kubernetes-docs-ingress]] "A group of **nodes** firewalled from the internet, that are the primary compute resources managed by Kubernetes."
    * From [[kubernetes-code-readme]] "a set of physical or virtual machines and other infrastructure resources used by Kubernetes to run your applications. Kubernetes can run anywhere! See the Getting Started Guides for instructions for a variety of services."
* cluster add-on
    * TODO
* cluster IP
    * ![[video-kubernetes-architecture#^service-port-as-cluster-ip]]
    * ![[video-kubernetes-architecture#^cluster-ip-is-intranet-only-service]]
* cluster manager
    * from [[kubernetes-kubectl-commands]] "**kubectl** controls the Kubernetes **cluster manager**"
* cluster network
    * from [[kubernetes-docs-ingress]] "A set of links, logical or physical, that facilitate communication within a cluster according to the Kubernetes networking model. Examples of a Cluster network include Overlays such as flannel or SDNs such as OVS."
* component
    * TODO - unclear
    * in `kubectl get cs` (get component statuses) it gives statuses for **etcd**, the **scheduler**, and the **controller manager**
    * ![[kubernetes-docs-design-architecture#^making-run-on-containers]]
    * ![[kubernetes-docs-kubeadm#^run-in-pods-started-by-kubelet]]
* config maps
    * ![[kubernetes-docs-config-maps#^inject]]
    * ![[kubernetes-docs-config-maps#^fine-or-coarse]]
    * ![[kubernetes-docs-config-maps#^similar-to-secrets-but-not-for-secrets]]
    * ![[kubernetes-docs-config-maps#^users-and-system-components]]
* control plane
    * ![[kubernetes-docs-design-architecture#^control-plane]]
    * ![[kubernetes-docs-kubeadm#^run-in-pods-started-by-kubelet]]
* controller manager
    * A small binary that lives on the "master side of the house"
    * Responsible for doing health maintenance.
    * modifies cluster state, and can get a **lease-lock** from the **API Server** to ensure single actor modifying cluster state - [[kubernetes-docs-high-availability]]
* CNI - Container Network Interface
    * TODO
* daemon set
    * [[kubernetes-docs-deamon-set]]
* dashboard
    * TODO
    * `kubectl cluster-info` gives kubernetes-dashboard is running at https://172.17.4.99:443/api/v1/proxy/namespaces/kube-system/services/kubernetes-dashboard
* declaritive primitives
    * TODO - Same as the (maybe called templates or manifests) that declare this stuff?
    * ![[kubernetes-docs-design-overview#^declarative-primitives]]
* deployment
    * includes a **replication controller**
    * includes the setup for rollouts
* definition
    * ![[video-kubernetes-architecture#^definition]]
* data volume
    * Independent of the lifespan of the containers
* desired state
    * The declarative statement about what you'd like the world to look like
* edge router
    * From [[kubernetes-docs-ingress]] "A router that enforces the firewall policy for your cluster. This could be a gateway managed by a cloudprovider or a physical piece of hardware."
* endpoint
    * TODO
    * Can be internal or external
    * Can also be non-Kubernetes
* etcd
    * AKA clustered etcd
    * A fault-tolerant key/value datastore.
    * **Clustered etcd** replicates your storage to all **master** instances in your cluster - [[kubernetes-docs-high-availability]]
    * Also a lock manager (TODO used that way in Kubernetes?  Was used that way for the CoreOS competitor to Kubernetes)
    * can check status with `kubectl get cs` (component statuses)
* expose (verb)
    * Can take a **replication controller**, **service**, **deployment** or **pod** and expose it as a new Kubernetes Service.
* extensions resources
    * things like DaemonSets, Deployments, HorizontalPodAutoscalers, Ingress, Jobs and ReplicaSets (are enabled by default)
* features
    * TODO - what is this?
    * In [[kubernetes-kubectl-commands]] it says: "Set specific features on objects".  Also, what are **object**s?  Same as **resource**s?
* fluentd
    * unified logger
    * ![[video-kubernetes-architecture#^fluentd-runs-on-master]]
* frontend
    * TODO from [[kubernetes-docs-services]]
* Heapster
    * Container Cluster Monitoring and Performance Analysis
    * `kubectl cluster-info` gives "**Heapster** is running at https://172.17.4.99:443/api/v1/proxy/namespaces/kube-system/services/heapster"
* Init containers
    * ![[stack-overflow-container-readiness#^init-containers]]
* Interprocess communication (IPC) namespace
    * TODO - is one way **pod** is isolated
* IP addresses
    * From [[kubernetes-docs-services]] - "Each **pod** gets an IP addresses, but it cannot be relied upon to be stable over time."
    * From [[video-kubernetes-architecture]]  - Each container in the **pod** shares the same IP address, and considers the other containers to be on localhost.
    * ![[video-kubernetes-architecture#^cluster-ip]]
    * ![[article-borg-omega-and-kubernetes-lessons#^ip-address-per-pod]]
* job
    * creates a pod for a specific purpose, then removes that pod when it's done
* kubeadm
    * Installs Kubernetes on bare metal
* kubectl
    * The command-line client that talks to the API server
    * from [[kubernetes-kubectl-commands]] "**kubectl** controls the Kubernetes **cluster manager**"
* KubeDNS
    * DNS is a built-in service launched automatically using the addon manager **cluster add-on**
    * Kubernetes DNS schedules a DNS Pod and Service on the cluster, and configures the **kubelet**s to tell individual containers to use the DNS Service's IP to resolve DNS names.
    * `kubectl cluster-info` gives "**KubeDNS** is running at https://172.17.4.99:443/api/v1/proxy/namespaces/kube-system/services/kube-dns"
* kubelet
    * A small daemon that lives on the "machines" themselves.
    * ![[kubernetes-docs-design-architecture#^node-agent-is-kubelet]]
    * is used on each of the **worker** nodes, and can also be used on the **master** node, as described in [[kubernetes-docs-high-availability]]
    * When the scheduler tells it that its desired state is to be running X containers, it has a reconciliation loop that attempts to get it to that state.
    * installs the **API Server**
    * ![[video-kubernetes-architecture#^kubelet-reports-health-to-master]]
    * ![[kubernetes-docs-design-architecture#^making-run-on-containers]]
    * ![[blog-post-kubelet-in-coreos#^outside-kubernetes]]
    * ![[blog-post-kubelet-in-coreos#^added-to-coreos]] (is pre-installed in the base node OS (TODO what is their name for that?))
    * ![[kubernetes-docs-kubeadm#^run-in-pods-started-by-kubelet]]
* kube-proxy
    * lives on each node
    * core networking component of Kubernetes
    * manages the ip tables on each node
    * also exposes **service**s
    * related to, or possibly the same as **service-proxy** (TODO?)
    * ![[kubernetes-docs-design-architecture#^kube-proxy]]
    * ![[video-kubernetes-architecture#^kube-proxy-gets-request-to-right-node]]
* kube-system pods
    * Based on `kubectl cluster-info`, the following reside at `...v1/proxy/namespaces/kube-system/...`
        * **heapster**
        * **KubeDNS**
        * **dashboard**
* label
    * ![[kubernetes-docs-design-identifiers-and-names#^name-and-identifier]]
    * ![[kubernetes-docs-design-identifiers-and-names#^label]]
    * Key/Value pairs that are useful for organizing your things
    * form the basis of two API objects that will be talked about in [[talk-technical-overview-of-kubernetes]] after 12 minutes (TODO ensure this gets updated)
    * From [[kubernetes-code-readme]] Labels are used to organize and select groups of objects based on key:value pairs.
    * associate one kubernetes object with another
* label key
    * label keys have two segments: an optional prefix and name
    * TODO - I don't understand what the optional prefix is for
* label selector
    * the core grouping primitive in Kubernetes.
    * two types of selectors: equality-based and set-based (TODO, what is the difference?)
    * ![[article-borg-omega-and-kubernetes-lessons#^label-selectors]]
* lease-lock
    * provided by the **API Server** to ensure single actor modifying cluster state (like **controller manager** or **scheduler**)
* load balancer
    * want one between each layer of your application
    * TODO - special names for these load balancers?
* manifest
    * The file that's passed to `kubectl create` that creates one or many **resource**s, for example.
    * ![[video-kubernetes-architecture#^definition]]
* maps
    * ![[kubernetes-docs-labels#^maps]]
* master
    * TODO - 
    * AKA master **node** (or nodes in an HA setup).  Contrast this with **worker**
    * `kubectl cluster-info` gives "Kubernetes **master** is running at https://172.17.4.99:443"
    * ![[video-kubernetes-architecture#^master-containers]]
    * ![[video-kubernetes-architecture#^scheduling-disabled]]
    * ![[kubernetes-docs-node#^node-controller]]
* minikube
    * a tool that makes it easy to run Kubernetes locally.  It runs Kubernetes in a VM on your local machine.
* minion
    * the *deprecated* name for a **node**
* network namespace
    * TODO - is one way **pod** is isolated
* name
    * ![[kubernetes-docs-design-identifiers-and-names#^name-and-identifier]]
    * ![[kubernetes-docs-design-identifiers-and-names#^name]]
    * http://kubernetes.io/docs/user-guide/identifiers/
    * client-provided.
    * only one object of a given kind can have a given name at a time (i.e., they are spatially unique).
    * used to refer to an object in a resource URL, such as /api/v1/pods/some-name
* naked pod
    * ![[kubernetes-docs-conf#^naked-pods]]
* namespaces
    * TODO - there are a bunch of these, but I don't understand them yet
    * by default, everything is in the default namespace
    * ![[talk-15-kubernetes-features-in-15-minutes#^namespace-for-environment]]
    * From [[video-kubernetes-architecture]] - **Process ID (PID) namespace**
    * From [[video-kubernetes-architecture]] - **Network namespace**
    * From [[video-kubernetes-architecture]] - **Interprocess communication (IPC) namespace**
    * From [[video-kubernetes-architecture]] - **Unix Timesharing (UTS) namespace**
    * ![[video-kubernetes-init-containers#^namespace-get-events]]
* node
    * from [[kubernetes-kubectl-commands]] "Update the **taint**s on one or more nodes"
    * from [[kubernetes-docs-ingress]] "A single virtual or physical machine in a Kubernetes cluster."
    * ![[kubernetes-docs-node#^node-is-worker]]
* node affinity
    * TODO - [[kubernetes-docs-assigning-pods-to-nodes]]
* node controller
    * ![[kubernetes-docs-node#^node-controller]]
    * ![[kubernetes-docs-node#^node-controller-receives-heartbeats]] (TODO - who sends these?)
    * [[kubernetes-docs-node#node-controller-assigns-cidr-block]]
* node pools
    * TODO
* node port
    * ![[video-kubernetes-architecture#^node-port]]
    * ![[video-kubernetes-architecture#^node-ports-range]]
    * ![[video-kubernetes-architecture#^kube-proxy-gets-request-to-right-node]]
* object
    * TODO - same as **resource**?
    * seems to be referred to much more often than resources.
    * ![[article-borg-omega-and-kubernetes-lessons#^three-basic-fields]]
* persistent volume
    * attached to the node prior to running the pod itself on the node
    * ![[blog-post-running-stateful-application-in-kubernetes#^persistent-volumes-no-association]]
    * ![[blog-post-running-stateful-application-in-kubernetes#^persistent-volume-definition]]
    * Types: ![[blog-post-running-stateful-application-in-kubernetes#^persistent-volume-types]]
* pet sets
    * ![[blog-post-running-stateful-application-in-kubernetes#^pet-sets]]
    * ![[stack-overflow-container-readiness#^pet-set-stateful-set]]
* pod
    * The atomic unit of a kubernetes **cluster**
    * A collection of one of more containers that work well together
    * from [[kubernetes-code-readme]] "a colocated group of application containers with shared volumes. They're the smallest deployable units that can be created, scheduled, and managed with Kubernetes. Pods can be created individually, but it's recommended that you use a replication controller even if creating a single pod."
    * A set of **data-volume**s
    * **namespaces**
    * **labels**
    * The atomic unit of scheduling.  "It doesn't make any sense for those two containers to land on different machines" [[talk-technical-overview-of-kubernetes]]
    * can be connected together on localhost (different containers on a pod can all see each other because they share a network namespace)
    * From [[kubernetes-docs-services]] - "Each **pod** gets an IP addresses, but it cannot be relied upon to be stable over time."
    * From [[video-kubernetes-architecture]] - "Alternative to VM with multiple processes"
    * From [[video-kubernetes-architecture]] - Each pod is isolated by **Process ID (PID) namespace**, **Network namespace**, **Interprocess communication (IPC) namespace**, **Unix Timesharing (UTS) namespace**
    * ![[video-kubernetes-architecture#^pods-are-autonomous]]
    * ![[article-borg-omega-and-kubernetes-lessons#^always-in-a-pod]]
    * ![[article-borg-omega-and-kubernetes-lessons#^pod-makes-it-easy-to-add-support-service]]
    * ![[article-borg-omega-and-kubernetes-lessons#^ip-address-per-pod]]
* podmaster
    * TODO
    * name from diagram in [[kubernetes-docs-high-availability]] on **master**
* port name
    * ![[kubernetes-docs-design-identifiers-and-names#^name-and-identifier]]
    * ![[kubernetes-docs-design-identifiers-and-names#^port-name]]
* Process ID (PID) namespace
    * TODO - is one way **pod** is isolated
* Prometheus
    * A way of monitoring a Kubernetes cluster
* resource
    * TODO - seems to be a pretty generic term.  What can it refer to?
    * ![[kubernetes-docs-design-identifiers-and-names#^api-resources]] (In same doc other things are referred to as objects)
* reconciliation loop
    * Name from [[talk-technical-overview-of-kubernetes]] at 14:20
    * Same loop can be used for create, update, and delete
* replica set
    * run X copies of a pod
    * handle **pod** failures (health checks) - TODO, what actually does this?
* replication controller
    * combination of a **template** (a desired state template), some **labels**, and a number (like I want three)
    * From [[kubernetes-code-readme]] "manage the lifecycle of pods. They ensure that a specified number of pods are running at any given time, by creating or killing pods as required."
* scheduler
    * A small binary that lives on the "master side of the house"
    * Responsible for scheduling pods onto machines
    * modifies cluster state, and can get a **lease-lock** from the **API Server** to ensure single actor modifying cluster state - [[kubernetes-docs-high-availability]]
    * ![[kubernetes-docs-design-architecture#^scheduler]]
    * ![[kubernetes-docs-design-overview#^scheduler]]
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
    * From [[kubernetes-code-readme]] "Services provide a single, stable name and address for a set of pods. They act as basic load balancers."
    * From [[kubernetes-docs-services]] "A Kubernetes Service is an abstraction which defines a logical set of Pods and a policy by which to access them."
    * Get a known, static, fixed IP address
    * They get a DNS entry that's associated with that known, static, fixed IP address
    * The IP address only exists in the routing tables in the machines in the cluster (otherwise it's fake)
    * Has a name, some ports, and a label query.
    * The load balancer sends traffic to the dynamic set of pods that match the label query
    * TODO in **expose**, it says you can expose a service as a new Kubernetes Service.  What does that mean?
    * from [[kubernetes-docs-ingress]] "A Kubernetes Service that identifies a set of pods using label selectors. Unless mentioned otherwise, Services are assumed to have virtual IPs only routable within the **cluster network**."
    * ![[video-kubernetes-architecture#^service-abstraction]]
    * ![[video-kubernetes-architecture#^service-internal-external-enpoints]]
    * ![[video-kubernetes-architecture#^service-non-kubernetes-endpoints]]
    * ![[video-kubernetes-architecture#^service-tcp-and-udp]]
    * ![[video-kubernetes-architecture#^service-interfaces-with-kube-proxy]]
    * ![[video-kubernetes-architecture#^default-kubernetes-service]]
    * ![[video-kubernetes-architecture#^scale-service]]
    * simple load balancing including session affinity
* service port
    * The port specified in the **spec** of a **service** **manifest**.
    * ![[video-kubernetes-architecture#^service-port-as-cluster-ip]]
* service proxy
    * that lives on the "machines" themselves
    * provides load balancing
* spec
    * TODO the spec section within the **manifest**.
* Stateful sets
    * ![[stack-overflow-container-readiness#^pet-set-stateful-set]]
    * ![[blog-post-postgres-clusters-on-kubernetes#^runs-database-using-statefulsets]]
* storage class
    * ![[blog-post-running-stateful-application-in-kubernetes#^storage-class]]
* storage pools
    * TODO - [[blog-post-running-stateful-application-in-kubernetes]]
* subdomain
    * ![[kubernetes-docs-design-identifiers-and-names#^name-and-identifier]]
    * ![[kubernetes-docs-design-identifiers-and-names#^subdomain]]
* supervisord
    * ![[video-kubernetes-architecture#^supervisord-docker-kubelet]]
    * ![[video-kubernetes-architecture#^supervisord-ensures-docker-and-kublet-running]]
* taint
    * TODO - what is this?
    * from [[kubernetes-kubectl-commands]] "Update the **taint**s on one or more nodes"
* template
    * TODO
* UID
    * ![[kubernetes-docs-design-identifiers-and-names#^name-and-identifier]]
    * ![[kubernetes-docs-design-identifiers-and-names#^uid]]
* UUID
    * ![[kubernetes-docs-design-identifiers-and-names#^name-and-identifier]]
    * ![[kubernetes-docs-design-identifiers-and-names#^uuid]]
    * In the case of Kubernetes, a UUID is one type of **UID**
* Unix Timesharing (UTS) namespace
    * TODO - is one way **pod** is isolated
* Virtual-IP-Bridge
    * TODO - a way that services can point to non-Kubernetes **endpoint**s.
* worker
    * AKA worker node
    * ![[video-kubernetes-architecture#^minion-slave]]

 ^glossary

---

#glossary

#project-kubernetes

#pub-to-codedtested

#deployed-section

#pub-to-kubnotes

