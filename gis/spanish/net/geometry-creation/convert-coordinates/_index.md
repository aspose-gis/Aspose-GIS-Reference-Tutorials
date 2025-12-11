---
date: 2025-12-11
description: Aprende a convertir coordenadas a DMS usando Aspose.GIS para .NET. Incluye
  ejemplos en C#, conversión de latitud y longitud en C# y una guía paso a paso.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Convertir coordenadas a DMS con Aspose.GIS para .NET
url: /es/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir coordenadas a DMS con Aspose.GIS

## Introducción
En este tutorial, descubrirás cómo **convertir coordenadas a DMS** (grados, minutos, segundos) usando la potente biblioteca Aspose.GIS para .NET. Ya sea que necesites c# convertir latitud longitud para aplicaciones de mapeo, generar cadenas de ubicación legibles por humanos, o simplemente explorar diferentes formatos de coordenadas, esta guía te lleva paso a paso con explicaciones claras y código C# listo para ejecutar.

## Respuestas rápidas
- **¿Qué significa “convertir coordenadas a DMS”?** Transforma valores numéricos de latitud/longitud en la notación tradicional de grados‑minutos‑segundos.  
- **¿Qué biblioteca maneja la conversión?** Aspose.GIS para .NET proporciona la clase `GeoConvert` con soporte de formato incorporado.  
- **¿Necesito una licencia para probarlo?** Hay una prueba gratuita disponible; se requiere una licencia comercial para uso en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+ y .NET 5/6+.  
- **¿Puedo usar el mismo código para otros formatos?** Sí—simplemente cambia el valor del enum `PointFormats` (p.ej., `DecimalDegrees`, `GeoRef`).  

## ¿Qué es la conversión de coordenadas a DMS?
Convertir coordenadas a DMS reescribe los valores decimales de latitud y longitud en un formato como `25°30'00"N 45°30'00"E`. Esta representación se usa ampliamente en cartografía, navegación e intercambio de datos GIS.

## ¿Por qué usar Aspose.GIS para la conversión de coordenadas?
- **API todo‑en‑uno** – Sin bibliotecas externas ni matemáticas complejas; Aspose.GIS maneja el análisis y formateo internamente.  
- **Alta precisión** – Manejo preciso de casos límite como valores negativos y designadores hemisféricos.  
- **Multiplataforma** – Funciona igual en entornos .NET de Windows, Linux y macOS.  
- **Extensible** – Cambia fácilmente entre DMS, grados decimales, grados‑minutos‑decimales y formatos GeoRef.  

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Conocimientos básicos de C#** – Familiaridad con variables, llamadas a métodos y salida de consola.  
2. **Aspose.GIS instalado** – Descarga el paquete más reciente desde el [sitio web de Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Importar espacios de nombres
Primero, importa los espacios de nombres requeridos para operaciones GIS:

```csharp
using System;
using Aspose.Gis;
```

## Guía paso a paso

### Paso 1: Iniciar el proceso de conversión
Imprimimos un mensaje amigable para que sepas que la demostración ha comenzado.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Paso 2: Convertir a grados decimales
Aunque el objetivo final es DMS, comenzamos mostrando la representación decimal original.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Paso 3: Convertir a grados minutos decimales
Este formato (`DD°MM.m'`) es un paso intermedio común cuando necesitas *convertir latitud longitud grados minutos*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Paso 4: Convertir a grados minutos segundos (DMS)
Este es el núcleo de nuestro tutorial—**convertir coordenadas a DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Paso 5: Convertir a GeoRef
Para mayor completitud, también demostramos el formato `GeoRef`, útil en flujos de trabajo de teledetección.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Problemas comunes y soluciones
- **Letras de hemisferio incorrectas** – Asegúrate de pasar valores positivos para norte/este y negativos para sur/oeste; la API agrega automáticamente el sufijo correcto.  
- **Salida en blanco inesperada** – Verifica que el ensamblado `Aspose.Gis` esté referenciado correctamente y que el proyecto apunte a una versión .NET compatible.  
- **Licencia no encontrada** – Coloca tu archivo de licencia en la raíz de la aplicación o configúralo programáticamente con `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Preguntas frecuentes

**P: ¿Es Aspose.GIS compatible con otros lenguajes de programación?**  
R: Aspose.GIS está dirigido principalmente a desarrolladores .NET, pero también está disponible una versión para Java.

**P: ¿Puedo probar Aspose.GIS antes de comprar?**  
R: Sí, puedes acceder a una prueba gratuita de Aspose.GIS desde el [sitio web](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener soporte para Aspose.GIS?**  
R: Puedes buscar ayuda en el foro de la comunidad Aspose.GIS [aquí](https://forum.aspose.com/c/gis/33).

**P: ¿Hay licencias temporales disponibles para Aspose.GIS?**  
R: Sí, se pueden obtener licencias temporales desde la [página de licencias temporales](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo comprar Aspose.GIS?**  
R: Puedes comprar Aspose.GIS desde la [página de compra](https://purchase.aspose.com/buy).

## Conclusión
Al seguir estos pasos, ahora sabes cómo **convertir coordenadas a DMS** y a otros formatos GIS comunes usando Aspose.GIS para .NET. Esta capacidad te permite integrar sin problemas cadenas de ubicación legibles por humanos en aplicaciones de mapeo, informes o cualquier flujo de trabajo de datos espaciales. Siéntete libre de experimentar con diferentes valores de latitud/longitud y explorar los otros formatos que ofrece la clase `GeoConvert`.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}