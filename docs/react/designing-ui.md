---
layout: home
parent: React
title: Designing UI
---

# Designing UI

1. **Break the UI into a component hierarchy**: Start by drawing boxes around every component and subcomponent in the mockup and naming them. If you work with a designer, they may have already named these components in their design tool. Ask them!
2. **Build a static version in React**: To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props
3. **Find the minimal but complete representation of UI state**: Think of state as the minimal set of changing data that your app needs to remember. The most important principle for structuring state is to keep it DRY (Don’t Repeat Yourself). Figure out the absolute minimal representation of the state your application needs and compute everything else on-demand
4. **Identify where your state should live**: Identify every component that renders something based on that state. Find their closest common parent component—a component above them all in the hierarchy.
5. **Add inverse data flow**: Currently your app renders correctly with props and state flowing down the hierarchy. But to change the state according to user input, you will need to support data flowing the other way.

## Reference

<https://react.dev/learn/describing-the-ui>
