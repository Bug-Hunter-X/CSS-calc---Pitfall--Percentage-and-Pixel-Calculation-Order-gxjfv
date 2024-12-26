# CSS calc() Pitfall: Percentage and Pixel Calculation Order

This repository demonstrates a common issue when using the `calc()` function in CSS to combine percentage and pixel values.  The order of operations can lead to unexpected layout behavior.

## The Problem

The `calc()` function in CSS calculates values based on their order. If you have `width: calc(50% - 10px);`, the percentage is calculated first, then the pixel value is subtracted. This means the 10px is subtracted from half the *parent's width*, not from half the *final width*.

## How to Reproduce

1. Clone this repository.
2. Open `index.html` in your browser.
3. Observe that the red box doesn't have exactly half the width of its container minus 10 pixels as you might expect. 

## The Solution

To avoid this issue, use alternative layout techniques, such as using flexbox or grid, or recalculate the values using Javascript if absolutely necessary. For simple cases, using only percentages or only pixels is often more reliable.