# About Astor.props

Astro.props is a global object available within the frontmatter script of an Astro component.
It contains any values that have been passed as attributes to that component when it's used in another
Astro component.

Example:

```plaintext
<!-- src/pages/index.astro -->
<MyComponent title="Hello Astro" message="Welcome to the site!" />
```

Inside the MyComponent.astro file, you access these passed values through the Astro.props

```
<!-- src/components/MyComponent.astro -->

---
const { title, message } = Astro.props;
---
<h1>{title}</h1>
<p>{message}</p>
```

We can also leverage typescrip and it's interface.

Example:

```plaintext
<!-- src/components/MyComponent.astro -->

---
interface Props {
  title: string;
  message?: string; // Optional prop
}
const { title, message = "Default message" }: Props = Astro.props;
---
<h1>{title}</h1>
<p>{message}</p>
```
