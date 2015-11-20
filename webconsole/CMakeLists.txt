set(_srcs
  src/usAbstractWebConsolePlugin.cpp
  src/usServicesPlugin.cpp
  src/usSettingsPlugin.cpp
  src/usSimpleWebConsolePlugin.cpp
  src/usVariableResolverStreamBuffer.cpp
  src/usWebConsoleActivator.cpp
  src/usWebConsoleConstants.cpp
  src/usWebConsoleServlet.cpp
  src/usWebConsoleDefaultVariableResolver.cpp
  src/usWebConsoleVariableResolver.cpp
)

set(_private_headers
  src/usServicesPlugin_p.h
  src/usSettingsPlugin_p.h
  src/usVariableResolverStreamBuffer_p.h
  src/usWebConsoleServlet_p.h
)

set(_public_headers
  include/usAbstractWebConsolePlugin.h
  include/usSimpleWebConsolePlugin.h
  include/usWebConsoleConstants.h
  include/usWebConsoleDefaultVariableResolver.h
  include/usWebConsoleVariableResolver.h
)

set(_resources
  manifest.json

  templates/main_footer.html
  templates/main_header.html
  templates/settings.html
  #templates/bundles.html
  #templates/bundle.html
  templates/services.html
  templates/service_interface.html

  res/css/main_style.css

  res/js/jquery.min.js
  res/js/pure.min.js
  res/js/tree.jquery.min.js
  res/js/jqtree.css

  res/KickStart/css/kickstart.css
  res/KickStart/css/kickstart-buttons.css
  res/KickStart/css/kickstart-forms.css
  res/KickStart/css/kickstart-grid.css
  res/KickStart/css/kickstart-menus.css
  res/KickStart/css/prettify.css
  res/KickStart/css/tiptip.css

  res/KickStart/css/fonts/fontawesome/css/font-awesome.min.css
  res/KickStart/css/fonts/fontawesome/css/font-awesome-ie7.min.css
  res/KickStart/css/fonts/fontawesome/font/FontAwesome.otf
  res/KickStart/css/fonts/fontawesome/font/fontawesome-webfont.eot
  res/KickStart/css/fonts/fontawesome/font/fontawesome-webfont.svg
  res/KickStart/css/fonts/fontawesome/font/fontawesome-webfont.ttf
  res/KickStart/css/fonts/fontawesome/font/fontawesome-webfont.woff

  res/KickStart/css/img/breadcrumbs-bg.gif
  res/KickStart/css/img/bx_loader.gif
  res/KickStart/css/img/controls.png
  res/KickStart/css/img/gray_jean.png
  res/KickStart/css/img/icon-arrow-right.png

  res/KickStart/js/kickstart.js
)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/main")

usMacroCreateBundle(WebConsole
  VERSION "0.99.0"
  DEPENDS HttpService
  INTERNAL_INCLUDE_DIRS src
  PUBLIC_HEADERS ${_public_headers}
  PRIVATE_HEADERS ${_private_headers}
  SOURCES ${_srcs}
  RESOURCES ${_resources}
)