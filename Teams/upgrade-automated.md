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
ms.openlocfilehash: b42785d4f8d765e7d9600c2e195e48d7ec60d8ba
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780650"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Atualizações automatizadas do Skype for Business Online para o Microsoft Teams

A Microsoft oferece atualizações automatizadas para o Teams para ajudar pequenas empresas a fazer a transição bem-sucedida do Skype for Business Online antes da aposentadoria de 31 de julho de 2021 do serviço. A atualização automatizada reduz o número de tarefas técnicas necessárias dos clientes e permite maior foco na preparação organizacional, na conscientização do usuário e no treinamento do Teams.

Uma atualização bem-sucedida do Skype for Business para o Microsoft Teams requer planejamento para preparação técnica e do usuário. Quando você estiver pronto para começar, [](upgrade-basic.md) a Microsoft oferece um plano de ação de atualização apresentando as principais atividades recomendadas e recursos associados para implementar uma mudança bem-sucedida do Skype for Business para o Teams.

## <a name="notifications-for-scheduled-customers"></a>Notificações para clientes agendados

Os clientes do Skype for Business Online qualificados para atualizações automatizadas para o Teams receberão uma série de notificações de atualização a partir de 30 dias antes da data de atualização agendada. Essas notificações serão entregues como Planos de Alteração postagens no Centro de Mensagens de Administração, atualizar emails para o Administrador Global e sinalizadores no aplicativo para usuários finais. 

Essas notificações comunicarão a data agendada da atualização automatizada, vinculam-se aos recursos de atualização e treinamento para ajudar a impulsionar a adoção e o uso do Teams e dar aos clientes a opção de adiar a atualização automatizada por mais 30 dias, caso não esteja pronto para atualizar até a data agendada.

## <a name="the-automated-upgrade-experience"></a>A experiência de atualização automatizada

As atualizações automatizadas são executadas na data de atualização agendada, que é comunicada nos emails de notificação, no Centro de Mensagens, bem como no portal de administração do Teams. A atualização levará aproximadamente 15 minutos durante o período em que os usuários finais ainda terão acesso à funcionalidade do Skype for Business Online. Após a conclusão da atualização e o logout dos usuários do Skype for Business Online, os usuários só poderão usar o Teams para mensagens, reuniões e chamadas.

## <a name="the-post-upgrade-experience"></a>A experiência pós-atualização

Quando a atualização automatizada for concluída, o Modo de **Coexistência** será definido apenas como Teams e só poderá ser alterado para um modo de coexistência diferente pela Microsoft. Os administradores devem revisar [as considerações sobre o modo Somente do Teams](teams-only-mode-considerations.md) antes da atualização. A tabela a seguir fornece uma visão geral de alto nível da experiência do usuário somente do Teams.


|  |  |
|---------|---------|
|**Chat e Chamada**     | <UL><LI>Todas as chamadas e chats são iniciados e recebidos no Teams<LI>Os usuários podem interop (chat/chamada) com qualquer usuário do Skype for Business<LI>Os usuários não podem se comunicar com usuários que estão usando o Skype for Consumer<LI>Os usuários serão redirecionados para o Teams se tentarem entrar no Skype for Business      </UL>  |
|**Reuniões**     |  <UL><LI>Os usuários agendam todas as novas reuniões no Teams (plug-in substituído)    </UL>   |
|**Dados Migrados**     |<UL><LI>Contatos existentes do Skype for Business, incluindo federados (mas sem listas de distribuição)<LI>Reuniões existentes do Skype for Business (online e no locais) são convertidas em reuniões do Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Adiar sua atualização automatizada

Transições bem-sucedidas do Skype for Business Online para o Microsoft Teams exigem planejamento técnico e preparação do usuário para garantir que sua organização esteja preparada para aproveitar a funcionalidade expandida e o desempenho do Teams. No entanto, conforme você planeja sua atualização, pode ser que sua organização ainda não esteja pronta para atualizar para o Teams no momento.

Se você receber uma notificação sobre sua atualização automatizada agendada para o Teams e quiser adiar para  uma data posterior, o Administrador Global poderá entrar no portal de administração do Teams e clicar no botão Adiar. Isso fará com que a data de atualização automatizada seja de 30 dias. Ao atualizar o portal de administração do Teams após o adiamento, você verá uma notificação que inclui sua nova data de atualização automatizada.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Solicitações de downgrade para o Skype for Business

Permitimos downgrades único do Teams para o SfBO, para permitir que os locatários se preparem ainda mais para a atualização para o Teams. Os locatários que foram downgrade serão reacionados para atualização automatizada por 60 dias a partir da data de downgrade.

## <a name="related-content"></a>Conteúdo relacionado

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Desativação do Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considerações sobre o modo Teams Only (Apenas Teams)](teams-only-mode-considerations.md)

