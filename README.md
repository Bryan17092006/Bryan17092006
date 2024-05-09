Web VPython 3.2
scene.lights[0].visible=False
sun=sphere(color=vector(1,1,0),pos=vec(0,0,0),radius=5, shininess=0, emissive=True)
#Distância ao Sol Escala:  1cm = 10 milhões de km
earth=sphere(color=vector(0,0,1),pos=vec(15,0,0),radius=1, shininess=10, make_trail=True)
venus=sphere(color=vector(1,1,0.5),pos=vec(10.8,0,0),radius=0.9, shininess=10, make_trail=True)
mercury=sphere(color=vector(0.5,0.5,0.5),pos=vec(5.8,0,0),radius=0.4, shininess=10, make_trail=True)
mars=sphere(color=vector(1,0,0),pos=vec(23,0,0),radius=0.5, shininess=10, make_trail=True)
#Distância ao Sol Escala:  1cm = 15 milhões de km
jupiter=sphere(color=vector(1,1,1),pos=vec(51,0,0),radius=11.2, shininess=10, make_trail=True)
saturn=sphere(color=vector(1,1,1),pos=vec(95,0,0),radius=9.4, shininess=10, make_trail=True)
uranus=sphere(color=vector(0,0,1),pos=vec(191,0,0),radius=4, shininess=10, make_trail=True)
neptune=sphere(color=vector(0,0,1),pos=vec(300,0,0),radius=3.9, shininess=10, make_trail=True)
moon=sphere(color=vector(0.5,0.5,0.5),pos=vec(394,0,0),radius=0.5, shininess=10, make_trail=True)
lamp=local_light(pos=vector(0,0,0), color=vector(1,1,1) )

earth.make_trail=True
venus.make_trail=True
mercury.make_trail=True
mars.make_trail=True
jupiter.make_trail=True
saturn.make_trail=True
uranus.make_trail=True
neptune.make_trail=True
moon.make_trail=False
framerate=50

earthOmega=2*3.14159/365

moonAngle=0
moonOmega=2*3.14159/28

while True:
  rate(framerate)
  earth.rotate(angle=earthOmega, axis=vector(0,1,0), origin=vector(0,0,0))
  mercury.rotate(angle=earthOmega, axis=vector(0.2056,1,0), origin=vector(0,0,0))
  venus.rotate(angle=earthOmega, axis=vector(0,1,0), origin=vector(0,0,0))
  mars.rotate(angle=earthOmega, axis=vector(0,1,0), origin=vector(0,0,0))
  jupiter.rotate(angle=earthOmega, axis=vector(0,1,0), origin=vector(0,0,0))
  saturn.rotate(angle=earthOmega, axis=vector(0,1,0), origin=vector(0,0,0))
  uranus.rotate(angle=earthOmega, axis=vector(0,1,0), origin=vector(0,0,0))
  neptune.rotate(angle=earthOmega, axis=vector(0,1,0), origin=vector(0,0,0))

  moonAngle+=moonOmega

  moon.pos=earth.pos + vector(2,0,0)
  moon.rotate(angle=moonAngle, axis=vector(0,1,0), origin=earth.pos)
