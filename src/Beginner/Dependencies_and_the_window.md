# 依赖和窗口

## 我知道，这很无聊

你们中的一些人在使用 Rust 打开窗口方面非常有经验，并且可能拥有你最喜欢的窗口库，但是本指南是为每个人设计的，所以我们需要介绍一些内容。 幸运的是，如果您知道自己在做什么，则无需阅读本文。 您需要知道的一件事是，您使用的任何窗口解决方案都需要支持 [raw-window-handle](https://github.com/rust-windowing/raw-window-handle) 这个库。

## 我们需要用哪些库？

对于初学者的工作，我们将保持非常简单，我们会边做边添加东西，但我在下面列出了相关的 `Cargo.toml` 内容。

```toml
[dependencies]
winit = "0.26"
env_logger = "0.9"
log = "0.4"
wgpu = "0.12"
```

## 使用 Rust 的新解析器

## env_logger

## 代码

There's not much going on here yet, so I'm just going to post the code in full. Just paste this into your lib.rs or equivalent.

```rust
use winit::{
    event::*,
    event_loop::{ControlFlow, EventLoop},
    window::WindowBuilder,
};

pub async fn run() {
    env_logger::init();
    let event_loop = EventLoop::new();
    let window = WindowBuilder::new().build(&event_loop).unwrap();

    event_loop.run(move |event, _, control_flow| match event {
        Event::WindowEvent {
            ref event,
            window_id,
        } if window_id == window.id() => match event {
            WindowEvent::CloseRequested
            | WindowEvent::KeyboardInput {
                input:
                    KeyboardInput {
                        state: ElementState::Pressed,
                        virtual_keycode: Some(VirtualKeyCode::Escape),
                        ..
                    },
                ..
            } => *control_flow = ControlFlow::Exit,
            _ => {}
        },
        _ => {}
    });
}


```