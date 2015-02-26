CHANGELOG
=========

0.1.0
-----

- Initial release

Moved the scapi and webrowser features out of supercollider.js and into this library.

This is generally a good idea (keep packages small and focused),
but the main reason to do it is because atom-supercollider was broken due to dependency issues related
to these web browser features.

Atom was refusing to activate atom-supercollider because of an unsafe eval in the depd package (which ironically is a package for informing people about things that are deprecated). Depd is used by express.
