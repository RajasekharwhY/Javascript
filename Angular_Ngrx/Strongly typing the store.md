## Define Interfaces for slices of state
  - One issue when defining the global application state ( lazy loading boudnary).
  - We need to establish logical boundaries with our lazy loaded features with the global application state.
  
  How to solve this: In the feature(Product) code, We will extend the global application state to include the 
  the feature (prouduct) slcie of interface. So we are keeping this in our lazy loading boundary. 
  When feature is lazy loaded, then we are exteding the global state to include the lazy loded feature in our 
  global application state.
  
  Import * ( Meaning import all the of the exported memebers )
  Import * as fromRoot from '../../state/app.state'
  
  export Interface state extends fromRoot.state {  // fromRoot.state -> have all the exported intefaces defined.
  products : productState;
  }
  
  if your feature is not lazy loaded you can directly define it in the global application state. 
  export interface state {
   Users: UserState; // Pre loaded features slices.
  }
  Above extends used for lazy loaded feature slices. 

## Use the Interfaces for strong typing
  Once we have the interfaces for the slices, next step is add the strong types in the reducer function 
  for both function parameters and retrun types. 
## Set Initial state value
  create an object for the intail state and assign the values
  - We can use the Javascript feature default functional paramerter syntax.

## Build selectors
  You can build any number of selectors based on the need to retrieve the different types of data 
  from the store. 
     -> you may want to get the entire slice of a feature. 
     -> you can get only some sub portion of a slice. 
  
  Selector is like a reusable query of our store.
  Just like a store proc to accessing our in memory state information.
  Selector are layer between the store and the components.
  It handles / encapsulate the complex data transfermations.
  And these are reusable, so other components can access the same way
  Selectors returned value is cached. (This is only evaluated when state changes)- This will 
  Improve the performance. 
  
  There are two basic types of selector functions provided by ngrx library: 
  - First type is a create feature selector -> to select the slice of a state. 
  - Second type is a create selector (it takes the two arguments ) - used to select the specific bit (you can map) of a feature slice 
        What are those two arguments. ?? 
  

## Using and composing selectors 
  We can compose multiple selectors to build a single selector
