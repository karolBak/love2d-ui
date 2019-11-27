# love2d-ui [![love2d version](https://img.shields.io/badge/L%C3%96VE-11.3-27a9e0?labelColor=e74999)](https://love2d.org)
Simple UI library for LÖVE framework.

#### Features:
- simple setup
- written in functional manner, no global state
- hierarchical structure as input
- compact syntax

## Run the demo
Library is the `UI.lua` file.

Demo code is inside `main.lua` file.

**Linux:**
Type `make` inside cloned repo to test the capabilities of the library.

## Usages:
- [karolBak/love2d-double-pendulum](https://github.com/karolBak/love2d-double-pendulum)
- [karolBak/love2d-lotka-volterra](https://github.com/karolBak/love2d-lotka-volterra)

## Example
```lua
local UI = require "UI"

function love.load ()
   -- Set up variables used as labels (note the curly brackets)
   explosives = {15}
   boom = "Not loaded"

   -- Set up functions for buttons
   function loadCannon () 
      boom = "Loaded" 
   end
   function setFire ()
      if boom == "Loaded" then 
         boom = "BOOM!" 
      end
   end
end

function love.draw ()
   UI.draw {
      UI.label { "Select amount of explosives" },
      UI.slider( 0, 100, explosives ),
      {  
         UI.button( "Load explosives", loadCannon ), 
         UI.button( "Set fire", setFire )
      },
      UI.label { boom },
   }
end
```
![Example of UI](example.png)

*Written in [Lua](https://www.lua.org/) using awesome [love2d](https://love2d.org/) framework.*
