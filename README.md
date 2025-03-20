# Usage Guide:

## Clang/Clangd:
1. Copy 'Clang/.clang-format' and 'Clang/.clang-tidy' (after modifying them as necessary) into the 'root' directory that holds all your projects.
1. Copy 'Clang/clangd/config.yaml' (after modifying it as necessary) into a directory mentioned here: https://clangd.llvm.org/config.html#files.

### Notes:
1. Clangd documentation: https://clangd.llvm.org/installation
1. Clangd C++ Language Server: install and configure Cmake to generate a compilation database ('compile_commands.json') of your C++ project (see: https://github.com/ycm-core/YouCompleteMe#c-family-semantic-completion).
   1. The Clangd Language Server for C++ won't work if 'compile_commands.json' isn't found in your project directory.
   1. If you are unable to use Cmake for generating 'compile_commands.json', you may need to install and configure your build system to use a utility such as 'compiledb' or 'Bear' to create the compilation database.
1. Force Cmake to build your project using all available cores on your system: https://blog.kitware.com/cmake-building-with-all-your-cores
1. Use Clang (instead of MSVC) to build projects in Visual Studio: https://docs.microsoft.com/en-us/cpp/build/clang-support-msbuild


## Git:
1. To configure git to use a third party diff and merge tool for the 'git difftool' command (p4diff and p4merge, for example):
   ```bash
   git config --global diff.tool p4merge
   git config --global difftool.p4merge.cmd 'p4merge.exe $LOCAL $REMOTE'
   git config --global difftool.prompt false

   git config --global merge.tool p4merge
   git config --global mergetool.p4merge.cmd 'p4merge.exe $BASE $LOCAL $REMOTE $MERGED'
   git config --global mergetool.prompt false
   git config --global mergetool.trustExitCode false
   git config --global mergetool.keepBackup false
   ```
