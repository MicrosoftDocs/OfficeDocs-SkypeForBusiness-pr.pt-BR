---
title: Atender chamadas de atendemento automático e fila de chamadas
ms.reviewer: waseemh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descreve os atendedores automáticos e filas de chamadas na nuvem e explica como você pode atender a essas chamadas no Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766855"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams
===========================================================

Os usuários do Teams podem receber e atender chamadas de atendedores automáticos na nuvem e filas de chamadas diretamente do cliente do Teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>O que são os atendimentos automáticos e filas de chamada?

Os participantes automáticos da nuvem fornecem uma série de avisos de voz ou um arquivo de áudio que os chamadores ouvem em vez de um operador humano quando eles ligarem para uma organização. Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.

As filas de chamadas na nuvem incluem saudações que são usadas quando alguém liga para um número de telefone de sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de procurar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que telefonam estão ouvindo música em espera. Você pode criar uma ou várias filas de chamadas para sua organização.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Lidar com um atender automático ou chamada na fila de chamada

Os usuários poderão diferenciar as chamadas recebidas de um atendedores automáticos ou fila de chamadas antes de atenderem a chamada. Juntamente com o nome e/ou o número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando falar, dando aos usuários um contexto melhor para endereçamento ao chamador.

A ilustração a seguir mostra como uma chamada recebida de um atendimento automático ou fila de chamadas aparecerá para um usuário.

![Captura de tela de uma notificação de chamada recebida](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Quando um atende-automático ou uma chamada na fila de chamada é atendida, o usuário pode processar a chamada como qualquer outra chamada &#x2014; pode adicionar ou fazer conferência em outro usuário ou transferir a chamada para outra parte. Além disso, as chamadas de atendimento automático serão encaminhadas com base na configuração do usuário.

> [!NOTE] 
> As chamadas na fila de chamadas não são encaminhadas com base na configuração do usuário. Isso é para garantir que os chamadores permaneçam na fila até que um agente possa atender a chamada e o chamador não seja encaminhado inesperadamente.

## <a name="supported-clients"></a>Clientes com suporte

O suporte para chamadas de fila de chamadas e atendimento automático está disponível nos seguintes clientes:

-    Cliente Microsoft Teams para Windows (versões de 32 e 64 bits)
-    Cliente do Microsoft Teams Mac
-    Aplicativo Microsoft Teams para iPhone
-    Aplicativo Microsoft Teams para Android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar o suporte a atendimento automático e fila de chamada para o Microsoft Teams

Para receber chamadas de atendimento automático e fila de chamadas no Microsoft Teams, você precisa configurar a política de interoperabilidade e a política de atualização. Revise a [migração e a interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business.](migration-interop-guidance-for-teams-with-skype.md) Se você não tiver o atendimento automático e/ou fila de [](create-a-phone-system-auto-attendant.md) chamada configurado e gostaria de fazer isso, consulte Configurar um atendimento automático na nuvem e Criar uma fila [de chamada na nuvem.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Problemas conhecidos

Quando os agentes da fila de chamadas recebem uma chamada em seu dispositivo móvel, as chamadas podem ficar em espera se o dispositivo estiver bloqueado. O usuário deve desbloquear o dispositivo primeiro e atender a chamada.


## <a name="related-topics"></a>Tópicos relacionados

-    [O que é o Sistema telefônico no Microsoft 365 ou no Office 365](what-is-phone-system-in-office-365.md)
-    [Criar uma fila de chamada do Cloud](create-a-phone-system-call-queue.md)
-    [Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)
-    [Configurar um atendedor automático do Cloud](create-a-phone-system-auto-attendant.md)

