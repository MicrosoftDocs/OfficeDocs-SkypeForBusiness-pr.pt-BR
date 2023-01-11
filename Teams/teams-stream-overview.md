---
title: Visão geral do codificador para streaming no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo fornecerá uma visão geral da configuração rtmp baseada em codificador para eventos de streaming do Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d7ea21edb6677397785367cecd3daaf9bbe513f3
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767910"
---
# <a name="live-streaming-events-in-microsoft-teams"></a>Eventos de streaming ao vivo no Microsoft Teams

Você pode criar eventos ao vivo usando o Microsoft Teams em toda a sua organização. Você pode agendar, produzir e entregar eventos ao vivo para vários cenários, como eventos em toda a empresa, atualizações de liderança e muito mais. Eventos de transmissão ao vivo permitem que os produtores faça a curadoria e controle do conteúdo transmitido para uma audiência.

Você pode criar, agendar e executar eventos ao vivo usando um único fluxo RTMP ou RTMPS de taxa de bits de um codificador – cuidaremos de toda a transcodificação para entrega de taxa de bit adaptável para seus espectadores.

Assim como qualquer outro vídeo no Teams, você pode abrir o evento ao vivo para toda a sua empresa ou limitar o acesso a grupos específicos. Isso fornece uma experiência de criação e exibição de ponta a ponta dentro do Teams.

Após o evento, o vídeo estará disponível sob demanda com recursos inteligentes, incluindo:

- Fala em texto e legendas fechadas.
- A pesquisa de transcrição e os códigos de tempo permitem encontrar rapidamente momentos que importam em um vídeo.

## <a name="live-events-in-microsoft-365"></a>Eventos ao vivo no Microsoft 365

Você pode criar um evento de vapor ao vivo no Teams ou no Yammer, onde quer que seu público, equipe ou comunidade resida. Os participantes podem assistir ao evento em vídeo de alta definição (HD) e enviar perguntas por meio de uma experiência de Q&A moderada. A integração contínua no Microsoft 365 significa que você pode usar o Teams para fornecer eventos altamente produzidos e de qualidade de estúdio.

## <a name="get-started"></a>Introdução

Verifique se os usuários que você deseja poder criar eventos ao vivo têm as permissões concedidas necessárias para criar um evento ao vivo. Por padrão, todos na sua organização podem criar um evento ao vivo, no entanto, um administrador do Teams pode restringir o acesso. Saiba mais sobre administração de eventos ao vivo.

1. Na navegação à esquerda do centro de administração do Teams, acesse **Políticas de eventos do Meetings** > **Live** > guia **Gerenciar Políticas** .
1. Se você quiser:
    1. edite a política padrão existente, escolha **Global (padrão em toda a organização)**.
    1. crie uma nova política personalizada, escolha **+Adicionar**.
    1. edite uma política personalizada, selecione a política e escolha **Editar**.

## <a name="monitor-your-event"></a>Monitorar seu evento

Como produtor, você pode usar o cliente do Teams para ver o feed de audiência (visível no lado direito) e o número de participantes atualmente exibindo o evento.

## <a name="capabilities"></a>Recursos

Veja a seguir as funcionalidades de eventos de transmissão ao vivo:

|Operação                                            |Limites                                                               |
|-----------------------------------------------------|---------------------------------------------------------------------|
|Criar eventos ao vivo no Teams (com codificador externo)  |Enterprise (E1, E3, E5), Educação (A3, A5)                          |
|Assistir ao evento ao vivo                                     |Os espectadores com permissões para exibir o evento e uma licença válida do Teams (a menos que o evento seja público, uma licença para exibição não é necessária) |
|Resolução máxima                                   |720p                                                                 |
|Eventos ao vivo simultâneos máximos (em pré-live ou ao vivo) |15                                                                   |
|Visualizadores simultâneos ativos                            |10000                                                                |
|Comprimento máximo do evento ao vivo                         |4 horas                                                              |
|Suporte ao cache de rede do parceiro                      |Hive, Kollective, Riverbed, Ramp, Microsoft                          |
|Outro suporte ao cache de rede                        |Pode funcionar, mas não tem suporte                                        |
|Controles DVR do participante                                |Pausa, velocidade de reprodução (2x catch up, 1x ao vivo), procure                |
|Legendas em tempo real                                   |Passagem de legenda 708 do codificador                                |
|Conversão automática de fala em texto e legendas                |Processado após o evento                                            |
|Discussões interativas                              |Com suporte via Yammer quando o evento é criado a partir do Yammer           |
|Comentários do Teams                                       |Disponível após o término do evento                                       |
|Exibição sob demanda no evento ao vivo (após o evento)        |Transição automática para live para sob demanda para exibição imediata e indexação no Teams |
|Gravação para download                               |Processado e disponível após o evento ao vivo pelos proprietários               |

Eventos ao vivo no Teams são um serviço altamente disponível e você pode esperar um bom desempenho em escala. No cenário improvável que resulta na necessidade de failover, eventos ao vivo usando codificação externa não terão redundância e não serão recuperáveis.
