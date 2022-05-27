---
title: 'Teams caso contoso de voz: atendedores automáticos e filas de chamadas'
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
description: 'Teams estudo de caso de voz para empresas multinacionais: atendedores automáticos e filas de chamadas'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c0b6da7bf00fd4e62cf3e9b3b08074bf1b42788
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681712"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Estudo de caso da Contoso: Atendedores automáticos e filas de chamadas

A Contoso estava familiarizada com atendedores automáticos e filas de chamadas de sua implantação Skype for Business local. Para entender como configurar atendedores automáticos de nuvem e filas de chamadas, eles revisaram o Plano para Teams atendedores [automáticos e filas de chamadas](plan-auto-attendant-call-queue.md).

## <a name="requirements-depending-on-site-type"></a>Requisitos dependendo do tipo de site

Dependendo do tipo de site, a Contoso tinha as seguintes necessidades:

- Tipo de site A: sistemas de telefonia herdados tradicionais 

  O Tipo de Site A precisava manter o mesmo número de telefone associado à recepção que o número de seus atendedores automáticos. Os principais departamentos de cada um desses sites teriam suas próprias filas de chamadas que seriam roteados para os membros da equipe. Houve uma mistura de sites que usaram Sistema de Telefonia roteamento direto e Sistema de Telefonia com Planos de Chamadas.  

- Tipo de site B: Skype for Business Enterprise Voice 

  O Tipo de Site B tinha atendedores automáticos e filas de chamadas existentes que precisavam migrar para Teams. A Contoso precisava manter os números de telefone associados aos atendedores automáticos. A Contoso moveu a maioria desses sites para Sistema de Telefonia planos de chamadas. No entanto, nos poucos locais em que os Planos de Chamadas não estão disponíveis, a Contoso moveu esses sites para uma configuração de Roteamento Direto.  

- Tipo de site C: Skype for Business Enterprise Voice & sistema de telefonia herdado tradicional 

  O tipo de site C tinha atendedores automáticos existentes que residiam no sistema de telefonia herdado tradicional. As decisões e as configurações para este site eram as mesmas que o Tipo de Site A.   

- Para todos os tipos de site, a Contoso fez as seguintes perguntas:

  - P: Usaremos números novos ou existentes? 
    R: A Contoso decidiu usar os números de telefone existentes para serem atribuídos à conta de serviço para o atendedor automático. 

  - P: Quando o atendedor automático estará disponível para aceitar chamadas de entrada? 
    R: A Contoso decidiu definir o horário comercial e ter chamadas recebidas após o horário comercial redirecionadas para um atendedor automático "após o horário comercial".  

  - P: Como as chamadas serão roteados para membros em uma fila de chamadas: roteamento de atendedor, serial ou round robin? 
    R: A Contoso decidiu usar o roteamento do Atendedor, 

  - P: Como determinaremos quando um usuário deve ou não receber uma chamada? 
    R: A Contoso decidiu usar opções de tratamento de chamadas para determinar se o agente está disponível: roteamento baseado em presença. 


## <a name="configuration"></a>Configuração

As etapas para configurar um atendedor automático e uma fila de chamadas incluem o seguinte descrito em [Gerenciar contas de recursos](manage-resource-accounts.md): 

1. Obter um número de serviço. 

2. Obtenha uma licença Sistema de Telefonia - Usuário Virtual ou uma licença Sistema de Telefonia paga para usar com a conta de recurso ou uma Sistema de Telefonia licença.

3. Crie a conta de recurso. Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada. 

4. Atribua o Sistema de Telefonia ou uma Sistema de Telefonia - Licença de usuário virtual à conta de recurso. Para obter mais informações, [consulte Microsoft 365 Sistema de Telefonia – licença de usuário virtual](./teams-add-on-licensing/virtual-user.md).

5. Atribua um número de telefone de serviço à conta de recurso à qual você atribuiu licenças. 

6. Criar uma fila Sistema de Telefonia chamada ou atendedor automático 

7. Vincule a conta de recurso com uma fila de chamadas ou atendedor automático. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites com Sistema de Telefonia roteamento direto 

A Contoso teve que configurar o número de telefone fornecido pela operadora local como o número de serviço no Office 365. 

- Para configurar um número de telefone disponível por meio do Roteamento Direto, a Contoso seguiu as instruções localizadas em [Gerenciar Contas de Recursos](manage-resource-accounts.md). Como Office 365 não está ciente dos números de telefone locais, a Contoso usou o PowerShell para concluir a configuração.   

- Para configurar o atendedor automático de nuvem, a Contoso seguiu as etapas descritas em [Configurar um atendedor automático de nuvem](create-a-phone-system-auto-attendant.md). 

- Para configurar uma fila de chamadas na nuvem, a Contoso seguiu as etapas descritas em [Criar uma fila de chamadas na nuvem](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites com Sistema de Telefonia plano de chamada

A Contoso teve que portar o número de telefone que foi usado Skype for Business Enterprise Voice atendedores automáticos para Sistema de Telefonia Office 365. Isso permitiu que o mesmo número seja atribuído como um número de serviço para uso como atendedor automático. 

- Para portar o número de telefone, a Contoso seguiu [](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) as instruções em Transferir números de telefone para Teams e obteve diretrizes adicionais em Gerenciar números de [telefone para sua organização](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para configurar um atendedor automático de nuvem, a Contoso seguiu as etapas descritas em [Configurar um atendedor automático de nuvem](create-a-phone-system-auto-attendant.md).

-  Para configurar uma fila de chamadas na nuvem, a Contoso seguiu as etapas descritas em [Criar uma fila de chamadas na nuvem](create-a-phone-system-call-queue.md).  

