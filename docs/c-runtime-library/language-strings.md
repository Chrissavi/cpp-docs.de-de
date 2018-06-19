---
title: Sprachenzeichenfolgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92ad129a5703f509cfd9543497cceffae3a6e7b3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391362"
---
# <a name="language-strings"></a>Language Strings
Die Funktionen `setlocale` und `_create_locale` können die von der Windows NLS-API unterstützten Sprachen auf Betriebssystemen verwenden, die nicht die Unicode-Codepage verwenden. Eine Liste der unterstützten Sprachen nach Betriebssystemversion finden Sie in der [National Language Support (NLS) API Reference](https://www.microsoft.com/resources/msdn/goglobal/default.mspx) (API-Referenz zur Unterstützung der Landessprache [National Language Support, NLS]). Die Sprachenzeichenfolge kann ein beliebiger Wert aus den Spalten für die **Sprache** und die **Abkürzung der Sprachnamen** der Liste der unterstützten Sprachen sein. Weitere Informationen zur Sprachunterstützung nach Betriebssystemversion finden Sie unter [Appendix A: Product Behavior](http://msdn.microsoft.com/goglobal/bb896001.aspx) in „[MS-LCID]: Windows Language Code Identifier (LCID) Reference“ (Anhang A: Produktverhalten in „[MS-LCID]: Windows-Sprachcodebezeichner – Referenz“).   
  
Die Implementierung der C-Laufzeitbibliothek unterstützt ebenfalls diese Sprachenzeichenfolgen:  
  
|Sprachenzeichenfolge|Entsprechender Gebietsschemaname|  
|---------------------|----------------------------|  
|american|en-US|  
|american english|en-US|  
|american-english|en-US|  
|australian|en-AU|  
|belgian|nl-BE|  
|canadian|en-CA|  
|chh|zh-HK|  
|chi|zh-SG|  
|chinese|zh|  
|chinese-hongkong|zh-HK|  
|chinese-simplified|zh-CN|  
|chinese-singapore|zh-SG|  
|chinese-traditional|zh-TW|  
|dutch-belgian|nl-BE|  
|english-american|en-US|  
|english-aus|en-AU|  
|english-belize|en-BZ|  
|english-can|en-CA|  
|english-caribbean|en-029|  
|english-ire|en-IE|  
|english-jamaica|en-JM|  
|english-nz|en-NZ|  
|english-south africa|en-ZA|  
|english-trinidad y tobago|en-TT|  
|english-uk|en-GB|  
|english-us|en-US|  
|english-usa|en-US|  
|french-belgian|fr-BE|  
|french-canadian|fr-CA|  
|french-luxembourg|fr-LU|  
|french-swiss|fr-CH|  
|german-austrian|de-AT|  
|german-lichtenstein|de-LI|  
|german-luxembourg|de-LU|  
|german-swiss|de-CH|  
|irish-english|en-IE|  
|italian-swiss|it-CH|  
|norwegian|Nein|  
|norwegian-bokmal|nb-NO|  
|norwegian-nynorsk|nn-NO|  
|portuguese-brazilian|pt-BR|  
|spanish-argentina|es-AR|  
|spanish-bolivia|es-BO|  
|spanish-chile|es-CL|  
|spanish-colombia|es-CO|  
|spanish-costa rica|es-CR|  
|spanish-dominican republic|es-DO|  
|spanish-ecuador|es-EC|  
|spanish-el salvador|es-SV|  
|spanish-guatemala|es-GT|  
|spanish-honduras|es-HN|  
|spanish-mexican|es-MX|  
|spanish-modern|es-ES|  
|spanish-nicaragua|es-NI|  
|spanish-panama|es-PA|  
|spanish-paraguay|es-PY|  
|spanish-peru|es-PE|  
|spanish-puerto rico|es-PR|  
|spanish-uruguay|es-UY|  
|spanish-venezuela|es-VE|  
|swedish-finland|sv-FI|  
|swiss|de-CH|  
|uk|en-GB|  
|mehreren|en-US|  
|usa|en-US|  
  
## <a name="see-also"></a>Siehe auch  
 [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Länder-/Regionszeichenfolgen](../c-runtime-library/country-region-strings.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)