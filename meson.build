project(
    'taggedalgebraic',
    ['d'],
    license: 'BSL-1.0',
    meson_version: '>=0.58.1',
    version: '0.11.22',
)

include_directories = include_directories('source')

sources = files(
    'source/taggedalgebraic/package.d',
    'source/taggedalgebraic/taggedalgebraic.d',
    'source/taggedalgebraic/taggedunion.d',
    'source/taggedalgebraic/visit.d',
)

library_dep = declare_dependency(
    sources: sources,
    include_directories: include_directories,
)

# https://github.com/mesonbuild/meson/issues/6862
if build_machine.system() == 'darwin'
	library_lib = library(
		'taggedalgebraic',
        dependencies: library_dep,
		install: true,
	)
else
	library_lib = library(
		'taggedalgebraic',
        dependencies: library_dep,
		install: true,
		version: meson.project_version(),
	)
endif

install_headers(
	sources,
	subdir: 'd/taggedalgebraic/taggedalgebraic',
)

test_exe = executable(
	'taggedalgebraic_test',
	dependencies: library_dep,
	d_unittest: true,
	link_args: '-main',
)

test('test_taggedalgebraic', test_exe)
