## Examples of Failed Tests

```bash
▶ pytest sklearn/linear_model/_glm/tests/test_glm.py::test_glm_max_iter_argument
=================================================== test session starts ====================================================
platform darwin -- Python 3.9.7, pytest-6.2.5, py-1.10.0, pluggy-1.0.0
rootdir: /Users/reshamashaikh/software-build/scikit-learn, configfile: setup.cfg
plugins: cov-3.0.0
collected 5 items                                                                                                          

sklearn/linear_model/_glm/tests/test_glm.py FFFFF                                                                    [100%]

========================================================= FAILURES =========================================================
_________________________________________ test_glm_max_iter_argument[not a number] _________________________________________

max_iter = 'not a number'

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)

sklearn/linear_model/_glm/tests/test_glm.py:150: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
sklearn/linear_model/_glm/glm.py:319: in fit
    opt_res = scipy.optimize.minimize(
../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/_minimize.py:623: in minimize
    return _minimize_lbfgsb(fun, x0, args, jac, bounds,
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fun = <scipy.optimize.optimize.MemoizeJac object at 0x13997ae80>, x0 = array([1.5, 0. ])
args = (array([[1.],
       [2.]]), array([1, 2]), array([0.5, 0.5]), 1.0, <sklearn._loss.glm_distribution.NormalDistribution object at 0x13997af40>, <sklearn.linear_model._glm.link.IdentityLink object at 0x13997afd0>)
jac = <bound method MemoizeJac.derivative of <scipy.optimize.optimize.MemoizeJac object at 0x13997ae80>>
bounds = [(None, None), (None, None)], disp = None, maxcor = 10, ftol = 2.220446049250313e-13, gtol = 0.0001, eps = 1e-08
maxfun = 15000, maxiter = 'not a number', iprint = -1, callback = None, maxls = 20, finite_diff_rel_step = None
unknown_options = {}, m = 10, pgtol = 0.0001, factr = 1000.0, n = 2, new_bounds = (array([-inf, -inf]), array([inf, inf]))
sf = <scipy.optimize._differentiable_functions.ScalarFunction object at 0x13997ad00>
func_and_grad = <bound method ScalarFunction.fun_and_grad of <scipy.optimize._differentiable_functions.ScalarFunction object at 0x13997ad00>>

    def _minimize_lbfgsb(fun, x0, args=(), jac=None, bounds=None,
                         disp=None, maxcor=10, ftol=2.2204460492503131e-09,
                         gtol=1e-5, eps=1e-8, maxfun=15000, maxiter=15000,
                         iprint=-1, callback=None, maxls=20,
                         finite_diff_rel_step=None, **unknown_options):
        """
        Minimize a scalar function of one or more variables using the L-BFGS-B
        algorithm.
    
        Options
        -------
        disp : None or int
            If `disp is None` (the default), then the supplied version of `iprint`
            is used. If `disp is not None`, then it overrides the supplied version
            of `iprint` with the behaviour you outlined.
        maxcor : int
            The maximum number of variable metric corrections used to
            define the limited memory matrix. (The limited memory BFGS
            method does not store the full hessian but uses this many terms
            in an approximation to it.)
        ftol : float
            The iteration stops when ``(f^k -
            f^{k+1})/max{|f^k|,|f^{k+1}|,1} <= ftol``.
        gtol : float
            The iteration will stop when ``max{|proj g_i | i = 1, ..., n}
            <= gtol`` where ``pg_i`` is the i-th component of the
            projected gradient.
        eps : float or ndarray
            If `jac is None` the absolute step size used for numerical
            approximation of the jacobian via forward differences.
        maxfun : int
            Maximum number of function evaluations.
        maxiter : int
            Maximum number of iterations.
        iprint : int, optional
            Controls the frequency of output. ``iprint < 0`` means no output;
            ``iprint = 0``    print only one line at the last iteration;
            ``0 < iprint < 99`` print also f and ``|proj g|`` every iprint iterations;
            ``iprint = 99``   print details of every iteration except n-vectors;
            ``iprint = 100``  print also the changes of active set and final x;
            ``iprint > 100``  print details of every iteration including x and g.
        callback : callable, optional
            Called after each iteration, as ``callback(xk)``, where ``xk`` is the
            current parameter vector.
        maxls : int, optional
            Maximum number of line search steps (per iteration). Default is 20.
        finite_diff_rel_step : None or array_like, optional
            If `jac in ['2-point', '3-point', 'cs']` the relative step size to
            use for numerical approximation of the jacobian. The absolute step
            size is computed as ``h = rel_step * sign(x0) * max(1, abs(x0))``,
            possibly adjusted to fit into the bounds. For ``method='3-point'``
            the sign of `h` is ignored. If None (default) then step is selected
            automatically.
    
        Notes
        -----
        The option `ftol` is exposed via the `scipy.optimize.minimize` interface,
        but calling `scipy.optimize.fmin_l_bfgs_b` directly exposes `factr`. The
        relationship between the two is ``ftol = factr * numpy.finfo(float).eps``.
        I.e., `factr` multiplies the default machine floating-point precision to
        arrive at `ftol`.
    
        """
        _check_unknown_options(unknown_options)
        m = maxcor
        pgtol = gtol
        factr = ftol / np.finfo(float).eps
    
        x0 = asarray(x0).ravel()
        n, = x0.shape
    
        if bounds is None:
            bounds = [(None, None)] * n
        if len(bounds) != n:
            raise ValueError('length of x0 != length of bounds')
    
        # unbounded variables must use None, not +-inf, for optimizer to work properly
        bounds = [(None if l == -np.inf else l, None if u == np.inf else u) for l, u in bounds]
        # LBFGSB is sent 'old-style' bounds, 'new-style' bounds are required by
        # approx_derivative and ScalarFunction
        new_bounds = old_bound_to_new(bounds)
    
        # check bounds
        if (new_bounds[0] > new_bounds[1]).any():
            raise ValueError("LBFGSB - one of the lower bounds is greater than an upper bound.")
    
        # initial vector must lie within the bounds. Otherwise ScalarFunction and
        # approx_derivative will cause problems
        x0 = np.clip(x0, new_bounds[0], new_bounds[1])
    
        if disp is not None:
            if disp == 0:
                iprint = -1
            else:
                iprint = disp
    
        sf = _prepare_scalar_function(fun, x0, jac=jac, args=args, epsilon=eps,
                                      bounds=new_bounds,
                                      finite_diff_rel_step=finite_diff_rel_step)
    
        func_and_grad = sf.fun_and_grad
    
        fortran_int = _lbfgsb.types.intvar.dtype
    
        nbd = zeros(n, fortran_int)
        low_bnd = zeros(n, float64)
        upper_bnd = zeros(n, float64)
        bounds_map = {(None, None): 0,
                      (1, None): 1,
                      (1, 1): 2,
                      (None, 1): 3}
        for i in range(0, n):
            l, u = bounds[i]
            if l is not None:
                low_bnd[i] = l
                l = 1
            if u is not None:
                upper_bnd[i] = u
                u = 1
            nbd[i] = bounds_map[l, u]
    
        if not maxls > 0:
            raise ValueError('maxls must be positive.')
    
        x = array(x0, float64)
        f = array(0.0, float64)
        g = zeros((n,), float64)
        wa = zeros(2*m*n + 5*n + 11*m*m + 8*m, float64)
        iwa = zeros(3*n, fortran_int)
        task = zeros(1, 'S60')
        csave = zeros(1, 'S60')
        lsave = zeros(4, fortran_int)
        isave = zeros(44, fortran_int)
        dsave = zeros(29, float64)
    
        task[:] = 'START'
    
        n_iterations = 0
    
        while 1:
            # x, f, g, wa, iwa, task, csave, lsave, isave, dsave = \
            _lbfgsb.setulb(m, x, low_bnd, upper_bnd, nbd, f, g, factr,
                           pgtol, wa, iwa, task, iprint, csave, lsave,
                           isave, dsave, maxls)
            task_str = task.tobytes()
            if task_str.startswith(b'FG'):
                # The minimization routine wants f and g at the current x.
                # Note that interruptions due to maxfun are postponed
                # until the completion of the current minimization iteration.
                # Overwrite f and g:
                f, g = func_and_grad(x)
            elif task_str.startswith(b'NEW_X'):
                # new iteration
                n_iterations += 1
                if callback is not None:
                    callback(np.copy(x))
    
>               if n_iterations >= maxiter:
E               TypeError: '>=' not supported between instances of 'int' and 'str'

../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/lbfgsb.py:367: TypeError
______________________________________________ test_glm_max_iter_argument[0] _______________________________________________

max_iter = 0

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>

sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
______________________________________________ test_glm_max_iter_argument[-1] ______________________________________________

max_iter = -1

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>

sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
_____________________________________________ test_glm_max_iter_argument[5.5] ______________________________________________

max_iter = 5.5

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>

sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
__________________________________________ test_glm_max_iter_argument[max_iter4] ___________________________________________

max_iter = [1]

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)

sklearn/linear_model/_glm/tests/test_glm.py:150: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
sklearn/linear_model/_glm/glm.py:319: in fit
    opt_res = scipy.optimize.minimize(
../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/_minimize.py:623: in minimize
    return _minimize_lbfgsb(fun, x0, args, jac, bounds,
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fun = <scipy.optimize.optimize.MemoizeJac object at 0x1399dfb50>, x0 = array([1.5, 0. ])
args = (array([[1.],
       [2.]]), array([1, 2]), array([0.5, 0.5]), 1.0, <sklearn._loss.glm_distribution.NormalDistribution object at 0x1399df6d0>, <sklearn.linear_model._glm.link.IdentityLink object at 0x1399dfe50>)
jac = <bound method MemoizeJac.derivative of <scipy.optimize.optimize.MemoizeJac object at 0x1399dfb50>>
bounds = [(None, None), (None, None)], disp = None, maxcor = 10, ftol = 2.220446049250313e-13, gtol = 0.0001, eps = 1e-08
maxfun = 15000, maxiter = [1], iprint = -1, callback = None, maxls = 20, finite_diff_rel_step = None, unknown_options = {}
m = 10, pgtol = 0.0001, factr = 1000.0, n = 2, new_bounds = (array([-inf, -inf]), array([inf, inf]))
sf = <scipy.optimize._differentiable_functions.ScalarFunction object at 0x1399dfe20>
func_and_grad = <bound method ScalarFunction.fun_and_grad of <scipy.optimize._differentiable_functions.ScalarFunction object at 0x1399dfe20>>

    def _minimize_lbfgsb(fun, x0, args=(), jac=None, bounds=None,
                         disp=None, maxcor=10, ftol=2.2204460492503131e-09,
                         gtol=1e-5, eps=1e-8, maxfun=15000, maxiter=15000,
                         iprint=-1, callback=None, maxls=20,
                         finite_diff_rel_step=None, **unknown_options):
        """
        Minimize a scalar function of one or more variables using the L-BFGS-B
        algorithm.
    
        Options
        -------
        disp : None or int
            If `disp is None` (the default), then the supplied version of `iprint`
            is used. If `disp is not None`, then it overrides the supplied version
            of `iprint` with the behaviour you outlined.
        maxcor : int
            The maximum number of variable metric corrections used to
            define the limited memory matrix. (The limited memory BFGS
            method does not store the full hessian but uses this many terms
            in an approximation to it.)
        ftol : float
            The iteration stops when ``(f^k -
            f^{k+1})/max{|f^k|,|f^{k+1}|,1} <= ftol``.
        gtol : float
            The iteration will stop when ``max{|proj g_i | i = 1, ..., n}
            <= gtol`` where ``pg_i`` is the i-th component of the
            projected gradient.
        eps : float or ndarray
            If `jac is None` the absolute step size used for numerical
            approximation of the jacobian via forward differences.
        maxfun : int
            Maximum number of function evaluations.
        maxiter : int
            Maximum number of iterations.
        iprint : int, optional
            Controls the frequency of output. ``iprint < 0`` means no output;
            ``iprint = 0``    print only one line at the last iteration;
            ``0 < iprint < 99`` print also f and ``|proj g|`` every iprint iterations;
            ``iprint = 99``   print details of every iteration except n-vectors;
            ``iprint = 100``  print also the changes of active set and final x;
            ``iprint > 100``  print details of every iteration including x and g.
        callback : callable, optional
            Called after each iteration, as ``callback(xk)``, where ``xk`` is the
            current parameter vector.
        maxls : int, optional
            Maximum number of line search steps (per iteration). Default is 20.
        finite_diff_rel_step : None or array_like, optional
            If `jac in ['2-point', '3-point', 'cs']` the relative step size to
            use for numerical approximation of the jacobian. The absolute step
            size is computed as ``h = rel_step * sign(x0) * max(1, abs(x0))``,
            possibly adjusted to fit into the bounds. For ``method='3-point'``
            the sign of `h` is ignored. If None (default) then step is selected
            automatically.
    
        Notes
        -----
        The option `ftol` is exposed via the `scipy.optimize.minimize` interface,
        but calling `scipy.optimize.fmin_l_bfgs_b` directly exposes `factr`. The
        relationship between the two is ``ftol = factr * numpy.finfo(float).eps``.
        I.e., `factr` multiplies the default machine floating-point precision to
        arrive at `ftol`.
    
        """
        _check_unknown_options(unknown_options)
        m = maxcor
        pgtol = gtol
        factr = ftol / np.finfo(float).eps
    
        x0 = asarray(x0).ravel()
        n, = x0.shape
    
        if bounds is None:
            bounds = [(None, None)] * n
        if len(bounds) != n:
            raise ValueError('length of x0 != length of bounds')
    
        # unbounded variables must use None, not +-inf, for optimizer to work properly
        bounds = [(None if l == -np.inf else l, None if u == np.inf else u) for l, u in bounds]
        # LBFGSB is sent 'old-style' bounds, 'new-style' bounds are required by
        # approx_derivative and ScalarFunction
        new_bounds = old_bound_to_new(bounds)
    
        # check bounds
        if (new_bounds[0] > new_bounds[1]).any():
            raise ValueError("LBFGSB - one of the lower bounds is greater than an upper bound.")
    
        # initial vector must lie within the bounds. Otherwise ScalarFunction and
        # approx_derivative will cause problems
        x0 = np.clip(x0, new_bounds[0], new_bounds[1])
    
        if disp is not None:
            if disp == 0:
                iprint = -1
            else:
                iprint = disp
    
        sf = _prepare_scalar_function(fun, x0, jac=jac, args=args, epsilon=eps,
                                      bounds=new_bounds,
                                      finite_diff_rel_step=finite_diff_rel_step)
    
        func_and_grad = sf.fun_and_grad
    
        fortran_int = _lbfgsb.types.intvar.dtype
    
        nbd = zeros(n, fortran_int)
        low_bnd = zeros(n, float64)
        upper_bnd = zeros(n, float64)
        bounds_map = {(None, None): 0,
                      (1, None): 1,
                      (1, 1): 2,
                      (None, 1): 3}
        for i in range(0, n):
            l, u = bounds[i]
            if l is not None:
                low_bnd[i] = l
                l = 1
            if u is not None:
                upper_bnd[i] = u
                u = 1
            nbd[i] = bounds_map[l, u]
    
        if not maxls > 0:
            raise ValueError('maxls must be positive.')
    
        x = array(x0, float64)
        f = array(0.0, float64)
        g = zeros((n,), float64)
        wa = zeros(2*m*n + 5*n + 11*m*m + 8*m, float64)
        iwa = zeros(3*n, fortran_int)
        task = zeros(1, 'S60')
        csave = zeros(1, 'S60')
        lsave = zeros(4, fortran_int)
        isave = zeros(44, fortran_int)
        dsave = zeros(29, float64)
    
        task[:] = 'START'
    
        n_iterations = 0
    
        while 1:
            # x, f, g, wa, iwa, task, csave, lsave, isave, dsave = \
            _lbfgsb.setulb(m, x, low_bnd, upper_bnd, nbd, f, g, factr,
                           pgtol, wa, iwa, task, iprint, csave, lsave,
                           isave, dsave, maxls)
            task_str = task.tobytes()
            if task_str.startswith(b'FG'):
                # The minimization routine wants f and g at the current x.
                # Note that interruptions due to maxfun are postponed
                # until the completion of the current minimization iteration.
                # Overwrite f and g:
                f, g = func_and_grad(x)
            elif task_str.startswith(b'NEW_X'):
                # new iteration
                n_iterations += 1
                if callback is not None:
                    callback(np.copy(x))
    
>               if n_iterations >= maxiter:
E               TypeError: '>=' not supported between instances of 'int' and 'list'

../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/lbfgsb.py:367: TypeError
============================================== 5 failed, 2 warnings in 0.56s ===============================================
(sklearndev) 
~/software-build/scikit-learn  xscalar_glm ✗                                                                        1d ⚑  ⍉
▶ pytest sklearn/linear_model/_glm/tests/test_glm.py::test_glm_max_iter_argument
=================================================== test session starts ====================================================
platform darwin -- Python 3.9.7, pytest-6.2.5, py-1.10.0, pluggy-1.0.0
rootdir: /Users/reshamashaikh/software-build/scikit-learn, configfile: setup.cfg
plugins: cov-3.0.0
collected 5 items                                                                                                          

sklearn/linear_model/_glm/tests/test_glm.py FFFFF                                                                    [100%]

========================================================= FAILURES =========================================================
_________________________________________ test_glm_max_iter_argument[not a number] _________________________________________

max_iter = 'not a number'

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)

sklearn/linear_model/_glm/tests/test_glm.py:150: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
sklearn/linear_model/_glm/glm.py:319: in fit
    opt_res = scipy.optimize.minimize(
../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/_minimize.py:623: in minimize
    return _minimize_lbfgsb(fun, x0, args, jac, bounds,
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fun = <scipy.optimize.optimize.MemoizeJac object at 0x13b43ae80>, x0 = array([1.5, 0. ])
args = (array([[1.],
       [2.]]), array([1, 2]), array([0.5, 0.5]), 1.0, <sklearn._loss.glm_distribution.NormalDistribution object at 0x13b43afa0>, <sklearn.linear_model._glm.link.IdentityLink object at 0x13b43af70>)
jac = <bound method MemoizeJac.derivative of <scipy.optimize.optimize.MemoizeJac object at 0x13b43ae80>>
bounds = [(None, None), (None, None)], disp = None, maxcor = 10, ftol = 2.220446049250313e-13, gtol = 0.0001, eps = 1e-08
maxfun = 15000, maxiter = 'not a number', iprint = -1, callback = None, maxls = 20, finite_diff_rel_step = None
unknown_options = {}, m = 10, pgtol = 0.0001, factr = 1000.0, n = 2, new_bounds = (array([-inf, -inf]), array([inf, inf]))
sf = <scipy.optimize._differentiable_functions.ScalarFunction object at 0x13b43aee0>
func_and_grad = <bound method ScalarFunction.fun_and_grad of <scipy.optimize._differentiable_functions.ScalarFunction object at 0x13b43aee0>>

    def _minimize_lbfgsb(fun, x0, args=(), jac=None, bounds=None,
                         disp=None, maxcor=10, ftol=2.2204460492503131e-09,
                         gtol=1e-5, eps=1e-8, maxfun=15000, maxiter=15000,
                         iprint=-1, callback=None, maxls=20,
                         finite_diff_rel_step=None, **unknown_options):
        """
        Minimize a scalar function of one or more variables using the L-BFGS-B
        algorithm.
    
        Options
        -------
        disp : None or int
            If `disp is None` (the default), then the supplied version of `iprint`
            is used. If `disp is not None`, then it overrides the supplied version
            of `iprint` with the behaviour you outlined.
        maxcor : int
            The maximum number of variable metric corrections used to
            define the limited memory matrix. (The limited memory BFGS
            method does not store the full hessian but uses this many terms
            in an approximation to it.)
        ftol : float
            The iteration stops when ``(f^k -
            f^{k+1})/max{|f^k|,|f^{k+1}|,1} <= ftol``.
        gtol : float
            The iteration will stop when ``max{|proj g_i | i = 1, ..., n}
            <= gtol`` where ``pg_i`` is the i-th component of the
            projected gradient.
        eps : float or ndarray
            If `jac is None` the absolute step size used for numerical
            approximation of the jacobian via forward differences.
        maxfun : int
            Maximum number of function evaluations.
        maxiter : int
            Maximum number of iterations.
        iprint : int, optional
            Controls the frequency of output. ``iprint < 0`` means no output;
            ``iprint = 0``    print only one line at the last iteration;
            ``0 < iprint < 99`` print also f and ``|proj g|`` every iprint iterations;
            ``iprint = 99``   print details of every iteration except n-vectors;
            ``iprint = 100``  print also the changes of active set and final x;
            ``iprint > 100``  print details of every iteration including x and g.
        callback : callable, optional
            Called after each iteration, as ``callback(xk)``, where ``xk`` is the
            current parameter vector.
        maxls : int, optional
            Maximum number of line search steps (per iteration). Default is 20.
        finite_diff_rel_step : None or array_like, optional
            If `jac in ['2-point', '3-point', 'cs']` the relative step size to
            use for numerical approximation of the jacobian. The absolute step
            size is computed as ``h = rel_step * sign(x0) * max(1, abs(x0))``,
            possibly adjusted to fit into the bounds. For ``method='3-point'``
            the sign of `h` is ignored. If None (default) then step is selected
            automatically.
    
        Notes
        -----
        The option `ftol` is exposed via the `scipy.optimize.minimize` interface,
        but calling `scipy.optimize.fmin_l_bfgs_b` directly exposes `factr`. The
        relationship between the two is ``ftol = factr * numpy.finfo(float).eps``.
        I.e., `factr` multiplies the default machine floating-point precision to
        arrive at `ftol`.
    
        """
        _check_unknown_options(unknown_options)
        m = maxcor
        pgtol = gtol
        factr = ftol / np.finfo(float).eps
    
        x0 = asarray(x0).ravel()
        n, = x0.shape
    
        if bounds is None:
            bounds = [(None, None)] * n
        if len(bounds) != n:
            raise ValueError('length of x0 != length of bounds')
    
        # unbounded variables must use None, not +-inf, for optimizer to work properly
        bounds = [(None if l == -np.inf else l, None if u == np.inf else u) for l, u in bounds]
        # LBFGSB is sent 'old-style' bounds, 'new-style' bounds are required by
        # approx_derivative and ScalarFunction
        new_bounds = old_bound_to_new(bounds)
    
        # check bounds
        if (new_bounds[0] > new_bounds[1]).any():
            raise ValueError("LBFGSB - one of the lower bounds is greater than an upper bound.")
    
        # initial vector must lie within the bounds. Otherwise ScalarFunction and
        # approx_derivative will cause problems
        x0 = np.clip(x0, new_bounds[0], new_bounds[1])
    
        if disp is not None:
            if disp == 0:
                iprint = -1
            else:
                iprint = disp
    
        sf = _prepare_scalar_function(fun, x0, jac=jac, args=args, epsilon=eps,
                                      bounds=new_bounds,
                                      finite_diff_rel_step=finite_diff_rel_step)
    
        func_and_grad = sf.fun_and_grad
    
        fortran_int = _lbfgsb.types.intvar.dtype
    
        nbd = zeros(n, fortran_int)
        low_bnd = zeros(n, float64)
        upper_bnd = zeros(n, float64)
        bounds_map = {(None, None): 0,
                      (1, None): 1,
                      (1, 1): 2,
                      (None, 1): 3}
        for i in range(0, n):
            l, u = bounds[i]
            if l is not None:
                low_bnd[i] = l
                l = 1
            if u is not None:
                upper_bnd[i] = u
                u = 1
            nbd[i] = bounds_map[l, u]
    
        if not maxls > 0:
            raise ValueError('maxls must be positive.')
    
        x = array(x0, float64)
        f = array(0.0, float64)
        g = zeros((n,), float64)
        wa = zeros(2*m*n + 5*n + 11*m*m + 8*m, float64)
        iwa = zeros(3*n, fortran_int)
        task = zeros(1, 'S60')
        csave = zeros(1, 'S60')
        lsave = zeros(4, fortran_int)
        isave = zeros(44, fortran_int)
        dsave = zeros(29, float64)
    
        task[:] = 'START'
    
        n_iterations = 0
    
        while 1:
            # x, f, g, wa, iwa, task, csave, lsave, isave, dsave = \
            _lbfgsb.setulb(m, x, low_bnd, upper_bnd, nbd, f, g, factr,
                           pgtol, wa, iwa, task, iprint, csave, lsave,
                           isave, dsave, maxls)
            task_str = task.tobytes()
            if task_str.startswith(b'FG'):
                # The minimization routine wants f and g at the current x.
                # Note that interruptions due to maxfun are postponed
                # until the completion of the current minimization iteration.
                # Overwrite f and g:
                f, g = func_and_grad(x)
            elif task_str.startswith(b'NEW_X'):
                # new iteration
                n_iterations += 1
                if callback is not None:
                    callback(np.copy(x))
    
>               if n_iterations >= maxiter:
E               TypeError: '>=' not supported between instances of 'int' and 'str'

../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/lbfgsb.py:367: TypeError
______________________________________________ test_glm_max_iter_argument[0] _______________________________________________

max_iter = 0

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>

sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
______________________________________________ test_glm_max_iter_argument[-1] ______________________________________________

max_iter = -1

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>

sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
_____________________________________________ test_glm_max_iter_argument[5.5] ______________________________________________

max_iter = 5.5

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>

sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
__________________________________________ test_glm_max_iter_argument[max_iter4] ___________________________________________

max_iter = [1]

    @pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
    def test_glm_max_iter_argument(max_iter):
        """Test GLM for invalid max_iter argument."""
        y = np.array([1, 2])
        X = np.array([[1], [2]])
        glm = GeneralizedLinearRegressor(max_iter=max_iter)
        with pytest.raises(ValueError, match="must be a positive integer"):
>           glm.fit(X, y)

sklearn/linear_model/_glm/tests/test_glm.py:150: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
sklearn/linear_model/_glm/glm.py:319: in fit
    opt_res = scipy.optimize.minimize(
../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/_minimize.py:623: in minimize
    return _minimize_lbfgsb(fun, x0, args, jac, bounds,
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fun = <scipy.optimize.optimize.MemoizeJac object at 0x13b4bd790>, x0 = array([1.5, 0. ])
args = (array([[1.],
       [2.]]), array([1, 2]), array([0.5, 0.5]), 1.0, <sklearn._loss.glm_distribution.NormalDistribution object at 0x13b4bd610>, <sklearn.linear_model._glm.link.IdentityLink object at 0x13b4bd400>)
jac = <bound method MemoizeJac.derivative of <scipy.optimize.optimize.MemoizeJac object at 0x13b4bd790>>
bounds = [(None, None), (None, None)], disp = None, maxcor = 10, ftol = 2.220446049250313e-13, gtol = 0.0001, eps = 1e-08
maxfun = 15000, maxiter = [1], iprint = -1, callback = None, maxls = 20, finite_diff_rel_step = None, unknown_options = {}
m = 10, pgtol = 0.0001, factr = 1000.0, n = 2, new_bounds = (array([-inf, -inf]), array([inf, inf]))
sf = <scipy.optimize._differentiable_functions.ScalarFunction object at 0x13b4bd3d0>
func_and_grad = <bound method ScalarFunction.fun_and_grad of <scipy.optimize._differentiable_functions.ScalarFunction object at 0x13b4bd3d0>>

    def _minimize_lbfgsb(fun, x0, args=(), jac=None, bounds=None,
                         disp=None, maxcor=10, ftol=2.2204460492503131e-09,
                         gtol=1e-5, eps=1e-8, maxfun=15000, maxiter=15000,
                         iprint=-1, callback=None, maxls=20,
                         finite_diff_rel_step=None, **unknown_options):
        """
        Minimize a scalar function of one or more variables using the L-BFGS-B
        algorithm.
    
        Options
        -------
        disp : None or int
            If `disp is None` (the default), then the supplied version of `iprint`
            is used. If `disp is not None`, then it overrides the supplied version
            of `iprint` with the behaviour you outlined.
        maxcor : int
            The maximum number of variable metric corrections used to
            define the limited memory matrix. (The limited memory BFGS
            method does not store the full hessian but uses this many terms
            in an approximation to it.)
        ftol : float
            The iteration stops when ``(f^k -
            f^{k+1})/max{|f^k|,|f^{k+1}|,1} <= ftol``.
        gtol : float
            The iteration will stop when ``max{|proj g_i | i = 1, ..., n}
            <= gtol`` where ``pg_i`` is the i-th component of the
            projected gradient.
        eps : float or ndarray
            If `jac is None` the absolute step size used for numerical
            approximation of the jacobian via forward differences.
        maxfun : int
            Maximum number of function evaluations.
        maxiter : int
            Maximum number of iterations.
        iprint : int, optional
            Controls the frequency of output. ``iprint < 0`` means no output;
            ``iprint = 0``    print only one line at the last iteration;
            ``0 < iprint < 99`` print also f and ``|proj g|`` every iprint iterations;
            ``iprint = 99``   print details of every iteration except n-vectors;
            ``iprint = 100``  print also the changes of active set and final x;
            ``iprint > 100``  print details of every iteration including x and g.
        callback : callable, optional
            Called after each iteration, as ``callback(xk)``, where ``xk`` is the
            current parameter vector.
        maxls : int, optional
            Maximum number of line search steps (per iteration). Default is 20.
        finite_diff_rel_step : None or array_like, optional
            If `jac in ['2-point', '3-point', 'cs']` the relative step size to
            use for numerical approximation of the jacobian. The absolute step
            size is computed as ``h = rel_step * sign(x0) * max(1, abs(x0))``,
            possibly adjusted to fit into the bounds. For ``method='3-point'``
            the sign of `h` is ignored. If None (default) then step is selected
            automatically.
    
        Notes
        -----
        The option `ftol` is exposed via the `scipy.optimize.minimize` interface,
        but calling `scipy.optimize.fmin_l_bfgs_b` directly exposes `factr`. The
        relationship between the two is ``ftol = factr * numpy.finfo(float).eps``.
        I.e., `factr` multiplies the default machine floating-point precision to
        arrive at `ftol`.
    
        """
        _check_unknown_options(unknown_options)
        m = maxcor
        pgtol = gtol
        factr = ftol / np.finfo(float).eps
    
        x0 = asarray(x0).ravel()
        n, = x0.shape
    
        if bounds is None:
            bounds = [(None, None)] * n
        if len(bounds) != n:
            raise ValueError('length of x0 != length of bounds')
    
        # unbounded variables must use None, not +-inf, for optimizer to work properly
        bounds = [(None if l == -np.inf else l, None if u == np.inf else u) for l, u in bounds]
        # LBFGSB is sent 'old-style' bounds, 'new-style' bounds are required by
        # approx_derivative and ScalarFunction
        new_bounds = old_bound_to_new(bounds)
    
        # check bounds
        if (new_bounds[0] > new_bounds[1]).any():
            raise ValueError("LBFGSB - one of the lower bounds is greater than an upper bound.")
    
        # initial vector must lie within the bounds. Otherwise ScalarFunction and
        # approx_derivative will cause problems
        x0 = np.clip(x0, new_bounds[0], new_bounds[1])
    
        if disp is not None:
            if disp == 0:
                iprint = -1
            else:
                iprint = disp
    
        sf = _prepare_scalar_function(fun, x0, jac=jac, args=args, epsilon=eps,
                                      bounds=new_bounds,
                                      finite_diff_rel_step=finite_diff_rel_step)
    
        func_and_grad = sf.fun_and_grad
    
        fortran_int = _lbfgsb.types.intvar.dtype
    
        nbd = zeros(n, fortran_int)
        low_bnd = zeros(n, float64)
        upper_bnd = zeros(n, float64)
        bounds_map = {(None, None): 0,
                      (1, None): 1,
                      (1, 1): 2,
                      (None, 1): 3}
        for i in range(0, n):
            l, u = bounds[i]
            if l is not None:
                low_bnd[i] = l
                l = 1
            if u is not None:
                upper_bnd[i] = u
                u = 1
            nbd[i] = bounds_map[l, u]
    
        if not maxls > 0:
            raise ValueError('maxls must be positive.')
    
        x = array(x0, float64)
        f = array(0.0, float64)
        g = zeros((n,), float64)
        wa = zeros(2*m*n + 5*n + 11*m*m + 8*m, float64)
        iwa = zeros(3*n, fortran_int)
        task = zeros(1, 'S60')
        csave = zeros(1, 'S60')
        lsave = zeros(4, fortran_int)
        isave = zeros(44, fortran_int)
        dsave = zeros(29, float64)
    
        task[:] = 'START'
    
        n_iterations = 0
    
        while 1:
            # x, f, g, wa, iwa, task, csave, lsave, isave, dsave = \
            _lbfgsb.setulb(m, x, low_bnd, upper_bnd, nbd, f, g, factr,
                           pgtol, wa, iwa, task, iprint, csave, lsave,
                           isave, dsave, maxls)
            task_str = task.tobytes()
            if task_str.startswith(b'FG'):
                # The minimization routine wants f and g at the current x.
                # Note that interruptions due to maxfun are postponed
                # until the completion of the current minimization iteration.
                # Overwrite f and g:
                f, g = func_and_grad(x)
            elif task_str.startswith(b'NEW_X'):
                # new iteration
                n_iterations += 1
                if callback is not None:
                    callback(np.copy(x))
    
>               if n_iterations >= maxiter:
E               TypeError: '>=' not supported between instances of 'int' and 'list'

../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/lbfgsb.py:367: TypeError
============================================== 5 failed, 2 warnings in 0.66s ===============================================
(sklearndev) 
~/software-build/scikit-learn  xscalar_glm ✗      
```
