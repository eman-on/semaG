## PerfectWorld wings faded
#### Wings with fade in and fade out effect!
To make shooting normal ))

Video: https://www.youtube.com/watch?v=24HJ4gAcOMw

 

Files need to be placed into folder "...\Counter-Strike Global Offensive\csgo"

Code example:
```
 "VertexLitGeneric"                                      // or other type of texture
 {

	"$basetexture" "models\shop\perfectworld_wings\wings01" // texture path, without ".vmt"
	"$halflambert" 1                                 // texture parameters. 
	"$nocull" 1 
	"$var01" 130.0                                   // |-> var part -----------------------------------------------------------------------------|
	"$var02" 20.0                                    // | any variables can be described in this part. To do this: use "$" sighn.                 |
	"$temp" 0.0                                      // | in this example are 4 variables: var01, var02, temp and distance. So name can be any.   |
	"$distance" 0.0                                  // |-> theLINK: https://developer.valvesoftware.com/wiki/List_Of_Material_Proxies------------| <---- theLINK
	
	"Proxies"                                        // Proxies - functional parameters for textures, see more: "theLINK"
	{
		"PlayerProximity"                        // the proxy that gives output like distance from player position to center of the texture
		{
			"scale" 1
			"resultVar" "$distance"          // resulting variable - need to be described in "var part"
		}

		Subtract                                 // mathematical operations. see more: "theLINK"
	        {
        	        srcVar1     "$distance"
	       	        srcVar2     "$var02"
		              resultVar   "$distance"
	        }
		Subtract
	        {
        	        srcVar1     "$var01"
	       	        srcVar2     "$var02"
		              resultVar   "$temp"
	        }
		"Divide"                                  // mathematical operations. see more: "theLINK"
		{
			"srcVar1" "$distance"
			"srcVar2" "$temp"
			"resultVar" "$alpha"
		}
	}
 }
 ```
