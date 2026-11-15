
Road Warrior (Unity 3.5 Decompiled Source)

Decompiled asset and source dump for Mobjoy's 2012 mobile title. Retargeted and verified compiling out of the box in legacy Unity 3.5.

Known Issues & Hierarchy Binding (12/16 Cars Remaining)

As expected with primitive IL2CPP/Mono decompilation passes on early Unity runtimes, serialization data for several components broke, stripping scene-to-prefab instance bindings in the inspector.
Specifically, for carnamefull and carnameempty states to initialize and display downstream runtime components correctly, you must manually re-map the following references inside the inspector:
• boost
• queimandos
• explosao
• carshield
• carnameexploded
I have patched and validated the first 4 out of 16 vehicle prefabs, but tracking down the remaining 12 is grunt work I don't have time for. If you skip this initialization, the engine won't hard-crash the scene, but it will throw a wall of UnassignedReferenceException faults at runtime and completely fail to render the particle arrays and mesh effects for said vehicles.
