# PixiJS Guides
## Architecture Overview

OK, now that you've gotten a feel for how easy it is to build a PixiJS application, let's get into the specifics.  For the rest of the Basics section, we're going to work from the high level down to the details.  We'll start with an overview of how PixiJS is put together.

## The Code

Before we get into how the code is layed out, let's talk about where it lives.  PixiJS is an open source product hosted on [GitHub](https://github.com/pixijs/pixijs).  Like any GitHub repo, you can browse and download the raw source files for each PixiJS class, as well as search existing issues & bugs, and even submit your own.  PixiJS is written in a JavaScript variant called [TypeScript](https://www.typescriptlang.org), which enables type-checking in JavaScript via a pre-compile step.  <!--TODO: (If you're interested in using PixiJS in a TypeScript-based project, check out the guide on [Working with Bundlers](working-with-bundlers.md).)-->

## The Components

PixiJS is a modular rendering engine.  Each task required for generating, updating and displaying content is broken out into its own component.  Not only does this make the code cleaner, it allows for greater extensibility.  Additionally, with the use of the [PixiJS Customize tool](https://pixijs.io/customize/), it's possible to build a custom PixiJS file containing only the subset of features your project needs, saving download size.

Here's a list of the major components that make up PixiJS.  Note that this list isn't exhaustive.  Additionally, don't worry too much about how each component works.  The goal here is to give you a feel for what's under the hood as we start exploring the engine.

### Major Components

| Component | Description |
| --- | --- |
| **Renderer**<br>`@pixi/core` | The core of the PixiJS system is the renderer, which displays the scene graph and draws it to the screen.  The default renderer for PixiJS is based on WebGL under the hood. |
| **Container**<br>`@pixi/display` | Main display object which creates a scene graph: the tree of renderable objects to be displayed, such as sprites, graphics and text. See [Scene Graph](scene-graph.html) for more details. |
| **Loader** <br>`@pixi/loaders`| The loader system provides tools for asynchronously loading resources such as images and audio files. |
| **Ticker**<br>`@pixi/ticker` | Tickers provide periodic callbacks based on a clock.  Your game update logic will generally be run in response to a tick once per frame.  You can have multiple tickers in use at one time. |
| **Application**<br>`@pixi/app` | The Application is a simple helper that wraps a Loader, Ticker and Renderer into a single, convenient easy-to-use object. Great for getting started quickly, prototyping and building simple projects. |
| **Interaction**<br>`@pixi/interaction` | PixiJS supports both touch and mouse-based interaction - making objects clickable, firing hover events, etc. |
| **Accessibility**<br>`@pixi/accessibility` | Woven through our display system is a rich set of tools for enabling keyboard and screen-reader accessibility. |
