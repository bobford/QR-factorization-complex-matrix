# QR-factorization-complex-matrix
This is a QR factorization of a complex matrix using Java.

    This QR factorization of a complex matrix, at the class level, is modelled after an AI version.
    ChatGPT was asked for this but produced a QR factorization for a real matrix instead,
    illustrating the important concept that AI doesn't know what it doesn't know.

    The actual Java code is a conversion of the assembly code from an implementation on an Arm processor
    originally written by Bob Ford.
		
    The computation of the Householder vector follows the definition given in:
            http://arith.cs.ucla.edu/publications/House-Asil06.pdf

	 	This implementation seems particularly inefficient as it runs about 30 times slower than the
		assembly language version on an Armv8 processor. This may be due to the use of the Complex class.
		Specifically, on a 192x120 matrix, the assembly version takes 3.5 milliseconds while this Java version
		takes about 100 milliseconds, both on an older Android phone. As a comparison, similar code for a
		real matrix only differs by a factor of 2.5-3.

		Calling sequence:
		    Complex[][] z;                      // input matrix, m x n
		    QRfactorizationComplex qr = new QRfactorizationComplex(z);
		    Complex[][] r = qr.getR();          // output matrix will be n x n

