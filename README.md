# CSS_Locators
This comprehensive guide explores CSS locators, a powerful method for selecting web page elements based on attributes such as tag name, id, and class.

CSS locators are a method used to select elements on web pages based on their tag name, id, class, and other attributes. 

Let's explore how CSS locators are written and applied using Selenium WebDriver with Java.

---

### **CSS Locators Syntax**

The general syntax for CSS locators is as follows:

**`tagname[attribute='value']`**

In this syntax:

- **`tagname`** represents the element's tag name.
- **`attribute`** represents an attribute the element possesses.
- **`value`** is the value of the attribute.

For example, to select the **`<input id="username" type="text">`** element, you can use the CSS locator **`input[id='username']`**.

CSS locators also have shortcuts for some attributes like id and class. You can use **`#`** for id and **`.`** for class. 

For instance, both **`input#username`** and **`#username`** would select the same element.

---

### **Using CSS Locators with Selenium WebDriver in Java**

Selenium WebDriver provides the **`By.cssSelector()`** method to find elements on web pages using CSS locators. 

This method takes a CSS locator as a parameter and returns a matching **`WebElement`** object. 

If multiple elements match, it returns the first one. 

If no element matches, it throws a **`NoSuchElementException`** error.

---

Here's an example in Java:

```html
<button id="submit" type="button">Submit</button>

```

```java

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class CssLocatorExample {
    public static void main(String[] args) {
        // Start the WebDriver
        WebDriver driver = new ChromeDriver();
        // Go to a specific URL
        driver.get("https://www.example.com");
        // Find the element using a CSS locator
        WebElement button = driver.findElement(By.cssSelector("#submit"));
        // Perform actions on the element
        button.click();
    }
}

```

---

### **Examples of CSS Locators**

### ID Selection

```html
<input id="username" class="main" type="text">Submit</input>

```

In this example, the CSS locator **`#username`** is used to select elements with the id **`username`**.

1 way :  #value of ID    : **`#username`**
2 way : tagName#value of ID     : **`input#username`**

---

### Class Selection

```html
<input id="username" class="main" type="text">Submit</input>

```

In this example, the CSS locator **`.main`** is used to select elements with the class **`main`**.

**Xpath** : `**//input[@class='main']**`

**CSS**   : 

1 way :   .valueOfClass → **`.main`**   (if there is a space , put (.) instead of space )                     

2 way :   tagName.valueOfClass → **`input.main`**

---

### Attribute Selection

```html
<input id="username" class="btn btn-primary" type="text">Submit</input>

```

In this example, the CSS locator `**input[type='text']**` is used to select elements with the type **`text`**.

CSS : -[attribute=‘value’]    → `**[type="text"]**`
CSS : -[class=‘value’]     → `**[class='btn btn-primary']**`

---

### Combining Attributes Selection

```html
<input id="username" class="btn btn-primary" name="email" type="text">Submit
</input>

```

In this example, the CSS locator used to select elements with the type **`text`** and the id **`username`** is **`input[type='text'][id='username']`**.

**Xpath** : `**//input[@type='text'][@name="email"]**`        

→ also we can use with “ and ” &  “or ”

**CSS** :  TagName[attribute1=‘value1’][attribute2=‘value2’] 

→`**input[type='text'][name="email"]**`   

→we can NOT use “and” & “or”

---

### Substring (Starts With) Selection

```html
<input id="username" class="btn btn-primary" name="email" type="text">Submit
</input>

```

In this example, the CSS locator **`[id^='user']`** is used to select elements that have an id starting with **`user`**.

**Xpath** : `**//input[starts-with(@id,'user')]**`

**Xpath** : `**//input[starts-with(@class,'btn')]**`

**CSS** :  TagName[attribute^=‘value’]  → `**input[id^='user']**`
**CSS** :  TagName[attribute^=‘value’]  → `**input[class^='btn']**`

---

### Contains Selection

```html
<input id="username" class="btn btn-primary" name="email" type="text">Submit
</input>

```

In this example, the CSS locator **`[id^='ern']`** is used to select elements that contain the ID **`ern`**.

**Xpath** : `**//input[contains(@id,'ern')]**`
**CSS** : TagName[attribute*=‘value’] `**input[id*='ern']**`

---

### Child Element Selection


![Untitled](https://github.com/AhmetBeskazalioglu/CSS_Locators/assets/146031280/ba689312-7571-4cc9-a6d3-2feb8473b9c6)

In this example, the `**div.vsathm.light>div#serpvidans**` locator is used with the **`>`** symbol to find the child element.

---

I hope this helps you better understand and use CSS locators. See you!
