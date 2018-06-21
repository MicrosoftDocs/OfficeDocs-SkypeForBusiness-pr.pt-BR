---
title: Definir um novo tronco
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Você pode definir um tronco de (SIP) do protocolo de iniciação de nova sessão, fornecendo as seguintes informações:'
ms.openlocfilehash: 6f7dd7d8ab3aaa86eef78a5973194012e2e3b32c
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19978052"
---
# <a name="define-a-new-trunk"></a>Definir um novo tronco
 
Você pode definir um tronco de (SIP) do protocolo de iniciação de nova sessão, fornecendo as seguintes informações:
  
- **Nome do tronco**: nome exclusivo na sua topologia que identificará esse tronco
    
- **Gateway de PSTN associado**: selecione um gateway PSTN implantado e configurado em sua implantação da lista
    
- **Porta de escuta do gateway IP/PSTN**: porta na qual o gateway IP-PBX ou PSTN escutará. Deve ser exclusivo de todos os outras tronco portas de escuta configuradas em sua implantação
    
- **Protocolo de transporte SIP**: selecione na lista TCP ou TLS
    
- **Servidor de mediação associado**: selecione na lista um servidor de mediação que é implantado e configurado em sua implantação
    
- **Porta do servidor de mediação associado**: defina o valor da porta igual ao valor de porta TCP ou TLS do servidor de mediação que usará esse tronco SIP 
    
## <a name="see-also"></a>Consulte também

[Tronco M:N no Skype para Business Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Como implementar o tronco SIP?](http://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)