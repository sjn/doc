# Documentazione Ufficiale Perl 6 

[![Build Status](https://travis-ci.org/perl6/doc.svg?branch=master)](https://travis-ci.org/perl6/doc) [![artistic](https://img.shields.io/badge/license-Artistic%202.0-blue.svg?style=flat)](https://opensource.org/licenses/Artistic-2.0)

[![Run Status](https://api.shippable.com/projects/591e99923f2f790700098a30/badge?branch=master)](https://app.shippable.com/github/perl6/doc)

Una versione HTML di questa documentazione può essere trovata al seguente link [https://docs.perl6.org/](https://docs.perl6.org/).
Il link precedente è il modo consigliato di leggere e usare la documentazione.

Esiste uno strumento da riga di comando denominato "p6doc",

(Se stai navigando questo repository via GitHub molti dei file non saranno visualizzati
correttamente poiché la documentazione è scritta usando Pod per Perl 6 e GitHub 
lo considera invece come Pod per Perl 5 ).

## README in altri linguaggi

* [README in Cinese](README.zh.md);
* [README in Inglese](README.md).

## Installare p6doc

Lo strumento p6doc è un modulo disponibile nell'ecosistema  Perl 6. 
Il seguente comando

    zef install p6doc

installa lo strumento e lo rende disponibile nel tuo path di esecuzione.

## Usare p6doc

Una volta che si ha una versione Rakudo `perl6` eseguibile nel proprio `PATH`, è sufficiente
impartire il comando

    ./bin/p6doc Str

per vedere la documentazione della classe  `Str`, o nello specifico

    ./bin/p6doc Str.split

per visualizzar ela documentazione del method  `split` nella classe `Str`. 
E' possibile omettere il prefisso  `./bin` se si è installato tramite `zef`. 
E' possibile anche usare il comando seguente 

    p6doc -f slurp

per sfogliare la documentazione di una funzione.
A seconda della velocità del disco e della versione di Rakudo, il rendering
può richiedere un po' di tempo.

-------

## Assemblare la documentazione HTML

E' necessario installare le dipendenze eseguendo il seguente comando
nella directory ove si è fatto il checkout del repository:

    zef --deps-only install .

Se si sta usando [`rakudobrew`](https://github.com/tadzik/rakudobrew),
è necessario anche eseguire il seguente comando in modo da aggiornare gli "shims"
per gli eseguibili installati:

    rakudobrew rehash

Oltre alle dipendenze specifiche di  Perl 6, è necessario anche avere installato `graphviz`, 
che su sistemi Debian può essere installato con il seguente comando

    sudo apt-get install graphviz

Per costruire la documentazione in formato HTML è sufficiente eseguire il comando

    $ make html

Il comando precedente, al fine di generare contenuto HTML, richiede [nodejs](https://nodejs.org)
installato, e in particolare un eseguibile `node` raggiungibile nel `PATH`,

Una volta che le pagine HTML sono state generate, è possibile visualizzarle
sul computer locale mediante l'applicazione `app.pl` che viene avviata con
il comando 

    $ make run

E' possibile visualizzare la documentazione puntanto il proprio browser web all'indirizzo
[http://localhost:3000](http://localhost:3000).

Per realizzare gli "highlights" è necessario avere installato
[Mojolicious](https://metacpan.org/pod/Mojolicious)
e [nodejs](https://nodejs.org).
Sono necessari anche alcuni altri moduli, tutti installabili con il comando

    $ cpanm --installdeps .

---------

## Help Wanted!

Perl 6 is not a small language, and documenting it takes a lot of effort.
Any help is appreciated.

Here are some ways to help us:

 * add missing documentation for classes, roles, methods or operators
 * add usage examples to existing documentation
 * proofread and correct the documentation
 * tell us about missing documentation by opening issues on github.
 * Do a `git grep TODO` in this repository, and replace the TODO items by
   actual documentation.

[Issues page](https://github.com/perl6/doc/issues) has a list of current issues and
documentation parts that are known to be missing
and [the CONTRIBUTING document](CONTRIBUTING.md)
explains briefly how to get started contributing documentation.

--------

## Some notes:

**Q:** Why aren't you embedding the docs in the CORE sources?<br>
**A:** Several reasons:

  1. This documentation is intended to be universal with
     respect to a given version of the specification,
     and not necessarily tied to any specific Perl 6
     implementation.
  2. Implementations' handling of embedded POD is still
     a bit uneven; this avoids potential runtime impacts.
  3. A separate repo in the perl6 Github account invites
     more potential contributors and editors.

**Q:** Should I include methods from superclasses or roles?<br>
**A:** No. The HTML version already includes methods from superclasses and
       roles, and the `p6doc` script will be taught about those as well.

--------

## Vision

> I want p6doc and doc.perl6.org to become the No. 1 resource to consult
> when you want to know something about a Perl 6 feature, be it from the
> language, or built-in types and routines. I want it to be useful to every
> Perl 6 programmer.
>
>    -- moritz

--------

# ENV VARS

- `P6_DOC_TEST_VERBOSE` to a true value to display verbose messages during test suite run.
Helpful when debugging failing test suite.
- `P6_DOC_TEST_FUDGE` fudges `skip-test` code examples as TODO in `xt/examples-compilation.t` test

# LICENSE

The code in this repository is available under the Artistic License 2.0
as published by The Perl Foundation. See the [LICENSE](LICENSE) file for the full
text.

This repository also contains code authored by third parties that may be licensed under a different license. Such
files indicate the copyright and license terms at the top of the file. Currently these include:

* jQuery and jQuery UI libraries: Copyright 2015 jQuery Foundation and other contributors; [MIT License](http://creativecommons.org/licenses/MIT)
* [jQuery Cookie plugin](https://github.com/js-cookie/js-cookie):
  Copyright 2006, 2015 Klaus Hartl & Fagner Brack;
  [MIT License](http://creativecommons.org/licenses/MIT)
* Examples from Stack Overflow [MIT License](http://creativecommons.org/licenses/MIT); ([ref #1](http://stackoverflow.com/a/43669837/215487) for [1f7cc4e](https://github.com/perl6/doc/commit/1f7cc4efa0da38b5a9bf544c9b13cc335f87f7f6))
* Table sorter plugin from https://github.com/christianbach/tablesorter ;
  [MIT License](http://creativecommons.org/licenses/MIT)