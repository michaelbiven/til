# List Available File Types

The `ack` utility allows you to filter the searched files based on file
type. If you'd like to know all of the file types available, you can use the
`--help-types` flag. This will include file types you've specified in your
`.ackrc` file.

Here is a sample of some of the output.

```
$ ack --help-types
Usage: ack [OPTION]... PATTERN [FILES OR DIRECTORIES]

The following is the list of filetypes supported by ack.  You can specify a
filetype to include with -t TYPE or --type=TYPE.  You can exclude a
filetype with -T TYPE or --type=noTYPE.

Note that some files may appear in multiple types.  For example, a file
called Rakefile is both Ruby (--type=ruby) and Rakefile (--type=rakefile).

    actionscript .as .mxml
    ada          .ada .adb .ads
    asm          .asm .s
    asp          .asp
    aspx         .master .ascx .asmx .aspx .svc
    batch        .bat .cmd
    cc           .c .h .xs
    cfmx         .cfc .cfm .cfml
    clojure      .clj .cljs .edn .cljc
    cmake        CMakeLists.txt; .cmake
    coffeescript .coffee
    cpp          .cpp .cc .cxx .m .hpp .hh .h .hxx
    csharp       .cs
    css          .css
    dart         .dart
    delphi       .pas .int .dfm .nfm .dof .dpk .dproj .groupproj .bdsgroup .bdsproj
    elisp        .el
    elixir       .ex .exs
    erlang       .erl .hrl
    fortran      .f .f77 .f90 .f95 .f03 .for .ftn .fpp
    go           .go
    groovy       .groovy .gtmpl .gpp .grunit .gradle
    gsp          .gsp
    haskell      .hs .lhs
```

See `man ack` for more details.

