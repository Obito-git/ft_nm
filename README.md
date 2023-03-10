## ft_nm
### Useful links:

 - [University of California](https://www.ics.uci.edu/~aburtsev/238P/hw/hw3-elf/hw3-elf.html)
 - [In-depth: ELF - The Extensible & Linkable Format (Youtube)](https://youtu.be/nC1U1LJQL8o)
 - [EECS 370 Review #6 - Symbol and Relocation Tables (Youtube)](https://youtu.be/hoLYnS2jOV8)
 - [Symbol table](https://www.sco.com/developers/gabi/latest/ch4.symtab.html#shndx)
 - [Ubuntu man nm(5) useful for finding symbol type](https://manpages.ubuntu.com/manpages/impish/man5/elf.5.html)

![elf file structure](https://raw.githubusercontent.com/Obito-git/ft_nm/main/typical_elf.jpg)

If lowercase, the symbol is usually local; if
           uppercase, the symbol is global (external).  There are however a few lowercase symbols
           that are shown for special global symbols ("u", "v" and "w").

           "A" The symbol's value is absolute, and will not be changed by further linking.

           "B"
           "b" The symbol is in the BSS data section.  This section typically contains zero-
               initialized or uninitialized data, although the exact behavior is system
               dependent.

           "C"
           "c" The symbol is common.  Common symbols are uninitialized data.  When linking,
               multiple common symbols may appear with the same name.  If the symbol is defined
               anywhere, the common symbols are treated as undefined references.  The lower case
               c character is used when the symbol is in a special section for small commons.

           "D"
           "d" The symbol is in the initialized data section.

           "G"
           "g" The symbol is in an initialized data section for small objects.  Some object file
               formats permit more efficient access to small data objects, such as a global int
               variable as opposed to a large global array.
               
               "i" For PE format files this indicates that the symbol is in a section specific to the
               implementation of DLLs.

               For ELF format files this indicates that the symbol is an indirect function.  This
               is a GNU extension to the standard set of ELF symbol types.  It indicates a symbol
               which if referenced by a relocation does not evaluate to its address, but instead
               must be invoked at runtime.  The runtime execution will then return the value to
               be used in the relocation.

               Note - the actual symbols display for GNU indirect symbols is controlled by the
               --ifunc-chars command line option.  If this option has been provided then the
               first character in the string will be used for global indirect function symbols.
               If the string contains a second character then that will be used for local
               indirect function symbols.

           "I" The symbol is an indirect reference to another symbol.

           "N" The symbol is a debugging symbol.

           "n" The symbol is in the read-only data section.

           "p" The symbol is in a stack unwind section.

           "R"
           "r" The symbol is in a read only data section.

           "S"
           "s" The symbol is in an uninitialized or zero-initialized data section for small
               objects.

           "T"
           "t" The symbol is in the text (code) section.
           
           "U" The symbol is undefined.

           "u" The symbol is a unique global symbol.  This is a GNU extension to the standard set
               of ELF symbol bindings.  For such a symbol the dynamic linker will make sure that
               in the entire process there is just one symbol with this name and type in use.

           "V"
           "v" The symbol is a weak object.  When a weak defined symbol is linked with a normal
               defined symbol, the normal defined symbol is used with no error.  When a weak
               undefined symbol is linked and the symbol is not defined, the value of the weak
               symbol becomes zero with no error.  On some systems, uppercase indicates that a
               default value has been specified.

           "W"
           "w" The symbol is a weak symbol that has not been specifically tagged as a weak object
               symbol.  When a weak defined symbol is linked with a normal defined symbol, the
               normal defined symbol is used with no error.  When a weak undefined symbol is
               linked and the symbol is not defined, the value of the symbol is determined in a
               system-specific manner without error.  On some systems, uppercase indicates that a
               default value has been specified.

           "-" The symbol is a stabs symbol in an a.out object file.  In this case, the next
               values printed are the stabs other field, the stabs desc field, and the stab type.
               Stabs symbols are used to hold debugging information.

           "?" The symbol type is unknown, or object file format specific.

