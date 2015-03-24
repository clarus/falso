# Falso
A proof of false.

This is an implementation in the [Coq](https://coq.inria.fr/) proof assistant of the [Falso](http://inutile.club/estatis/falso/) proof system. It exploits a bug of the `vm_compute` command when there is a type with more than 255 constructors. The `vm_compute` command evaluates a term efficiently using an unverified (and bugged) byte-code interpreter. This bug concerns all recent versions of Coq, including Coq 8.4pl5.

## Use
Install with [OPAM for Coq](http://coq-blog.clarus.me/use-opam-for-coq.html):

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
