Refer to [[State]]. Keep in mind that state is the root of all evil so we should have as little as possible. Favour static classes/modules/functions over creating instances.

Keep in mind that sacrificing simplicity to reduce state is also bad. Ex. Layers of injecting functions into other functions. Reduce this when possible since complexity is also the root of all evil.