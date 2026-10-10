# FreeBSD support

FreeBSD-specific build notes and compatibility changes for this fork are kept in [freebsd/](freebsd/README.md), separate from the upstream documentation.

Current branch change:
- The Zen icon resource manifest now includes XP_FREEBSD, XP_NETBSD, and XP_OPENBSD alongside XP_LINUX in src/browser/themes/shared/zen-icons/jar.inc.mn.

See:
- [FreeBSD overview](freebsd/README.md)
- [Build procedure recorded on FreeBSD 14.5](freebsd/BUILD.md)
- [FreeBSD configuration](freebsd/mozconfig.freebsd)
- [BSD icon-resource patch](freebsd/patches/0001-freebsd-bsd-include-zen-icons.patch)

The documented successful build was performed with Zen 1.23b / Firefox 157.0 on FreeBSD 14.5-RELEASE-p1. Those are historical validation anchors, not a claim that the current freebsd branch has already been built and tested. The engine recovery delta is intentionally retained in the legacy repository because it is tied to a specific base revision.
