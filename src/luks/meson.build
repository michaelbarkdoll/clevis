libcryptsetup = dependency('libcryptsetup', version: '>=2.0.4', required: false)
luksmeta = dependency('luksmeta', version: '>=8', required: false)
pwmake = find_program('pwmake', required: false)

if libcryptsetup.found() and luksmeta.found() and pwmake.found()
  subdir('systemd')
  subdir('udisks2')

  bins += join_paths(meson.current_source_dir(), 'clevis-luks-unbind')
  mans += join_paths(meson.current_source_dir(), 'clevis-luks-unbind.1')

  bins += join_paths(meson.current_source_dir(), 'clevis-luks-unlock')
  mans += join_paths(meson.current_source_dir(), 'clevis-luks-unlock.1')

  bins += join_paths(meson.current_source_dir(), 'clevis-luks-bind')
  mans += join_paths(meson.current_source_dir(), 'clevis-luks-bind.1')

  mans += join_paths(meson.current_source_dir(), 'clevis-luks-unlockers.7')
else
  warning('Will not install LUKS support due to missing dependencies!')
endif