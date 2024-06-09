# README

## Overview

This repository contains an LR parser implemented in Python to parse and analyze a simple switch-case statement from a source code file. The parser tokenizes the source code, classifies tokens, and performs syntax analysis using a context-free grammar (CFG). The results are displayed in a tabular format and visualized using a syntax tree.

## Contents

- `sourcecode.txt`: The source code file containing the switch-case statement to be parsed.
- `LRparser.py`: The Python script implementing the LR parser.
- `README.md`: This README file.

## Requirements

- Python 3.x
- `nltk` library for tokenization and syntax tree visualization
- `tabulate` library for displaying results in tabular format
- `pandas` and `numpy` libraries for data manipulation

You can install the required libraries using:
```sh
pip install nltk tabulate pandas numpy
```

## Usage

1. **Prepare Source Code**: Place the source code to be parsed in the `sourcecode.txt` file.
2. **Run the Parser**: Execute the `LRparser.py` script to parse the source code and visualize the results.

## Detailed Description

### Tokenization

The parser begins by reading the source code from `sourcecode.txt` and tokenizing it using the `nltk` library. Each token is classified into categories such as keywords, digits, operators, strings, identifiers, and various punctuation marks.

### Token Classification

Tokens are classified based on regular expressions:
- Keywords: `switch`, `case`, `break`, `default`
- Digits: Numeric values
- Operators: `=`
- Strings: Single character strings
- Identifiers: Alphanumeric sequences starting with a letter
- Punctuation: `(`, `)`, `{`, `}`, `;`, `:`, `'`

### Context-Free Grammar (CFG)

The CFG for the switch-case statement is defined with the following non-terminal and terminal symbols:
- Non-terminals: `Start`, `Sdash`, `Cdash`, `Ddash`, `statement`, `expression`, `character`, `digit`
- Terminals: `switch`, `case`, `break`, `default`, `=`, digits, characters, punctuation

The CFG rules are applied to parse and reduce the tokens according to the defined grammar.

### Parsing Process

The parsing process involves:
- Initializing stacks for the parser and input
- Shifting tokens from the input stack to the parser stack
- Reducing tokens in the parser stack based on CFG rules
- Handling shift and reduce actions iteratively until the entire input is parsed

### Final Output

The parser outputs the following:
- A table displaying the parser stack, input stack, and actions (shift/reduce) at each step
- The final state of the parser stack indicating whether the input is accepted or rejected
- A syntax tree visualizing the parsed switch-case statement if the input is accepted



## Running the Script

To run the LR parser, execute the following command:

```sh
python LRparser.py
```

The script will read the source code from `sourcecode.txt`, parse it, and display the results. If the parsing is successful, a syntax tree will be generated and displayed.

## Conclusion

This LR parser provides a simple yet effective way to analyze switch-case statements in source code. It demonstrates the fundamental concepts of tokenization, classification, and syntax analysis using a context-free grammar. The parser can be extended to handle more complex language constructs and integrated into larger projects requiring syntax analysis.
