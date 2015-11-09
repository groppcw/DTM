# DTM
Dynamic Topic Modeling, as reimplemented to abstract matrix operations from algorithmic concerns.

This code is broken into two overall sections, linked together by Main; the first is the algorithm section, and the second the matrix representation. The algorithm section refers to matrix and vector objects only in general terms, receiving them from a factory class and generally not concerning itself with their particulars. The matrix section contains the strategies used for actually performing this arithmetic, and is wholly disconnected from the algorithmic particulars. All that binds them together is the initialization by Main, which chooses a strategy based on input parameters and then allows the two pieces to be unaware of each other.

While this means some very small scale optimizations may no longer be possible, this facilitates extensability in both the algorithm and the matrix representations. Using a new library for matrices, altering the structure of parallelization efforts, or implementing a new algorithm are all entirely unconnected tasks in this setup, and can be done independently and without concern for side effects as long as the software module's internal contracts are upheld. The goal is to create a framework not just for Dynamic Topic Modeling, but for any sort of matrix based algorithm.
