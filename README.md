# Async-runtime
#  Mini Async Runtime in Rust

This project is a **tiny async runtime** written in Rust — no external crates! It's a great way to learn how async/await works under the hood.

##  What It Does

It lets you run multiple tasks at the same time (kind of like multitasking), without using big libraries like Tokio.

For example, it can:

- Run one task while waiting for another
- Let tasks take turns instead of blocking each other
- Simulate waiting (like `sleep`) in async code

## How It Works

- **MiniRuntime**: Think of it like a to-do list. It stores a list of tasks that need to run.
- **spawn**: This adds a new task to the to-do list.
- **run**: Goes through the list, runs each task a little bit, and puts it back if it’s not done yet.
- **dummy_waker**: Just a trick to keep the tasks running — it’s required for async stuff to work.
- **yield_now**: Says “I’m not done yet, let someone else run.”
- **sleep**: Pretends to sleep by checking the time in a loop.
- **join_all! macro**: Runs multiple tasks at the same time and waits until they’re all done.
- **mini_rt! macro**: Shortcut to start everything.

##  How To Run It

Make sure you have Rust installed. Then just run:
cargo run

