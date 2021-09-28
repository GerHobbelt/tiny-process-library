project(
  'tiny-process-library',
  'cpp',
  default_options : ['cpp_std=c++11']
)

dep_threads = dependency('threads')

lib = library(
  'tiny-process-library',
  [
    'process.cpp',
    host_machine.system() == 'windows' ? 'process_win.cpp' : 'process_unix.cpp',
  ],
  dependencies : dep_threads,
  install : true,
)

install_headers('process.hpp')

dep_tiny_process_library = declare_dependency(
  link_with : lib,
  include_directories : include_directories('.'),
)

meson.override_dependency('tiny-process-library', dep_tiny_process_library)

if get_option('tests')
  subdir('tests')
endif