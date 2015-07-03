project('unzip', 'c')

sources = [
  'crc32.c', 'crypt.c', 'envargs.c', 'explode.c',
  'extract.c', 'fileio.c', 'globals.c', 'inflate.c', 'list.c', 'match.c',
  'process.c', 'ttyio.c', 'ubz2err.c', 'unreduce.c', 'unshrink.c', 'zipinfo.c',
]

plat_sources = ['unix/unix.c']

if get_option('shared_library')
  libtype = 'shared_library'
else
  libtype = 'static_library'
endif

unzip_cargs = ['-DUNIX']


libunzip = build_target('unzip6',
  sources, plat_sources,
  target_type : libtype,
  c_args : unzip_cargs,
)

unzip = executable('unzip',
  'unzip.c',
  c_args : unzip_cargs,
  link_with : libunzip,
)

unzip_dep = declare_dependency(include_directories : include_directories('.'),
  link_with : libunzip,
)
