### Notes:

1. **`<kbd>`**

   The `<kbd>` HTML element represents a span of inline text denoting textual user input from a keyboard, voice input, or any other text entry device.

2. **`data-*` attribute**

    The data-* attribute is used to store custom data private to the page or application.

    The data-* attribute gives us the ability to embed custom data attributes on all HTML elements.

    eg. 
    ```
    <ul>
    <li data-animal-type="bird">Owl</li>
    <li data-animal-type="fish">Salmon</li>
    <li data-animal-type="spider">Tarantula</li>
    </ul>
    ```

3. **`querySelector`** 

    returns the first Element within the document that matches the specified selector, or group of selectors. If no matches are found, `null` is returned. (`dfs`)

    selector can be a bit complicated. For example,
    ```
    var el = document.querySelector("div.user-panel:not(.main) input[name='login']");
    ```

4. **`transition`**

    ```
    /* Apply to 1 property */
    /* property name | duration */
    transition: margin-right 4s;

    /* property name | duration | delay */
    transition: margin-right 4s 1s;

    /* property name | duration | easing function */
    transition: margin-right 4s ease-in-out;

    /* property name | duration | easing function | delay */
    transition: margin-right 4s ease-in-out 1s;

    /* Apply to 2 properties */
    transition: margin-right 4s, color 1s;

    /* Apply to all changed properties */
    transition: all 0.5s ease-out;

    /* Global values */
    transition: inherit;
    transition: initial;
    transition: revert;
    transition: unset;
    ```

5. Errors
   
   After long pressing, the transition will not be triggered back.

   A possible solution:

    ```
    我也遇到这个问题，但发现原因并不是this.classList或者event.target.classList，而是在过滤事件的代码中
    if (event.propertyName !== 'transform') return;
    这里如果是transform或者box-shadow就会出现长按样式不能恢复的情况；
    如果改成检测border-left-color或者其他几个边框颜色就不会出现这个问题。
    感觉原因是浏览器多过渡动画的优化导致的，在连续点击时不明显的动画就不执行了（反正也看不出来），以提高性能。
    ```