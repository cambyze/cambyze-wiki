# React JavaScript library

![Cambyze Logo](cambyze_logo.png)

Main information about React. It will be used to create dynamic web user interfaces.

## Table of Contents

- [React apps management](#react-apps-management)
  - [Creation from a template](#creation-from-a-template)
  - [New method "createRoot" since "render" is deprecated](#new-method-createroot-since-render-is-deprecated)
- [Dynamic web](#dynamic-web)
  - [Create a component with JSX](#create-a-component-with-jsx)
  - [Mapping a collection “bookList” to the component “BookItem”](#mapping-a-collection-booklist-to-the-component-bookitem)
- [Events listening](#events-listening)

---

## React apps management

### Creation from a template

Ensure `yarn` is installed in the Node.js environment:

```bash
npm install -g yarn
```

Then use it. As an example for the new project `cambyze-react-app`:

```bash
yarn create react-app cambyze-react-app
```

### New method "createRoot" since "render" is deprecated

```javascript
import * as ReactDOMClient from 'react-dom/client';
import './styles/index.css';
import App from './components/App';

const container = document.getElementById('app');
const root = ReactDOMClient.createRoot(container);
root.render(<App tab="home" />);
root.render(<App tab="profile" />);
```

---

## Dynamic web

### Create a component with JSX

```javascript
function App() {
  return (
    <div>
      <Banner>
        <img src={logo} alt='Cambyze Shopping Center' className='lmj-logo' />
        <h1 className='lmj-title'>Cambyze Shopping Center</h1>
      </Banner>
      <ShoppingList />
    </div>
  );
}
```

### Mapping a collection “bookList” to the component “BookItem”

```javascript
function ShoppingList() {
  return (
    <div>
      <div>List of books</div>
      <ul className='lmj-book-list'>
        {bookList.map(({ id, cover, name, isSpecialOffer }) => (
          <BookItem
            id={id}
            cover={cover}
            name={name}
            isSpecialOffer={isSpecialOffer}
          />
        ))}
      </ul>
    </div>
  );
}
```

```javascript
import '../styles/BookItem.css';

function BookItem({ id, cover, name, isSpecialOffer }) {
  let sales;
  if (isSpecialOffer) {
    sales = <div className='lmj-sales'>Sales</div>;
  } else {
    sales = <div className='lmj-ordinary'></div>;
  }

  return (
    <li key={id} className='lmj-book-item'>
      {sales}
      <img className='lmj-book-item-cover' src={cover} alt={`${name} cover`} />
      {name}
    </li>
  );
}

export default BookItem;
```

---

## Events listening
Very easy with React, no need anymore to create a listener:
```javascript
function handleClick(bookName) {
  alert(`You want to buy the book ${bookName}?`);
}

function BookItem({ id, cover, name, isSpecialOffer }) {
  return (
    <li key={id} className='lmj-book-item' onClick={() => handleClick(name)}>
      ...
    </li>
  );
}
```
