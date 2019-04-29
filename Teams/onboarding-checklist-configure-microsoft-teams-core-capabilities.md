---
title: Lista de verificação de integração para configurar os recursos principais do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Siga o núcleo, tarefas de tarefas pendentes e atividades nesta lista de verificação quando você configura as equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: acaab4de788af1dc84a1cff0908868b1ddd924b4
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401971"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurar os principais recursos do Microsoft Teams

| Não | Atividade ou tarefa | Descrição | Concluído? | Informações adicionais |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Validar que o ambiente inclui todos os pré-requisitos de equipes | As equipes depende em outras plataformas para construir uma solução de colaboração de ponta a ponta. Trabalhar com as equipes de TI para garantir que você implantou e configurado adequadamente Exchange, SharePoint Online e OneDrive for Business. | | [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) |
| 2  | Validar que equipes está habilitado para o locatário | As equipes estão ativados por padrão para todas as organizações. Verifique a página de **Serviços & complementos** no Centro de administração do Office 365 para verificar se as equipes está habilitado para o seu locatário e habilitá-lo, se necessário. | | [Configurar o Microsoft Teams na sua organização do Office 365](office-365-set-up.md) |
| 3  | Configurar funções e permissões | As equipes de suportam a dois tipos de funções: membro e proprietário. <br/><br/>Depois de adicionar um membro para uma equipe, um proprietário também pode promover um membro à função de proprietário. Como prática recomendada, recomendamos que você tenha pelo menos dois proprietários atribuídos a cada equipe. <br/><br/>Por padrão, todas as pessoas na organização que tem uma caixa de correio hospedada no Exchange Online podem criar uma equipe. Um usuário que cria uma nova equipe recebe automaticamente a função de proprietário para essa equipe. <br/><br/>Se for necessário, você pode configurar as configurações de grupo do Office 365 para que somente usuários específicos criar novas equipes. | | [Atribuir funções e permissões no Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Grupos do Office 365 e Teams da Microsoft](office-365-groups.md) <br/><br/>[Gerenciar quem pode criar grupos do Office 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Definir configurações de equipes de todo o locatário | Você pode definir algumas configurações de equipes a nível de locatário. Os usuários habilitados para equipes herdarem essas definições da configuração do inquilino:<ul><li>Geral</li><li>Integração de email</li><li>Aplicativos</li><li>Armazenamento em nuvem personalizado</li><li>Chamadas e reuniões</li><li>Mensagens</li></ul>| | [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md) |
| 5  | OPCIONAL: Configurar o acesso de convidado | Você usa o acesso de convidado em equipes para colaborar com pessoas fora da sua organização, concedendo a eles acesso às equipes e canais. Acesso de convidado é uma configuração de nível de locatário em equipes. Ele está desativado por padrão. <br/>Habilitar o acesso do convidado e definir configurações de todo o locatário convidado, se sua organização estiver planejando usar esse recurso. | | [Acesso para convidado no Microsoft Teams](guest-access.md) |
| 6  | OPCIONAL: Configure a diretiva de nomenclatura de equipes | As equipes aproveita as políticas de nomenclatura para Office 365 grupos quando os usuários criar ou editar os nomes de equipe. <br/><br/>Por padrão, não há restrições de nomenclatura são aplicadas quando um usuário cria uma equipe. <br/><br/>Se você precisar impor regras para nomes de equipes, configure os grupos do Office 365 nomenclatura diretivas que se aplicam à sua organização. Você pode definir obrigatórios prefixos e sufixos e especificar palavras bloqueadas. | | [Planejar grupos do Office 365 ao criar equipes no Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Diretiva de nomenclatura de grupos do Office 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurar o Exchange para o domínio SMTP de equipes | As equipes usa o Exchange Online para enviar notificações aos membros da equipe usando o domínio SMTP — email.teams.microsoft.com — quando tiver sido adicionados ou removidos. <br/><br/>Certifique-se de adicionar este domínio SMTP à lista de domínios aceitos na infraestrutura do Exchange. | | [Adicionar o domínio SMTP ao Microsoft Teams como um domínio aceito no Exchange Online](smtp-accepted-domain.md) |
| 8  | Configurar e gerenciar o acesso de usuário às equipes | Embora é altamente recomendável que você habilite todos os usuários para equipes, você pode permitir ou não permitir o acesso às equipes em uma base por usuário por como atribuir ou remover a licença de equipes do produto. | | [Gerenciar o acesso de usuários ao Microsoft Teams](user-access.md) |
| 9  | Atribuir licenças aos usuários | Atribuir licenças aos usuários recursos como conferência de áudio, sistema telefônico e planos de chamada | | [Atribuir licenças do Skype for Business e do Microsoft Teams](assign-teams-licenses.md) <br/><br/>[MyAdvisor – scripts de ativação do usuário](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_6,5_2_0_3) |
| 10 | Opcional: Usar o PowerShell para administrar as equipes | Você pode usar os cmdlets do PowerShell ao invés do Centro de administração do Office 365 para administrar e gerenciar configurações de equipes. | | [As equipes da Microsoft PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |