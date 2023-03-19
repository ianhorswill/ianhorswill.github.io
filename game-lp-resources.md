---
layout: page
title: Logic programming resources for game devs
permalink: /game-lp-resources/
---

This is a page of resources for the various tools discussed in Rob Zubek and Ian Horswill's GDC 2023 AI Summit talk.

GDC 2023 talk: Logic Programming in Commercial Games
- Slides: [pptx](Talks/Logic-programming-talk.pptx) [pdf](Talks/Logic-programming-talk.pdf)
- Join us on Discord: [Logic programming for game devs](https://discord.gg/rnBCEcgN) server

Interactive demos:
- **[MicroCoG](https://github.com/ianhorswill/MicroCoG)** can see an interactive demo of the *City of Gangsters* social
inference system running against a CoG game save file.
- **[Imaginarium](https://github.com/ianhorswill/Imaginarium)**: download the release, run it, hit escape to go to the main menu, and then choose one of the example generators and press one of the buttons at the top of the screen.  See the [Imaginarium tutorial](Tutorials/Imaginarium-tutorial.pdf) for more info.

Repos for different AI tools:
- **[TELL](https://github.com/ianhorswill/TELL)**: Typed, Embedded Logic Language  
  This lets you do simple logic programming tasks inside C# code, and mix-and-match LP and C#.  It's a limited version of
  logic programming; it doesn't support Prolog's matching of complex terms (Prolog's data structures), or the cut (!) operation.
  Used in an unannounced SomaSim project.  See the [TELL tutorial](Tutorials/TELL-tutorial.pdf) for more info.
- **[TED](https://github.com/ianhorswill/TED)**: Typed, Embedded DATALOG  
  This is like TELL, except it executes bottom-up instead of top-down.  Note that it is a not a proper version of datalog.
  It doesn't support recursion and its semantics are somewhat Prolog-like.  It's being used for large-scale city simulation
  and an unannounced SomaSim project.
- **[UnityProlog](https://github.com/ianhorswill/UnityProlog)**: Prolog interpreter with Unity interop  
  This is a nearly full version of ISO Prolog.  It was used in SomaSim's *Project Highrise* for consistency-checking of
  assets, e.g. checking that all strings have localization in all languages, there aren't multiple localizations, etc.
  It was also used for planning and natural language processing in the experimental game *MKULTRA*.
- **[Step](https://github.com/ianhorswill/Step)**: Simple Text Planner, a logic programming language for text generation  
  This is used in the upcoming PCG app from Machine Age Productions for the tabletop RPG, *[iHunt: Killing Monsters in the
  Gig Economy](https://ihunt.fun/)* by Olivia Hill and Filamena Young.  The Step repo is the base interpreter.  For
  an interactive command line and debugger, use [StepRepl](https://github.com/ianhorswill/StepRepl).  If you use it, install the StepHighlighter extension in VS Code.  For more information see the [Step tutorial](Tutorials/Step.zip)
- **[CatSAT](https://github.com/ianhorswill/CatSAT)**: Randomized SAT/SMT Solver   
  This is a randomized constraint solver used for character PCG in SomaSim's *City of Gangsters*.  It's also the underlying
  constraint solver used by *Imaginarium*.
- **[Imaginarium](https://github.com/ianhorswill/Imaginarium)**: Casual constraint-based PCG for table-top RPG players  
  This is a system that lets GMs and players create generators for random game artifacts using a simplified English-like
  syntax.  See the [Imaginarium tutorial](Tutorials/Imaginarium-tutorial.pdf) for more information.  This is the interactive app.  If you want to use the raw system inside your own game, use
  [ImaginariumCore](https://github.com/ianhorswill/ImaginariumCore).  If you use it, install the Imaginarium extension in
  VS Code.
- **[BotL](https://github.com/ianhorswill/BotL)**: A highly optimized logic programming engine for games  
  This largely does the same subset of logic programming that TELL does, but goes to extreme lengths to avoid dynamic
  memory allocation and run-time type checking.  It was used in SomaSim's *City of Gangters* for social reasoning.  At this
  point, I don't know that I would recommend using it.  The tooling for the other languages is much better and TED is probably
  just as fast.  If we do native code compilation for TED, it will be much faster.