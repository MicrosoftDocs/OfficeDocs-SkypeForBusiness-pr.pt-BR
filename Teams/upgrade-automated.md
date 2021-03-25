---
title: Atualizações automatizadas| Atualização do Skype Business para o Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Visão geral das atualizações automatizadas do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120533"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Atualizações automatizadas do Skype for Business Online para o Microsoft Teams

A Microsoft oferece atualizações automatizadas para o Teams para ajudar pequenas empresas a fazer a transição bem-sucedida do Skype for Business Online antes da reforma de 31 de julho de 2021 do serviço. A atualização automatizada reduz o número de tarefas técnicas necessárias dos clientes e permite maior foco na preparação organizacional, no reconhecimento do usuário e no treinamento do Teams.

Uma atualização bem-sucedida do Skype for Business para o Microsoft Teams requer planejamento para preparação técnica e do usuário. Quando você estiver pronto para começar, [](upgrade-basic.md) a Microsoft oferece um plano de ação de atualização com atividades recomendadas principais e recursos associados para implementar uma movimentação bem-sucedida do Skype for Business para o Teams.

## <a name="notifications-for-scheduled-customers"></a>Notificações para clientes agendados

Os clientes do Skype for Business Online qualificados para atualizações automatizadas para o Teams receberão uma série de notificações de atualização a partir de 30 dias antes da data de atualização agendada. Essas notificações serão entregues como *Plan for Change* posts in the Admin Message Center, upgrade emails to the Global Admin, and in-app flags to end-users.

Essas notificações comunicarão a data agendada da atualização automatizada, vinculam-se aos recursos de atualização e treinamento para ajudar a impulsionar a adoção e o uso do Teams e dar aos clientes a opção de adiar a atualização automatizada por mais 30 dias, caso não esteja pronto para atualizar por sua data agendada.

## <a name="the-automated-upgrade-experience"></a>A experiência de atualização automatizada

Atualizações automatizadas são executadas na data de atualização agendada, que é comunicada nos emails de notificação, no Centro de Mensagens, bem como no portal de administração do Teams. A atualização levará aproximadamente 15 minutos durante o qual os usuários finais ainda terão acesso à funcionalidade do Skype for Business Online. Depois que a atualização for concluída e os usuários acessarem o Skype for Business Online, os usuários só poderão usar o Teams para mensagens, reuniões e chamadas.

## <a name="the-post-upgrade-experience"></a>A experiência pós-atualização

Quando a atualização automatizada é concluída, o Modo de **Coexistência** é definido como Somente Equipes e só pode ser alterado para um modo de coexistência diferente pela Microsoft. Os administradores devem revisar [considerações](teams-only-mode-considerations.md) de modo Somente do Teams antes da atualização. A tabela a seguir fornece uma visão geral de alto nível da experiência do usuário Somente do Teams.


|  |  |
|---------|---------|
|**Chat e Chamada**     | <UL><LI>Todas as chamadas e chats são iniciadas e recebidas no Teams<LI>Os usuários podem fazer a interopção (chat/chamada) com qualquer usuário do Skype for Business<LI>Os usuários não podem se comunicar com usuários que estão usando o Skype for Consumer<LI>Os usuários serão redirecionados para o Teams se tentarem entrar no Skype for Business      </UL>  |
|**Reuniões**     |  <UL><LI>Os usuários agendam todas as novas reuniões no Teams (plug-in substituído)    </UL>   |
|**Dados Migrados**     |<UL><LI>Contatos existentes do Skype for Business, incluindo federados (mas sem listas de distribuição)<LI>Reuniões existentes do Skype for Business (tanto no ambiente quanto online) são convertidas em reuniões do Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Adiar a atualização automatizada

Transições bem-sucedidas do Skype for Business Online para o Microsoft Teams exigem planejamento técnico e preparação do usuário para garantir que sua organização esteja preparada para aproveitar a funcionalidade expandida e o desempenho do Teams. No entanto, ao planejar sua atualização, você pode descobrir que sua organização ainda não está pronta para atualizar para o Teams no momento.

Se você receber uma notificação sobre sua atualização automatizada agendada para o Teams e quiser adiar para uma data posterior, o Administrador Global poderá entrar no portal de administração do Teams e clicar no botão *Adiar.* Fazer isso adiará a data de atualização automatizada de 30 dias. Ao atualizar o portal de administração do Teams após o adiamento, você verá uma notificação que inclui sua nova data de atualização automatizada.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Solicitações para downgrade para o Skype for Business

Permitimos downgrades único do Teams para o SfBO, para permitir que os locatários se preparem ainda mais para a atualização para o Teams. Os locatários que foram rebaixados serão reacionados para atualização automatizada por 60 dias a partir da data de rebaixamento.

## <a name="related-content"></a>Conteúdo relacionado

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Desativação do Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considerações sobre o modo Teams Only (Apenas Teams)](teams-only-mode-considerations.md)