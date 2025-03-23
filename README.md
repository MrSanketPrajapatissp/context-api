

## Context API in React example: 

```jsx
import React, { createContext, useContext, useState } from "react";

const AppContext = createContext(null);

export const Parent = () => {
  const [UserName, setUserName] = useState("Sanekt131");

  return (
    <div>
      <div> Username: {UserName}</div>
      <AppContext.Provider value={{ UserName, setUserName }}>
        <Child />
      </AppContext.Provider>
    </div>
  );
};

export const Child = () => {
  return (
    <div>
      <GrandChild />
    </div>
  );
};

export const GrandChild = () => {
  const { setUserName } = useContext(AppContext);
  return (
    <div>
      <button
        onClick={() => {
          setUserName("Harry$324");
        }}
      >
        Change userName
      </button>
    </div>
  );
};

function App() {
  return (
    <div>
      <Parent />
    </div>
  );
}

export default App;



```
