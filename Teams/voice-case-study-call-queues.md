---
title: Teams de caso contoso de voz
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams de caso de voz para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121289"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Estudo de caso da Contoso: Atendimentos automáticos e filas de chamada

A Contoso estava familiarizada com os atendimentos automáticos e filas de chamada de suas implantações Skype for Business local. Para entender como configurar os atendimentos automáticos de nuvem e filas de chamada, eles revisaram Plan for Teams auto [attendants and call queues](plan-auto-attendant-call-queue.md).

## <a name="requirements-depending-on-site-type"></a>Requisitos dependendo do tipo de site

Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:

- Tipo de site A: sistemas de telefonia herdados tradicionais 

  Tipo de site A necessário para manter o mesmo número de telefone associado à recepcionista como o número de seus atendimentos automáticos. Os principais departamentos de cada um desses sites teriam suas próprias filas de chamada que seriam roteada para os membros da equipe. Houve uma mistura de sites que usavam Sistema de Telefonia roteamento direto e Sistema de Telefonia com planos de chamadas.  

- Tipo de site B: Skype for Business Enterprise Voice 

  O Tipo de Site B tinha atendentes automáticos e filas de chamada existentes que precisavam migrar para Teams. A Contoso precisava manter os números de telefone associados aos atendimentos automáticos. A Contoso moveu a maioria desses sites para Sistema de Telefonia com Planos de Chamada. No entanto, nos poucos locais em que Planos de Chamadas não estava disponível, a Contoso moveu esses sites para uma configuração de Roteamento Direto.  

- Tipo de site C: Skype for Business Enterprise Voice & sistema de telefonia herdado tradicional 

  O Tipo de Site C tinha os atendimentos automáticos existentes que residiam no sistema de telefonia herdado tradicional. As decisões e configurações para este site eram as mesmas que o Tipo de Site A.   

- Para todos os tipos de site, a Contoso fez as seguintes perguntas:

  - P: Vamos usar números novos ou existentes? 
    R: A Contoso decidiu usar números de telefone existentes para serem atribuídos à conta de serviço do atendimento automático. 

  - P: Quando o atendimento automático estará disponível para aceitar chamadas de entrada? 
    R: a Contoso decidiu definir o horário comercial e ter chamadas recebidas após o horário comercial redirecionadas para um atendimento automático "pós-horário".  

  - P: Como as chamadas serão roteados para membros em uma fila de chamadas: roteamento de robin de atendimento, série ou round? 
    R: a Contoso decidiu usar o roteamento de atendimento, 

  - P: Como determinaremos quando um usuário deve ou não receber uma chamada? 
    R: A Contoso decidiu usar opções de tratamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença. 


## <a name="configuration"></a>Configuração

As etapas para configurar um atendimento automático e uma fila de chamada incluem o seguinte descrito em [Gerenciar contas de recursos](manage-resource-accounts.md): 

1. Obtenha um número de serviço. 

2. Obtenha uma licença Sistema de Telefonia de usuário virtual ou uma licença de Sistema de Telefonia paga para usar com a conta de recurso ou uma Sistema de Telefonia de usuário.

3. Crie a conta de recurso. Um atendimento automático ou fila de chamada é necessário para ter uma conta de recurso associada. 

4. Atribua a Sistema de Telefonia ou uma Sistema de Telefonia - Licença de usuário virtual à conta de recurso. Para obter mais informações, [consulte Microsoft 365 Sistema de Telefonia – Licença do usuário virtual.](./teams-add-on-licensing/virtual-user.md)

5. Atribua um número de telefone de serviço à conta de recurso à que você atribuiu licenças. 

6. Criar uma fila Sistema de Telefonia de chamada ou atendimento automático 

7. Vincule a conta de recurso com uma fila de chamada ou um atendimento automático. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites com Sistema de Telefonia com roteamento direto 

A Contoso precisou configurar o número de telefone fornecido pela operadora local como o número de serviço no Office 365. 

- Para configurar um número de telefone disponível por meio do Roteamento Direto, a Contoso seguiu as instruções localizadas em [Gerenciar Contas de Recursos.](manage-resource-accounts.md) Como Office 365 não está ciente dos números de telefone locais, a Contoso usou o PowerShell para concluir a instalação.   

- Para configurar o atendimento automático na nuvem, a Contoso seguiu as etapas descritas [em Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md) 

- Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em [Create a Cloud call queue](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites com Sistema de Telefonia com plano de chamada

A Contoso precisou por o número de telefone usado para Skype for Business Enterprise Voice automáticos para Sistema de Telefonia Office 365. Isso permitiu que o mesmo número fosse atribuído como um número de serviço para uso como um atendimento automático. 

- Para portabilidade do número de telefone, a Contoso seguiu as instruções em [Transferir](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) números de telefone para Teams e obteve orientações adicionais em Gerenciar números de telefone [para sua organização](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para configurar um atendimento automático na nuvem, a Contoso seguiu as etapas descritas em [Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)

-  Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em [Create a Cloud call queue](create-a-phone-system-call-queue.md).  

