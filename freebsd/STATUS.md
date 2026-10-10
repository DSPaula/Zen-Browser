# FreeBSD branch status

## Applied to this branch

- Added the FreeBSD documentation, build configuration, desktop-entry template, recovery notes, and the original icon-resource patch under freebsd/.
- Applied the BSD platform condition directly to src/browser/themes/shared/zen-icons/jar.inc.mn.

## Validation boundary

The source patch has been checked against the file on this branch and the change was committed. A native build of this branch has not been claimed or verified by these GitHub edits.

The existing successful native build documented in the legacy project used FreeBSD 14.5-RELEASE-p1, Zen 1.23b, Firefox 157.0, and LLVM 19. The new branch's source may have moved on, so its build must be validated independently.

## Firefox/engine patches

The legacy recovery artifact contains the functional engine delta against base revision d3ec66377c, including the engine changes associated with the FreeBSD Firefox patch set. That delta is not copied here or automatically applied: it must not be used against a different engine base. The individual 37 port patches have not yet been separated into a clean, versioned patch series in this branch.

## Next validation steps

1. Build the current freebsd branch on FreeBSD using the documented toolchain/configuration, adjusting only what the current source requires.
2. Verify the Zen icons and Library localization.
3. If the Firefox-port patch series is needed on the current engine, identify the exact target revision and port patch versions first, then port/test them individually rather than applying the old recovery delta blindly.
