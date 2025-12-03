---
date: 2025-12-03
description: Aprenda a comparar geometrías usando Aspose.GIS para .NET y verifique
  la igualdad de geometrías en sus aplicaciones .NET.
language: es
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Cómo comparar geometrías para igualdad usando Aspose.GIS para .NET
url: /net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo comparar geometrías para igualdad usando Aspose.GIS para .NET

## Introducción
En este tutorial descubrirás **cómo comparar geometrías** con Aspose.GIS para .NET. Ya sea que estés construyendo un servicio de mapeo, realizando análisis espacial, o simplemente necesites verificar que dos formas representan la misma ubicación, saber cómo comparar geometrías es esencial. Te guiaremos a través de un ejemplo completo, de extremo a extremo, que muestra cómo crear, modificar y probar la igualdad de geometrías en solo unas pocas líneas de código C#.

## Respuestas rápidas
- **¿Qué significa “comparar geometrías”?** Verifica si dos objetos geométricos ocupan el mismo espacio, sin importar cómo fueron construidos.  
- **¿Qué método se utiliza?** `SpatiallyEquals` de la API de Aspose.GIS.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Versiones de .NET compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **¿Tiempo típico de implementación?** Aproximadamente 5‑10 minutos para una verificación básica de igualdad.

## ¿Qué es la igualdad de geometrías?
La igualdad de geometrías (a menudo llamada igualdad espacial) significa que dos geometrías representan el mismo conjunto exacto de puntos en la superficie de la tierra. Dos formas pueden construirse de manera diferente —un MultiLineString frente a un LineString único— pero seguir siendo espacialmente iguales.

## ¿Por qué usar Aspose.GIS para comparar geometrías?
Aspose.GIS proporciona un motor de geometría robusto y de alto rendimiento que:
- Maneja una amplia gama de formatos vectoriales (WKT, GeoJSON, Shapefile, etc.).
- Ofrece métodos de comparación conscientes de la precisión como `SpatiallyEquals`.
- Funciona sin conexión, sin servicios externos, lo que lo hace ideal para entornos seguros o aislados.

## Requisitos previos
Antes de comenzar, asegúrate de contar con lo siguiente:

- **.NET Framework o .NET Core instalados** – cualquier versión compatible con Aspose.GIS.  
- **Biblioteca Aspose.GIS para .NET** – descárgala desde la [página de descarga de Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **Un IDE de desarrollo** – Visual Studio, Rider o VS Code con extensiones de C#.

## Importar espacios de nombres
En tu proyecto .NET, agrega las sentencias `using` requeridas para que el compilador sepa dónde encontrar las clases GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Paso 1: Definir las geometrías
Primero, creamos dos geometrías que compararemos. En este ejemplo `geometry1` es un `MultiLineString` compuesto por dos segmentos de línea, mientras que `geometry2` es un `LineString` único que abarca los mismos puntos de inicio y fin.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Paso 2: Verificar la igualdad de las geometrías
Ahora usamos el método `SpatiallyEquals` para ver si las dos formas son consideradas iguales por el motor GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

La consola imprime `True` porque, a pesar de la construcción diferente, ambas geometrías cubren la misma línea desde (0,0) hasta (2,2).

## Paso 3: Modificar una geometría
Para ilustrar cómo un cambio afecta la igualdad, añadimos un punto extra a `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Paso 4: Volver a comprobar la igualdad después de la modificación
Después de la modificación, las geometrías ya no son iguales, por lo que `SpatiallyEquals` devuelve `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

El resultado `False` confirma que el punto adicional rompió la igualdad espacial.

## Problemas comunes y consejos
- **Problemas de precisión** – Si trabajas con coordenadas de muy alta precisión, considera redondear o usar una sobrecarga de tolerancia de `SpatiallyEquals`.  
- **SRIDs diferentes** – Asegúrate de que ambas geometrías compartan el mismo Identificador de Sistema de Referencia Espacial (SRID) antes de comparar.  
- **Rendimiento** – Para colecciones grandes, las comparaciones por lotes usando LINQ pueden reducir la sobrecarga.

## Preguntas frecuentes
**P: ¿Puedo usar Aspose.GIS para .NET con otros frameworks .NET?**  
R: Sí, Aspose.GIS funciona con proyectos .NET Framework, .NET Core y .NET Standard.

**P: ¿Hay una prueba gratuita disponible?**  
R: Por supuesto. Descarga una prueba desde la [página de versiones de Aspose.GIS](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar la documentación completa de la API?**  
R: La documentación detallada está en la [página de documentación de Aspose.GIS](https://reference.aspose.com/gis/net/).

**P: ¿Cómo obtengo ayuda si tengo un problema?**  
R: Publica tu pregunta en el foro de la comunidad de Aspose.GIS [aquí](https://forum.aspose.com/c/gis/33).

**P: ¿Puedo comprar una licencia temporal para evaluación?**  
R: Sí, las licencias temporales están disponibles en la [página de compra](https://purchase.aspose.com/temporary-license/).

## Conclusión
Ahora sabes **cómo comparar geometrías** usando Aspose.GIS para .NET, desde la creación de los objetos hasta la verificación de la igualdad espacial y el manejo de modificaciones. Esta capacidad es un bloque fundamental para análisis espaciales más avanzados, como validación de topología, detección de duplicados y filtrado basado en geometrías.

---

**Última actualización:** 2025-12-03  
**Probado con:** Aspose.GIS for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}