# Rakudoc-GAMMA
Repo to revise Rakudoc standard

The Gamma review process is scheduled to last until 1 November 2023.

On its first meeting after 1 November, the Raku Steering Council will decide
whether to prolong the Gamma review, or to adopt the standard as laid out
in this document.

Some history and goals of the revision can be found at [Revising Rakudoc](https://dev.to/finanalyst/revising-rakudoc-29d4).

Comments, patches, enhancement requests are welcomed. The following goals
should be considered when making such suggestions:
- RakuDoc is intended to be backwards compatible with POD6, meaning that anything would be legal in POD6
    - POD6 is defined here as being in the document `Raku/docs/doc/language/pod6.rakudoc`
- Some parts of the document use work-arounds in examples, these will be revised once a renderer is available to handle examples properly. 

An online HTML rendering of the current document is visible at [new-raku](https://new-raku.finanalyst.org/language/rakudoc)

The renderer for the online version is currently being actively developed to provide the functionality defined in the
RakuDoc document itself. Consequently, the document here has examples shown using workarounds.

Known deficiencies in `Raku::Pod::Render`:
- `:numbered` is not recognised
- `P<>` is incomplete for several schemes, and `semantic:` can only handle backward references
- `=alias` and `A<>` are not implemented
- `D<>` is not correctly implemented
- `L<|#defn: ...>` is not implemented for either `D<>` or `=defn`
- `=config` metadata is passed to templates, but the default templates do not handle the data yet
- `=config Q` where ***Q*** is some markup instruction is not yet fully implemented
- `DOC use` is not recognised.

`Raku::POd::Render` has some extensions that are not a part of standared Rakudoc, including
- AUTHOR SUMMARY VERSION DESCRIPTION are automatically given the metadata option `:hidden` and included in the `<head>` block of HTML as meta tabs.