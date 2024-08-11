# AI Shopping Assistant ChatBot gist (named: Rosie)

## Screen recording demo
https://anneuy.com/demos/shop-assistant-ai-demo.webm

## Background
I am working on an online Shopify store called "Modern Kastle" selling diaper bags I designed. I've been really into the AI space lately so I thought it would be fun to experiment with the OpenAI API (company behind the famous Chat GPT-3).
This is a snippet of a chatbox component from a custom Shopify App I made from scratch, which I started last Sunday, May 28.
This AI chatbot's goal is to help direct potential buyers to a product depending on their preferences, as if they are engaging with a real store salesperson.
It's also pretty fun to put on the shop I'd think :)

## MVP functionality goals:
- [x] engages in natural conversation with a potential buyer with the goal of a suitable product recommendation
- [x] shares a clickable product link of a product (opens in a new tab)
- [x] AI uses actual Shopify product data queried via GraphQL Admin API
- [x] does not comply with requests that are outside the scope of a shop assistant
- [ ] available to be added onto the storefront theme via an App Block (in progress)

## Key tech
- ReactJS/Typescript
- OpenAI API (chat completions) using Chat-GPT3.5-turbo model
- Shopify CLI
- ExpressJS
- Vite

## Challenges
1. Training the AI on actual shop product data - I have successfully plugged in the dev store's dummy product and variants but there were a number of challenges around this, such as the limit of querying up to 250 products at a time, as well as how to actually train the AI whether it be fine-tuning, semantic search or just adding to the message context. A solution to the 250 product limit is to implement bulk operation mutation and queries, and I did figure out the cheapest and most effective way to train the AI.
2. Showing the ChatBot on the storefront - React is supported on the Embedded App page for Shopify Apps out-of-the-box, but App Blocks for theme extensions only support vanilla javascript. I haven't figured out how to render the React ChatBox onto the storefront yet because of this limitation. This is in progress.
3. Learning new tech - this is the first time I've used the Express framework. At first this tripped me off with how to define the app's local API. Now I understand how this ties in better with Shopify's built-in GraphQL and REST API client.
4. Vite - I have prior experience with Webpack and given its popularity I was surprised the Shopify node template used Vite. So far the issues I've had are overcome with reading docs and googling.

## What I would have done differently or improved upon if I had more time
Maybe I would have directly tried to develop this as an app theme extension, instead of a Shopify App. That would have introduced me to the vanilla js issue earlier so I could spend more time on solving it.

With more time, I would also implement Firebase and think about the server piece to this, to avoid storing the API Keys in the frontend.
Regardless, this project is ongoing and I am passionate to make it work!
