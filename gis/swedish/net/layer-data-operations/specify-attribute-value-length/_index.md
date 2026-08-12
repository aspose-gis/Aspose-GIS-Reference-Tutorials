---
date: 2026-05-16
description: Exempel på vektorlager som visar hur man ställer in fältbredd, definierar
  attributbredd och lägger till attributlängd i Aspose.GIS för .NET – en komplett
  steg‑för‑steg‑guide.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Hur man ställer in fältbredd
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Exempel på vektorlager – Hur man ställer in fältbredd i Aspose.GIS för .NET
url: /sv/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorlagrets exempel – Hur man ställer in fältbredd i Aspose.GIS för .NET

I det här **vektorlagrets exemplet** kommer du att lära dig hur man ställer in fältbredd för ett attribut när du skapar en Shapefile med Aspose.GIS för .NET. Vi går igenom varje steg, från att importera namnrymder till att lägga till ett objekt, och förklarar varför kontroll av attributlängd är viktigt för dataintegritet och interoperabilitet med andra GIS-verktyg.

## Snabba svar
- **Vad är huvudsyftet med den här guiden?** Att visa hur du ställer in fältbredd för ett attribut i en shapefile med Aspose.GIS för .NET.  
- **Vilken klass definierar fältbredden?** `FeatureAttribute.Width`.  
- **Behöver jag en licens för att köra koden?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilket filformat används i exemplet?** ESRI Shapefile (`.shp`).  
- **Kan jag ändra bredden efter att lagret har skapats?** Nej – bredden måste definieras innan du lägger till objekt.

## Vad är fältbredd och varför är det viktigt?
Fältbredd (även kallad attributlängd) är det maximala antalet tecken som ett strängfält kan lagra i en Shapefiles DBF-komponent. Att ställa in rätt bredd förhindrar tyst trunkering, garanterar att andra GIS‑applikationer läser data exakt som du skrev in dem, och håller filstorleken förutsägbar — varje extra tecken lägger till en byte per post.

