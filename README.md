## Redollar
A totally new pattern that enables you to use intimate querying apis in React💰

### Abstract
There are two types of developers. You probably are new to React, fascinated by this state-oriented mode before becoming confused about something. **Data interaction is an issue between components**, especially for those written in different files. That's the moment when you have to embark on a treck of deeper learning and finally get beaten by myriad concepts: redux, reducer, action, dispatch, blah...

On the other hand, you probably are proficient in React and familiar with those senior concepts. There is no doubt that redux is great since it is solid and sophisticated. However, having been suffered from its inerp pattern for several times, you start to doubt **whether it is necessary to apply redux into all kinds of applications**. Let's just get rid of it before it becomes compulsory.

Here is **redollar** introduced.

### Quick Look
Let's take an example. There are three component files ```Card.js```,```Timer.js```,```Counter.js```, which are aggregated to simply play a feature of counting. The following is the structure.
```
-- Card
    |
     -- Timer
          |
           -- Counter
```
What if you want to change the number of Counter just in ```Card.js```. **Redollar offers your ability to do so!**. Here are the code examples.
```jsx
/*Card.js*/

import $ from 'redollar';
import Timer from './Timer';

export class Card extends $ {

    componentDidMount () {

        setInterval(() => {
            
            let num = parseInt($('Counter'.getPro('num')) + 1;

            $('Counter').setProp({num});

        }, 1000);

    }

    return (
        <div>
            <Time/>
        </div>
    )
}

```

```jsx
/**Timer.js**/

import $ from 'redollar';
import Counter from './Counter';

export default class Timer extends $ {

    return (
        <div>
            <Counter/>
        </div>
    )
}
```

```jsx
/**Counter.js**/

import $ from 'redollar';
export default class Counter extends $ {
    
    constructor (props) {
        super(props);
    }

    defaultProp () {
        
        return {
            num: 0
        }
    
    }

    render () {

        return (
            <h3>
                {this.props.num}
            </h3>
        )

    }


}
```
You can get the full example [here](https://github.com/captainwz/redollar/tree/master/example/src).

### Installation
```
npm install --save redollar
```






