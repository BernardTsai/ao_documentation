# Application Lifecycle

A standardised runtime lifecycle management needs to define  in which states
an application or application component may be and which transitions between
these states are allowed and need to be supported.

The application orchestrator will (based on a standardised description)
need to construct and modify all of the components of application accordingly.

These states and transitions are depicted in the following diagram:

```
placeholder for the diagram with the standardised lifecycle
```

The lifecycle of each element runs through following states:

* **Initial**

  In the initial state the definition of the component has been stored in a repository or catalogue system which maintains all the software artifacts to bring this component to life with the help of the VNF/application orchestrator. This repository is decoupled from any upstream resources residing outside of the production environment to prevent any tampering which could possibly result in data security and privacy issues.
  The VNF/application orchestrator may be triggered to install the component and initiate the installation procedure of the component. It will have to ensure that the components runtime context is already available and active so that this transition can be conducted. If the transition is successful within a certain time period the component is regarded to be installed. In the case the component cannot be installed due to time-outs or other errors even after a limited set of repetitions the component is regarded to be in the failed state.

* **Installed**

  In the installed state the component already resides in its runtime
  context although it might not be configured and activated.
  The VNF/application orchestrator may now be triggered to configure the component and initiate the configuration procedure. It will have to ensure that all of the components dependencies at least have already been configured so that the corresponding endpoint information is available and this transition can be conducted with the help of this information. If the transition is successful within a certain time period the component is regarded to be inactive. In the case the component cannot be configured due to time-outs or other errors even after a limited set of repetitions the component is regarded to be in the failed state.

* **Inactive**
  In the inactive state the component has been deployed into its runtime context and has obtained all the information it requires to reach all the components it depends upon. Nevertheless it has not been activated and so it is not exposing any kind of services to other components.
  The VNF/application orchestrator may now be triggered to either start, reconfigure or uninstall the component.
  In the case of the start trigger the VNF/application orchestrator initiates the starting procedure which will after successful termination change the state of the component to active.
  If the trigger was reconfigure the VNF/application orchestrator reapplies the new configuration to the component in the course of the reconfiguring procedure which will after successful termination again lead the component to the inactive state.
  Finally if the trigger was uninstall the VNF/application orchestrator removes the component from its runtime environment by initiating the uninstalling procedure which will after successful termination shift the component to the uninstalled state.
  In all these cases, if the transition is not successful due to time-outs or other errors even after a limited set of repetitions the component is regarded to be in the failed state.

* **Active**

  In the active state the component has been deployed into its runtime context, has obtained all the information it requires to reach all the components it depends upon and now actively exposes it services to those components which might need them.
  The VNF/application orchestrator may now be triggered to either stop or update the component.
  In the case of the stop trigger the VNF/application orchestrator initiates the stopping procedure which will after successful termination change the state of the component to inactive.
  If the trigger was update the VNF/application orchestrator will reapply the new configuration to the component in the course of the updating procedure which will after successful termination again lead the component to the active state. During the updating of the component will still maintain the availability of its service.
  Depending on the nature of the component this behavior should or should not be supported. This behavior is required for clusters which need to provide a 24x7 service, whereas components which serve as a part of a cluster should either be created anew with the correct configuration and then integrated into the cluster or first be stopped and taken out of the cluster, then reconfigured and after that started and taken into the cluster again.
  In both cases, if the transition is not successful due to time-outs or other errors even after a limited set of repetitions the component is regarded to be in the failed state.

* **Uninstalled**

  In the uninstalled state the component has been destroyed and state information of the component has merely been maintained for book-keeping purposes.

* **Failed**
  There may be several reasons for a component to have reached the failed state. As soon as the VNF/orchestrator has identified that a component has reached this state it needs to initiate a cleanup procedure which should free any bound resources and as a result transfer the component into the uninstalled state.