## Förutsättningar
- **Aspose.GIS för .NET-biblioteket** – ladda ner från [download link](https://releases.aspose.com/gis/net/).  
- **Utvecklingsmiljö** – Visual Studio 2022, Visual Studio Code eller någon IDE som stödjer .NET 6+.  
- **Skrivbehörighet** – en mapp på disken där den genererade shapefilen kommer att sparas.

## Varför använda ett vektorlagrets exempel med definierad bredd?
Aspose.GIS stödjer **mer än 30 GIS‑filformat**, inklusive Shapefile, GeoJSON, KML och GML. När du uttryckligen ställer in fältbredd undviker du standardgränsen på 255 tecken, vilket onödigt kan blåsa upp `.dbf`‑filen med upp till 255 × antalPoster byte. I stora dataset motsvarar detta märkbara lagringsbesparingar.

## Hur man ställer in fältbredd för ett attribut?
I det här avsnittet laddar eller skapar vi ett `VectorLayer` som pekar på mål‑`.shp`‑filen, definierar ett strängattribut med en exakt bredd och lägger sedan till objekt — allt i några koncisa satser. `VectorLayer` representerar ett vektordataset såsom en Shapefile och ger åtkomst till dess geometri och attributtabell. Nedan är det direkta, handlingsbara receptet som du kan följa steg‑för‑steg:

Ladda eller skapa ett `VectorLayer` som pekar på mål‑`.shp`‑filen, deklarera ett strängattribut med namnet **wide** med `Width = 120`, och lägg sedan till ett objekt vars värde följer den 120‑teckensgränsen. Aspose.GIS kommer automatiskt att trunkera längre strängar till den definierade bredden, vilket bevarar datakonsistens utan att kasta undantag.

### Importera namnrymder
`FeatureAttribute`, `VectorLayer` och relaterade typer finns i namnrymden `Aspose.Gis`. Importera dem högst upp i din fil:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Skapa VectorLayer
`VectorLayer`‑klassen representerar en vektordatakälla (t.ex. en Shapefile). Det är behållaren som lagrar objekt och deras attribut.

`VectorLayer`‑klassen är Aspose.GIS representation av ett vektordataset, som hanterar geometri och attributtabeller i minnet. Skapa en instans som pekar på en ny eller befintlig `.shp`‑fil.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Lägg till attribut med specifik längd
Definiera ett strängattribut kallat **wide** och sätt dess `Width`‑egenskap till 120 tecken. Detta är huvudsteget i **vektorlagrets exempel**.

`FeatureAttribute`‑objektet beskriver en kolumn i attributtabellen; att sätta `Width = 120` instruerar Shapefile‑skrivaren att allokera exakt 120 byte för varje post i detta fält.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Proffstips:** `Width`‑egenskapen gäller endast för strängattribut. Numeriska, datum‑ eller booleska fält ignorerar `Width` eftersom deras storlek är fast enligt datatypen.

### Konstruera och lägg till objekt
Skapa ett `Feature`, tilldela ett värde som ryms inom 120‑teckensgränsen, och lägg till det i lagret. Om strängen överskrider gränsen trunkerar Aspose.GIS den tyst till den definierade bredden, vilket bevarar dataintegritet.

`Feature`‑klassen kapslar geometrin och attributvärdena; efter att attributet har satts, skriver anropet `layer.Add(feature)` posten till Shapefilen.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Om du försöker tilldela en längre sträng kommer Aspose.GIS att trunkera den till den definierade bredden, vilket bevarar dataintegritet.

## Vanliga fallgropar & felsökning
- **Glömt att sätta `Width` innan du lägger till attributet?** Standardbredden är 255 tecken; att ändra den senare påverkar inte redan skapade fält. Definiera alltid bredden först.  
- **Använder du en icke‑strängdatatyp?** `Width` ignoreras för numeriska eller datumfält; se till att attributets `AttributeDataType` är `String`.  
- **Fel: “Field not found”?** Attributnamn är skiftlägeskänsliga. Verifiera att namnet som används i `SetValue` exakt matchar namnet som definierats i schemat.  
- **Oväntad ökning av filstorlek?** Större bredd ökar `.dbf`‑storleken linjärt. För 10 000 poster ger en breddökning från 50 till 120 ungefär 700 KB.

## Vanliga frågor
**Q: Hur kan jag skaffa en tillfällig licens för Aspose.GIS för .NET?**  
A: Du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta community‑support för Aspose.GIS för .NET?**  
A: Besök [Aspose.GIS‑forumet](https://forum.aspose.com/c/gis/33) för hjälp från andra användare och officiella svar.

**Q: Finns det en gratis provversion av Aspose.GIS för .NET?**  
A: Ja, utforska den [gratis provversionen](https://releases.aspose.com/) för att uppleva hela funktionsuppsättningen utan kostnad.

**Q: Hur köper jag en licens för Aspose.GIS för .NET?**  
A: Köp din licens [här](https://purchase.aspose.com/buy).

**Q: Var kan jag hitta dokumentationen för Aspose.GIS för .NET?**  
A: Se [dokumentationen](https://reference.aspose.com/gis/net/) för omfattande API‑detaljer.

**Q: Kan jag ändra fältbredden efter att lagret har skapats?**  
A: Nej. Fältbredden måste definieras innan attributet läggs till; för att ändra den måste du återskapa lagret med det nya schemat.

**Q: Påverkar en större bredd filstorleken?**  
A: Shapefiles lagrar strängfält med fast längd, så en ökning av bredden ökar `.dbf`‑filens storlek proportionellt mot antalet poster.

## Slutsats
Detta **vektorlagrets exempel** demonstrerade hur man ställer in fältbredd för ett attribut i en Shapefile med Aspose.GIS för .NET, och visade hur man lägger till ett attribut med en specifik längd på ett effektivt sätt. Genom att kontrollera attributbredd undviker du datatrunkering, håller filstorlekar optimala och säkerställer sömlös interoperabilitet med andra GIS‑plattformar. Experimentera med olika bredder, utforska [dokumentationen](https://reference.aspose.com/gis/net/), och lås upp hela potentialen för geospatial utveckling med Aspose.GIS.

---

**Senast uppdaterad:** 2026-05-16  
**Testad med:** Aspose.GIS 24.11 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hämta lagerattribut – Hämta lagerattributinformation med Aspose.GIS för .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Hur man hämtar attributvärde (standard) med Aspose.GIS för .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Skapa vektorlager i File GDB – Aspose.GIS .NET-handledning](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}