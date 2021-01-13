---
title: Planejar o controle de chamada remota no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pelo Telefonar via Trabalho. Nas versões de cliente do Skype for Business Server 2015 e no futuro, o controle de chamada remota não está mais disponível para configuração no cliente e foi removido para uso.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813511"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planejar o controle de chamada remota no Skype for Business
 
O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pelo Telefonar via Trabalho.  *Nas versões de cliente do Skype for Business Server 2015 e no futuro, o controle de chamada remota não está mais disponível para configuração no cliente e foi removido para uso.* 
  
 Os usuários de controle de chamada remota em sua organização que estão em servidores front-end executando o Lync Server podem continuar a usar o controle de chamada remota, mesmo se eles estão usando um cliente do Skype for Business. No entanto, para todos os usuários que estão no Skype for Business Server, o controle de chamada remota não é suportado. Consulte a tabela a seguir para combinações de servidor/cliente e se elas podem suportar o controle de chamada remota ou Telefonar via Trabalho.
  
||**Cliente Skype for Business com interface do usuário do Skype habilitada**|**Cliente Skype for Business com interface do usuário do Lync habilitada**|**Cliente Skype for Business 2016**|**Cliente Lync 2013**|**Cliente do Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype para Business Server <br/> |Telefonar via Trabalho  <br/> |1  <br/> |Telefonar via Trabalho  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |1  <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |
| Lync Server 2010 <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |1  <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |
   
1. Nenhum dos recursos é suportado.
  
Para obter mais informações, [consulte Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.
  
## <a name="see-also"></a>Confira também

[Planejar o Telefonar via Trabalho no Skype for Business Server](call-via-work.md)
  
[Comparação de recursos do cliente de desktop para o Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Fazer uma chamada do Skype for Business, mas usar seu telefone de mesa PBX para áudio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

