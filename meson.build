project('lfs', 'c',
  default_options: [
    'b_lto=true',
    'b_staticpic=false',
    'c_std=c2x',
    'warning_level=3',
  ],
  license: ['BSD-3-Clause'],
  version: '2.9.3')

c_args = [
  '-ffunction-sections',
]

link_args = [
  '-Wl,--gc-sections', '-fno-exceptions',
]

lib_sources = files([
  'lfs_util.c',
  'lfs.c',
])

lib = library(meson.project_name(),
  lib_sources,
  c_args: c_args,
  link_args: link_args,
  install: true,
)

install_headers('lfs.h', 'lfs_util.h')

# Create a pkgconfig file
pkg = import('pkgconfig')
pkg.generate(lib)
