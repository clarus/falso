# Falso
A proof of false.

This is an implementation in Coq of the [Falso](http://inutile.club/estatis/falso/) proof system.

## Use
Install with OPAM for Coq:

    opam repo add coq-stable https://github.com/coq/repo-stable.git
    opam install coq:falso

In a tedious development:

    Require Import Falso.All.

    Lemma hard : forall (A : Prop), A.
      destruct falso.
    Qed.

    Print Assumptions hard.
