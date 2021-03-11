# Normal_Modes
My goal was to solve a system of identical masses connected by springs of equal spring constant, held with springs between fixed walls.


I researched an efficient way to solve the equations of motion.  One option was to find the eigenvalues and eigenvectors of Newton's equation (put into nicely symmetric forms when all masses and spring constants are equal).  The method here would be to assume a complex exponential form: x(t) = A_n*exp(iwt), then find the non-trivial solutions for A_n.  This, however, was not the easiest way of solving the system of equations. 

I found another method for solving the system of equations.  First, a recursive relationship was found for A_n in terms of A_(n-1) and A_(n+1). By claiming that the forms of the constants A_n = B*cos(n*T) + C*sin(n*T), I was able to derive equations for A_n and w, the amplitudes of each mass (indexed n) and the frequency of the m-mode.  N, total number of masses, and m, the mode we wish to investigate, were specified at the top of the main() function.

The form of the .data file allowed me to use GNUplot to make a gif.  The form of the gif has all N masses spaced out by 1 along the x axis and shows their relative motion in the y-direction.  This is not strictly how the masses move in real life (as we only have one dimension in real life) but it provides a nice visualisation of the normal mode.  The formulae hold for any N and m < N.

During the process, to help me understand what was going on, I plotted the x(t) motion as a function of time.  This is why I wrote to magnitude.data and frequency.data in my main() function.

This assessment was the first instance of using vectors.  These dynamics forms of memory are incredibly useful.  If I were using rigid-memory arrays, the programme would not be able to handle changing the value of N, total number of masses, very easily without a lot of fiddling.  This was an excellent introduction to vectors.  I practised using logic loops to iterate through vectors and experimented with different ways of extracting elements from a vector.  I noticed that it was not possible to multiply vectors (or perform calculations with same-sized vectors) as it is on other programmes such as Mathematica.  I was able to overcome this by simply creating a for-loop to iterate through and extract float-type data instead of vector<float>-type data to write to my .data file.

I wanted to learn how to make an animation on GNUplot.  With some help from a friend (as well as the internet!), I wrote a .p script to create a .gif file.  I experimented with the parameters of the gif file and the frame rate.  I am confident I would be able to create some cool animations in the future because of the experience I gained during this assessment in GNUplot.
