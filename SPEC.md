####Architecture requirements

###### #1
- Zero coupling between child project
- No importing of functions/objects/classes/etc
- No shared state
- Shared libraries through MF is ok

###### #2
- Near-zero coupling between container and child apps
- Container shouldn’t assume that a child is using a particular framework
- Any necessary communication done with callbacks or simple events

###### #3
- CSS from one project shouldn’t affect another

###### #4
- Version control (monorepo vs separate) shouldn’t have any impact on the overall project
- Some people want to use monorepos
- Some people want to keep everything in a separate repo

###### #5
- Container shouldn’t be able to decide to always use the lates version of a microfrontend or specify a specific version
- (1) Container will always use the latest version of a child app (doesn’t require a redeploy of container)
- (2) Container can specify exactly what version of a child it wants to use (requires a redeploy to charge)

###### #6
- Users can navigate around to different subapps using routing logic built into the Container.
- Users can navigate around in a subapp using routing logic build into subapp itself.
- Not all subapps will require routing

###### #7
- New routes add to a subapp shouldn’t require a redeploy of the container

###### #8
- We might need to show two or more microfrontends at the same time.
- This will occur all the time if we have some kind of sidebar nav that is built as a separate microfrontend

###### #9
- We want to use off-the-shelf routing solutions.
- Building a routing library can be hard - we don’t want to author a new one.
- Some amount of custom coding is OK

###### #10
- We need navigation features for sub-apps in both hosted mode and in isolation

###### #11
- If different apps need to communicate information about routing, it should be done in as generic a fashion as possible.
Each app might be using a completely different navigation framework.