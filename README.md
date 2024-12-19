# Revealed_Preference

This project provides a Python-based toolkit for analyzing revealed preference theory, including detecting violations of various axioms such as WARP, SARP, and GARP. It is intended for economists, researchers, and students working in microeconomics and consumer theory.

## Features

1. **Weak Axiom of Revealed Preference (WARP) Analysis**:
   - Functions to detect whether consumption choices violate WARP.
2. **Strong Axiom of Revealed Preference (SARP) Analysis**:
   - Tools to identify preference cycles and violations of SARP.
3. **Generalized Axiom of Revealed Preference (GARP) Analysis**:
   - Functions for checking violations of GARP with support for strict revealed preferences.
4. **Preference Graph Analysis**:
   - Detection of cycles in preference graphs to support SARP and GARP checks.

## Functions Overview

`check_revealed_preference(price_a, quantity_a, price_b, quantity_b)`
- Checks if two consumption bundles satisfy WARP.
- **Parameters**:
  - `price_a`, `price_b`: Price vectors of two consumption bundles.
  - `quantity_a`, `quantity_b`: Quantity vectors of two consumption bundles.
- **Returns**: `True` if WARP is satisfied, `False` otherwise.

`check_strict_direct_preference(price_a, quantity_a, price_b, quantity_b)`
- Checks for strict direct revealed preferences between two bundles.

`detect_cycle(preference_graph)`
- Detects cycles in a preference graph, which can indicate SARP or GARP violations.

`check_warp_violation(quantity_list, price_list)`
- Detects WARP violations across multiple consumption bundles.

`check_sarp_violation(quantity_list, price_list)`
- Detects SARP violations, including cycles in preference graphs.

`check_garp_violation(quantity_list, price_list)`
- Detects GARP violations and evaluates strict preferences in addition to basic WARP violations.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/XStrachey/Revealed_Preference.git
   ```

## Usage

### Example
```python
price_list = [
    [10, 15],
    [20, 10],
    [15, 20]
]
quantity_list = [
    [2, 1],
    [1, 2],
    [1.5, 1.5]
]

result = check_warp_violation(quantity_list, price_list)
print(result)
```

### Output
The function returns a dictionary summarizing violations:
- `has_violation`: Whether any violations exist.
- `pair_violation`: Pairs of bundles where violations occur.
- `violation_count`: Total number of violations.
- `violation_ratio`: Proportion of violating pairs.