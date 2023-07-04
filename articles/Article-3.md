# CSS New Viewport Units

## Introduction
When you're styling certain elements of a website or web application, you might want to use a certain percentage of the viewport. For example, you want to make an elemnt 100% of the viewport height. You can do this by using the `vh` unit. This unit is relative to the viewport height. So if you want to make an elemnt 100% of the viewport height, you can do this by using `height: 100vh;`. 

But sometimes some of the standard browser navigation bars can stand in the way, forcing the elements to be pushed down, which would mean that not everything of that element is visible. This is a problem that can be solved by using dynamic viewport units.

## Dynamic Viewport Units
To solve this problem, there are dynamic viewport units. These units are relative to the viewport height and width, but they take the browser navigation bars into account. There are 3 dynamic viewport units: `lvh`, `svh` and `dvh`.

| svh-lvh-dvh |
|:---:|
|![Dynamic viewport units](https://www.terluinwebdesign.nl/en/wp-content/uploads/tw-img/2022/03/incoming-20-new-css-viewport-units-svh-lvh-dvh-svw-lvw-dvw-w1683.png.webp) |


### `lvh` 
The unit `lvh` stands for large viewport height. This it takes 100% of the viewport height, including the browser navigation bars. So this is actually the same as using `vh`.

### `svh`
The unit `svh` stands for small viewport height. This unit it takes 100% of the viewport height, excluding the browser navigation bars. This means that whenever
which means that whenever the browser navigation bars are visible, the element will be 100% of the viewport height, but when the browser navigation bars are hidden, the element will be 100% of the viewport height with some extra space at the bottom.

### `dvh`
The unit `dvh` stands for dynamic viewport height. This unit it takes 100% of the viewport height, but it will dynamically change when the browser navigation bars are hidden or visible. This means that whether the browser navigation bars are visible or not, the element will always be 100% of the viewport height with no extra space at the bottom.

!!!warning
    When using the dynamic viewport height it can make the screen a bit jittery when the element is trying to adjust tyhe height. When this is the case you can maybe use the [svh](#svh) unit instead.

## Compatibility
The support for these dynamic viewport units is pretty good. But it us **currently** only 89%. Which means that for some browsers the dynamic viewport units won't work. But this is only for a small percentage of the users. 

[Kevin Powell](#sources) had a tip for a fallback for the dynamic viewport units. You can use the `vh` unit as a fallback.

like so:
```css
.element {
    /* If the browser does not understand the svh unit, it will stick with the normal vh */
    height: 100vh;
    height: 100svh;
}
```

However he did explain that this is not a perfect solution. but it works for the small percentage of users that don't have support for the dynamic viewport units.

## Conclusion
The dynamic viewport units are a great addition to the CSS language. It makes it easier to make elements 100% of the viewport height, without having to worry about the browser navigation bars. The support for these units is pretty good, which means that you can use them in your projects. But you should always keep in mind that there are still some users that don't have support for these units. So you should always have a fallback for these units.

I will definitely use these units in my projects, because they are very useful. And I think that you should use them too.

## Sources
- [terluinwebdesign](https://www.terluinwebdesign.nl/en/css/incoming-20-new-css-viewport-units-svh-lvh-dvh-svw-lvw-dvw/)
- [dev.to](https://dev.to/frehner/css-vh-dvh-lvh-svh-and-vw-units-27k4)  
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [Can I Use](https://caniuse.com/viewport-unit-variants)
- [Kevin Powell](https://www.youtube.com/watch?v=veEqYQlfNx8)