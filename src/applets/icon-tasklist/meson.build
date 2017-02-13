# Icon Tasklist Applet build

applet_icontasklist_dir = applets_dir + '.icon-tasklist'

custom_target('plugin-file-icontasklist',
    input : 'IconTasklistApplet.plugin.in',
    output : 'IconTasklistApplet.plugin',
    command : [intltool, '--desktop-style', podir, '@INPUT@', '@OUTPUT@'],
    install : true,
    install_dir : applet_icontasklist_dir)

applet_icontasklist_sources = [
    'AppSystem.vala',
    'IconTasklistApplet.vala',
    'Buttons.vala',
]

applet_icontasklist_deps = [
    dep_gtk3,
    dep_peas,
    dep_wnck,
    dep_gdkx11,
    link_libplugin,
]

shared_library(
    'icontasklistapplet',
    applet_icontasklist_sources,
    dependencies: applet_icontasklist_deps,
    vala_args: [
        '--pkg', 'budgie-1.0',
        '--pkg', 'libpeas-1.0',
        '--pkg', 'gtk+-3.0',
        '--pkg', 'gdk-x11-3.0',
        '--pkg', 'libwnck-3.0',
    ],
    c_args: [
        '-DWNCK_I_KNOW_THIS_IS_UNSTABLE',
    ],
    install: true,
    install_dir: applet_icontasklist_dir,
)

install_data(
    'com.solus-project.icon-tasklist.gschema.xml',
    install_dir: join_paths(datadir, 'glib-2.0', 'schemas'),
)