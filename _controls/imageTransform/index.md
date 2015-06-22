---
name: Image Transform
type: imageTransform
group: images
description: A virtual control that modifies images.
value: "string: the path to the image"
available: 3
generics: false
properties:

  - title: ID
    key: id
    type: string
    required: yes
    description: The ID for this control. This ID must be unique within this stack. The ID is used to refer to the control's property. IDs should be alpha-numeric (dashes and underscores are allowed), but should not contain special characters.





  - title: Scale Mode
    key: imageScaleMode
    type: Number
    default: 0 (Scale to Fit)
    markdown: yes


  - title: Scale
    key: imageScale
    type: Number
    default: 100
    description: When the Scale Mode property is set to 1 (Scale to Fill), you may either define a scale percent, width/height maximums, or both. If both or set, then the Max Width and Max Height properties take precidence.





  - title: Max Width
    key: imageMaxWidth
    type: Number
    description: The Max Width will add a maxium width contraint to the image. This constraint is only applied if the value is non-zero and the Max Width Enable property is enabled. This contraint will take precedence over other properties (such as the Scale property.)

  - title: Max Height
    key: imageMaxHeight
    type: Number
    description: The Max Height will add a maxium height contraint to the image. This constraint is only applied if the value is non-zero and the Max Height Enable property is enabled. This contraint will take precedence over other properties (such as the Scale property.)



  - title: Max Width Enable
    key: imageMaxWidthEnable
    type: Boolean
    default: Disabled
    description: Enabling the Max Width will add the maxium width contraint to the image specified in the Max Width property.  This contraint will take precedence over other properties (such as the Scale property.)

  - title: Max Height Enable
    key: imageMaxHeightEnable
    type: Boolean
    default: Disabled
    description: Enabling the Max Height will add the maxium height contraint to the image specified in the Max Height property.  This contraint will take precedence over other properties (such as the Scale property.)




  - title: Rotation
    key: imageRotation
    type: number
    default: 0
    description: The amount of rotation (in degrees) to rotate the image. The rotation is not done in CSS. The image is rotated and rerendered. Note that image rotations of just a few degrees, especially of smaller images, can lead to artifacts.





  - title: Border Width
    key: imageBorderWidth
    type: number
    description: The width of the border. Borders are rendered into the image (not CSS).

  - title: Border Color
    key: imageBorderColor
    type: "string: HTML RGB Hex string"
    description: The color of the border. Borders are rendered into the image (not CSS).





  - title: Shadow Color
    key: imageShadowColor
    type: "string: HTML RGB Hex string"
    description: The color of the shadow.  Light colors can be used for a glow effect. Shadows are rendered into the image (not CSS).

  - title: Shadow Opacity
    key: imageShadowColor
    type: "string: HTML RGB Hex string"
    description: The opacity of the shadow. Opacity of `0` is fully transparent and will disable the shadow. Shadows are rendered into the image (not CSS).

  - title: Shadow Blur
    key: imageShadowColor
    type: "string: HTML RGB Hex string"
    description: The amount of blur added to the shadow.  Shadows are rendered into the image (not CSS).

  - title: Shadow Offset X
    key: imageShadowColor
    type: "string: HTML RGB Hex string"
    description: The offset of the shadow in the horizontal direction.  Shadows are rendered into the image (not CSS).

  - title: Shadow Offset Y
    key: imageShadowColor
    type: "string: HTML RGB Hex string"
    default: Black
    required: yes
    description: The offset of the shadow in the vertical driction. Shadows are rendered into the image (not CSS).


---

A virtual control to transform any image. 

Image transforms give developers access to all the image editing functionality within Stacks, but fully controlled by the developer. You can scale, rotate, and apply borders and shadows. 

Image transforms can take an image well or an `%image%` stack as input. Many transforms can be applied to the same image (e.g., to output several different sizes of an image). 

Image transforms are especially useful for creating thumbnail images that must be small and cropped to a specific dimension.