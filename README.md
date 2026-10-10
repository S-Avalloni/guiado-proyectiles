# Control Óptimo en el Guiado de Proyectiles

## Instalación

### Requisitos previos

- Julia 1.12+.

### Pasos de instalación

1. Clonar el repositorio y abrir una terminal en la carpeta que contiene `Project.toml`.
2. Iniciar Julia en la terminal:

   ```sh
   julia --project=.
   ```

3. En la consola de Julia, instalar todas las dependencias del proyecto:

   ```julia
   using Pkg
   Pkg.instantiate()
   ```


## Uso

wip

## Documentación

Para detalles sobre el modelamiento, ver `docs/`.

# Planeación

- [ ] Obtener modelamiento del problema general.
- [ ] Programar el caso lineal con un proyectil y target.
- [ ] Programar el caso no lineal con un proyectil y target.
- [ ] Estudiar la controlabilidad, observabilidad y estabilidad de los problemas.
- [ ] Realizar simulaciones, comparando distintos métodos numéricos.
- [ ] Programar el caso con 2 proyectiles.
- [ ] Programar el caso con $N$ proyectiles.

