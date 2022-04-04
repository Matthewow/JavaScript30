### Notes:

1. **Variables in CSS**
   
   ```
   :root{
      --base: #ffc600;
      --spacing: 10px;
      --blue: 10px;
    }

    img {
      padding: var(--spacing);
      background: var(--base);
      filter: blur(var(--blur))
    }
   ```
2. **Obj.dataset**
   
   returns all the data- type of attributes.

3. **Change CSS attributes**

    ```
    document.documentElement.style
        .setProperty(`--${this.name}`, this.value + suffix);
    ```