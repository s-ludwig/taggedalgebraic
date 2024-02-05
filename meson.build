project(
    'taggedalgebraic',
    ['d'],
    meson_version: '>=1.3.1',
)

subdir('source/taggedalgebraic')

taggedalgebraic_dep = declare_dependency(
    sources: taggedalgebraic_src,
    include_directories: taggedalgebraic_includes,
)

test_exe = executable(
	'taggedalgebraic_test',
	dependencies: taggedalgebraic_dep,
	d_unittest: true,
	link_args: '-main',
)

test('test_taggedalgebraic', test_exe)
