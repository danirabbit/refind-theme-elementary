project('refind-theme-elementary', 'c',
    version: '0.1.0'
)

comp = find_program('rsvg-convert')


icons = [
    'back-selected-big',
    'back-selected-small',
    'func_about',
    'func_exit',
    'func_firmware',
    'func_reset',
    'func_shutdown'
]

foreach icon : icons
    mytarget = custom_target(icon,
      output : icon + '.png',
      input : 'icons/' + icon + '.svg',
      command : [comp, '@INPUT@', '-o', '@OUTPUT@'],
      install : true,
      install_dir : '/boot/efi/EFI/refind/elementary'
    )
endforeach


install_data(
    'refind.conf',
    install_dir: '/boot/efi/EFI/refind'
)

install_subdir(
    'elementary',
    install_dir: '/boot/efi/EFI/refind'
)
