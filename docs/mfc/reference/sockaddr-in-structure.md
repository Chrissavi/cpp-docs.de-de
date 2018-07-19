---
title: SOCKADDR_IN-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e5ec6ebf4329ff03c75240dc7cec93e9ba46331
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885737"
---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN-Struktur
In der Internetadressenfamilie wird die `SOCKADDR_IN`-Struktur von Windows Sockets verwendet, um eine lokale oder Remoteendpunktadresse festlegen, mit der ein Socket verbunden werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct sockaddr_in{  
    short sin_family;  
    unsigned short sin_port;  
struct in_addr sin_addr;  
    char sin_zero[8];  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *sin_family*  
 -Adressenfamilie (muss AF_INET sein).  
  
 *sin_port*  
 IP-Port.  
  
 *sin_addr*  
 IP-Adresse.  
  
 *sin_zero*  
 Auffüllung, um die Struktur ebenso groß wie `SOCKADDR` zu machen.  
  
## <a name="remarks"></a>Hinweise  
 Dies ist die Form der `SOCKADDR`-Struktur speziell für die Internetadressenfamilie; sie kann in `SOCKADDR` umgewandelt werden.  
  
 Die IP-Adressenkomponente dieser Struktur ist vom Typ `IN_ADDR`. Die `IN_ADDR` Struktur wird in Windows Sockets-Headerdatei WINSOCK definiert. H wie folgt:  
  
```  
struct in_addr {
    union {
        struct {  
            unsigned char s_b1, s_b2, s_b3, s_b4;  
        } S_un_b;  
        struct {  
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;  
};  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winsock2.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR-Struktur](../../mfc/reference/sockaddr-structure.md)
