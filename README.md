# Statistical-Transformations
This repository showcases transformations of statistical distributions. The focus is on using an existing famous RV distribution (eg. Poisson, Gamma, etc.) and creating a new RV with a distribution that is based on a mathematical transformation of the old one.


# 1 to 1 Distribution Prompt
This file is a Python script that is designed to be run in a Google Colaboratory or other similar JupyterLab-like workspace. It assumes that the user has installed the necessary libraries (listed in the import statements at the top) or that the user's environment has these libraries pre-installed.
The script will prompt the user for various specifications about an initial random variable called X. X will follow one of the more common famous probability distributions (eg. Poisson, Gamma, Normal, etc.) with parameters specified by the user. After the user is prompted about the specifics of X, they will be asked to define a new random variable Y in terms of X. The expression that defines Y must be written in standard Python syntax. For example, if Y = e^X, the user should enter "e", followed by a double asterisk, followed by "X" to define Y.
After the program receives information about X and Y's distribution parameters, it will plot a random sample of each distribution with n = 1000 individually, then plot them overlayed on top of each other. It will also include a smooth-line approximation of these distributions after the histogram visual.

# Precautions: 
- Keep in mind that the limits of this representation are bounded by the ability of a Python workspace to hold the value of whatever array entry is present in either X or Y, since these are represented using numpy arrays. When creating exponential transformations, this can cause an overflow error and the graph of Y will not appear. For example, if Y = 10^X, then the larger values of X can cause inf overflow when transformed into Y. 
- The array representation of X and Y is also relevant when trying to define an expression for Y in terms of X. For example, to represent the transformation Y = ln(X), it is best practice to use Y = np.log(X) instead of math.log(X), since math.log() expects a parameter of size 1, while np.log() is meant to accomodate entire arrays of values.
