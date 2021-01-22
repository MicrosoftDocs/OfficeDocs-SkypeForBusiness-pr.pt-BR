---
title: Estudo de caso da Contoso Voice Teams
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
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918727"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Estudo de caso da Contoso: atendedores automáticos e filas de chamadas

A contoso já está familiarizada com atendedores automáticos e filas de chamadas na implantação do Skype for Business local. Para compreender como configurar atendedores automáticos na nuvem e filas de chamadas, eles revisaram o [plano para atendedores automáticos e filas de chamadas do teams](plan-auto-attendant-call-queue.md).

## <a name="requirements-depending-on-site-type"></a>Requisitos dependendo do tipo de site

Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:

- Tipo de site A: sistemas tradicionais de telefonia herdada 

  Tipo de site A necessário para manter o mesmo número de telefone associado ao recepcionista como o número dos atendedores automáticos. Os principais departamentos para cada um desses sites teriam suas próprias filas de chamadas que roteiariam para os membros da equipe. Houve uma mistura de sites que usaram o sistema telefônico com roteamento direto e sistema telefônico com planos de chamada.  

- Tipo de site B: Skype for Business Enterprise Voice 

  O tipo de site B tinha atendedores automáticos e filas de chamadas existentes que precisavam migrar para o Microsoft Teams. A contoso precisou manter os números de telefone associados aos atendedores automáticos. A contoso moveu a maioria desses sites para o sistema telefônico com planos de chamadas. No entanto, nos poucos locais em que os planos de chamada não estavam disponíveis, a contoso moveu esses sites para uma configuração de roteamento direto.  

- Tipo de site C: Skype for Business Enterprise Voice & sistema de telefonia tradicional herdado 

  Tipo de site C tinha atendedores automáticos existentes que residiam no sistema de telefonia tradicional herdada. As decisões e configurações para este site foram iguais às do tipo de site A.   

- Para todos os tipos de sites, a contoso fez as seguintes perguntas:

  - P: vamos usar números novos ou existentes? 
    R: a Contoso decidiu usar números de telefone existentes para ser atribuído à conta de serviço para o atendedor automático. 

  - P: quando o atendedor automático estará disponível para aceitar as chamadas recebidas? 
    R: a Contoso decidiu definir o horário comercial e ter chamadas recebidas após o horário comercial ser redirecionado para o atendedor automático de "depois de horas".  

  - P: como as chamadas serão encaminhadas para os membros de uma fila de chamadas: roteamento de atendedor, serial ou Round Robin? 
    R: contoso decidiu usar o roteamento de atendedor, 

  - P: como determinamos quando um usuário deve ou não ter uma chamada? 
    R: a Contoso decidiu usar as opções de gerenciamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença. 


## <a name="configuration"></a>Configuração

As etapas para configurar um atendedor automático e uma fila de chamada incluem o seguinte descrito em [gerenciar contas de recursos](manage-resource-accounts.md): 

1. Obter um número de serviço. 

2. Obter um sistema telefônico gratuito-licença de usuário virtual ou uma licença do sistema de telefonia paga para uso com a conta do recurso ou uma licença do sistema de telefonia.

3. Criar a conta do recurso. Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada. 

4. Atribua o sistema telefônico ou um sistema telefônico-licença de usuário virtual para a conta do recurso. Para obter mais informações, consulte [sistema telefônico Microsoft 365 – licença de usuário virtual](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).

5. Atribua um número de telefone de serviço à conta de recurso à qual você atribuiu licenças. 

6. Criar uma fila de chamadas do sistema telefônico ou um atendedor automático 

7. Vincule a conta do recurso a uma fila de chamadas ou atendedor automático. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites com sistema telefônico com roteamento direto 

A contoso precisou configurar o número de telefone fornecido pela operadora local como o número de serviço do Office 365. 

- Para configurar um número de telefone disponível por meio do direcionamento direto, a contoso seguiu as instruções localizadas em [gerenciar contas de recursos](manage-resource-accounts.md). Como o Office 365 não reconhece os números de telefone locais, a contoso usava o PowerShell para concluir a configuração.   

- Para configurar o atendedor automático na nuvem, a contoso seguiu as etapas descritas em [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md). 

- Para configurar uma fila de chamada em nuvem, a contoso seguiu as etapas descritas em [criar uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites com o sistema telefônico com plano de chamadas

A Contoso tinha que portar o número de telefone usado para atendedores automáticos do Skype for Business Enterprise Voice ao sistema telefônico do Office 365. Isso permitia que o mesmo número fosse atribuído como um número de serviço para uso como atendedor automático. 

- Para portar o número de telefone, a contoso seguiu as instruções em [transferir números de telefone para o Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) e obter orientação adicional em [gerenciar números de telefone para sua organização](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

- Para configurar um atendedor automático na nuvem, a contoso seguiu as etapas descritas em [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).

-  Para configurar uma fila de chamada em nuvem, a contoso seguiu as etapas descritas em [criar uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).  

 