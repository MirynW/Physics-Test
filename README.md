# Physics-Test
A test of using Java collections as well as creating my own format for a physics engine.
This format will use an iterator to loop through objects in a ArrayList<Object> arr.
These objects will be of a type which is created by using polymorphism examples of this are Statics, Rigids, Functional.
---Statics---
  *Solid objects of infinite mass (collisions elastically bounce as a reversal of velocity [v*-1])
  *They can have functional properties included or have certain Rigid characteristics such as bounce, friction, interaction.
  *Statics will generally be used as walls for containing physics tests.
---Rigids---
  *Solid objects of selected mass (collisions occur elastically based on elastic collision formula [See calculating pi with collisions])
  *Properties include: Friction, Mass, Size, Gravity, [Pull, Push](magnetism), [Density, Pressure](cloth/movement based mesh deforming        properties), ect...
  *They can have functional properties, although these should be limited as the act of using collisions are already a performance hit,         most functionality will be based on collision.
  ---Functional---
  *Non-solid objects, can be visible with a draw method.
  *Event Handlers, Sounds, Canvas, Graphics, Any Iterable Object that needs to be called on a set time interval.
  
  ****************************************************************************************************************************************
  ----Handling Collisions----
    *Start with cube based collisions -> if vertex intersection occurs, apply elastic collision functions on both objects if the collision       is with another Rigid; Else if the collision is with a Static, apply elastic collision function as with infinite mass on the Static       side [o1.v[x][y] * -1]. Statics must not handle collisions with other statics this means that the type must be checked before             running the static collision method (Statics handle intersections with rigids, rigids only handle intersections with other rigids);       Else, the collision is with a Functional type and the methods based on such a collision must be dealt with, this could include some       type of draw method being called to overlap an object or some other functionality. Collisions of this type are only based on passing       through an area, raycasting may not be necessary.
----Handling Rigid Collisions----
  *raycasting/point intersection, apply impulse to point, AffineTransform for rotations
  *determine force based on elastic collision function as well as use the depth of collision to determine strength of impulse on point of    collision.
