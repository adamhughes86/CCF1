# CCF1
Consistent CSS Formatting - A CSS Formatting Standard

## 1. Overview
**This is a work in progress**

These standards are only applied to *Input CSS* and not *Output CSS*. With ever expanding Preprocessor use it is harder to maintain your output CSS if you want to make use of extends and mixins. By defining that this standard only applies to Input CSS means we don’t need to worry about using a Preprocessor or writing in standard CSS. *Sass will be used for examples* but these rules should be carried over to your preprocessor of choice.

### 2. Spaces and Indentation
- Use 2 spaces instead of tabs for indentation
- Opening braces **must** have 1 space between them and the last selector
- The closing brace **must** be on it's own line
- 1 space **must** seperate the declaration property and the value. This space should follow the colon. There should be no space between the property and colon
- There **must not** be trailing whitespace on declarations
- Blank lines may be used to separate blocks of code but no more than 2 blank lines should be used
- Indent all block content
- When grouping selectors, individual selectors **must** be on separate lines
- There **must** be a blank line at the end of every file

##### Example
    .nav {
      height: 120px;
      width: 100%;
      background-color: #ebe;
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
- Nested Pseudo Classes and Pseudo Elements *should* follow all declarations
- There **must** be 1 blank line between Nested elements and Declarations
- Nested Selectors *should* be last
- You *should not* nest more than three levels deep

##### Example
    .nav {
      height: 120px;
      width: 100%;
      background-color: #ebe;

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
- Declarations **must** be on their own line
- Declarations *should* be alphabetised
- Vendor prefixes **must** immediately preceed their unprefixed version. Vendor Prefixes should also be alphabetical order

#### 3.1. Declaration Order - Preprocessors
- Declarations *should* be ordered by group (`Content`, `Position`, `Box Model`, `Typography`, `Visual`, `Misc`)
- Declarations within groups *should* be ordered by type or alphabetically
- Extends *should* be listed at the top of the declaration
- Mixins and Functions *should* follow Extends
- Mixins with one clear function (such as providing a fallback) should be placed within correct group (e.g. `font-size` and `linear-gradient` mixins)
- Standard CSS properties *should* be last
- Blank lines can be used to separate extends, mixins and declarations from each other

##### Example
    .item {
      @extend .link;

      @include decoration(wide);

      // Content
      content: 'Pretty important';

      // Positioning
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      z-index: 0;

      // Box model
      clear: both;
      display: block;
      float: left;
      margin: 20px 0;
      padding: 10px;
      height: 120px;
      width: 100%;
      max-height: 120px;
      max-width: 800px;
      overflow: hidden;

      // Typography
      color: #000;
      font-family: 'Arial', sans-serif;
      @include font-size(16);
      line-height: 1.2;
      text-align: left;
      text-decoration: none;
      text-indent: 0;

      // Visual
      background-color: #ebe;
      -moz-border-radius: 5px;
      -webkit-border-radius: 5px;
      border-radius: 5px;
      opacity: 1;
      transition: all 0.5s;

      // Misc
      // Can be used for any styles that do not fit into these groups
    }

**The comments are for demostrative purposes only.** This list of styles is not exhaustive and more styles can be placed within each group. Try to keep some sort of order within groups whether it's by type or alphabetically.

### 4. Value Formatting
- Do not use unit values after `0` values
- Use shorthand properties when you can
- If only overriding one value your *should* use longhand form to avoid unneccesary changes
- Use 3 character Hexademical values when possible
- Use single quotation marks instead of double
- Always wrap strings in quotations
- Values in `font-family` should all be individually wrapped in quotes except for final fallback value (e.g. `sans-serif, serif, monotype`)
- Values **must** end with semi-colon
- Include leading 0's in values for legibility (e.g. `font-size: .9em;` should be written `font-size: 0.9em;`)

##### Example
    .item {
      margin: 20px 5px;
      padding: 0 10px;
      color: #000;
      font-family: 'Helvetica Neue', 'Helvetica', 'Arial', sans-serif;
      font-size: 0.9em;
      background: transparent url('/images/pattern.png') 0 0 repeat-x;
      border: 1px solid #ebe;
    }

    @media (max-width: 600px) {
      .item {
        margin-bottom: 10px;
      }
    }

### 5. Commenting
- Comment tags *should* be a double slash `//` in Preprocessors and a simple slash-asterisk pattern in plain CSS `/* Comment */
- Inline comments describing a declaration **must** be placed at the end of the value with a space either side of the comment tag
- Block level comments about a **must** should be placed immediately above the selector and have one blank line above
- Any comments describing whole components *should* follow the KSS commenting standard
- Use comments to describe any elements that the code is unclear or if code may need to be explained

##### Example
    .nav {
      width: 100%
    }

    // Comment about this item
    .item {
      margin: 20px 5px; // Comment describing this properties effect
      padding: 0 10px;
      color: #000;
      border: 1px solid #ebe;
    }
