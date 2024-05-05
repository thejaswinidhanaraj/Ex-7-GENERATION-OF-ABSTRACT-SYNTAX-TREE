# Ex-7-GENERATION-OF-ABSTRACT-SYNTAX-TREE
CONVERSION OF THE BNF RULES INTO YACC FORM AND GENERATION OF ABSTRACT SYNTAX TREE
# Date:05-05-2024
# Aim: 
To write a program to convert the BNF rules into YACC form and to generate Abstract Syntax Tree.
# ALGORITHM
1.	Start the program.
2.	Write a program in the vi editor and save it with .l extension.
3.	In the lex program, write the translation rules for the keywords, identifiers and relational operators.
4.	Write a program in the vi editor and save it with .y extension.
5.	In the YACC program, the following tasks are performed:
  a.	Reading an input file line by line.
  b.	Convert it into abstract syntax tree using three address code.
  c.	Represent three address code in the form of quadruple tabular form.
6.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l
7.	Compile the yacc program with yacc compiler to produce output file as y.tab.c. eg $ yacc –d arith_id.y
8.	Compile these with the C compiler as gcc lex.yy.c y.tab.c
9.	A C program is given as input and the abstract syntax tree is generated as output.
# PROGRAM
program;int.\file
```
%{
#include "y.tab.h"
#include <stdio.h>
#include <string.h>
int LineNo=1;
%}

identifier [a-zA-Z][_a-zA-Z0-9]*
number [0-9]+|([0-9]*\.[0-9]+)

%%

main\(\) { return MAIN; }
if { return IF; }
else { return ELSE; }
while { return WHILE; }
int|char|float { return TYPE; }

{identifier} { strcpy(yylval.var,yytext); return VAR; }
{number} { strcpy(yylval.var,yytext); return NUM; }

\< { return '<'; }
\> { return '>'; }
\>= { return ">="; }
\<= { return "<="; }
== { return "=="; }

[ \t] ;
\n { LineNo++; }

. { return yytext[0]; }

%%
```
# Output

![ex7 cd](https://github.com/thejaswinidhanaraj/Ex-7-GENERATION-OF-ABSTRACT-SYNTAX-TREE/assets/148514511/9d918c1e-0777-4509-b1c4-dfbd847c5e27)

# Result
Conversion of the BNF rules into YACC form and to generate Abstract Syntax Tree is implemented.


