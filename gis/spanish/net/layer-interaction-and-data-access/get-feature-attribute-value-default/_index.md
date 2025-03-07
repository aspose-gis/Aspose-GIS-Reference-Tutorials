---
title: Obtener valor de atributo de característica (predeterminado)
linktitle: Obtener valor de atributo de característica (predeterminado)
second_title: Aspose.GIS API .NET
description: ¡Desbloquee el poder de Aspose.GIS para .NET! Recupere y manipule valores de atributos de entidades sin esfuerzo con esta guía paso a paso. ¡Descarga tu versión de prueba ahora!
weight: 14
url: /es/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtener valor de atributo de característica (predeterminado)

## Introducción
¡Bienvenido al mundo de Aspose.GIS para .NET! En esta guía completa, profundizaremos en las complejidades de recuperar valores de atributos de características utilizando las poderosas capacidades de Aspose.GIS. Ya sea que sea un desarrollador experimentado o recién esté comenzando, este tutorial le proporcionará un recorrido paso a paso, lo que le permitirá aprovechar todo el potencial de esta notable herramienta.
## Requisitos previos
Antes de embarcarnos en esta aventura de codificación, asegúrese de cumplir con los siguientes requisitos previos:
- Un conocimiento práctico de C# y .NET framework.
-  Aspose.GIS para .NET instalado. Si no, descárgalo de[aquí](https://releases.aspose.com/gis/net/).
- Un editor de código, como Visual Studio, para seguirlo sin problemas.
## Importar espacios de nombres
En su proyecto C#, asegúrese de incluir los espacios de nombres necesarios:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Ahora, dividamos cada ejemplo en una serie de pasos fáciles de seguir.
## Obtener valor de atributo de característica (predeterminado)
### Paso 1: configurar el entorno
Comience definiendo la ruta a su directorio de documentos:
```csharp
string dataDir = "Your Document Directory";
```
### Paso 2: crea una capa GeoJson
Cree una capa GeoJson y defina un atributo con valores predeterminados:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Paso 3: construir una característica
Construya una característica usando el atributo definido:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Paso 4: recuperar valores
Recuperar valores de atributos con varios escenarios:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // valor == nulo
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // valor == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // valor == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Configuración de valores predeterminados
### Paso 1: crea otra capa GeoJson
Repite el proceso con una capa GeoJson diferente y un atributo doble:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Paso 2: construir una función (nuevamente)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Paso 3: recuperar y establecer valores
Recupere y establezca valores de atributos, mostrando los valores predeterminados:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // valor == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // valor == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // valor == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
¡Felicidades! Ha aprovechado con éxito el poder de Aspose.GIS para .NET para recuperar y manipular valores de atributos de entidades.
## Conclusión
En este tutorial, exploramos los matices de recuperar valores de atributos de características usando Aspose.GIS para .NET. Con su API intuitiva y capacidades sólidas, Aspose.GIS abre un mundo de posibilidades para el desarrollo de SIG en entornos .NET.
## Preguntas frecuentes
### ¿Aspose.GIS es compatible con .NET Core?
Sí, Aspose.GIS es totalmente compatible con .NET Core y brinda soporte multiplataforma.
### ¿Puedo utilizar Aspose.GIS para proyectos comerciales?
¡Absolutamente! Aspose.GIS viene con una licencia comercial que le permite utilizarlo en sus aplicaciones comerciales sin restricciones.
### ¿Dónde puedo encontrar apoyo y recursos adicionales?
 Visita el[Foro Aspose.GIS](https://forum.aspose.com/c/gis/33) para obtener apoyo de la comunidad y explorar[documentación](https://reference.aspose.com/gis/net/) para obtener información detallada.
### ¿Hay una prueba gratuita disponible?
 Sí, puedes explorar Aspose.GIS con una prueba gratuita. Descargalo[aquí](https://releases.aspose.com/).
### ¿Cómo obtengo una licencia temporal para realizar pruebas?
 Para licencias temporales, visite[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
