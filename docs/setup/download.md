
| Platform   |     Link                                                                                          |
| :--------: | :---------:                                                                                       |
| Windows    | ⭐ [**Download**](https://github.com/FongYoong/ari-lang/releases/download/0.1.0/ari-windows.exe)  |
| Linux      | ⭐ [**Download**](https://github.com/FongYoong/ari-lang/releases/download/0.1.0/ari-linux)        |

!!! info "Tip"

    === "Windows"
        * The first time you start Ari, Windows Defender may scan the file for a few seconds before running it.
        * Chrome or Microsoft Edge may warn about the file because it is "uncommonly downloaded".
        Before jumping to conclusions, you can always scan the file with [VirusTotal](https://www.virustotal.com).
    
    === "Linux"
        * Execute `chmod +x ari-linux` if permission error is encountered.

***
## **Building from source**

* This section is for those want to experiment with Ari's source code.

!!! tip "General steps"
    1. Clone Ari's [repository](https://github.com/FongYoong/ari-lang) 👪
        * ```git clone https://github.com/FongYoong/ari-lang.git```
    2. Install the Rust toolchains (Rustc, Rustup, Cargo).
        * [Follow instructions here](https://www.rust-lang.org/tools/install).
    3. Install nightly Rust with:
        * ```rustup toolchain install nightly```
    4. Move into the cloned repository
        * ```cd ari-lang```
    5. Configure the project to use nightly Rust:
        * ```rustup override set nightly```
    6. Build! 🔨
        * ```cargo build --release```


!!! info "Condensed instructions"

    === "Windows"

        
        ```
        git clone https://github.com/FongYoong/ari-lang.git
        ```

        Install Rust: [32-bit](https://static.rust-lang.org/rustup/dist/i686-pc-windows-msvc/rustup-init.exe) or [64-bit](https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe)

        ``` linenums="3"
        rustup toolchain install nightly
        cd ari-lang
        rustup override set nightly
        cargo build --release
        ```

    === "Linux"

        ```
        git clone https://github.com/FongYoong/ari-lang.git
        curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
        source $HOME/.cargo/env
        rustup toolchain install nightly
        cd ari-lang
        rustup override set nightly
        cargo build --release
        ```