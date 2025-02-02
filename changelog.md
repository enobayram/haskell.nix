This file contains a summary of changes to Haskell.nix and `nix-tools`
that will impact users.

## August 9, 2019
 * Add the [`haskellLib.collectComponents`](https://input-output-hk.github.io/haskell.nix/reference/library/#haskellLib) function.

## June 21, 2019
 * Add `ghcWithPackages` and `ghcWithHoogle` to hsPkgs ([documentation](https://input-output-hk.github.io/haskell.nix/reference/library/#package-set-functions).
 * Benchmark components can now build successfully.
 * Reduced the closure bloat of nix-tools, and added closure size limit to CI.
 * Added more reference documentation and set up auto-generated
   documentation for [Module Options](https://input-output-hk.github.io/haskell.nix/reference/modules/).
 * Miscellaneous bug fixes.

## June 7, 2019
  * Several additions to the [documentation](https://input-output-hk.github.io/haskell.nix/).
    * More information about getting nix-tools, Haskell.nix, pinning.
    * Updates the stack-to-nix and cabal-to-nix guides.
    * Adds a section on development environments.
    * Adds a little information about cross compilation.
    * Adds a (partially complete) reference section (command line manuals, library reference).
    * Symlinks the changelog into the documentation pages.

## May 29, 2019
  * Added `shellFor` function to package set.

## May 28, 2019
  * Added `snaphots` and `haskellPackages` attributes to the
    Haskell.nix top-level.

## May 22, 2019
  * Add the `cleanSourceHaskell` utility function to the Haskell.nix
    top-level.

## May 21, 2019
  * Add the `callCabalProjectToNix` function, which uses "import from
    derivation" (IFD) so that nix-tools doesn't need to be run
    manually.
  * The `hackage.nix` update process has changed, so that Cabal index
    state hashes are also included in the generated repo.

## May 20, 2019
  * Remove Travis CI in favour of Buildkite.

## May 17, 2019
  * Add the `callStackToNix` function, which uses "import from
    derivation" (IFD) so that `stack-to-nix` doesn't need to be run
    manually.

## Mar 15, 2019
  * `overlays` was renamed to `extras` in
    [#79](https://github.com/input-output-hk/haskell.nix/pull/79)
    to prevent confusion between the notion of Nix overlays.

    Therefore `plan-pkgs` and `stack-pkgs` as generated by `plan-to-nix` and `stack-to-nix` will
    expose `extras` instead of `overlay`. Similarly `mkStackPkgSet`, `mkPkgSet` and `mkCabalProjectPkgSet`
    take a `pkg-def-extras` instead of `pkg-def-overlay` argument.  If you are using `iohk-nix`, the
    `iohk-overlay` was parameter was renamed to `iohk-extras`.
