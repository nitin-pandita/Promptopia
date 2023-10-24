# Introduction to Next JS

Q1: What is the difference between Next js and React Js?

Ans: 

- Next js has easy routing, in React js we have to install an additional package for the routing but in Next Js we route through the “file system”
- API endpoint: Next js makes it very easy to create the API endpoint, which was not there in React js.
- Next js is very fast as compared to the react js
- Automatic Code Splitting: It reduces a website's search time and improves the user experience.

## Next Js is an extension of the React js

### Installation:

```jsx
npx create-next-app@latest
```

> Whenever we are using the UseState or other UseEffect it is very important to make the next js to “use client” instead of “server side”
> 

Q: When to use Server components and when to use Client components ?

Ans: 

| What do you need to do? | Server Component | Client Component |
| --- | --- | --- |
| Fetch data | ✔ | ❌ |
| Access backend resources (directly) | ✔ | ❌ |
| Keep sensitive information on the server (access tokens, API keys, etc) | ✔ | ❌ |
| Keep large dependencies on the server / Reduce client-side JavaScript | ✔ | ❌ |
| Add interactivity and event listeners (onClick(), onChange(), etc) | ❌ | ✔ |
| Use State and Lifecycle Effects (useState(), useReducer(), useEffect(), etc) | ❌ | ✔ |
| Use browser-only APIs | ❌ | ✔ |
| Use custom hooks that depend on state, effects, or browser-only APIs | ❌ | ✔ |
| Use https://react.dev/reference/react/Component | ❌ | ✔ |

- We can use Next  js for rourting this is done by this structure :

![Untitled](Introduction%20to%20Next%20JS%204b84c9e4577044578c9e6bb08b46463c/Untitled.png)

- We just need to create a folder in the app folder and inside of that, we need to create a “page.js” file.

```jsx
localhost:3000/posts
```

If we want to have a sub-page inside the main page we can create a new folder inside the posts folder:

```jsx
localhost:3000/posts/new
```

![Untitled](Introduction%20to%20Next%20JS%204b84c9e4577044578c9e6bb08b46463c/Untitled%201.png)

## Dynamic Routing:

To get the dynamic values from the routing, we can create a folder inside a square brackets.

Like : 

![Untitled](Introduction%20to%20Next%20JS%204b84c9e4577044578c9e6bb08b46463c/Untitled%202.png)

# [✔][ ✔] — Data Fetching — [✔][✔]

### Next js provides three ways to fetch data

1. SSR: Server Side Rendering: Dynamic server render data.
2. SSG: Static Site Generation: 
3. ISG: Incremental Static Generation.

## Next Js EndPoint :

Serverless endpoint for creating a full stack application.

```jsx
app.get('/api/users',(req,res) => (
// piece of code
)
```

This can’t happen:

>app

> users

>router.js

>page.js ❌

To keep our code clean we can create route by making the file structure like this:

![Untitled](Introduction%20to%20Next%20JS%204b84c9e4577044578c9e6bb08b46463c/Untitled%203.png)

```jsx
HTTP://localhost:3000/api/user
```

## SEO and MetaData

We can  define metadata  in two ways:

1. Static 
2. Dynamic

For Static Data:

```jsx
export const metadata = {
	title: "Home",
};
```

For Dynamic Data:

```jsx
export async function generateMetaData({params, searchParams}){
const product = await getProduct(params.id);
return {title: product.title};
}
```