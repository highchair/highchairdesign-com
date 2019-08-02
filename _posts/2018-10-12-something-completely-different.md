---
layout: post
title: "And now for something completely different"
date: 2018-10-12 19:00:00 -0500
#categories: [ 'Random' ]
---

A recent project brought me this bit of WYSIWYG editor span spam:

```
<p>
  <span>
    <span>
      <span>
        <span>
          <span>
            <span>
              <span>
                <span>
                  <span>
                    <span>
                      <span>
                        <span>
                          <span>
                            <span>
                              <span>
                                <span>
                                  <span>
                                    <span> [ content ] </span>
                                  </span>
                                </span>
                              </span>
                            </span>
                          </span>
                        </span>
                      </span>
                    </span>
                  </span>
                </span>
              </span>
            </span>
          </span>
        </span>
      </span>
    </span>
  </span>
</p>
```

Which I thought was hilarious. [Jason Pamental](//www.rwt.io) did as well. So I had
to reimagine a very famous, and very silly, sketch as an homage: 

```
<p aria-describedby="reference"><q class="waitress">Morning!</q></p>
<p aria-describedby="reference"><q class="man">Well, what've you got, then?</q></p>
<p aria-describedby="reference">
  <q class="waitress">Well, there's egg and bacon; egg sausage and bacon; egg and 
    <span>; 
      egg bacon and 
      <span>; 
        egg bacon sausage and 
        <span>; 
          <span> 
            bacon sausage and 
            <span>; 
              <span> egg 
                <span>
                  <span> bacon and 
                    <span>; 
                      <span> sausage 
                        <span>
                          <span> bacon 
                            <span> 
                              tomato and 
                                <span>; or Lobster Thermidor au Crevette with a Mornay sauce served in a Provencale manner with shallots and aubergines garnished with truffle pate, brandy and with a fried egg on top and 
                                  <span>.</span>
                                </span>
                              </span>
                            </span>
                          </span>
                        </span>
                      </span>
                    </span>
                  </span>
                </span>
              </span>
            </span>
          </span>
        </span>
      </span>
    </span>
  </q>
</p>
<p aria-describedby="reference"><q class="woman">Have you got anything without <span>?</span></q></p>
<p aria-describedby="reference"><q class="waitress">Well, there's <span>egg sausage and <span></span>, that's not got much <span> in it</span>.</q></p>
<p aria-describedby="reference"><q class="woman">I don't want ANY <span>!</span></q></p>
<p>—<cite id="reference">Monthy Python's Flying Circus</cite></p>
```

Jokes for nerds...

[WYSIWYG]: What You See Is What You Get