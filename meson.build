# SPDX-License-Identifier: BSD-3-Clause
# Copyright(c) 2021 Intel Corporation

project('vscode-cpp-test', 'C', 'cpp',
	# Get version number from file.
	# Fallback to "more" for Windows compatibility.
	version: '1.0.0',
	license: 'BSD',
	meson_version: '>= 0.53.2'
)

# create config file
cne_conf = configuration_data()
cne_conf.set('TEST_CONFIG_OPTION', 1)

# write the build config
build_cfg_file = 'config.h'
configure_file(output: build_cfg_file, configuration: cne_conf)
install_headers(join_paths(meson.build_root(), build_cfg_file), subdir: meson.project_name().to_lower())

# declare config file as dependency
build_cfg = declare_dependency(include_directories: include_directories('.'))

# create a dummy executable
sources = files('test.c')
deps = [build_cfg]
test_exe = executable('vscode-cpp-test', sources, dependencies: deps)
