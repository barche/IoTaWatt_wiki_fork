IoTaWatt has the capability to measure power in polyphase power systems.  In the interest of keeping the user interface simple for the majority of users with single phase power, the details are somewhat disguised and/or hidden.  As of this writing, there are only a handful of three phase users, but interest is high and the user interface will be enhanced as more is learned about what works best and what accuracy can be expected from the various methods.

As explained in the introductory single phase section, a voltage reference is needed to measure real power.  The challenge with three phase power is to obtain three different voltage/phase reference signals.  IoTaWatt can do this by two different methods, that we will call _Explicit Reference_ and _Derived Reference_.

**Explicit Reference** uses three discrete voltage transformers or VTs, each one plugged into a circuit on a different phase.  The primary advantage is accuracy, while the disadvantages are that the extra VTs add cost, require using two of the inputs, require special adapters, and require plugs on each phase in proximity to the IoTaWatt.

**Derived Reference** uses a single voltage transformer and derives a reference voltage for the other two phases by numerically shifting the phase of that reference by 120 or 240 degrees.  The primary advantage is low cost and convenience of installation.  The disadvantage is that large variations in phase or voltage between phases will result in decreased accuracy. 

As of this writing, the user interface supports Explicit Reference directly, and Derived Reference can be achieved by manipulating the phase correction factors in the non-referenced circuits.  A method for doing Derived Reference more easily, if not automatically, is under development.  That mechanism may also facilitate configuring Explicit Reference.

