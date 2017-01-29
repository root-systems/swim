#LEARNING REACT + REDUX

##DIAGRAMS:
- TBD

##RESOURCE LIST:
- https://facebook.github.io/react/docs/hello-world.html [The official React docs are actually pretty good - examples, relatively friendly approach]
- http://redux.js.org/docs/introduction/index.html [Likewise for the Redux docs. I’d suggest coming to these after the React docs, and there is a little more assumption about ES6 familiarity here, but the key thing to get down is the concept of how data flows, and what ‘things’ (i.e. actions, reducers, store) are involved in that flow]
- https://egghead.io/courses/getting-started-with-redux [30 free videos with code on learning Redux, from the creator. I’ve only actually watched a couple of these, but lots of people vouch for them]
- https://github.com/lukehoban/es6features [A guide to ES6 features - i can’t remember the resource i used when learning ES6 but it was something like this. We only really end up using the first 5 or 6 things on there, and the import / export syntax - Mikey in fact has a repo that adds only select features from ES6 to a project https://github.com/ahdinosaur/es2040. IMO the key with ES6 is practice and getting used to weird-looking code. And if you don’t like a feature, don’t use it!]
- https://github.com/gaearon/redux-thunk [This is IMO the most understandble + easily implementable approach to doing asynchronous ‘work’ with Redux. Out of the box, Redux doesn’t handle async operations like API requests - it assumes all actions are completed instantaneously. Redux-thunk is a little bit of a mind-bend when first learning Redux, but the docs are good.]
- https://lodash.com/docs/4.17.4 [Feels a bit weird including Lodash here, but I find it’s functions pretty invaluable for doing complex work - i would end up writing sub-par implementations of them myself a lot if I didn’t have them. The hardest thing IMO with Lodash is knowing what they’ve called the function that does the thing you’re thinking of… it just seems to take practice and looking through the docs, happy to help out with my knowledge on this! Most common ones for me:
  - Map / Filter / Reduce (though i actually kinda like the default JS ones)
  - Assign (again the default JS one works fine too)
  - Concat / Without (good for array mangling that doesn’t mutate the input array)
  - Find (grab the first matching thing from array / object)
  - Omit (i don’t want this key:value in my object, return it without that key:value)
  - isPlainObject / isEmpty etc (good ways to check a thing is actually a thing)

##CODE EXAMPLES:
- https://github.com/iainkirkpatrick/tempo-client/tree/master/app [This is a wee example of a client-side app with React + Redux, with the structure style that Root Systems is using (‘domain-driven-development’). The domains aren’t particularly fleshed out yet, but there is one example of the action-reducer cycle. I need to do a bit of work before you can try it out - atm the server repo probably won’t ‘just work’ if you download it, it relies on Postgres being installed etc - but it might be a useful small example to look at. It also includes a minimal example of a GET to an API with redux-thunk, which is useful to wrap the brain around.]
- https://gist.github.com/iainkirkpatrick/5f50cc5d47f66b4290ff935fdb252893 [This is copy+pasted code from FitAdvisor, with most files that make up the Orders domain. It’s a bit hard to look at all-in-one like this, but hopefully you can trace how the files are linked up and strengthen the basic idea. One file not included is effects.js - Effects are a particular approach for doing asynchronous actions with Redux, i.e. when we need to fetch data from an API. We are trying them on FA, but I’m not convinced so far that they are worth the mental overhead (I find them kinda confusing) and so I think redux-thunk (https://github.com/gaearon/redux-thunk) is the better approach to begin with in terms of learning. It also has better docs than the effects library we are using]
