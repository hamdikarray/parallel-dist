# parallel-dist

### Purpose ###

To launch simply multithreaded jobs

### Example ###

```

//Create the parallel instance

Parallel<Integer, Boolean> p = new Parallel<>();


//setting a listener : for logging, % of progession ....
p.setListener(new ParallelListener<Integer, Boolean>() {

	@Override
	public synchronized void endItem(OperationStateEnum ose, Integer element, Boolean result, Exception e) {
    // TODO Auto-generated method stub
	}

	@Override
	public void end() {
    // TODO Auto-generated method stub
	}

	@Override
	public void startItem(Integer element) {
		// TODO Auto-generated method stub
	}

	@Override
	public void start(int numThreads, Iterable<Integer> elements, Long keepAliveTime, Long timeout,
			TimeUnit unit, boolean breakOnError) {
		// TODO Auto-generated method stub
	}

});

//setting the function perform 
p.blockingFor(4, Arrays.asList(new Integer[] { 1, 2 }), new Parallel.Operation<Integer, Boolean>() {

	@Override
	public Boolean perform(Integer index) throws Exception {
		return index >= 2;
	}
}, true);


```
