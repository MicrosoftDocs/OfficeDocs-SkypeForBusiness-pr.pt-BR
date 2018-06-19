---
title: Planejamento de controle de chamada remota no Skype for Business 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Controle de chamada remota era um recurso nas versões anteriores do Microsoft Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho. Nas versões do cliente para Skype para Business Server 2015 e de chamada remoto, encaminhar de passando para o controle não está mais disponível para configurar no cliente e foi removido para uso.
ms.openlocfilehash: 83e3138d11113d46b3225980205150f79d85235c
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504030"
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a>Planejamento de controle de chamada remota no Skype for Business 2015
 
Controle de chamada remota era um recurso nas versões anteriores do Microsoft Lync Server que permitia aos usuários controlar seus telefones PBX com o Lync Server. Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho.  *Nas versões do cliente para Skype para Business Server 2015 e de chamada remoto, encaminhar de passando para o controle não está mais disponível para configurar no cliente e foi removido para uso.* 
  
 Usuários de controle de chamada remota em sua organização hospedados em servidores Front-End executando o Lync Server podem continuar a usar o controle de chamada remota, mesmo que estejam usando um Skype para o cliente de negócios. No entanto, para todos os usuários hospedagem no Skype para Business Server, o controle de chamada remota não é suportado. Consulte a tabela a seguir das combinações servidor/cliente e se elas podem suportar o controle de chamada remota ou Telefonar via Trabalho.
  
||**Skype para negócios 2015 cliente com Skype UI habilitado**|**Skype para negócios 2015 With Lync UI do cliente habilitado**|**Skype para Business 2016 Client**|**Cliente do Lync 2013**|**Cliente do Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server 2015 <br/> |Chamada via Trabalho  <br/> |1 <br/> |Chamada via Trabalho  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |1 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |
| Lync Server 2010 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |1 <br/> |Controle de chamada remota  <br/> |Controle de chamada remota  <br/> |
   
1. Nenhum recurso é suportado.
  
Para obter mais informações, consulte [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) na documentação do Lync Server 2013.
  
## <a name="see-also"></a>Consulte também

[Planejar para chamada Via trabalho no Skype para Business Server 2015](call-via-work.md)
  
[Comparação de recursos do cliente de desktop do Skype para negócios](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Tornar um Skype para chamada de negócios, mas usar seu telefone de mesa PBX para áudio](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)