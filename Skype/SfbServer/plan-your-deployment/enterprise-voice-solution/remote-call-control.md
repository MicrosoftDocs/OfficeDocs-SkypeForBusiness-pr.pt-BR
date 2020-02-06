---
title: Plano de controle de chamada remota no Skype for Business
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
description: O controle de chamada remota foi um recurso nas versões anteriores do Lync Server que permitia aos usuários controlar os telefones PBX com o Lync Server. No Skype for Business Server, este recurso foi substituído por meio da chamada por meio do trabalho. Nas versões do cliente para o Skype for Business Server 2015 e encaminhadas, o controle de chamada remota não está mais disponível para ser configurado no cliente e foi removido para uso.
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802501"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Plano de controle de chamada remota no Skype for Business
 
O controle de chamada remota foi um recurso nas versões anteriores do Lync Server que permitia aos usuários controlar os telefones PBX com o Lync Server. No Skype for Business Server, este recurso foi substituído por meio da chamada por meio do trabalho.  *Nas versões do cliente para o Skype for Business Server 2015 e encaminhadas, o controle de chamada remota não está mais disponível para ser configurado no cliente e foi removido para uso.* 
  
 Os usuários de controle de chamada remota em sua organização que são hospedados em servidores front-end que executam o Lync Server podem continuar a usar o controle de chamada remota, mesmo se estiverem usando um cliente Skype for Business. No entanto, para todos os usuários hospedados no Skype for Business Server, não há suporte para o controle de chamada remota. Consulte a tabela a seguir das combinações servidor/cliente e se elas podem suportar o controle de chamada remota ou Telefonar via Trabalho.
  
||**Cliente Skype for Business com interface do usuário do Skype habilitada**|**Interface do usuário do Skype for Business com interface do usuário do Lync habilitada**|**Cliente Skype for Business 2016**|**Cliente do Lync 2013**|**Lync 2010 Client**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Chamada via Trabalho  <br/> |1 <br/> |Chamada via Trabalho  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |um <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |
| Lync Server 2010 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |um <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |
   
1. Não há suporte para nenhum recurso.
  
Para obter mais informações, consulte [controle de chamada remota](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.
  
## <a name="see-also"></a>Confira também

[Planejar a chamada por meio do trabalho no Skype for Business Server](call-via-work.md)
  
[Comparação de recursos do cliente de desktop do Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Fazer uma chamada no Skype for Business, mas usar seu telefone de mesa PBX para áudio](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

