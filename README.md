# CCF1
Consistent CSS Formatting - A CSS Formatting Standard

## Overview
These standards are only applied to Input CSS and not Output CSS. With ever expanding Preprocessor use it is harder to maintain your output CSS if you want to make use of extends and mixins. By defining that this standard only applies to Input CSS means we don’t need to worry about using a Preprocessor or writing in standard CSS.

### Spaces and Indentation
Use 4 spaces instead of tabs for indentation

Opening braces must have 1 space between them and the last selector

Closing brace must be on it's own line

1 space must seperate the declaration property and the value. This space should follow the colon. There should be no space between the property and colon

There must not be trailing whitespace on declarations

Blank lines may be used to separate blocks of code but no more than 2 blank lines should be used

Indent all block content

#### Example code block
    .nav {
        background-color: #ebe;
        height: 120px;
        width: 100%;
    }
    .item {
        display: inline;
        padding: 10px 20px;
    }

    @media (max-width: 600px) {
        .item {
            display: block;
            text-align:center;
        }
    }

### Declaration Order
To do

### Value Formatting
To do

### Preprocessor Guidelines
To do