# Next.js

## Introduction
Next.js is a React framework that enables functionality such as server-side rendering and generating static websites for React-based web applications.

## Basic Syntax
```javascript
// Example of a basic Next.js page
import React from 'react';

const Home = () => {
  return (
    <div>
      <h1>Welcome to Next.js!</h1>
    </div>
  );
};

export default Home;
```

## Common Use Cases
- Server-side rendering (SSR)
- Static site generation (SSG)
- Building SEO-friendly web applications
- API routes

## Advanced Features
- **API Routes**: Create API endpoints within your Next.js application.
- **Dynamic Routing**: Create dynamic routes with file-based routing.
- **Incremental Static Regeneration (ISR)**: Update static content after build time.
- **Image Optimization**: Optimize images with the built-in Image component.

## Code Snippets
### API Routes
```javascript
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello, world!' });
}
```

### Dynamic Routing
```javascript
// pages/posts/[id].js
import { useRouter } from 'next/router';

const Post = () => {
  const router = useRouter();
  const { id } = router.query;

  return <p>Post: {id}</p>;
};

export default Post;
```

### Incremental Static Regeneration
```javascript
// pages/index.js
export async function getStaticProps() {
  const res = await fetch('https://api.example.com/data');
  const data = await res.json();

  return {
    props: {
      data,
    },
    revalidate: 10, // Revalidate at most once every 10 seconds
  };
}

const Home = ({ data }) => {
  return (
    <div>
      <h1>Data from API</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
};

export default Home;
```

### Image Optimization
```javascript
// pages/index.js
import Image from 'next/image';

const Home = () => {
  return (
    <div>
      <h1>Optimized Image</h1>
      <Image src="/path/to/image.jpg" alt="Example Image" width={500} height={500} />
    </div>
  );
};

export default Home;
```

## Tips & Best Practices
- **Use `getStaticProps` and `getServerSideProps`**: Use these functions to fetch data at build time or request time.
- **Optimize Images**: Use the built-in Image component for automatic image optimization.
- **Dynamic Imports**: Use dynamic imports to load components only when needed.
- **SEO**: Use the `next/head` component to manage the document head for better SEO.
- **Environment Variables**: Use environment variables to manage configuration.

## External Resources
- [Next.js Official Documentation](https://nextjs.org/docs)
- [Next.js GitHub Repository](https://github.com/vercel/next.js)
- [Awesome Next.js](https://github.com/unicodeveloper/awesome-nextjs)