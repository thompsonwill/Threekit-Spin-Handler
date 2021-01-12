# Threekit 2D Spin Handler

This code will help you add a spin effect to your Threekit 2D player. 

* Somewhere on the asset there has to be an attribute that manipulates the rotation of the items. For example, create an attribute called "View Angles" that house angles the item can be seen in [0, 30, 60, 90...]

* Add the code from spin.js to your project. Replace any instances of `attrName = "**Rotation_Attribute**"` with your corresponding attribute name. 

* You can change the direction of the spin by changing the `direction` value to `1` or `-1`.

* When the player is initialized, you can then call the function from spin.js which will add our `2D Spin` tool to the player. 

* If the spin is too sensitive or not sensitive enough, adjust the `maxWidth` variables in the spin.js file. 

```
window
  .threekitPlayer({
    authToken: "01234567-89ab-cdef-0123-456789abcdef",
    el: document.getElementById("player"),
    stageId: "27b9cd7e-2bb2-4a18-b788-160743eb4b33",
    assetId: "e12a45f7-8b39-cd06-e12a-45f78b39cd06",
    },
    showConfigurator: true,
    showAR: true,
  })
  .then(async (api) => {
    window.player = api;
    window.configurator = await api.getConfigurator();
    apply2DSpin({ attrName: "**Rotation_Attribute**", direction: 1 })(api);
  });

  ```