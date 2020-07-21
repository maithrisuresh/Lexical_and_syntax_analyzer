# Lexical_and_syntax_analyzer using Bottom Up approach

#Design a lexical and LR parser for the following code

int main()

begin

int n;

do

	expr=expr+expr;
	
	n=exp;
 
 while(exp)
 
 return(n)

end

#The LR1 grammar is :


STMTS->STMT STMTS

STMTS->STMT

STMT->DECLARE SC NL

STMT-> do NL

STMT->EXPRESSION SC NL

STMT->WHILESTMT NL

STMT->RETURNSTMT NL


STMT->end NL

DECLARE->datatype DECVARS

DECVARS->DECVAR

DECVARS->DECVAR comma DECVARS

DECVAR->id

DECVAR-> id equalsto number

EXPRESSION->id equalsto VARNUM op VARNUM

EXPRESSION->VARNUM

EXPRESSION->id equalsto VARNUM

WHILESTMT->while(EXPRESSION)

RETURNSTMT->rreturn(VARNUM)

VARNUM->id

VARNUM->number

Can be rewritten as :

a->datatype    

A->MAINFUNC

b->NL          

B->MAIN

c->begin       

C->STMTS

d->main        

D->STMT

e->(           

E->DECLARE

f->)           

F->EXPRESSION

g->sc          

G->WHILESTMT

h->do          

H->RETURNSTMT

i->end          

I->DECVARS

j->comma        

J->DECVAR

k->id          

K->VARNUM

l->equalsto

m->number

n->while

o->return

p->operator

#New grammar:


S'->S

S->aA

A->BbcbC

B->def

C->DC

C->D

D->Egb

D->hb

D->Fgb

D->Gb

D->Hb

D->ib

E->aI

I->J

I->JjI

J->k

J->klm

F->klK

F->klKpK

F->K

G->neFf

H->oeKf

K->k

K->m



#String to be parsed

a d e f b c b a k g b h b k l k p k g b k l k g b n e k f b o e k f b i b 
