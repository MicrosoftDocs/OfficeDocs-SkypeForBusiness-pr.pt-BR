---
title: Lista de verificação de integração - Configurar recursos principais - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga as principais tarefas e atividades de tarefas a realizar nesta lista de verificação ao configurar o Teams para sua organização.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2987b507b9fa149ad874b1035a753586c05b23d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802301"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurar os principais recursos do Microsoft Teams

| Não | Atividade ou tarefa | Descrição | Concluído? | Informações adicionais |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Validar se seu ambiente inclui todos os pré-requisitos do Teams | O Teams depende de outras plataformas para construir uma solução de colaboração de ponta a ponta. Trabalhe com suas equipes de TI para garantir que você implantou e configurou corretamente o Exchange, o SharePoint Online e o OneDrive for Business. | | [Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) |
| 2  | Validar se o Teams está habilitado para o locatário | O Teams está ligado por padrão para todas as organizações. Verifique a **página &** de serviços no Centro de administração do Microsoft 365 para verificar se o Teams está habilitado para sua organização e habilita-lo, se necessário. | | [Configurar o Microsoft Teams no Microsoft 365 ou no Office 365](office-365-set-up.md) |
| 3  | Configurar funções e permissões | As equipes suportam dois tipos de funções: Membro e Proprietário. <br/><br/>Depois de adicionar um membro a uma equipe, um proprietário também pode promover um membro à função Proprietário. Como prática prática, recomendamos que você tenha pelo menos dois proprietários atribuídos a cada equipe. <br/><br/>Por padrão, todos na organização que têm uma caixa de correio hospedada no Exchange Online podem criar uma equipe. Um usuário que cria uma nova equipe tem automaticamente a função Proprietário para essa equipe. <br/><br/>Se for necessário, você pode configurar as configurações de grupo do Microsoft 365 para permitir que usuários específicos criem novas equipes. | | [Atribuir funções e permissões no Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Grupos do Microsoft 365 e Microsoft Teams](office-365-groups.md) <br/><br/>[Gerenciar quem pode criar Grupos do Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurar configurações do Teams em todo o locatário | Você pode definir algumas configurações do Teams no nível do locatário. Os usuários habilitados para o Teams herdam essas configurações da configuração do locatário:<ul><li>Geral</li><li>Integração de email</li><li>Aplicativos</li><li>Armazenamento em nuvem personalizado</li><li>Chamadas e reuniões</li><li>Mensagens</li></ul>| | [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md) |
| 5  | OPCIONAL: Configurar o acesso de convidado | Use o acesso de convidados no Teams para colaborar com pessoas de fora da sua organização, concedendo a elas acesso a equipes e canais. O acesso de convidado é uma configuração no nível do locatário no Teams. Ela está desativada por padrão. <br/>Habilita o acesso de convidado e configure as configurações de convidado em todo o locatário, se sua organização planeja usar esse recurso. | | [Acesso para convidado no Microsoft Teams](guest-access.md) |
| 6  | OPCIONAL: Configurar a política de nomenguração do Teams | O Teams aproveita as políticas de nomen como grupos do Microsoft 365 quando os usuários criam ou editam nomes de equipe. <br/><br/>Por padrão, nenhuma restrição de nomeação é aplicada quando um usuário cria uma equipe. <br/><br/>Se você precisar impor regras para nomes de equipes, configure as políticas de nomeação de Grupos do Microsoft 365 que se aplicam à sua organização. Você pode definir prefixos e sufixos obrigatórios e especificar palavras bloqueadas. | | [Planejar grupos do Microsoft 365 ao criar equipes no Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Política de nomeação de Grupos do Microsoft 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurar o Exchange para o domínio SMTP do Teams | O Teams usa o Exchange Online para enviar notificações aos membros da equipe usando o domínio SMTP — email.teams.microsoft.com — quando eles foram adicionados ou removidos. <br/><br/>Certifique-se de adicionar esse domínio SMTP à lista de domínios aceitos em sua infraestrutura do Exchange. | | [Criar listas de remetentes seguros no Exchange](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurar e gerenciar o acesso do usuário ao Teams | Embora seja altamente recomendável habilitar todos os usuários do Teams, você pode permitir ou permitir o acesso ao Teams por usuário atribuindo ou removendo a licença de produto do Teams. | | [Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md) |
| 9  | Atribuir licenças aos usuários | Atribuir licenças aos usuários para recursos como Audioconferência, Sistema de Telefonia e Planos de Chamada | | [Atribuir licenças de complemento do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Opcional: Usar o PowerShell para administrar o Teams | Você pode usar cmdlets do PowerShell em vez do Centro de administração do Microsoft 365 para administrar e gerenciar as configurações do Teams. | | [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
