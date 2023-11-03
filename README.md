# Accordion Menu in React from Scratch 
Initial Project Setup
---
Create a new project using create-react-app
```
npx create-react-app react-accordion-demo
```
Once the project is created, delete all unnecessary files from the `src`folder. Create a new folder with the name `Accordion` inside the `src folder` and add files `Accordian.js`,  `AccordianItems.js`, `list.js` and`styles.css` .

Open the `styles.css` file and add the contents.

How to Create the Initial Pages
---
Open the `src/App.js` file and add the following content inside it:

```
import { Accordion } from './Acordion/Accordion';
import './App.css';

function App() {
  return (
    <div>
      <Accordion />
    </div>
  );
}

export default App;
```
Now, open the `Accordion/Accordion.js` file and add the following content inside it:
```
import { AccordionItem } from "./AccordionItem";
import { list } from './list';
import './style.css';

export const Accordion = () =>{
    return(<div>
        {list.map((item, index) => 
            <AccordionItem key= {index}
                            title = {item.title}
                            content= {item.content}/>
                            
       ) }
        </div>    
    )
}
```
Then open the `Accordion/AccordionItems.js` file and add the following content inside it:
```
import { useState } from "react"

export const AccordionItem = ({title, content}) => {

    const [isOpen, setIsOpen] = useState(false);

  const handleIsOpen = () => {
        setIsOpen(!isOpen)
}

 return(<div>
    <div className= {isOpen ? 'active' : "default" } onClick={handleIsOpen}>
        {title}
    </div>
    {

    isOpen && <div className="content">
        { content }
        </div>
       }
 </div> ) 
}
```
open the `Accordion/list.js` file and add the following content inside it:

````
export const list = [
    {
        title:"title one",
        content:"content ONE"
    },
    {
        title:"title two",
        content:"content TWO"
    },
    {
        title:"title three",
        content:"content THEE"
    }
]
````

Now, if you check the application, you will see the following screen:
![Screenshot 2023-11-03 112142](https://github.com/HannaFleming/Accordion/assets/124400864/638060cd-fd8f-4516-bdd7-cf63bcbd353e)

As you can see, initially, the accordion is closed. When we click on the title, the accordion opens and we can click on it again to close it.

![Screenshot 2023-11-03 112219](https://github.com/HannaFleming/Accordion/assets/124400864/9d0155b7-3229-449d-a756-a5e3b4452699)

![Screenshot 2023-11-03 112235](https://github.com/HannaFleming/Accordion/assets/124400864/c867d445-ee6b-47a6-9f8f-0da6a6ab0ae4)
# Thanks for reading!
