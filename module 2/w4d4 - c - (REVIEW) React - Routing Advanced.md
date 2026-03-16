
# React - Routing Advanced

<!-- 

Status: notes


-->



## URL parameters vs Query String

- URL structure: 
  https://cdn.cognitiveseo.com/blog/wp-content/uploads/2019/11/url-structure-1024x538.jpg

- Examples of URL Params

  https://localhost:3000/countries/42
  https://localhost:3000/artists/madonna
  https://localhost:3000/artists/madonna/albums/5


- Examples of Query String

  https://localhost:3000/rooms?maxPrice=200
  https://localhost:3000/rooms?sort=price




## URL parameters (aka. dynamic routes)


OPTION 1:

```js
<Routes>
    <Route path="/" element={<HomePage />} />
    <Route path="/characters/:characterId" element={<CharacterDetails />} />
</Routes>
```


<!--
  @LT: use this approach 
  (keep API request in App.js & pass array as props)

  Later, in CharacterDetails, implement a 2nd request to the API 
  (explain students that the goal is to refresh syntax)

-->



OPTION 2:

```jsx
<Route path='/' element={renderListOfCharacters()}
```





```js
import { useParams } from "react-router";

function CharacterDetails(props) {
  const {characterId} = useParams();
  // ...
}

```




## (self-guided) Query Strings


Note: 
- lab "React Stack Tracker" includes query strings in the last bonus iteration
- show briefly in the Student Portal

For query string there's a hook `useSearchParams`:
- https://reactrouter.com/docs/en/v6/api#usesearchparams


