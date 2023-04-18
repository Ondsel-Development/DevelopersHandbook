---
title: Roadmap
description:
   The roadmap provides broad objectives for the direction of FreeCAD development
layout: default
---

# {{page.title}}

{{page.description}}

# Development Roadmap 1.0

This document describes several high-level objectives for the FreeCAD project.  Rather than being a laundry list of development tasks, it focuses on a small set of strategic initiatives that, if achieved, will move FreeCAD closer to an ideal future state.  Of course, people may, _and probably will_ argue about _which_ future state FreeCAD should pursue.  For the purposes of this document we assume the following: 

1. We want FreeCAD to have a healthy development community where new features are regularly added, bugs are quickly resolved, and performance is maintained.
2. We want a large and diverse community of people using FreeCAD to do real work, including commercial, academic, and hobby pursuits.
3. We want the code-base to be maintainable, understandable, and testable.
4. We want the user interface to be beautiful, intuitive, and efficient.
5. We want high-quality and relevant documentation. 
6. We want the software to be well-designed to support a variety of use-cases including scripted operation.
7. We want a stable and well-designed API to allow FreeCAD to be included in other workflows and tools.

## Why Build a Roadmap?

Technical discussions often become contentious because the decisions made have real consequences.  Well-meaning people may disagree because they have differing priorities or goals.  

A well-designed roadmap is beneficial because it _first_ focuses on the priorities and then encourages technical decision-making in context.  

A good roadmap will be useful to many different kinds of people:

1. Developers will be able to make better decisions about which features should be addressed first and which bugs are worth fixing.
2. Maintainers can prioritize PR code-review and merge activity.
3. New contributors can get a sense of where and how their efforts would be most useful.
4. Non-developer contributors can prepare better documentation, support users more effectively, and advocate for appropriate changes.
5. The FPA can allocate resources to encourage key development efforts, plan events, and raise funds. They can encourage sponsors appropriately and push back on sponsors with goals that are not consistent with project goals.
6. Content creators can build curriculum, prepare tutorials, and aid with educating users about new features.
7. Ondsel and other commercial partners can plan their product offerings effectively.
8. GSoC and other mentors will be able to define projects that are consistent with the general project direction.
9. Other open-source projects can identify opportunities for partnership and co-development.

## Why Now?

FreeCAD releases have never followed a predictable routine.  Instead, the project’s unofficial motto,  “It’s done when it’s done” has dictated when official releases are prepared.  This model has served the project very well for many years but not without controversy and consequences.

Within the last couple of years many things in the FreeCAD ecosystem have changed.  

The user community has grown dramatically.  It has spread far beyond the forum and includes far more non-developer users now.

The FPA was formed to protect the FreeCAD project and encourage its growth.  The FPA has started receiving donations. Deploying those funds well has becoming a challenge itself.  

Ondsel was formed as an open-core public benefit corporation building around the FreeCAD project.  As a commercial enterprise, they have a strong need for predictabiilty in the development process and project goals.  

Commercial users have an increasing interest to deploy FreeCAD in production environments.

FreeCAD is reaching a state of feature-completeness that suggests a 1.0 release. After that point, backwards compatibility and document stability will become increasingly important.

Universities, trade schools, and online educators have shown interest in teaching FreeCAD and offering some form of certification.

## Who Gets to Write or Change It?

The roadmap is, in a sense, a living document.  It should be frequently reviewed and revised. The FPA is the steward of the document itself and takes the lead on drafting and revising its content, but it should reflect the will of the whole FreeCAD community.  The FPA actively seeks input from the community members and other stakeholders, partners and industry experts. 

# Roadmap

This roadmap outlines broad strategic objectives. Code contributions from developers will always be evaluated on their merits but are more likely to receive timely attention and be successfully merged if they are consistent with the stated objectives of this roadmap.

## Objective: Model Stability

Robust, stable models are a necessary precursor to widespread adoption of FreeCAD.  Some types of breakage are the unavoidable result of poor design practices by the user but FreeCAD must commit itself to reducing or eliminating as many causes of breakage as possible. Focus areas include:

1. Toponaming resolution and optimization
2. Reduction of sketcher solver errors
3. UI/UX features that promote better modeling practices and avoid brittleness.
    1. Make good practices easier.
    2. Remove / replace tools that allow unstable results.
4. Improved stability around linked documents.

## Objective: Assembly

Assembly is a core feature of modern CAD systems.  Without an integrated assembly capability, users are forced to use one of several add-on options.  With competing alternatives available, collaboration and interoperability is negatively affected.  Adoption of an assembly workbench should consider, at a minimum, a base set of features including

1. An assembly data format.  A data standard for the representation of assembly information in the FreeCAD document.  The standard should be well thought-out and usable both by the integrated solution as well as add-on options.
2. A license-compatible solver or the option to include a solver at a later date.
3. A minimum set of features to satisfy the 80+% of requirements of typical users.

## Objective: Flatten the Learning Curve

CAD is hard.  These are complicated and powerful tools and the user should be expected to invest appropriate time to learn to use them well.  However, UI/UX inconsistency makes the learning process more difficult than it need be.  The FreeCAD community must pursue a program of UI normalization to make learning FreeCAD easier.  

