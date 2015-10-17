# Coding Guidelines

## Purpose

This document serves to catalog coding advice and practices that we choose to orient by.  We belive that clarity 
trumps cleverness and that code is written to communicate thought forms between humans &mdash; it bears as a
significant perk that computers can run it as well, but that is strictly secondary to the former benefit.

## Policy on Ternaries

Ternary statements are meant to assign a value-result that is to be determined based on a _protasis_ (aka _an 
if-condition_).  It is inappropriate to use them for conditional logic that expresses flow or intermediate value 
accumulation.  

While nimble-minded programmers, the likes of whom we hope to attract to this organization, can assuredly eloquently articulate how, in reality, all programming can be conceived of as a value determination operation based on a calculation that needs necessarily have no intermediate state provided a set of immutable inputs (e.g. Haskell, Lisp, or any of the _functional paradigm_ langauges), we also trust said individuals to have the coding maturity to see how the policy's position is designed to support the more criticial goal of supporting readability and communicability of thought forms.  

**Compliant:**  `adoration_factor = dog.moyen_poodle? ? 10_000 : 1`

**Non-compliant:** `adoration_factor = dog.moyen_poodle? ? (calculate_base_adoration + calculate_moyen_poodle_bonus) * 1.10 : calculate_base_adoration`

Ternaries are not to be used with assignments of `true` or `false` values.  Method names should be sufficient to reflect this intention *or* a coercive double-negation (`!!`) or negation (`!`) ought be used.:

**Non-compliant:** `living_life_some_consider_a_myth = the_kid.is?(WILL_SMITH) ? true : false`

**Tip:** Oftentimes the use of a ternary with extreme cleverness suggests that the programmer consider the refactoring "[INTRODUCE EXPLAINING VARIABLE](https://sourcemaking.com/refactoring/extract-variable)" or "[EXTRACT METHOD](https://sourcemaking.com/refactoring/extract-method)."

