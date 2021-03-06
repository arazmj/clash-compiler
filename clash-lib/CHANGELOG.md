# Changelog for the [`clash-lib`](http://hackage.haskell.org/package/clash-lib) package

## 0.5.7
* New features:
  * Support for copying string literals from Haskell to generated code
  * Collect and copy data-files

* Fixes bugs:
  * Signals declared twice when not using a clock-generating component [#60](https://github.com/clash-lang/clash-compiler/issues/60)

## 0.5.6 *June 3rd 2015*
* New features:
  * Support Verilog backend
  * Generated component names are prefixed by the name of the module containing the `topEntity`

## 0.5.5 *May 18th 2015*
* New features:
  * Make inlining and specialisation limit configurable
  * Make debug message level configurable

* Fixes bugs:
  * Netlist: ensure that the arguments of a component instantiation are always simple variables
  * CaseCon transformation: ensure that we run the compile-time evaluator on the subject before handling the one-alternative case
  * Emit a warning if a function remains recursive, instead of producing an error: compilation can still be successful if the function is an argument to a higher-order blackbox that doesn't use the function.
  * Emit a warning if inlining limit is reached, instead of producing an error: compilation can still be successful if the function is an argument to a higher-order blackbox that doesn't use the function.
  * Always inline terms that have a type of kind `Constraint`

## 0.5.4 *May 10th 2015*
* New features:
  * Add `~COMPNAME` tag: primitives get access to the component name in which they are instantiated

## 0.5.3 *May 5th 2015*
* New features:
  * `TopEntity` wrappers are now specified as `ANN` annotation pragmas
* Fixes bugs:
  * Lost system1000 clock in VHDL generation... [#53](https://github.com/clash-lang/clash-compiler/issues/53)
  * `flattenCallTree` sometimes introduces free variables

## 0.5.2 *May 1st 2015*
* New features:
  * Generate wrappers around `topEntity` that have constant names and types

## 0.5.1 *April 20th 2015*
* GHC 7.10 support

## 0.5 *March 11th 2015*
* New features:
  * Simplify BlackBox handling, and improve VHDL generation. [#47](https://github.com/clash-lang/clash-compiler/issues/47)
  * Use unbound-generics. [#48](https://github.com/clash-lang/clash-compiler/issues/48)

* Fixes bugs:
  * VHDL generation error: wrapper for sum-of-products type. [#44](https://github.com/clash-lang/clash-compiler/issues/44)

## 0.4.1 *February 4th 2015*
* Fixes bugs:
  * Treat BlackBox expressions as declarations when DC args. [#37](https://github.com/christiaanb/clash2/issues/33)
  * Don't inline recursive closed bindings

## 0.4 *November 17th 2014*
* New features:
  * Support for clash-prelude 0.6

* Fixes bugs:
  * Ambiguous type: 'std_logic_vector' or 'std_ulogic_vector' [#33](https://github.com/christiaanb/clash2/issues/33)

## 0.3.2 *June 5th 2014*

* Fixes bugs:
  * VHDL array constant ambiguous [#18](https://github.com/christiaanb/clash2/issues/18)
  * Exception: can't create selector [#24](https://github.com/christiaanb/clash2/issues/24)
  * Calls to `vhdlTypeMark` don't result to inclusion of VHDL type in types.vhdl [#28](https://github.com/christiaanb/clash2/issues/28)

## 0.3.1 *May 15th 2014*

* New features:
  * Make ANF lift non-representable values [#7](https://github.com/christiaanb/clash2/issues/7)
  * Hardcode `fromInteger` for `Signed` and `Unsigned` [#9](https://github.com/christiaanb/clash2/issues/9)
  * Replace VHDL default hole by error hole [#13](https://github.com/christiaanb/clash2/issues/13)

* Fixes bugs:
  * Type families are not expanded [#3](https://github.com/christiaanb/clash2/issues/3)
  * Exception: CLaSH.Netlist.VHDL(512): fromSLV: Vector 13 Bool [#5](https://github.com/christiaanb/clash2/issues/5)
  * Incorrect vhdl generation for default value in blackbox [#6](https://github.com/christiaanb/clash2/issues/6)
  * Duplicate type names when multiple ADTs need the same amount of bits [#8](https://github.com/christiaanb/clash2/issues/8)
  * Circuit testbench generation with MAC example fails[#15](https://github.com/christiaanb/clash2/issues/15)

* Code improvements:
  * Refactor Netlist/BlackBox [#10](https://github.com/christiaanb/clash2/issues/10)
  * CPP special-case conversion of `Control.Exception.Base.irrefutPatError` [#11](https://github.com/christiaanb/clash2/issues/11)
