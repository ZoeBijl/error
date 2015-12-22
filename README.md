# Techniques to display errors and a proposal

## How to handle and display errors for user input?

What are the different ways to communicate error messages (to all users)? [Tests are located in `index.html`](https://rawgit.com/ZoeBijl/error/master/tests/index.html).

### Resources

* [Form validation with the pattern attribute](http://webdesign.tutsplus.com/tutorials/html5-form-validation-with-the-pattern-attribute--cms-25145)
* [Aria-errormessages property: what void does it fill?](https://github.com/w3c/aria/issues/128)
* [Proposal for an `error` element](https://gitter.im/w3c/a11ySlackers?at=56783de1091b6f9e043a1294)
* [`input` element](http://www.w3.org/TR/html5/forms.html#the-input-element)
* [`output` element](http://www.w3.org/TR/html5/forms.html#the-output-element)
* [Common `input` element attributes](http://www.w3.org/TR/html5/forms.html#common-input-element-attributes)
* [Live validation with CSS by Hugo Giraudel](http://codepen.io/HugoGiraudel/pen/b3274eb0bf93bed79afeafd30b7a33f1)
* [WAI Tutorials: Forms: User Notifications](http://www.w3.org/WAI/tutorials/forms/notifications/)
* [What is best practice for designing form error messages?](http://ux.stackexchange.com/questions/26173/what-is-best-practice-for-designing-form-error-messages)

## The `error` element

Would it make sense to add an `error` element to HTML? I think so, so I've started a [proposal for the `error` element](https://rawgit.com/ZoeBijl/error/master/proposal/index.html). This still needs a lot of research.

### Examples

If we only allow phrasing content—like `label`:

```
<label for="username">Username</label>
<input type="text"
  id="username"
  name="username"
  placeholder="Lowercase only, e.g.: soren"
  pattern="[a-z]{3,15}">
<error for="username">Username should only contain lowercase letters. e.g. soren</error>
```

If we also allow other markup—like `blockquote`:

```
<error for="firstname">
  <p>First names cannot contain spaces, because we hate you, Mary Lou.</p>
  <ul>
    <li>Check that your name doesn't contain spaces</li>
    <li>If your name does contain spaces, consider getting your name legally changed</li>
    <li>Consider altering your name to camelCase</li>
    <li>Re-fill in the input, this time without spaces</li>
  </ul>
</errror>
```

We can also display all errors as a list:

```
<ul>
  <li><error for="firstname">First names cannot contain spaces, because we hate you, Mary Lou.</error></li>
  <li><error for="lastname">Last names need to be at least five characters long, so suck it Mr. Bijl.</error></li>
</ul>
```

Link it to a form:

```
<form id="whisky">
  ...
</form>
<error form="whisky">The server rejected your order because you only ordered one bottle. Order at least two.</error>
```

### Resources

* []
