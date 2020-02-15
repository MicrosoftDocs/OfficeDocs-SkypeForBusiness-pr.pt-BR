---
title: Planejar o controle de chamada remota no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: O controle de chamada remota era um recurso em versões anteriores do Lync Server, que permitia aos usuários controlar seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pela chamada via trabalho. Nas versões do cliente para o Skype for Business Server 2015 e em frente, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982796"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planejar o controle de chamada remota no Skype for Business
 
O controle de chamada remota era um recurso em versões anteriores do Lync Server, que permitia aos usuários controlar seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pela chamada via trabalho.  *Nas versões do cliente para o Skype for Business Server 2015 e em frente, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.* 
  
 Os usuários de controle de chamada remota em sua organização hospedados em servidores front-end que executam o Lync Server podem continuar a usar o controle de chamada remota, mesmo que eles estejam usando um cliente Skype for Business. No entanto, para qualquer usuário hospedado no Skype for Business Server, não há suporte para o controle de chamada remota. Consulte a tabela a seguir para combinações de servidor/cliente e se eles podem suportar o controle de chamada remota ou ligar via trabalho.
  
||**Cliente Skype for Business com interface do usuário do Skype habilitada**|**Cliente Skype for Business com interface do usuário do Lync habilitado**|**Cliente 2016 do Skype for Business**|**Cliente do Lync 2013**|**Cliente do Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Ligar via trabalho  <br/> |1  <br/> |Ligar via trabalho  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |1  <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |
| Lync Server 2010 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |1  <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |
   
1. Nenhum dos recursos tem suporte.
  
Para obter mais informações, consulte [controle de chamada remota](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.
  
## <a name="see-also"></a>Confira também

[Planejar a chamada via trabalho no Skype for Business Server](call-via-work.md)
  
[Comparação de recursos do cliente de desktop para o Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Fazer uma chamada do Skype for Business, mas usar seu telefone de mesa PBX para áudio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

