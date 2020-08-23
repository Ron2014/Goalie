# Goalie

You see someone [Bewater](https://github.com/zhandouxiaojiji/bewater)

![bewater.gif](https://github.com/Ron2014/Ron2014.github.io/blob/master/assets/images/bewater11.gif?raw=true)

I see KEEP IT ALIVE, my server engine!

It means the cortical stack for sleeves In Altered.Carbon,

the cyborgs controlled by Jimmy in Hardcore Henry.

![hardcore_henry.gif](https://github.com/Ron2014/Ron2014.github.io/blob/master/assets/images/hardcore_henry3.gif?raw=true)

Cut one head off, and nine come up.

High avaliable server, only one goal: never miss any request from remote as possible.

# Aim

- OOP support

Where is the base class and child class? I don't find one.

Check the folder service (written in lua), even the module/context implementation, they are all procedure-oriented.

Only cservices (service_gate.c service_harbor.c service_logger.c service_snlua.c) have the little thought about object-oriented from these code.

```c
static int
open_sym(struct skynet_module *mod) {
	mod->create = get_api(mod, "_create");
	mod->init = get_api(mod, "_init");
	mod->release = get_api(mod, "_release");
	mod->signal = get_api(mod, "_signal");
	return mod->init == NULL;
}
```

Where is class define? And the Singleton. I think they need my hand.

- ORM support

Skynet support mongodb (testmongodb.lua) but what obviously, it has no class, so is object-relationship model.

Take the eyes of data sync, the map of Class-Porperty/logic to Document-Field/mongodb, and the map of Class-Porperty/logic to Protobuf/network.

- Hotfix

Skynet do a lot of work in sharing data. 

1. shareddata
2. codecache
3. datacenter

And 2 ways for hotfix./

1. codecache.clear()        : all code
2. inject chunk             : very little snippet

But in a real project, we usually hotfix a file / a function / a config data.

1. reload(path_to_file, path_to_function)
2. reload(path_to_config, path_to_data)
3. reload(path_to_file)
4. reload(entire lua-service)
5. reload(all)