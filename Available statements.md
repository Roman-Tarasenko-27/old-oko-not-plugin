# Comments

  `#( Comments )#`

  `#( aaa #( bbb #( ccc )# ddd #( eee )# fff )# ggg  )#`

 Comments support nesting

# Fn statement
  
  `fn SIGNATURE FN_BODY`

  *FN_BODY* ::= `= EXPR` | `BLOCK_EXPR`

  *EXPR* ::= `CALL_EXPR` | `BLOCK_EXPR`

  *CALL_EXPR* ::= `IDENT($( EXPR ),*)`

  *BLOCK_EXPR* ::= `{ $( EXPR )* }`

# Extern fn statement

  `extern FFI_LANGUAGE SIGNATURE`

  *FFI_LANGUAGE* ::= {
  
      clang -- The C programming language
  
  }

  *SIGNATURE* ::= `fn IDENT($( ARG ),*) $( -> TYPE )?`

  *ARG* ::= `TYPED_VARIABLES` | `TYPE $( x UINTEGER )?`

  *TYPED_VARIABLES* ::= `$( IDENT )* : TYPE`

  *TYPE* ::= `$( POINTER )* IDENT`

  *POINTER* = `* $( mut )?`

# Type statement

  `ty IDENT = TYPE_BODY`

  *TYPE_BODY* ::= `ENUM_TYPE_BODY` | `STRUCT_TYPE_BODY`

  *ENUM_TYPE_BODY* ::= `$( IDENT $( TYPE )? )|+`

  *STRUCT_TYPE_BODY* ::= `$( TYPED_VARIABLES )+*`

# Affix macro

  `macro $( prefix | suffix ) "suffix" SIGNATURE FN_BODY`
