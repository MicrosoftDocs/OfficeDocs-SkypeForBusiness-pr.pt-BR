---
title: Lista de verificação de integração - Configurar recursos principais - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga o núcleo, tarefas e atividades a fazer nesta lista de verificação quando você configurar Teams para sua organização.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1d8368f43dd321ff03a5ecfc31fa376e13bda8c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417364"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurar Microsoft Teams principais recursos

| Não | Atividade ou tarefa | Descrição | Concluído? | Informações adicionais |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Validar se seu ambiente inclui todos os Teams pré-requisitos | Teams depende de outras plataformas para construir uma solução de colaboração de ponta a ponta. Trabalhe com suas equipes de TI para garantir que você tenha implantado e configurado corretamente Exchange, SharePoint Online e OneDrive for Business. | | [Como o Microsoft Office SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) |
| 2  | Validar Teams está habilitado para o locatário | Teams está ligado por padrão para todas as organizações. Verifique a **página Serviços & de** Centro de administração do Microsoft 365 no Centro de administração do Microsoft 365 para verificar se o Teams está habilitado para sua organização e habilita-lo, se necessário. | | [Configurar Microsoft Teams em Microsoft 365 ou Office 365](office-365-set-up.md) |
| 3  | Configurar funções e permissões | Teams suporte a dois tipos de funções: Membro e Proprietário. <br/><br/>Depois de adicionar um membro a uma equipe, um proprietário também pode promover um membro à função Proprietário. Como prática prática, recomendamos que você tenha pelo menos dois proprietários atribuídos a cada equipe. <br/><br/>Por padrão, todos na organização que têm uma caixa de correio hospedada Exchange Online podem criar uma equipe. Um usuário que cria uma nova equipe é automaticamente concedido a função Proprietário para essa equipe. <br/><br/>Se precisar, você pode configurar as Microsoft 365 de grupo para permitir que usuários específicos criem novas equipes. | | [Atribuir funções e permissões no Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365 grupos e Microsoft Teams](office-365-groups.md) <br/><br/>[Gerenciar quem pode criar Microsoft 365 Grupos](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurar configurações de Teams locatários | Você pode configurar algumas Teams configurações no nível do locatário. Os usuários habilitados para Teams herdam essas configurações da configuração do locatário:<ul><li>Geral</li><li>Integração de email</li><li>Aplicativos</li><li>Armazenamento em nuvem personalizado</li><li>Chamadas e reuniões</li><li>Mensagens</li></ul>| | [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md) |
| 5  | OPCIONAL: Configurar o acesso de convidados | Você usa o acesso de convidados Teams colaborar com pessoas de fora da sua organização, concedendo a eles acesso a equipes e canais. O acesso de convidados é uma configuração de nível de locatário Teams. Ela está desativada por padrão. <br/>Habilita o acesso de convidados e configure as configurações de convidados em todo o locatário, se sua organização planeja usar esse recurso. | | [Acesso para convidado no Microsoft Teams](guest-access.md) |
| 6  | OPCIONAL: Configurar uma Teams de nomenrção | Teams aproveita as políticas de nomenis de Microsoft 365 grupos quando os usuários criam ou editam nomes de equipe. <br/><br/>Por padrão, nenhuma restrição de nomeação é aplicada quando um usuário cria uma equipe. <br/><br/>Se você precisar impor regras para nomes de equipes, configure Microsoft 365 de nomenis de grupos que se aplicam à sua organização. Você pode definir prefixos e sufixos obrigatórios e especificar palavras bloqueadas. | | [Planejar grupos Microsoft 365 ao criar equipes no Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Microsoft 365 de nomenis de grupos](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurar Exchange para o domínio Teams SMTP | Teams usa Exchange Online para enviar notificações aos membros da equipe usando o domínio SMTP — email.teams.microsoft.com — quando eles foram adicionados ou removidos. <br/><br/>Certifique-se de adicionar esse domínio SMTP à lista de domínios aceitos em sua Exchange infraestrutura. | | [Criar listas de remetentes seguros Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurar e gerenciar o acesso do usuário Teams | Embora seja altamente recomendável habilitar todos os usuários para Teams, você pode permitir ou não o acesso ao Teams por usuário atribuindo ou removendo a licença do produto Teams. | | [Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md) |
| 9  | Atribuir licenças aos usuários | Atribuir licenças aos usuários para recursos como Audioconferência, Sistema de Telefonia e Planos de Chamada | | [Atribuir Microsoft Teams licenças de complemento](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Opcional: use o PowerShell para administrar Teams | Você pode usar cmdlets do PowerShell em vez do Centro de administração do Microsoft 365 para administrar e gerenciar Teams configurações. | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |