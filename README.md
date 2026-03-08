# Ayudantes de CMake (cmake_helpers)

Scripts auxiliares y módulos de CMake para simplificar la configuración, compilación y manejo de proyectos C++ multiplataforma (Windows, macOS, Linux).

Este repositorio es un **fork** actualizado y mantenido de [desktop-app/cmake_helpers](https://github.com/desktop-app/cmake_helpers), la colección de helpers que se utiliza en el proyecto **Telegram Desktop** y en el **Desktop App Toolkit**.

## ¿Para qué sirve?

Esta colección incluye funciones y módulos útiles de CMake para:

- Inicializar targets de forma consistente (`init_target.cmake`)
- Generar targets automáticamente (`generate_target.cmake`)
- Manejar opciones de compilación multiplataforma (`opciones.cmake`, `opciones_win.cmake`, `opciones_mac.cmake`, `opciones_linux.cmake`)
- Validar y configurar compiladores específicos (ej. DirectX en Windows)
- Soporte para Qt (incluyendo Qt 6), LTO, advertencias estrictas, frameworks, etc.
- Scripts auxiliares en Python para tareas de build y validación (`ejecutar_cmake.py`, `validar_compilador_d3d.py`, etc.)
- Integración con herramientas externas (NuGet, cppgir, etc.)

Es especialmente útil si estás desarrollando aplicaciones de escritorio con **Qt**, **C++17/C++20**, y necesitas builds reproducibles en varias plataformas.

## Diferencias con el original

En esta versión (fork) se han aplicado varios ajustes y mejoras, entre ellas:

- Soporte mejorado y actualizado para **cppgir**
- Más advertencias habilitadas en macOS
- Reversiones y fixes en compiladores D3D (Windows)
- Uso de ARGN donde corresponde para mayor flexibilidad
- Habilitación opcional de **Link Time Optimization (LTO)**
- Soporte para Qt 6 en Windows vía NuGet
- Limpieza de jemalloc y otras actualizaciones menores
- Forzado temporal de toolchain v143 en Windows (compatibilidad win7)

(Última sincronización con el upstream: rama master de desktop-app/cmake_helpers)

## Cómo usarlo en tu proyecto

1. Añade este repositorio como submódulo (recomendado):

   ```bash
   git submodule add https://github.com/cerdaquirozr-cibernetico/ayudantes_de_cmake cmake_helpers
   git submodule update --init --recursive
