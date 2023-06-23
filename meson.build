project('libb64', ['c', 'cpp'],
  version: '2.0.0.1',
  default_options: ['warning_level=3'],
)

incdir = include_directories('include')

libb64 = library('b64', 'src/cdecode.c', 'src/cencode.c',
  include_directories: incdir,
  c_args: '-Wno-implicit-fallthrough' )

libb64_dep = declare_dependency(include_directories: incdir, link_with: libb64)

BUFFERSIZE = 16777216

executable('base64', 'base64/base64.cc',
  include_directories: incdir,
  link_with: libb64,
  cpp_args: [
    '-Wno-implicit-fallthrough',
    '-DBUFFERSIZE=' + BUFFERSIZE.to_string()
  ]
)
