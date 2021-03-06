## 3.2.2

### Fixes

- `MGBoxProvider` and `MGLayoutManager` fixes for keeping internal box reuse 
  data clean
 
## 3.2.1

### Fixes

- `MGBoxProvider` bug fix for updating visible indexes during fast scrolling 

## 3.2.0 

### Enhancements

- Added `appeared` and `disappeared` methods and `onAppear` and `onDisappear` 
  block properties which fire when a box is automatically added or removed 
  during box reuse / offscreen culling.

## 3.1.0

### Enhancements

- Added `[self when:object does:Something do:Thing]` custom event observing. 
  See [#118](https://github.com/sobri909/MGBoxKit/issues/118) for details.

## 3.0.0

### Upgrading

- the `screenshot:` method changed signature to `screenshotWithShadow:scale:`

### Enhancements

- `MGBoxProvider` box reuse and offscreen culling, allowing for much larger 
  tables/grids
- `MGLine` can auto resize the width of `UITextField` items to fit
- new setters for `top`, `right`, `bottom`, `topLeft` etc
- arm64 fixes

## 2.1.0

#### Upgrading

- There shouldn't be any backwards compatibility breaks. Please let me know if 
  you find any!
- Note that the project, repo, and folders have been renamed to **MGBoxKit**

#### Enhancements

- Optional non-recursive layout: `dontLayoutChildren`
- Optional `minWidth` property
- Text colour Mush markup: "this string has {#123456|coloured text}"
- New block properties for `onTouchesBegan`, `onTouchesEnded`,  
  `onTouchesCancelled`
- New UIView convenience CGFloat getters for `top`, `right`, `bottom`, `left`
- New line spacing properties for MGLine content: `leftLineSpacing`, 
  `middleLineSpacing`, `rightLineSpacing`

## 2.0.0

#### Upgrading

- `MGBox` now requires the `CoreText` framework. Add this to your project.
- Also add these new files to your project:
  - `MGLineStyled.m/h`
  - `MGMushParser.m/h`
  - `Categories/NSAttributedString+MGTrim.m/h`
  - `Categories/UIColor+MGExpanded.m/h`
- `MGLine` now has a default `underlineType` of none. For tables using 
  `MGTableBoxStyled`, replace `MGLine` with `MGLineStyled`, or set your 
  `MGLine` instances to have a `borderStyle` of `MGBorderEtchedTop | MGBorderEdgedBottom`.

#### Enhancements

- **Mush Lightweight Markup**
  - Markup similar to Markdown/Textile, providing bold, italic, underline, and 
    monospace.  
- **MGLine Now Accepts NSAttributedStrings**
- **MGBox Borders**
  - Set individual border colours with `topBorderColor`, `rightBorderColor`, 
    `bottomBorderColor`, `leftBorderColor`.
  - Set all border colours in one go with `borderColors`.
  - Optionally modify borders directly with `topBorder`, `rightBorder`, 
    `bottomBorder`, `leftBorder`.
- **MGBox Etched Border Style**
  - `borderStyle` property replaces the deprecated `underlineType`, and is 
    available in all `MGBox` subclasses. Allows an etched border style 
    optionally for top/right/bottom/left.      
- **New MGLine Text Style Properties**
  - Properties for left/middle/right text colours, shadow colours, shadow 
    offsets, alignments.

See the documentation for usage examples of the new APIs.

#### Deprecated

- `-[MGLine underlineType]`, replaced by `-[MGBox borderStyle]`
