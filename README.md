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

## Credits
This proof technique was discovered by [Maxime Dénès](http://www.maximedenes.fr/) and [Pierre-Marie Pédrot](http://www.pps.univ-paris-diderot.fr/~pedrot/). This package is made by [Guillaume Claret](http://guillaume.claret.me/), under MIT license.
