---
title: Atualizações automatizadas | Atualização do Skype Business para o Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Visão geral de atualizações automatizadas do Skype for Business para o Teams
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
ms.openlocfilehash: 1ed959f74be1074ab8ed60b3fe54f06384b7990a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836163"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Atualizações automatizadas do Skype for Business online para o Microsoft Teams

A Microsoft oferece atualizações automatizadas para o Microsoft Teams para ajudar as pequenas empresas a fazer a transição bem-sucedida do Skype for Business Online antes do dia 31 de julho de 2021 o descontinuação do serviço. A atualização automatizada reduz o número de tarefas técnicas necessárias para os clientes e permite maior foco na prontidão organizacional, no reconhecimento do usuário e no treinamento do teams.

Uma atualização bem-sucedida do Skype for Business para o Microsoft Teams requer o planejamento de prontidão técnica e do usuário. Quando estiver pronto para começar, a Microsoft oferece um [plano de ação de atualização](upgrade-basic.md) com as principais atividades recomendadas e os recursos associados para a implementação de uma mudança bem-sucedida do Skype for Business para o Microsoft Teams.

## <a name="notifications-for-scheduled-customers"></a>Notificações para clientes agendados

Os clientes do Skype for Business online qualificados para atualizações automatizadas para o Microsoft Teams receberão uma série de notificações de atualização a partir de 30 dias antes da data de atualização programada. Essas notificações serão entregues como *plano para alterações de alterações* no centro de mensagens de administração, atualização de emails para o administrador global e sinalizadores no aplicativo para usuários finais.

Essas notificações se comunicarão com a data programada da atualização automatizada, serão links para recursos de atualização e treinamento para ajudar a adotar a adoção e o uso do Teams, e darão aos clientes a opção de adiar o upgrade automatizado para 30 dias adicionais em o evento que ele não está pronto para atualizar pela data agendada.

## <a name="the-automated-upgrade-experience"></a>A experiência de atualização automatizada

As atualizações automatizadas são executadas na data de atualização agendada que é comunicada nos emails de notificação, no centro de mensagens e no portal de administração do teams. A atualização levará aproximadamente 15 minutos durante o tempo que os usuários finais ainda terão acesso à funcionalidade do Skype for Business online. Após a conclusão da atualização, e o logoff dos usuários do Skype for Business Online, os usuários só poderão usar o Microsoft Teams para mensagens, reuniões e chamadas.

## <a name="the-post-upgrade-experience"></a>A experiência após a atualização

Quando a atualização automatizada é concluída, o **modo de coexistência** é definido somente como Teams e só pode ser alterado para um modo de coexistência diferente pela Microsoft. Os administradores devem analisar as [considerações do modo somente equipes](teams-only-mode-considerations.md) antes da atualização. A tabela a seguir fornece uma visão geral de alto nível da experiência do usuário do Microsoft Teams.


|  |  |
|---------|---------|
|**Chat e chamadas**     | <UL><LI>Todas as chamadas e chats são iniciados e recebidos no Teams<LI>Os usuários podem usar a interoperabilidade (chat/chamada) com qualquer usuário do Skype for Business<LI>Os usuários não podem se comunicar com usuários que usam o Skype for Consumer<LI>Os usuários são redirecionados para o Microsoft Teams se tentarem entrar no Skype for Business      </UL>  |
|**Reuniões**     |  <UL><LI>Os usuários agendam todas as novas reuniões no Microsoft Teams (plug-in substituído)    </UL>   |
|**Dados migrados**     |<UL><LI>Contatos existentes do Skype for Business, incluindo Federated (mas sem listas de distribuição)<LI>Reuniões existentes do Skype for Business (locais e online) são convertidas em reuniões de equipes</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Adiando a atualização automatizada

As transições bem-sucedidas do Skype for Business online para o Microsoft Teams exigem planejamento técnico e prontidão do usuário para garantir que sua organização esteja preparada para tirar proveito da funcionalidade e do desempenho expandidos do teams. No entanto, ao planejar a atualização, você pode achar que sua organização ainda não está pronta para fazer a atualização para o Microsoft Teams no momento.

Se você receber uma notificação sobre a atualização automatizada agendada para o Microsoft Teams e quiser adiar para uma data posterior, o administrador global do Office 365 pode entrar no portal de administração do Teams e clicar no botão *adiar* . Isso fará com que a data de atualização automatizada seja reforçada 30 dias. Quando você atualizar o portal de administração do teams depois de adiar, você verá uma notificação que inclui a nova data de atualização automatizada.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Solicitações para fazer downgrade para o Skype for Business

Permitimos downgrades unidirecionais do teams para o SfBO, para permitir que os locatários se preparem em sua atualização para o Microsoft Teams. Os locatários que tiverem downgrade serão reengrenados para atualização automatizada de 60 dias a partir da data de downgrade.

## <a name="related-content"></a>Conteúdo relacionado

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Desativação do Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considerações sobre o modo Teams Only (Apenas Teams)](teams-only-mode-considerations.md)

