---
title: Atender chamadas de atendedor automático e fila de chamadas
ms.reviewer: colongma
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descreve atendedores automáticos de nuvem e filas de chamadas e explica como você pode atender a essas chamadas em Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 595be9303c0d9732c3e2580b06bf3a0a55a27088
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853072"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams

Teams usuários podem receber e atender chamadas de atendedores automáticos de nuvem e filas de chamadas diretamente de seus Teams cliente.

## <a name="what-are-auto-attendants-and-call-queues"></a>O que são atendedores automáticos e filas de chamadas?

Os atendedores automáticos de nuvem fornecem uma série de prompts de voz ou um arquivo de áudio que os chamadores escutam em vez de um operador humano quando eles chamam uma organização. Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.

As filas de chamadas na nuvem incluem saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que chamam estão ouvindo música em espera. Você pode criar uma ou várias filas de chamadas para sua organização.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Manipulando uma chamada automática de atendedor ou fila de chamadas

Os usuários poderão diferenciar chamadas de entrada de um atendedor automático ou fila de chamadas antes de atenderem à chamada. Juntamente com o nome e/ou o número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando acessar, fornecendo aos usuários um contexto melhor para lidar com o chamador.

A ilustração a seguir mostra como uma chamada de entrada de um atendedor automático ou fila de chamadas aparecerá para um usuário.

![Captura de tela de uma notificação de chamada de entrada.](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Depois que uma chamada automática de atendedor ou fila de chamadas é atendida, o usuário pode processar a chamada como qualquer outra chamada &#x2014; pode adicionar ou conferência em outro usuário ou transferir a chamada para outra parte. Além disso, as chamadas de atendedor automático serão encaminhadas com base na configuração do usuário.

> [!NOTE] 
> Chamadas de fila de chamadas não são encaminhadas com base na configuração de regras de atendimento de chamadas do usuário. Isso é para garantir que os chamadores permaneçam na fila até que um agente possa atender à chamada e o chamador não seja encaminhado inesperadamente.

> Os agentes não são notificados sobre chamadas perdidas ou mensagens de voz para chamadas de fila de chamadas.

## <a name="supported-clients"></a>Clientes com suporte

O suporte para chamadas automáticas de atendedor e fila de chamadas está disponível nos seguintes clientes:

-    Microsoft Teams Windows cliente (versões de 32 e 64 bits)
-    Cliente Microsoft Teams para Mac
-    Aplicativo Microsoft Teams para iPhone
-    Aplicativo Microsoft Teams para Android

O Teams cliente tem suporte apenas com um modo de [coexistência de Teams somente](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar o atendedor automático e o suporte à fila de chamadas para Microsoft Teams

Para receber chamadas automáticas de atendedor e fila de chamadas Microsoft Teams, você precisa configurar a política de interoperabilidade e a política de atualização. Examine a [migração e a interoperabilidade para organizações que Teams em conjunto com Skype for Business](migration-interop-guidance-for-teams-with-skype.md). Se você não tiver o atendedor automático e/ou a fila de chamadas configurados e quiser fazer isso, [](create-a-phone-system-auto-attendant.md) consulte Configurar um atendedor automático de nuvem e Criar uma fila de chamadas [na nuvem](create-a-phone-system-call-queue.md).

## <a name="known-issues"></a>Problemas Conhecidos

Quando um agente da fila de chamadas recebe uma chamada em seu dispositivo móvel, a chamada pode ficar em espera se o dispositivo estiver bloqueado. Os usuários devem desbloquear o dispositivo primeiro e, em seguida, responder à chamada.


## <a name="related-topics"></a>Tópicos relacionados

[Criar uma fila de chamada do Cloud](create-a-phone-system-call-queue.md)

[Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)

[Configurar um atendedor automático do Cloud](create-a-phone-system-auto-attendant.md)

