---
title: Lista de verificação de integração-configurar recursos essenciais-Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga as tarefas principais, tarefas pendentes e atividades desta lista de verificação quando você configura o Teams para sua organização.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7d167b8e1e868f550067b08f2f7dbfb22cb0a41
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042098"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurar os recursos principais do Microsoft Teams

| Não | Atividade ou tarefa | Descrição | Concluído? | Informações adicionais |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Validar que seu ambiente inclui todos os pré-requisitos do teams | O Teams depende de outras plataformas para construir uma solução de colaboração de ponta a ponta. Trabalhe com suas equipes de ti para garantir que você tenha implantado e configurado adequadamente o Exchange, o SharePoint Online e o OneDrive for Business. | | [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) |
| 2  | Validar que o Microsoft Teams está habilitado para o locatário | O Teams está ativado por padrão para todas as organizações. Verifique a página **serviços & suplementos** no centro de administração do Microsoft 365 para verificar se as equipes estão habilitadas para seu locatário e habilite-as se necessário. | | [Configurar o Microsoft Teams no Microsoft 365 ou no Office 365](office-365-set-up.md) |
| 3  | Configurar funções e permissões | O Teams dá suporte a dois tipos de funções: membro e proprietário. <br/><br/>Depois de adicionar um membro a uma equipe, um proprietário também pode promover um membro para a função de proprietário. Como prática recomendada, recomendamos que você tenha pelo menos dois proprietários atribuídos a cada equipe. <br/><br/>Por padrão, todos na organização que tem uma caixa de correio hospedada no Exchange Online pode criar uma equipe. Um usuário que cria uma nova equipe recebe automaticamente a função de proprietário da equipe. <br/><br/>Se for necessário, você pode definir as configurações de grupo do Office 365 para permitir que apenas usuários específicos criem novas equipes. | | [Atribuir funções e permissões no Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Grupos do Microsoft 365 e o Microsoft Teams](office-365-groups.md) <br/><br/>[Gerenciar quem pode criar grupos do Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Definir configurações de equipes inteiras de locatários | Você pode definir algumas configurações de equipes no nível do locatário. Os usuários habilitados para o Teams herdam essas configurações da configuração do locatário:<ul><li>Geral</li><li>Integração de email</li><li>Aplicativos</li><li>Armazenamento em nuvem personalizado</li><li>Chamadas e reuniões</li><li>Mensagens</li></ul>| | [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md) |
| 5  | OPCIONAL: configurar o acesso de convidado | Você usa o acesso de convidado no Teams para colaborar com pessoas de fora da sua organização, concedendo a elas acesso a equipes e canais. O acesso de convidado é uma configuração em nível de locatário no Teams. Ela está desativada por padrão. <br/>Habilite o acesso de convidado e configure as configurações de convidados em todo o locatário, se sua organização planeja usar esse recurso. | | [Acesso para convidado no Microsoft Teams](guest-access.md) |
| 6  | OPCIONAL: configurar política de nomenclatura de equipes | O Teams aproveita as políticas de nomenclatura dos grupos do Microsoft 365 quando os usuários criam ou editam nomes de equipe. <br/><br/>Por padrão, nenhuma restrição de nomenclatura é aplicada quando um usuário cria uma equipe. <br/><br/>Se você precisar impor regras para nomes de equipes, configure o Microsoft 365 groups Naming Policies que se aplicam à sua organização. Você pode definir prefixos e sufixos obrigatórios e especificar palavras bloqueadas. | | [Plano para grupos do Microsoft 365 durante a criação de equipes no Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Política de nomenclatura de grupos do Microsoft 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurar o Exchange para o domínio SMTP do teams | O Microsoft Teams usa o Exchange Online para enviar notificações para os membros da equipe usando o domínio SMTP – email.teams.microsoft.com — quando foram adicionados ou removidos. <br/><br/>Certifique-se de adicionar esse domínio SMTP à lista de domínios aceitos na sua infraestrutura do Exchange. | | [Adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online](smtp-accepted-domain.md) |
| 8  | Configurar e gerenciar o acesso do usuário às equipes | Embora seja altamente recomendável que você habilite todos os usuários do Teams, é possível permitir ou proibir o acesso ao Teams por usuário ao atribuir ou remover a licença de produto do teams. | | [Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md) |
| 9  | Atribuir licenças a usuários | Atribuir licenças a seus usuários para obter recursos como videoconferência, sistema telefônico e planos de chamada | | [Atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 254 | Opcional: usar o PowerShell para administrar equipes | Você pode usar cmdlets do PowerShell em vez do centro de administração do Microsoft 365 para administrar e gerenciar as configurações do teams. | | [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
