foreach s : ['io_test', 'open_close_test', 'multithread_test']
  test(
    s,
    executable(
      s,
      '@0@.cpp'.format(s),
      dependencies : [dep_tiny_process_library, dep_threads],
    ),
    timeout : 60,
  )
endforeach