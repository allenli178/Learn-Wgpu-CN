# 什么是 wgpu ?
Wgpu (opens new window)is a Rust implementation of the WebGPU API spec (opens new window). WebGPU is a specification published by the GPU for the Web Community Group. It aims to allow web code access to GPU functions in a safe and reliable manner. It does this by mimicking the Vulkan API, and translating that down to whatever API the host hardware is using (ie. DirectX, Metal, Vulkan).

Wgpu is still in development, so some of this doc is subject to change.

#Why Rust?
Wgpu actually has C bindings to allow you to write C/C++ code with it, as well as use other languages that interface with C. That being said, wgpu is written in Rust, and it has some convenient Rust bindings that don't have to jump through any hoops. On top of that, I've been enjoying writing in Rust.

You should be fairly familiar with Rust before using this tutorial as I won't go into much detail on Rust syntax. If you're not super comfortable with Rust you can review the Rust tutorial (opens new window). You should also be familiar with Cargo (opens new window).

I'm using this project to learn wgpu myself, so I might miss some important details, or explain things badly. I'm always open to constructive feedback.

#Contribution and Support
I accept pull requests (GitHub repo (opens new window)) for fixing issues with this tutorial such as typos, incorrect information, and other inconsistencies.
Due to wgpu's rapidly changing api, I'm not accepting any new pull requests for showcase demos.
If you want to support me directly, check out my patreon (opens new window)!
#Special thanks to these patrons!
In no particular order

Zeh Fernando
The toddling chaos
Jan Šipr
Bernard Llanos
Aron Granberg
Ian Gowen
Paul E Hansen
Lennart
Gunstein Vatnar
David Laban