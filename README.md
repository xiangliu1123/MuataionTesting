# Mutation Testing Report on Polynomial Module

## Introduction

This report presents the results of mutation testing performed on the `Polynomial` Python module using the MutPy tool. Mutation testing helps evaluate the effectiveness of test cases by introducing small changes (mutations) to the code and checking if the existing test suite can detect these changes.

## List of Defined Mutation Operators

MutPy applies various mutation operators, some of which are observed in this testing:

- **ASR (Arithmetic Operator Replacement)**: Replace arithmetic operators (e.g., `+` with `-`).
- **BCR (Break/Continue Replacement)**: Replace `break` with `continue` and vice versa.
- **COI (Conditional Operator Insertion)**: Insert conditional operators to alter program flow.
- **ROR (Relational Operator Replacement)**: Replace relational operators (e.g., `>` with `>=`).
- **SIR (Statement Insertion/Removal)**: Insert or remove certain statements.

## Description of Applied Mutations and Their Impact

The following mutations were introduced and their impacts observed:

1. **ASR in `__str__` and `__add__` methods**: Changes like `term += 'x^'` to `term -= 'x^'` and similar in addition operation. These mutations resulted in incorrect string representations and mathematical operations.
2. **BCR in `get_derivative_coefficients` method**: Replacing `continue` with `break` led to early termination of loops, affecting the calculation logic.
3. **COI in various methods**: Conditional changes, such as altering `if len(self.coefficients) == 0:` to `if not (len(self.coefficients) == 0):`, caused incorrect handling of edge cases.
4. **ROR in `find_root_bisection` method**: Changing relational operators impacted the root-finding logic, leading to incorrect or non-optimal solutions.
5. **SIR in `get_derivative_coefficients` method**: Insertion/removal of statements in the derivative calculation altered the function's behavior.

## Summary of Mutant Survival and Killing

- **Total Mutants Generated**: 89
- **Killed Mutants**: 24 (27.0%)
- **Survived Mutants**: 20 (22.5%)
- **Incompetent Mutants**: 45 (50.6%)
- **Timeout Mutants**: 0 (0.0%)

## Analysis of the Test Suite's Effectiveness

The mutation score is 54.5%, indicating that over half of the mutants were detected (killed) by the test suite. While this is a moderate score, the high percentage of incompetent mutants (50.6%) suggests that many mutations resulted in code that was either nonsensical or did not compile, limiting the effectiveness of this metric.

## Recommendations for Improving the Test Suite

1. **Enhance Coverage**: Focus on adding test cases that cover edge cases and complex scenarios, especially for mathematical operations.
2. **Refine Assertions**: Strengthen the assertions in the test cases to catch subtle changes in the code behavior.
3. **Review Incompetent Mutants**: Examine the incompetent mutants to understand why they failed to compile or execute, and adjust the test suite to cover such scenarios if possible.

## Conclusion

Mutation testing of the `Polynomial` module revealed areas where the test suite can be improved. While the current test suite is moderately effective, enhancements in test coverage and assertions can lead to a more robust and comprehensive testing strategy, ensuring higher code quality and reliability.
"""

## Output after Mutation Testing with Mutpy
[0.00000 s] incompetent
[*] Mutation score [10.02380 s]: 54.5%
   - all: 89
   - killed: 24 (27.0%)
   - survived: 20 (22.5%)
   - incompetent: 45 (50.6%)
   - timeout: 0 (0.0%)

