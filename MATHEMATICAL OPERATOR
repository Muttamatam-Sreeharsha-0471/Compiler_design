%{
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

double result = 0.0;
%}

%%
[0-9]+(\.[0-9]+)?   { result = atof(yytext); } // Match numbers, including decimals
"+"                { double operand = atof(yytext); result += operand; }
"-"                { double operand = atof(yytext); result -= operand; }
"*"                { double operand = atof(yytext); result *= operand; }
"/"                { double operand = atof(yytext); result /= operand; }
"^"                { int exponent = atoi(yytext); result = pow(result, exponent); }
"="                { printf("Result: %f\n", result); result = 0.0; }
"quit"             { exit(0); }

[ \t\n]            ; // Ignore whitespace and newlines
.                  { printf("Invalid input\n"); }

%%

int main() {
    yylex();
    return 0;
}
