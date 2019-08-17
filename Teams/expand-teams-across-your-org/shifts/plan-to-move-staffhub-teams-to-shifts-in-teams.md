---
title: Planeje mover suas equipes do StaffHub para turnos no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenha orientação sobre como planejar para mover suas equipes do StaffHub para turnos no Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0804b3fb0783a588fdd79dfec1a8dd39e4d92f34
ms.sourcegitcommit: a0df7479662b3bea488c19722ad588981f58a5e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "36447958"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Planeje mover suas equipes do StaffHub para turnos no Microsoft Teams

> [!IMPORTANT]
> A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md). 

Fazer a transição do StaffHub para o Teams começa quando você começa a planejar a alteração. Para ajudar a garantir que a mudança para o Microsoft Teams seja bem-sucedida, criamos uma linha do tempo de exemplo que demonstra um plano de transição típico. A linha do tempo de exemplo descreve as atividades de planejamento para se preparar para a movimentação e leva você para mover as equipes do StaffHub da sua organização para o Microsoft Teams.

Use a linha do tempo como orientação para planejar a mudança do StaffHub para o Microsoft Teams e personalizá-la de acordo com as necessidades da sua organização. Certifique-se de revisar os recursos vinculados às etapas na linha do tempo.

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>Prepare-se para mover suas equipes do StaffHub para o Microsoft Teams

|Etapa |Orientação  |Recurso |
|---------|---------|---------|
|1    |Preparar e identificar participantes         |         |
|2     |Examine a documentação na transição do StaffHub para o Teams and Teams onboards         |[StaffHub a ser desativado](microsoft-staffhub-to-be-retired.md)<br><br>[Mover suas equipes do StaffHub para turnos no Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Comece a usar o Microsoft Teams](../../get-started-with-teams-quick-start.md)         |
|3    |Habilitar grupos do Office 365 para sua organização        |[Grupos e equipes do Office 365](../../Office-365-groups.md)      |
|4    |Verifique se os pré-requisitos foram atendidos         |[Verificar se os pré-requisitos foram atendidos](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |Atribuir licenças de equipe a usuários do StaffHub em sua organização|[Atribuir licenças do Teams](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Gerenciamento do acesso de usuários ao Teams](../../user-access.md)      |
|6    |Instalar o módulo PowerShell do StaffHub        |[Instalar o módulo PowerShell do StaffHub](install-the-staffhub-powershell-module.md)        |
|7     |Determine a linha do tempo e identifique os usuários do StaffHub para mover-se para o Teams       |[Executar um relatório para exibir o uso ativo do StaffHub](run-report-to-show-staffhub-usage.md) |
|08     |Identifique os usuários do StaffHub que não têm uma conta do Azure AD (mostra como "inativo" no StaffHub) e vincule uma conta para elas     |[Vincular uma conta do Azure AD para os membros da equipe do StaffHub que não têm uma](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|222    |Criar conteúdo de treinamento para usuários personalizados para sua organização         |[Preparar um plano de preparação do usuário para Teams](../../upgrade-user-readiness.md)     |
|254    |Comunicar-se a usuários do StaffHub sobre a transição para turnos no Microsoft Teams         |         |
|11:00     |Instalar clientes do Microsoft Teams         |[Obter clientes para o Teams](../../get-clients.md) |
|12    |Atribua a política de configuração do aplicativo FirstLineWorker aos usuários (ou crie e atribua uma política de configuração de aplicativo personalizada) para fixar o aplicativo turnos a clientes do teams  |[Atribuir a política de configuração do aplicativo FirstlineWorker aos usuários](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|0,13     |Treinar os usuários sobre como usar turnos e equipes         |[Usuários integrados ao Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[Documentação de ajuda de turnos](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Documentação da Ajuda do Teams](https://support.office.com/teams)<br><br>[Vídeos de treinamento do Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |Examine sua lista de equipes do StaffHub para garantir que todos os usuários dessas equipes devem ser movidos para o Microsoft Teams. Remova os usuários que não devem estar no cronograma. |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>Mover as equipes do StaffHub da sua organização para o Microsoft Teams

|Etapa |Orientação |Recurso  |
|---------|---------|---------|
|1  |Identificar uma equipe piloto e mover uma equipe          |[Mover uma equipe do StaffHub](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |Valide a equipe piloto e identifique os problemas de movimentação. Atualize a documentação de treinamento conforme necessário.         |         |
|3     |Identifique outras equipes piloto e mude de cinco para dez equipes         |[Mover suas equipes do StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |Identificar as equipes de StaffHub restantes e movê-las em uma abordagem em fases         |[Mover suas equipes do StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |Continuar a fornecer suporte para turnos e equipes         |         |
|6     |Se a redefinição de senha de autoatendimento estiver habilitada, execute um relatório para dar suporte a problemas de logon no Microsoft Teams       |[Executar um relatório de configuração de redefinição de senha de autoatendimento](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
