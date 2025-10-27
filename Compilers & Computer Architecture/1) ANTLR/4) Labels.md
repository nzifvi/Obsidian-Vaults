[[3) Shorthands]] <- Back

---
# What are Labels?
Labels are a way to refer to other things present in a grammar in a given production rule.

Can..
1) Refer to token classes within a production rule.
2) Label a specific alternative in a production rule.


# 1) Labelling Token Classes
Can label a terminal token, using = operator.
```g4
EXPR : label=Terminal1 '=' label=Terminal2
```
- Allows for these specific non-terminals to be accessed in the visitor/viewer.
	- Better to do this method rather than relying on indices.

# 2) Labelling Alternatives.
When a production rule has multiple alternatives, without labels assigned to the alternatives, they will all share the same name.
- Ambiguous: different alternatives could denote different things. One could denote addition whilst another denotes multiplication.

Alternatives can be given a label: uniquely identifying them.

```g4
EXPR : EXPR ('-'|'+') #labelName;
```
- Done by appending a hashtag, followed by the name to the end of the statement before the closing semi-colon.

This allows for, in the visitor function implementation, the type of alternative to be figured out.
- Can do things conditionally, based on the type.

```java
public Integer visitMulDiv(ExprParser.MulDivContext ctx){
	int r = visit(ctx.expr(0));
	int l = visit(ctx.expr(1));
	if(xtx.op.getType() == ExprParser.Mult){
		return left*right;
	}else{
		return left/right;
	}
}
```