# orch build configuration

orch_src = [
  'orch.c',
  'opt.c',
]
orch_src += ini_src
orch_src += common_src

executable(
  'hirte',
  orch_src,
  include_directories: [
    common_inc,
    ini_inc
  ],
  dependencies: [
    systemd_dep
  ],
  link_with: hirte_lib,
  install: true
)
