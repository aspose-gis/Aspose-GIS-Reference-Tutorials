---
date: 2026-02-13
description: Aprende cómo convertir coordenadas a DMS con Aspose.GIS para .NET. Esta
  guía paso a paso en C# muestra cómo convertir latitud y longitud, grados decimales
  a DMS y más.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Cómo convertir coordenadas a DMS con Aspose.GIS para .NET
url: /es/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo convertir coordenadas a DMS con Aspose.GIS

## Introducción
En este tutorial, aprenderás **cómo convertir coordenadas** a DMS (grados, minutos, segundos) usando la potente biblioteca Aspose.GIS para .NET. Ya sea que necesites **c# convert lat long**, generar cadenas de ubicación legibles por humanos, o simplemente explorar diferentes formatos de coordenadas, esta guía te lleva paso a paso con explicaciones claras y código C# listo para ejecutar.

## Respuestas rápidas
- **¿Qué significa “convert coordinates to DMS”?** Transforma valores numéricos de latitud/longitud en la notación tradicional de grados‑minutos‑segundos.  
- **¿Qué biblioteca maneja la conversión?** Aspose.GIS para .NET proporciona la clase `GeoConvert` con soporte de formato incorporado.  
- **¿Necesito una licencia para probarlo?** Hay una prueba gratuita disponible; se requiere una licencia comercial para uso en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+ y .NET 5/6+.  
- **¿Puedo usar el mismo código para otros formatos?** Sí—simplemente cambia el valor del enum `PointFormats` (p. ej., `DecimalDegrees`, `GeoRef`).  

## Cómo convertir coordenadas a DMS
Antes de sumergirnos en el código, aclaremos por qué DMS sigue siendo valioso. Cartógrafos, pilotos y muchos proveedores de datos GIS confían en DMS porque es amigable para los humanos y se alinea con los mapas tradicionales. Aspose.GIS elimina la necesidad de cálculos manuales, permitiéndote centrarte en la lógica de tu aplicación.

## ¿Qué es la conversión de coordenadas a DMS?
Convertir coordenadas a DMS reescribe los valores decimales de latitud y longitud en un formato como `25°30'00"N 45°30'00"E`. Esta representación se usa ampliamente en cartografía, navegación e intercambio de datos GIS.

## ¿Por qué usar Aspose.GIS para la conversión de coordenadas?
- **All‑in‑one API** – Sin bibliotecas externas ni cálculos complejos; Aspose.GIS maneja el análisis y formateo internamente.  
- **High accuracy** – Manejo preciso de casos límite como valores negativos y designadores hemisféricos.  
- **Cross‑platform** – Funciona igual en entornos .NET de Windows, Linux y macOS.  
- **Extensible** – Cambia fácilmente entre DMS, grados decimales, grados‑minutos‑decimales y formatos GeoRef.  

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Basic knowledge of C#** – Familiaridad con variables, llamadas a métodos y salida de consola.  
2. **Aspose.GIS installed** – Descarga el paquete más reciente desde el [Aspose.GIS website](https://releases.aspose.com/gis/net/).  

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
Aunque el objetivo final es DMS, comenzamos mostrando la representación decimal original. Esto también demuestra la ruta **decimal degrees to dms** que seguirás más adelante.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Paso 3: Convertir a grados minutos decimales  
Este formato (`DD°MM.m'`) es un paso intermedio común cuando necesitas *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Paso 4: Convertir a grados minutos segundos (DMS)  
Este es el núcleo de nuestro tutorial—**convert coordinates to DMS**.

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
- **Incorrect hemisphere letters** – Asegúrate de pasar valores positivos para norte/este y negativos para sur/oeste; la API agrega automáticamente el sufijo correcto.  
- **Unexpected blank output** – Verifica que el ensamblado `Aspose.Gis` esté referenciado correctamente y que el proyecto apunte a una versión .NET compatible.  
- **License not found** – Coloca tu archivo de licencia en la raíz de la aplicación o configúralo programáticamente con `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Preguntas frecuentes

**Q: ¿Es Aspose.GIS compatible con otros lenguajes de programación?**  
A: Aspose.GIS se dirige principalmente a desarrolladores .NET, pero también está disponible una versión Java.

**Q: ¿Puedo probar Aspose.GIS antes de comprar?**  
A: Sí, puedes acceder a una prueba gratuita de Aspose.GIS desde el [website](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener soporte para Aspose.GIS?**  
A: Puedes buscar asistencia en el foro de la comunidad Aspose.GIS [here](https://forum.aspose.com/c/gis/33).

**Q: ¿Hay licencias temporales disponibles para Aspose.GIS?**  
A: Sí, se pueden obtener licencias temporales en la [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo comprar Aspose.GIS?**  
A: Puedes comprar Aspose.GIS en la [purchase page](https://purchase.aspose.com/buy).

## Conclusión
Al seguir estos pasos, ahora sabes cómo **convert coordinates to DMS** y otros formatos GIS comunes usando Aspose.GIS para .NET. Esta capacidad te permite integrar sin problemas cadenas de ubicación legibles por humanos en aplicaciones de mapeo, informes o cualquier flujo de trabajo de datos espaciales. Siéntete libre de experimentar con diferentes valores de latitud/longitud y explorar los otros formatos que ofrece la clase `GeoConvert`.

---

**Última actualización:** 2026-02-13  
**Probado con:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}