The first step in this process is to stop making things worse by accepting UI submissions that are poorly designed or implemented.  Focus areas:

1. Creation of a UI/UX ‘style book’.  This would be a guidebook for developers to follow when creating core and add-on functionality.  The style book would also be useful when evaluating new submissions that affect user experience.  Eventually, the style book standards can be used to ‘score’ existing workbenches and identify opportunities for improvement. 
2. A ‘first run’ wizard to familiarize the user with essential customizations and features.
3. Reduce confusing UI elements:
    1. Eliminate redundant tools
    2. Suppress infrequently-used workbenches
    3. Consolidate settings, preferences, and other customization tools
    4. Make toolbar placement more predictable and stable
4. Make toolbar placement consistent.
5. Make tasks fail safely.  Tasks should always be in transactions and ‘undo’ cleanly. Red errors in the console are unacceptable for normal workflow.
6. Normalize the use of terminology both within FreeCAD and, when possible, with external standards.
7. Improve support for materials and implement it consistently across all workbenches.

## Objective:  Seamless Extensibility

FreeCAD has an addon manager to allow the user to add niche features.  This provides two important functions.  First, it allows the core application to remain leaner and avoid bloat. Second, it allows for competing solutions early on.  Our approach to addons, however, has been somewhat undisciplined.  As a result, the quality of addons is very uneven.  Some are excellent and behave light native parts of the application.  Others feel and behave inconsistently.  Still others are completely broken or unmaintained.  If we want the addon capability to serve both purposes, additional development is needed.  Focus areas include:

1. Improve the Addon Manager workbench to make it easier for users to find good well-maintained addons.  Maybe a ‘Featured’ section if addon workbench has a responsive maintainer, minimum open bugs.   Maybe a user review?  Without some status, we could end up with lots of cruft polluting the manager.
2. Establish standards for addons to meet to achieve a ‘recommended’ or ‘featured’ status. Featured addons should: 
    1. Have an engaged maintainer
    2. Have minimal high priority open issues tickets
    3. Comply with published style book
    4. Support translation
    5. Support unit schema
    6. Install and function cleanly with only the addon manager.
3. Improve scriptability
    1. Improved editor / support external editor
    2. Native debugger
    3. Improved API

## Objective:  Have the Best Documentation Possible

Documentation has become as important as the FreeCAD application itself. Good documentation can offer a bridge to new users and smooth the learning curve. It can make all the difference between an application that is hard to use and one that is easy to learn.

The FreeCAD documentation is generally in a very good state already. But it could, and should, go much further.  Focus areas include:

1. Low-friction to revision through the browser
2. Git-trackable
3. Versions of the documentation that match software versions
4. Good translation support
5. Support for off-line readers
6. Natural integration of developer / API documentation

## Objective: UI Modernization and Beautification

We want the FreeCAD application to be both efficient and attractive.  We want it to integrate well with the rest of the desktop experience, to be responsive and to be delightful to use. Focus areas include:

1. User customization 
    1. Themes
2. Modern UI concepts
    1. Eg “pie menu”
    2. Context menus
    3. Ribbon Bar
3. Efficient use of screen area
    1. Transparency
    2. Multi-screen support
4. Enhanced visualizaton
    1. Shadows
    2. Simplified ray tracing and rendering

## Objective: Streamlined Workflow

Performing common and repetitive tasks should be as effortless as possible.  FreeCAD developers should commit themselves to building efficient workflows throughout the application.  This means minimizing clicks and unnecessary dialogs.  It means adding dedicated tools for routine functions rather than relying on generalized tools that may require more steps. It means anticipating and giving the user efficient access to information when and where they need it.  Focus areas include:

1. Better and consistent measuring tools
2. Improve sketcher: 
    1. Missing tools: 
        1. Offset tool
        2. Circular pattern
        3. Usable rectangular array
        4. Constrain contextually
3. Seamless copy-paste of geometries/sketches
4. Uniform selection modes
5. Uniform approach to user parameters
6. Simplified access to commonly needed data
    1. Volume
    2. Mass
    3. Moment
    4. Center of gravity
    5. Surface area
7. Text alignment tool

## Objective: Lower Barriers to Entry

FreeCAD has an enormous number of functions and for a new user, there is no obvious way to use just a task oriented subset.  It should be possible for new users to access a subset of FreeCAD functionality, say on the level of a TinkerCAD.  As they gain experience, they can use additional functions.

FreeCAD has a major terminology problem for new users.  We have a Part workbench that doesn't make parts and a Part Design workbench that isn't used to design parts.  We have Pads and Extrudes, Pockets and Cuts, Fuses and Unions, etc.  We have a Part container and a Group container(?) but no core functions to populate a container (e.g. a core assembly function).

[This discussion](https://forum.freecad.org/viewtopic.php?p=669869#p669869) on the FreeCAD forum about nomenclature serves as a starting point to improve the state of affairs with terminology.

## Objective: Prevent Shooting Yourself in the Foot

FreeCAD allows users to do things that are known to build fragile models, such as building features based on variable foundations (e.g. sketches on faces, dimensions based on drawing lines).  We even have icons and commands for doing this.  FreeCAD should prevent "dangerous" actions, convert them behind the scenes to safe actions or at least provide a warning about unsafe practices.
