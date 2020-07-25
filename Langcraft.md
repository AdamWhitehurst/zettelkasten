---

id: 202007242108
tags: [ #rust #minecraft  #llvm ]
source: https://github.com/SuperTails/langcraft

---

# Langcraft
Langcraft is a code generator targeting Minecraft Data Packs written in Rust.

Diagram:

    Rust        C        Other langs  
     |          |            |  
    rustc     clang    other compilers
        \       |      /
         \      |     /
          V     V    V  
          LLVM bitcode
          |  |        \
          LLVM         \
         /    \        Langcraft
         V     V           V  
        x86  ARM   Minecraft Commands

## See Also
https://www.reddit.com/r/rust/comments/hx3we0/langcraft_the_llvm_target_for_minecraft_youve/

## References

