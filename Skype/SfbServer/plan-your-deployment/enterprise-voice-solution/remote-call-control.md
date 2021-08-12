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
description: O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. Em Skype for Business Server, esse recurso foi substituído por Call Via Work. Nas versões do cliente para Skype for Business Server 2015 e adiante, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.
ms.openlocfilehash: c7b4156c90810206824d922af17b83381a64afe17a3a927825eae91445245cfa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302365"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planejar o controle de chamada remota no Skype for Business
 
O controle de chamada remota era um recurso em versões anteriores do Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. Em Skype for Business Server, esse recurso foi substituído por Call Via Work.  *Nas versões do cliente para Skype for Business Server 2015 e adiante, o controle de chamada remota não está mais disponível para configurar no cliente e foi removido para uso.* 
  
 Os usuários de controle de chamada remota em sua organização que estão em servidores front-end executando o Lync Server podem continuar a usar o controle de chamada remota, mesmo que eles estão usando um cliente Skype for Business. No entanto, para todos os usuários que estão Skype for Business Server, não há suporte para o controle de chamada remota. Consulte a tabela a seguir para combinações de servidor/cliente e se elas podem suportar o controle de chamada remota ou Chamada via Trabalho.
  
||**Skype for Business Cliente Com Skype interface do usuário habilitada**|**Skype for Business Cliente com a interface do usuário do Lync habilitada**|**Skype for Business 2016 Client**|**Cliente Lync 2013**|**Cliente do Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype para Business Server <br/> |Chamada via Trabalho  <br/> |1 <br/> |Chamada via Trabalho  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |1 <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |
| Lync Server 2010 <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |1 <br/> |Controle de Chamada Remota  <br/> |Controle de Chamada Remota  <br/> |
   
1. Nenhum dos recursos é suportado.
  
Para obter mais informações, consulte [Controle de Chamada Remota](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) na documentação do Lync Server 2013.
  
## <a name="see-also"></a>Confira também

[Planejar a chamada via trabalho no Skype for Business Server](call-via-work.md)
  
[Comparação de recursos do cliente de área de trabalho para Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Faça uma Skype for Business, mas use seu telefone de mesa PBX para áudio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)