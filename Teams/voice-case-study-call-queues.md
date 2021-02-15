---
title: Estudo de caso do Teams voice Contoso
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
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918727"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Estudo de caso da Contoso: Atendimentos automáticos e filas de chamada

A Contoso estava familiarizada com os atendimentos automáticos e filas de chamadas da implantação local do Skype for Business. Para entender como configurar os atendimentos automáticos na nuvem e filas de chamada, eles revisaram o Plano para os [atendimentos automáticos e filas de chamada do Teams.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Requisitos dependendo do tipo de site

Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:

- Tipo de Site A: sistemas tradicionais de telefonia herdados 

  O Tipo de Site A é necessário para manter o mesmo número de telefone associado ao recepcionista do número dos seus atenderes automáticos. Os principais departamentos de cada um desses sites teriam suas próprias filas de chamada que seriam encaminhada para os membros da equipe. Havia uma combinação de sites que usavam o Sistema de Telefonia com Roteamento Direto e Sistema de Telefonia com Planos de Chamada.  

- Tipo de site B: Skype for Business Enterprise Voice 

  O tipo de site B tinha os atendimentos automáticos e filas de chamada existentes que precisavam migrar para o Teams. A Contoso precisava manter os números de telefone associados aos atenderes automáticos. A Contoso moveu a maioria desses sites para o Sistema de Telefonia com Planos de Chamada. No entanto, nos poucos locais em que os Planos de Chamada não estão disponíveis, a Contoso moveu esses sites para uma configuração de Roteamento Direto.  

- Tipo de Site C: Skype for Business Enterprise Voice & tradicional sistema de telefonia herdado 

  O Tipo de Site C tinha os participantes automáticos existentes que residiam no sistema de telefonia herdado tradicional. As decisões e configurações deste site eram as mesmas que o Tipo de Site A.   

- Para todos os tipos de site, a Contoso fez as seguintes perguntas:

  - P: Vamos usar números novos ou existentes? 
    R: A Contoso decidiu usar números de telefone existentes para serem atribuídos à conta de serviço do atender automaticamente. 

  - P: Quando o atender automático estará disponível para aceitar chamadas recebidas? 
    R: A Contoso decidiu definir o horário comercial e ter as chamadas recebidas após o horário comercial redirecionadas para um atender automático "horas extras".  

  - P: Como as chamadas serão roteada para membros em uma fila de chamadas: roteamento de atendimento, série ou round? 
    R: A Contoso decidiu usar o roteamento do Attendant, 

  - P: Como determinaremos quando um usuário deve ou não receber uma chamada? 
    R: A Contoso decidiu usar as opções de tratamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença. 


## <a name="configuration"></a>Configuração

As etapas para configurar um atendimento automático e uma fila de chamada incluem os seguintes descritos em [Gerenciar contas de recursos:](manage-resource-accounts.md) 

1. Obtenha um número de serviço. 

2. Obtenha uma licença gratuita do Sistema de Telefonia – Usuário Virtual ou uma licença paga do Sistema telefônico para usar com a conta de recurso ou uma licença do Sistema de Telefonia.

3. Criar a conta de recurso. Um atendimento automático ou fila de chamada é necessário para ter uma conta de recurso associada. 

4. Atribua o Sistema telefônico ou um sistema telefônico – licença de usuário virtual à conta de recurso. Para obter mais informações, consulte [Microsoft 365 Phone System – Licença de Usuário Virtual.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)

5. Atribua um número de telefone de serviço à conta de recurso à onde você atribuiu licenças. 

6. Criar uma fila de chamadas do Sistema de Telefonia ou um atender automático 

7. Vincule a conta de recurso com uma fila de chamada ou um atendimento automático. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites com Sistema telefônico com roteamento direto 

A Contoso teve que configurar o número de telefone fornecido pela operadora local como o número de serviço no Office 365. 

- Para configurar um número de telefone disponível por meio do Roteamento Direto, a Contoso seguiu as instruções localizadas em [Gerenciar Contas de Recursos.](manage-resource-accounts.md) Como o Office 365 não está ciente dos números de telefone locais, a Contoso usou o PowerShell para concluir a configuração.   

- Para configurar o atendimento automático na nuvem, a Contoso seguiu as etapas descritas [em Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md) 

- Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em Criar uma fila [de chamada na nuvem.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites com Sistema de Telefonia com plano de Chamada

A Contoso teve que fazer a portabilidade do número de telefone usado para os atenderes automáticos do Skype for Business Enterprise Voice para o Sistema Telefônico do Office 365. Isso permitiu que o mesmo número fosse atribuído como um número de serviço para ser usado como um atendimento automático. 

- Para fazer a portabilidade do número de telefone, a Contoso seguiu as instruções em Transferir números de telefone para o [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e obteve orientações adicionais em Gerenciar números de [telefone para sua organização.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

- Para configurar um atendimento automático na nuvem, a Contoso seguiu as etapas descritas [em Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)

-  Para configurar uma fila de chamada na nuvem, a Contoso seguiu as etapas descritas em Criar uma fila [de chamada na nuvem.](create-a-phone-system-call-queue.md)  

 