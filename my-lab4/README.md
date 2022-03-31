## Some changes were needed:

At at_controller.go:

'''
logger := log.FromContext(ctx).WithValues("namespace", req.NamespacedName, "at", req.Name)
//instead of logger := r.Log.WithValues("namespace", req.NamespacedName, "at", req.Name)
'''

'''
r.Recorder.Event(instance, "Normal", "PhaseChange", cnatv1alpha1.PhaseRunning) //eventtype should be "Normal" not "Running".
'''

'''
r.Recorder.Event(instance, "Normal", "PhaseChange", cnatv1alpha1.PhaseDone) //eventtype should be "Normal" not "Done".
'''



