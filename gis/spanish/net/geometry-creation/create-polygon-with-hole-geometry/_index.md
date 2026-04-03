---
date: 2026-04-03
description: Aprenda cómo crear geometría de polígono con agujero usando Aspose.GIS
  para .NET. Esta guía le muestra cómo crear un agujero en un polígono y trabajar
  con datos geoespaciales.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Crear polígono con geometría de agujero
second_title: Aspose.GIS .NET API
title: Crear polígono con geometría de agujero usando Aspose.GIS
url: /es/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear geometría de polígono con agujero usando Aspose.GIS

## Introducción
En este tutorial, **creará geometría de polígono con agujero** usando Aspose.GIS para .NET. Ya sea que esté construyendo una aplicación de mapeo, realizando análisis espacial o preparando datos para servicios GIS, saber cómo incrustar un agujero dentro de un polígono es esencial. Recorreremos todo el proceso paso a paso, desde la configuración del entorno hasta la generación del objeto polígono final.

## Respuestas rápidas
- **¿Qué significa “crear polígono con agujero”?** Significa construir un polígono que contiene uno o más anillos interiores (agujeros) que se excluyen del área.  
- **¿Qué biblioteca maneja esto?** Aspose.GIS para .NET ofrece soporte completo para anillos exteriores e interiores.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Cuánto tiempo lleva?** Normalmente menos de 10 minutos para implementar y probar.

## Cómo agregar un agujero a un polígono usando Aspose.GIS
Agregar un agujero es simplemente una cuestión de definir un **anillo interior** y adjuntarlo al polígono. La biblioteca se encarga de la orientación y la validez, por lo que puede centrarse en las coordenadas que representan el vacío que necesita.

## ¿Qué es “crear polígono con agujero”?
Crear un polígono con un agujero implica definir un **anillo exterior** que delimita el contorno externo y uno o más **anillos interiores** que recortan espacios vacíos. Los anillos interiores a menudo se denominan *agujeros* porque representan áreas que no forman parte de la superficie del polígono.

## ¿Por qué crear un agujero en un polígono usando Aspose.GIS?
- **Modelado espacial preciso:** Características del mundo real como lagos dentro de parcelas de tierra o patios dentro de edificios requieren agujeros.  
- **Interoperabilidad:** Formatos como Shapefile, GeoJSON y GML admiten nativamente anillos interiores; Aspose.GIS los preserva.  
- **Rendimiento:** La biblioteca gestiona la validez de la geometría, por lo que no necesita escribir código de validación personalizado.

## Escenarios del mundo real para polígonos con agujeros
1. **Parcela de tierra con un lago interno** – el lago se modela como un agujero para que no se cuente en el área de la parcela.  
2. **Huella de edificios con patios** – el patio se excluye de la huella del edificio.  
3. **Zonas protegidas dentro de un área de conservación mayor** – puede excluir secciones restringidas sin crear capas separadas.

## Requisitos previos
Antes de comenzar, asegúrese de contar con los siguientes requisitos:
1. Biblioteca Aspose.GIS para .NET: Puede descargarla desde [here](https://releases.aspose.com/gis/net/).  
2. Entorno de desarrollo: Asegúrese de tener un entorno de desarrollo configurado con Visual Studio o cualquier otro IDE de .NET instalado.

## Importar espacios de nombres
Primero, necesita importar los espacios de nombres necesarios para trabajar con las funcionalidades de Aspose.GIS. Así es como se hace:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ahora, procedamos a crear una geometría de polígono con agujero usando Aspose.GIS para .NET.

## Paso 1: Crear objeto Polygon
Comenzamos instanciando un objeto `Polygon` vacío que más adelante contendrá tanto los anillos exteriores como los interiores.

```csharp
Polygon polygon = new Polygon();
```

## Paso 2: Definir anillo exterior
El anillo exterior define el contorno externo del polígono. Añada puntos en orden horario para formar una forma cerrada.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Paso 3: Definir anillo interior (agujero)
A continuación, creamos un anillo interior—este es el **agujero** que se excluirá del área del polígono. Los puntos se añaden típicamente en orden antihorario, pero Aspose.GIS maneja la orientación automáticamente.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Paso 4: Asignar anillo exterior y agregar anillo interior al polígono
Finalmente, adjunte el anillo exterior al polígono y luego agregue el anillo interior (el agujero). El método `AddInteriorRing` puede llamarse varias veces si necesita varios agujeros.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Consejos y buenas prácticas
- **La orientación importa para la legibilidad** – aunque Aspose.GIS corrige automáticamente la orientación, mantener los anillos exteriores en sentido horario y los interiores en sentido antihorario facilita la inspección de la geometría en visores GIS.  
- **Cerrar cada anillo** – siempre repita la primera coordenada como el último punto; esto garantiza una forma cerrada válida.  
- **Validar después de la creación** – puede llamar a `polygon.IsValid` para asegurarse de que la geometría cumpla con los estándares OGC antes de guardarla.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| El agujero no se muestra en el visor GIS | Orientación del anillo interior invertida | Asegúrese de que los puntos se añadan en la dirección opuesta al anillo exterior (antihorario). |
| Error de polígono inválido | Anillos no cerrados (primer ≠ último punto) | Repita el primer punto como último punto en cada anillo (como se muestra arriba). |
| Geometría vacía inesperada | Olvidó asignar `ExteriorRing` antes de agregar anillos interiores | Establezca `polygon.ExteriorRing` primero, luego llame a `AddInteriorRing`. |

## Preguntas frecuentes
### 1. ¿Qué es Aspose.GIS?
Aspose.GIS es una biblioteca .NET que permite a los desarrolladores trabajar con datos geoespaciales, creando, leyendo y manipulando varios formatos de archivos geoespaciales.

### 2. ¿Puedo usar Aspose.GIS para proyectos comerciales?
Sí, puede usar Aspose.GIS tanto en proyectos personales como comerciales adquiriendo una licencia. Visite [here](https://purchase.aspose.com/buy) para más detalles.

### 3. ¿Hay una prueba gratuita disponible para Aspose.GIS?
Sí, puede obtener una prueba gratuita de Aspose.GIS desde [here](https://releases.aspose.com/).

### 4. ¿Dónde puedo encontrar soporte para Aspose.GIS?
Puede encontrar soporte para Aspose.GIS en el [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. ¿Cómo puedo obtener una licencia temporal para Aspose.GIS?
Puede obtener una licencia temporal para Aspose.GIS desde [here](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-04-03  
**Probado con:** Aspose.GIS 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}