
# Despliegue en producción de una aplicación hecha en Vuejs

### Utilizando una herramienta de empaquetado

En el archivo **webpack.config.js**

Verificar que publicPath tiene como valor **./dist/** como aparece en el siguiente código, sino cambiarlo.
~~~
 if (process.env.NODE_ENV === 'production') {
...
module.exports.output.publicPath = './dist/'
module.exports.devtool = '#source-map'

 module.exports.plugins = (module.exports.plugins || []).concat([
    new webpack.DefinePlugin({
      'process.env': {
        NODE_ENV: '"production"'
      }
    })
...
}
~~~
> Luego, ejecutar en la ubicación del proyecto el comando **npm run build** 
Al ejecutarlo se creará una carpeta llamada **dist**. 
Esta carpeta contiene el código JavaScript comprimido en uno o varios archivos .js, támbien almacena las imágenes, iconos utilizados en 
la aplicación.

> Lo que hace el publicPath al establecerle el valor **./dist/** es definir en el archivo **index.html** la ruta  donde se encuentran los archivos fuentes de la aplicación.

```
Con insertar la carpeta **dist** y el archivo **index.html** en el directorio del servidor es suficiente para 
que la aplicación funcione de forma correcta.
```
