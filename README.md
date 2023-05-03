Download Link: https://assignmentchef.com/product/solved-cs-754-assignment-2
<br>
Advanced Image Processing







<ol>

 <li>Refer to a copy of the paper ‘The restricted isometry property and its implications for compressed sensing’ in the homework folder. Your task is to open the paper and answer the question posed in each and every green-colored highlight. The task is the complete proof of Theorem 3 done in class. [24 points = 1.5 points for each of the 16 questions]</li>

 <li>Your task here is to implement the ISTA algorithm for the following three cases:</li>

</ol>

<ul>

 <li>Consider the image from the homework folder. Add iid Gaussian noise of mean 0 and variance 4 (on a [0,255] scale) to it, using the ‘randn’ function in MATLAB. Thus y = x + η where η .V(0, 4). You should obtain x from y using the fact that patches from x have a sparse or near-sparse representation in the 2D-DCT basis.</li>

 <li>Divide the image shared in the homework folder into patches of size 8 x Let x<strong>i </strong>be the vectorized version of the i<sup>th</sup> patch. Consider the measurement y<strong>i </strong>= 4x<strong>i </strong>where 4 is a 32 x 64 matrix with entries drawn iid from .V(0, 1). Note that x<strong>i </strong>has a near-sparse representation in the 2D-DCT basis U which is computed in MATLAB as ‘kron(dctmtx(8)’,dctmtx(8)’)’. In other words, x<strong>i </strong>= UO<strong>i </strong>where O<strong>i </strong>is a near-sparse vector. Your job is to reconstruct each x<strong>i </strong>given y<strong>i </strong>and 4 using ISTA. Then you should reconstruct the image by averaging the overlapping patches. You should choose the a parameter in the ISTA algorithm judiciously. Choose A = 1 (for a [0,255] image). Display the reconstructed image in your report. State the RMSE given as IX(:) – <sup>ˆ</sup>X(:)I2/IX(:)I2 where X<sup>ˆ</sup> is the reconstructed image and X is the true image. [16 points]</li>

 <li>Repeat the reconstruction task using the Haar wavelet basis via the MATLAB command ‘dwt2’ with the option ‘db1’. Display the reconstructed image in your report. State the RMSE. Use MATLAB function handles carefully. [8 points]</li>

 <li>Consider a 100-dimensional sparse signal x containing 10 non-zero elements. Let this signal be convolved with a kernel h = [1,2,3,4,3,2, 1]/16 followed by addition of Gaussian noise of standard deviation equal to 5% of the magnitude of x to yield signal y, i.e. y = h * x + η. Your job is to reconstruct x from y given h. Be careful of how you create the matrix A in the ISTA algorithm. [8 points]</li>

</ul>

<ol start="3">

 <li>One of the questions that came up in a live session was the notion of an oracle. Consider compressive measurements y = 4x + η of a purely sparse signal x, where IηI2 &lt; €. When we studied Theorem 3 in class, I had made a statement that the solution provided by the basis pursuit problem for a purely sparse</li>

</ol>




signal comes very close (i.e. has an error that is only a constant factor worse than) an oracular solution. An oracular solution is defined as the solution that we could obtain if we knew in advance the indices (set S) the non-zero elements of the signal x. This homework problem is to understand my statement better. For this, do as follows. In the following, we will assume that the inverse of Φ<strong>T S</strong>Φ<strong>S </strong>exists, where Φ<strong>S </strong>is a submatrix of Φ with columns belonging to indices in S.

<ul>

 <li>Express the oracular solution x<sup>˜</sup> using a pseudo-inverse of the sub-matrix Φ<strong>S</strong>. [5 points]</li>

 <li>Now, show that l<sup>˜</sup>x −xl2 = IΦ<strong> S</strong>ηI2 ≤ ~Φ<strong><sub> S</sub></strong><sub>~</sub><sub>2</sub><sub>I</sub><sub>η</sub><sub>I</sub><sub>2</sub><sub>.</sub> Here Φ<strong><sub> S</sub></strong> 4 (Φ<strong><sup>T</sup></strong><strong> S</strong>Φ<strong>S</strong>)−1Φ<strong>T <sub>S</sub></strong> is standard notation for the pseudo-inverse of Φ<strong>S</strong>. The largest singular value of matrix X is denoted as X 12. [3 points]</li>

</ul>

1                            <u>1</u>

<ul>

 <li>Argue that the largest singular value of Φ<strong><sub> S</sub></strong> lies between <u>√</u><u>1</u> + δ2k and <u>√</u><u>1</u> − δ2k where k = |S| and δ2k</li>

</ul>

is the RIC of Φ of order 2k. [4 points]

<u>€</u>

<ul>

 <li>This yields __________________ . Argue that the solution given by Theorem 3 is only a</li>

</ul>

<u>√</u>1 + δ2k ≤ Ix − <sup>˜</sup>x~2 ≤      €

<u>√</u>1 − δ2k

constant factor worse than this solution. [3 points]

<ol start="4">

 <li>If s &lt; t where s and t are positive integers, prove that δ<sub>s</sub> ≤ δt where δ<sub>s</sub>, δt stand for the restricted isometry constant (of any sensing matrix) of order s and t [8 points]</li>

 <li>Here is our obligatory Google search question :-). Your task is to find out any one paper from within the last 5 years, apart from our Tapestry pooling paper from <a href="https://arxiv.org/abs/2005.07895,">https://arxiv.org/abs/2005.07895</a><u>,</u> which applied compressed sensing for group testing (not necessarily for COVID-19 pooling, but other applications or even theoretical papers are fine). You may look for references in the Tapestry pooling paper as well. Unpublished papers from arxiv are allowed as well. Answer the following questions: (1) Mention the title of the paper and a link to it. (2) Mention the key objective function being minimized in the paper with the meaning of all symbols clearly explained. (3) Enlist any three differences between the proposed approach and the Tapestry pooling approach. [8+7=15 points]</li>

 <li>Consider the problem P1: min<strong><sub>x</sub></strong>IxI1 t. y − ΦxI2 ≤ €. Also consider the LASSO problem which seeks to minimize the cost function J(x) = Iy − ΦxI2 <sub>2</sub> + AIxI1. If x is a minimizer of J(.) for some value of A &gt; 0, then show that there exists some value of € for which x is also the minimizer of the problem P1. [6 points] (Hint: Consider €’ = Iy − ΦxI2. Now use the fact that x is a minimizer of J(.) to show that it is also a minimizer of P1 subject to an appropriate constraint involving €’.)</li>

</ol>