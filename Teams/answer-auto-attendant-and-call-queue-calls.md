---
title: Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descreve atendedores automáticos da nuvem e filas de chamadas e explica como você pode responder a essas chamadas no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a78ed7e0bb40d83f7b46d4d4a008f964180c32d0
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2019
ms.locfileid: "34185291"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams
===========================================================

Os usuários do teams podem receber e atender chamadas de atendedores automáticos da nuvem e filas de chamadas diretamente do cliente de suas equipes. Para usuários do Teams, o recurso atendedor automático agora está disponível geralmente, e o recurso de fila de chamadas está em visualização. 

## <a name="what-are-auto-attendants-and-call-queues"></a>O que são atendedores automáticos e filas de chamadas?

Os atendedores automáticos na nuvem fornecem uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem em vez de uma operadora humana quando eles chamam para uma organização. Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.

As filas de chamadas na nuvem incluem Saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de Pesquisar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que chamam são ouvindo música em espera. Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Manipulando um atendedor automático ou chamada em fila de chamadas

Os usuários poderão diferenciar as chamadas recebidas de um atendedor automático ou da fila de chamadas antes de atenderem a chamada. Juntamente com o nome e/ou o número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando alcançar, dando aos usuários um contexto melhor para o endereçamento do chamador.

A ilustração a seguir mostra como uma chamada de entrada de um atendedor automático ou fila de chamadas aparecerá para um usuário.

![Notificação de chamada recebida](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Quando um atendedor automático ou uma chamada de fila de chamada for respondido, o usuário poderá processar a chamada como qualquer outra chamada & # x2014; Eles podem adicionar ou enviar uma conferência em outro usuário ou transferir a chamada para outra pessoa. Além disso, as chamadas de atendedor automático serão encaminhadas com base na configuração do usuário.

> [!NOTE] 
> As chamadas da fila de chamadas não são encaminhadas com base na configuração do usuário. Isso é para garantir que os chamadores permaneçam na fila até que um agente possa atender a chamada, e o chamador não seja encaminhado inesperadamente.

## <a name="supported-clients"></a>Clientes com suporte

O suporte para o atendedor automático e as chamadas da fila de chamadas está disponível nos seguintes clientes:

-   Microsoft Teams Windows Client (versões de 32 e 64 bits)
-   Cliente Mac do Microsoft Teams
-   Aplicativo iPhone do Microsoft Teams
-   Aplicativo Android do Microsoft Teams

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar o atendedor automático e o suporte à fila de chamadas do Microsoft Teams

Para receber chamadas de atendedor automático e fila de chamadas no Microsoft Teams, você precisa configurar a política de interoperabilidade e a política de atualização. Revise [a migração e a interoperabilidade de organizações que usam o Skype for Business em equipe](migration-interop-guidance-for-teams-with-skype.md). Se você não tiver o atendedor automático e/ou a fila de chamadas configurada e quiser fazer isso, consulte [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md) e [criar uma fila de chamadas na nuvem](create-a-phone-system-call-queue.md).

## <a name="related-topics"></a>Tópicos relacionados

-   [O que é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md)
-   [Criar uma fila de chamada do Cloud](create-a-phone-system-call-queue.md)
-   [Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)
-   [Configurar um atendedor automático do Cloud](create-a-phone-system-auto-attendant.md)

