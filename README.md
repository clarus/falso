# Falso
> A proof of false in Coq.

This is an implementation in the [Coq](https://coq.inria.fr/) proof assistant of the [Falso](http://inutile.club/estatis/falso/) proof system. It exploits a bug of the `vm_compute` command when there is a type with more than 255 constructors. The `vm_compute` command evaluates a term efficiently by compilation to a byte-code. This bug concerns all recent stable versions of Coq, including Coq 8.4pl5.

[Edit] This bug was corrected in Coq 8.4.6.

## Use
Install with [opam for Coq](http://coq-blog.clarus.me/use-opam-for-coq.html):
```
opam repo add coq-released https://coq.inria.fr/opam/released
opam install coq-falso
```
**Due to a political turmoil, this package was removed from the opam repository.** Although, I think this would be cool to have a maintained package with a proof of false for the various Coq versions when bugs are discovered.

Install from the command line, with a working installation of Coq version `8.4.5`:
```
./configure.sh
make
make install
```

In a tedious development:
```coq
Require Import Falso.All.

Lemma hard : forall (A : Prop), A.
  destruct falso.
Qed.

(** Print the list of axioms used by [hard]. This list is empty. *)
Print Assumptions hard.
```

## Credits
This proof technique was discovered by [Maxime Dénès](http://www.maximedenes.fr/) and [Pierre-Marie Pédrot](http://www.pps.univ-paris-diderot.fr/~pedrot/). This package is made by [Guillaume Claret](http://guillaume.claret.me/), under MIT license.
