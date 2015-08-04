# CCF1
Consistent CSS Formatting - A CSS Formatting Standard

## 1. Overview
These standards are only applied to Input CSS and not Output CSS. With ever expanding Preprocessor use it is harder to maintain your output CSS if you want to make use of extends and mixins. By defining that this standard only applies to Input CSS means we don’t need to worry about using a Preprocessor or writing in standard CSS. Sass will be used for examples but these rules should be carried over to your preprocessor of choice.

### 2. Spaces and Indentation
Use 4 spaces instead of tabs for indentation

Opening braces must have 1 space between them and the last selector

Closing brace must be on it's own line

1 space must seperate the declaration property and the value. This space should follow the colon. There should be no space between the property and colon

There must not be trailing whitespace on declarations

Blank lines may be used to separate blocks of code but no more than 2 blank lines should be used

Indent all block content

##### Example code block
    .nav {
        background-color: #ebe;
        height: 120px;
        width: 100%;
    }
    .nav-item {
        display: inline;
        padding: 10px 20px;
    }

    @media (max-width: 600px) {
        .item {
            display: block;
            text-align:center;
        }
    }

#### 2.1. Spaces and Indentation - Preprocessors
Nested Pseudo Classes and Pseudo Elements should follow all declarations

There should be 1 blank line between Nested elements and Declarations

Nested Selectors should be last

Do not nest more than three levels deep

##### Example code block
    .nav {
        background-color: #ebe;
        height: 120px;
        width: 100%;

        &:before {
            content: 'The nav is here:';
            display: inline;
            padding: 10px 20px;
        }
        &-item {
            display: inline;
            padding: 10px 20px;

            &:hover {
                text-decoration: underline;
            }
        }
    }

### 3. Declaration Order
Declarations should be alphabetised

Vendor prefixes must immediately follow their unprefixed version. Vendor Prefixes should also be alphabetical order

#### 3.1. Declaration Order - Preprocessors
Declarations in mixins and extends should be alphabetised

Extends should be listed at the top of the declaration

Mixins and Functions should follow Extends

Standard CSS properties should be last

Blank lines can be used to separate extends, mixins and declarations from each other

##### Example code block
    .item {
        @extend .link;

        @include font-size(16);

        background-color: #ebe;
        border-radius: 5px;
        -moz-border-radius: 5px;
        -webkit-border-radius: 5px;
        height: 120px;
        overflow: hidden;
        width: 100%;
    }

### 4. Value Formatting
To do

### 5. Preprocessor Guidelines
To do