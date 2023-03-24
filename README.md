# newton-dichotomy-secant-methods-for-unimodal-functions

Here are several optimization methods for unimodal functions satisfying the Lipschitz conditions
1. # Dichotomy
  A rather obvious dependence is observed: “If a continuous function at the limit values has the value of different indicators, then inside this interval it has a root (at least one, but maybe several)”. On this basis, a numerical finding of the approaching value of the root function is constructed. In general, this method is called dichotomy, i.e. dividing the segment into two parts. The general algorithm looks like this:

  Set start interval [X_{left}..X_{right}];
  Make sure that the function has a different sign at the ends;
  Repeat
  select point X inside the interval;
  compare the output function in the result of X with compare the function in one of the threads;
  if allowed, then move this end interval to point X,
  otherwise move to point X another end interval;
  until the desired accuracy is achieved.
  Variants of dichotomy methods have the primary right to choose points of view. Consider the dichotomy options: the half-division method and the chord method.

2. # Newton method
  This is an iterative numerical method for finding the root (zero) of a given function. The method was first proposed by the English physicist, mathematician and astronomer Isaac Newton (1643-1727), under whose name it gained its fame. The search for a solution is carried out by constructing successive approximations and is based on the principles of simple iteration. The method has quadratic convergence. In the case of solving optimization problems, it is assumed that the function f(x) is twice continuously differentiable. Finding the minimum of the function f(x) is done by finding a stationary point, i.e. point x^* satisfying the equation f'(x)=0, which is solved by Newton's method.


If x^k is the point obtained at the kth step, then the function f'(x) is approximated by its tangent equation:

y = f'($x^k$) + (x - $x^k$)f''($x^k$)

,
and the point x^{k+1} is chosen as the intersection of this line with the axis Ox, i.e.

$x^{k+1} = x^k - frac{f'(x^k)}{f''($x^k$)}$.

The inconvenience of this method is the need to calculate the first and second derivatives at each point. This means that it is applicable only when the function f(x) has a sufficiently simple analytical form so that the derivatives can be calculated explicitly by hand. Indeed, whenever a new problem is solved, it is necessary to choose two specific subroutines (functions) for calculating the derivatives f'(x) and f''(x), which does not allow one to construct general algorithms, i.e. applicable to any type of function.

When the starting point of iterations x_0 is sufficiently close to the desired minimum, the rate of convergence of Newton's method is generally quadratic. However, the global convergence of Newton's method, generally speaking, is not guaranteed.

A good way to ensure global convergence of this method is to combine it with another method to quickly get a good approximation of the desired optimum. Then several iterations of Newton's method, with this point as the starting point, are sufficient to obtain excellent accuracy.
3. # Secant method
