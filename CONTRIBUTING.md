# Cómo contribuir


## Dependencias

Utilizamos [poetry](https://github.com/python-poetry/poetry) para gestionar las dependencias.

Para instalarlas necesitarás ejecutar el comando `install`:

``bash
poetry install
```

Para activar tu `virtualenv` ejecuta `poetry shell`.


## Un comando mágico

Ejecuta `make test` para ejecutar todo lo que tenemos


## Pruebas

Usamos `pytest` y `flake8` para el control de calidad.
También usamos [wemake_python_styleguide](https://github.com/wemake-services/wemake-python-styleguide) para reforzar la calidad del código.

Para ejecutar todas las pruebas:

``bash
pytest
```

Para ejecutar linting:

``bash
flake8 .
```

Tenga en cuenta: la carpeta del entorno virtual excluida por defecto por la comprobación de estilo de flake8 es `.venv`.
Si desea personalizar este parámetro, debe hacerlo en `setup.cfg`.
Estos pasos son obligatorios durante el CI.


## Comprobaciones de tipo

Usamos `mypy` para ejecutar comprobaciones de tipo en nuestro código.
Para usarlo:

``bash
mypy scdlbot tests/**/*.py
```

Este paso es obligatorio durante el CI.


## Enviar tu código

Utilizamos [trunk based](https://trunkbaseddevelopment.com/)
de desarrollo (también lo llamamos a veces `wemake-git-flow`).

¿Qué sentido tiene este método?

1. Usamos la rama protegida `master`,
	por lo que la única manera de empujar su código es a través de pull request
2. Usamos ramas de emisión: para implementar una nueva característica o para corregir un error
	crea una nueva rama llamada `issue-$TASKNUMBER`.
3. A continuación, cree una solicitud de extracción a la rama `master`.
4. Usamos `git tag`s para hacer las publicaciones, así podemos rastrear lo que ha cambiado
	desde la última versión

Así, de esta manera logramos un proceso de desarrollo fácil y escalable
que nos libera del infierno de la fusión y de las ramas de larga duración.

En este método, la última versión de la aplicación está siempre en la rama `master`.

### Antes de enviar

Antes de enviar tu código por favor haz los siguientes pasos:

1. Ejecuta `pytest` para asegurarte de que todo funcionaba antes
2. Añade los cambios que quieras
3. Añade pruebas para los nuevos cambios
4. Edita la documentación si has cambiado algo significativo
5. Actualice `CHANGELOG.md` con un resumen rápido de sus cambios
6. Ejecuta `pytest` de nuevo para asegurarte de que sigue funcionando
7. Ejecuta `mypy` para asegurarte de que los tipos son correctos
8. Ejecuta `flake8` para asegurarte de que el estilo es correcto
9. Ejecutar `doc8` para asegurar que los documentos son correctos


## Otra ayuda

Puedes contribuir difundiendo esta biblioteca.
También sería una gran contribución escribir
un breve artículo sobre cómo está utilizando este proyecto.
También puedes compartir tus mejores prácticas con nosotros.
*** Translated with www.DeepL.com/Translator (free version) ***