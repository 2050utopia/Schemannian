Expressions
-----------

Following the Lisp family rule, "Schemennian" uses prefix notations. Every value in a list can be either a number or a symbol. The current supported operations (which are noted as symbols) includes ``'=``, ``'+``, ``'*``, ``'**`` (exponential function), ``'log``, ``'sin``, and ``'cos``. To support differential equation related topics, there are two special tags includes ``'function`` and ``'deriv``.

For example, Newton's law of universal gravitation :math:`F = (G m1 m2)/r^2` can be expressed as

.. code:: scheme

    '(= F (* G m1 m2 (** r -2)))

One of the trigonometric identities :math:`sin(x+y) = sin(x) cos(y) + cos(x) sin(y)` can be expressed as

.. code:: scheme

    '(= (sin (+ x y)) (+ (* (sin x) (cos y)) (* (cos x) (sin y))))

And the Lagrangian of a simple pendulum can be expressed as

.. code:: scheme

    '(+ (* -1 g m1 (+ pivotY1 (* -1 l1 (cos (function theta1 t)))))
        (* 0.5 m1 (** l1 2) (** (deriv (function theta1 t) t) 2)))