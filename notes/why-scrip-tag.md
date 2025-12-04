In AstroJS when we want to add some interactivity we need to send the JavaScript to the client.

when we use astro's syntax ({var_name}) we are actually providing variables that will be used once to
generate static html. Once the code is built, the js code is "thrown away". That's how Astro is capable
of sending so little JavaScript to the client, making websites faster.
