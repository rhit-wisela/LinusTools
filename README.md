# LinusTools
some maple functions I wrote that might be useful. will be updated periodically until May 2026

# Installation Directions
1. Download LinusTools.mw
2. Run Maple as administrator (required for saving the package to the proper directory)
3. Execute the entire worksheet

# LinusTools Documentation
  Changes made on load:
  - load the inttrans package
  - rename √(-1) to 'j'

  Functions:
    angle(z)
      returns the complex angle of z.
      example: angle(j) = π/2
    avg(x::seq(anything))
      returns the average of any number of inputs.
      example: avg(5, 10, 15) = 10
    cnv(x)
      converts x into scientific notation. must be a real number.
      example: cnv(0.01) = [1,-2]
    cnv2(x)
      converts x into engineering units. must be a real number.
      example: cnv(0.01) = [10, -3]
    conv(x,y,t)
      performs a convolution integral on x and y with respect to t.
      example: conv(rect(t),rect(t),t) = tri2(t)
    conv2(x,y,t)
      performs a convolution integral on x and y with respect to t. does not work very well. do not use.
    db2u(x)
      converts x from decibels to linear units.
      example: db2u(60) = 1000
    delta(x)
      rename of the Dirac function.
    delta2(t)
      returns 1 if t = 0 and 0 otherwise.
    eangle(z)
      returns evalf(angle(z)).
    ep2r(r,theta)
      returns evalf(p2r(r,theta)).
    er2p(z)
      returns evalf(r2p(z).
    init
      function run on package load. likely does nothing.
    p2r(r,theta)
      converts the given polar number to rectangular
      example: p2r(1,π/2) = j
    par(x::seq(anything))
      caculates the reciprocal of the sum of the reciprocals of the inputs. commonly used for equivalent resistance of resistors in parallel.
      example: parr(10, 10, 10, 10) = 2.5
    r2p(z)
      converts the rectangular number to polar
      example: r2p(j) = 1,π/2
    rect(t)
      rectangular distribution. returns 1 if -0.5<=t<0.5 and 0 otherise.
    sinc(t)
      returns 1 if t=0 and sin(πt)/πt otherwise
    stdev(x::seq(anything))
      returns the standard deviation of any number of inputs.
      example: stdev(5,10,15) = 4.082
    tri(t)
      triangular wave with amplitude = 1, period = 1
    tri2(t)
      triangular pulse distribution with amplitude = 1, width = 2
    u(t)
      rename of the Heaviside function
    u2(t)
      returns 1 if t>=0 and 0 otherwise
    u2db(x)
      converts x from linear units to decibels
      example: u2db(1000) = 60
    zc(w,C)
      returns the impedance of a _C_ farad capacitor at _w_ rad/sec
      example: zc(10,10) = -j/100
    zl(w,L)
      returns the impedance of an _L_ henry inductor at _w_ rad/sec
      example: zl(10,10) = j*100

# DegreeMode Documentation
  Automatically converts all affected functions to degree mode on package load.
  Call rad() to convert to radians and call deg() to convert to degrees.

  Affected functions:
  - angle
  - arccos
  - arccot
  - arccsc
  - arcsec
  - arctan
  - cos
  - cot
  - csc
  - exp
  - p2r
  - r2p
  - sec
  - sin
  - tan

  Examples:
  - angle(j) = 90
  - sin(90) = 1
  - arctan(1) = 45
  - exp(180*j) = -1
  - r2p(j) = 1,90
