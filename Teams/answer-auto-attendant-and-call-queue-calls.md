---
title: Atender chamadas de fila de chamadas e atende a chamadas automáticas
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 6c60f0f3bcf5fc683a15c5b22cc7b98aa384d477
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733360"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams

Teams os usuários podem receber e atender chamadas de atendedores automáticos na nuvem e chamar filas diretamente de seus clientes Teams cliente.

## <a name="what-are-auto-attendants-and-call-queues"></a>O que são os atendimentos automáticos e filas de chamada?

Os atendentes automáticos de nuvem fornecem uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem em vez de um operador humano quando eles chamam uma organização. Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.

As filas de chamadas na nuvem incluem saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de procurar o próximo agente de chamada disponível para manipular a chamada enquanto as pessoas que chamam ouvem música em espera. Você pode criar uma ou várias filas de chamadas para sua organização.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Manipulando um atendimento automático ou chamada de fila de chamada

Os usuários poderão diferenciar chamadas de entrada de um atendedores automáticos ou fila de chamadas antes de atenderem a chamada. Juntamente com o nome e/ou número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando alcançar, dando aos usuários um contexto melhor para lidar com o chamador.

A ilustração a seguir mostra como uma chamada de entrada de um atendimento automático ou fila de chamadas aparecerá para um usuário.

![Captura de tela de uma notificação de chamada de entrada.](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Depois que um atendedo automático ou uma chamada de fila de chamada é atendido, o usuário pode processar a chamada como qualquer outra chamada &#x2014; ele pode adicionar ou conferência em outro usuário ou transferir a chamada para outra parte. Além disso, as chamadas de atendimento automático serão encaminhadas com base na configuração do usuário.

> [!NOTE] 
> As chamadas de fila de chamadas não são encaminhadas com base na configuração do usuário. Isso é para garantir que os chamadores permaneçam na fila até que um agente possa atender à chamada e o chamador não seja encaminhado inesperadamente.

> Os agentes não são notificados de chamadas perdidas ou de caixa postal para chamadas de fila de chamadas.

## <a name="supported-clients"></a>Clientes com suporte

O suporte para chamadas de fila de chamadas e atendimento automático está disponível nos seguintes clientes:

-    Microsoft Teams Windows cliente (versões de 32 e 64 bits)
-    Cliente Microsoft Teams para Mac
-    Aplicativo Microsoft Teams para iPhone
-    Aplicativo Microsoft Teams para Android

O Teams cliente só tem suporte com um modo de [co-existência de Teams Somente](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar o atendimento automático e o suporte à fila de chamada para Microsoft Teams

Para receber chamadas de atendimento automático e fila de chamadas no Microsoft Teams, você precisa configurar a política de interoperabilidade e a política de atualização. Consulte [Migração e interoperabilidade para organizações que usam Teams em conjunto com Skype for Business](migration-interop-guidance-for-teams-with-skype.md). Se você não tiver o atendimento automático e/ou fila de chamada configurada e gostaria de fazer isso, consulte [Configurar](create-a-phone-system-auto-attendant.md) um atendimento automático na nuvem e Criar uma fila de chamada [na nuvem.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Problemas Conhecidos

Quando os agentes de fila de chamadas recebem uma chamada em seu dispositivo móvel, as chamadas podem ficar em espera se o dispositivo estiver bloqueado. O usuário deve desbloquear o dispositivo primeiro e, em seguida, atender à chamada.


## <a name="related-topics"></a>Tópicos relacionados

-    [O que Sistema de Telefonia em Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md)
-    [Criar uma fila de chamada do Cloud](create-a-phone-system-call-queue.md)
-    [Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)
-    [Configurar um atendedor automático do Cloud](create-a-phone-system-auto-attendant.md)

