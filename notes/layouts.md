```plaintext
---
<!-- src/pages/index.astro -->
import BaseLayout from '../layouts/BaseLayout.astro';
const pageTitle = "Home Page";
---
<BaseLayout>
  <h2>My awesome blog subtitle</h2>
</BaseLayout>
```

Here we're using double closing tags syntax, but that's only because we want to be able to insert
content within it, this way we can place it, inside the `BaseLayout.astro` component using the special
element `<slot />`

```plaintext
<!-- src/layouts/BaseLayout.astro -->
---
// -- Components Imports
import Header from '../components/Header.astro';
import Footer from '../components/Footer.astro';

import '../styles/global.css';
const { pageTitle } = Astro.props;
---
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" type="image/svg+xml" href="/favicon.svg" />
    <meta name="viewport" content="width=device-width" />
    <meta name="generator" content={Astro.generator} />
    <title>{pageTitle}</title>
  </head>
  <body>
    <Header />
    <h1>{pageTitle}</h1>
    <slot />
    <Footer />
    <script>
        import "../scripts/menu.js";
    </script>
  </body>
</html>
```

Notice that the `h2` (and anything else there), will be rendered just before the <Footer />

The <slot /> allows you to inject (or “slot in”) child content written between opening and closing
<Component></Component> tags to any Component.astro file.

## Pass page-specific values as props

```plaintext
---
<!-- src/pages/index.astro -->
import BaseLayout from '../layouts/BaseLayout.astro';
const pageTitle = "Home Page";
---
<BaseLayout pageTitle={pageTitle}>
  <h2>My awesome blog subtitle</h2>
</BaseLayout>
```

```plaintext
<!-- src/layouts/BaseLayout.astro -->
---
// -- Components Imports
import Header from '../components/Header.astro';
import Footer from '../components/Footer.astro';

import '../styles/global.css';
const { pageTitle } = Astro.props;
---
```

Notice that we are using page specific props here...
