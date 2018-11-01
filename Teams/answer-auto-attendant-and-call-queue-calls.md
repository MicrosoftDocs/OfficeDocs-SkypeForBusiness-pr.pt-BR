---
title: Atender atendedor automático e chamadas de fila de chamadas diretamente a partir de equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: article
ms.service: msteams
description: Descreve os atendedores automáticos de sistema telefônico e filas de chamada e explica como você pode atender essas chamadas em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b0b533020def2e344991fa758304888c8166436
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839201"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Atender atendedor automático e chamadas de fila de chamadas diretamente a partir de equipes
===========================================================

Os usuários de equipes podem receber e atenda as chamadas do Skype para Business Online atendedor automático e filas de chamadas diretamente do seu cliente de equipes. Para usuários de equipes, o recurso de atendedor automático agora está disponível no mercado e a capacidade de fila de chamada está no modo de visualização. 

## <a name="what-are-auto-attendants-and-call-queues"></a>Cite atendedores automáticos de um e filas de chamada?

Atendedores automáticos da telefone sistema fornecem uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem, em vez de um operador humano quando ele liga para uma organização. Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.

Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera. Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Manipulação de uma chamada de fila de chamada e atendente automático

Os usuários poderão diferenciar as chamadas de entrada a partir de uma fila de espera chamada e atendente automático antes que eles atender a chamada. Junto com o nome e/ou número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando fazer contato, proporcionando aos usuários um melhor contexto para abordar o chamador.

A ilustração a seguir mostra como uma chamada de entrada a partir de uma fila de espera chamada e atendente automático será exibido para um usuário.

![Notificação de chamada recebida](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Depois que uma chamada de fila de chamada e atendente automático for atendida, o usuário pode processar a chamada como qualquer chamada & #x 2014; eles podem adicionar ou conferência de outro usuário ou transferir a chamada para outra pessoa. Além disso, as chamadas de atendedor automático serão encaminhadas com base na configuração do usuário.

> [!NOTE] 
> Chamadas de fila de chamada não são encaminhadas com base na configuração do usuário. Isso é para garantir que os chamadores permanecem na fila de espera até que um operador pode atender a chamada e o chamador não é encaminhado inesperadamente.

## <a name="supported-clients"></a>Clientes suportados

Suporte para chamadas de fila de chamada e atendedor automático está disponível nos seguintes clientes:

-   Cliente do Windows para Microsoft Teams (versões de 32 e 64 bits)
-   Cliente Mac para Microsoft Teams
-   Aplicativo do Microsoft Teams para iPhone
-   Aplicativo do Microsoft Teams para Android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurar o suporte de fila attendant e chamada de automático for Microsoft Teams

Para receber o atendedor automático e chamar as chamadas de fila em Teams da Microsoft, você precisa configurar sua política de interoperabilidade e atualização de política. Analise a [migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md). Se você não tiver o atendedor automático e/ou chamada fila configurado e gostaria de fazê-lo, consulte [Configurar um atendedor automático de sistema telefônico](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) e [criar uma fila de chamada do sistema telefônico](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

## <a name="related-topics"></a>Tópicos relacionados

-   [Qual é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md)
-   [Criar uma fila de chamadas do Sistema de Telefonia](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [O que são atendedores automáticos do Sistema de Telefonia?](what-are-phone-system-auto-attendants.md)
-   [Configurar o atendedor automático do Sistema de Telefonia](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

