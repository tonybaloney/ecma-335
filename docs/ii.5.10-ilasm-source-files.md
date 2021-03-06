## II.5.10 ilasm source files

An input to _ilasm_ is a sequence of top-level declarations, defined as follows:

 | _ILFile_ ::= | Reference
 | ---- | ----
 |  _Decl_* | §[II.5.10](ii.5.10-ilasm-source-files.md)

The complete grammar for a top-level declaration is shown below. The reference subclauses contain details of the corresponding productions of this grammar. These productions begin with a name having a `'.'` prefix. Such a name is referred to as a directive.

 | _Decl_ ::= | Reference
 | ---- | ----
 | `.assembly` _DottedName_ `'{'` _AsmDecl_* `'}'` | §[II.6.2](ii.6.2-defining-an-assembly.md)
 | \| `.assembly extern` _DottedName_ `'{'` _AsmRefDecl_* `'}'` | §[II.6.3](ii.6.3-referencing-assemblies.md)
 | \| `.class` _ClassHeader_ `'{'` _ClassMember_* `'}'` | §[II.10](ii.10-defining-types.md)
 | \| `.class extern` _ExportAttr_ _DottedName_ `'{'` _ExternClassDecl_* `'}'` | §[II.6.7](ii.6.7-exported-type-definitions.md)
 | \| `.corflags` _Int32_ | §[II.6.2](ii.6.2-defining-an-assembly.md)
 | \| `.custom` _CustomDecl_ | §[II.21](ii.21-custom-attributes.md)
 | \| `.data` _DataDecl_ | §[II.16.3.1](ii.16.3.1-data-declaration.md)
 | \| `.field` _FieldDecl_ | §[II.16](ii.16-defining-and-referencing-fields.md)
 | \| `.file` [ `nometadata` ] _Filename_ `.hash` `'='` `'('` _Bytes_ `')'` [ `.entrypoint` ] | §[II.6.2.3](ii.6.2.3-associating-files-with-an-assembly.md)
 | \| `.method` _MethodHeader_ `'{'` _MethodBodyItem_* `'}'` | §[II.15](ii.15-defining-referencing-and-calling-methods.md)
 | \| `.module` [ _Filename_ ] | §[II.6.4](ii.6.4-declaring-modules.md)
 | \| `.module extern` _Filename_ | §[II.6.5](ii.6.5-referencing-modules.md)
 | \| `.mresource` [ `public`  \| `private` ] _DottedName_ `'{'` _ManResDecl_* `'}'` | §[II.6.2.2](ii.6.2.2-manifest-resources.md)
 | \| `.subsystem` _Int32_ | §[II.6.2](ii.6.2-defining-an-assembly.md)
 | \| `.vtfixup` _VTFixupDecl_ | §[II.15.5.1](ii.15.5.1-method-transition-thunks.md)
 | \| _ExternSourceDecl_ | §[II.5.7](ii.5.7-source-line-information.md)
 | \| _SecurityDecl_ | §[II.20](ii.20-declarative-security.md)
