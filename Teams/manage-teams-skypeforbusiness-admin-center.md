---
title: Gerenciar equipes durante a transição para o novo Teams da Microsoft e Skype para Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Compreender como gerenciar todo o inquilino e configurações de usuário para as equipes durante a transição das equipes de experiência com o Centro de administração do Office 365 para o novo Teams Microsoft & Skype para Business Admin Center.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0f660130ce9fe2973178385e87433cac29fa8733
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-and-skype-for-business-admin-center"></a>Gerenciar equipes durante a transição para o novo Teams da Microsoft e Skype para Business Admin Center
======================================================

O novo Centro de administração do Microsoft Teams e Skype for Business estará disponível em breve! 

A partir de março de 2018, podemos gradualmente migrar as configurações para o Microsoft Teams & Skype para Business Admin Center do Skype atual para o Business Admin center e Teams Microsoft experiência no Centro de administração do Office 365. Quando uma configuração for migrada, você receberá uma notificação e será direcionado para o local da configuração no novo Centro de administração do Microsoft Teams e Skype for Business.

Que continuará migrar outras funcionalidades do Skype para Business Admin center nos próximos meses. Você pode permanecer atualizado por meio de nosso pública [mapa](https://aka.ms/Office365Roadmap).

> [!NOTE]
> Podemos está implantando o novo Teams Microsoft & Skype para Business Admin Center em estágios. Como resultado, todos os clientes não verá a nova Central de administração ao mesmo tempo. Você será notificado quando começar a usar o novo centro de administração.

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>O que é o novo Teams Microsoft & Skype para centro de administração de negócios?  

A nova experiência do Centro de administração fornecerá a você uma experiência unificada para gerenciar equipes e Skype para negócios. Oferecemos funcionalidade adicional, ideias de ponta a ponta e a capacidade de gerenciar configurações de equipes em um nível de usuário.

![Captura de tela do Skype para Business Admin Center & equipes da Microsoft.](media/manage-teams-skype-for-business-admin-center-portal.png)


Iniciando em março intermediário 2018, os seguintes recursos estarão disponíveis no novo Teams Microsoft & Skype para Business Admin Center: 

- **Política de mensagens de equipes da Microsoft**: criar a política de gerenciamento de nível do usuário da experiência do cliente do Microsoft Teams para cenários de mensagens.
- **Política de interoperabilidade de equipes da Microsoft**: configurar a experiência de interoperabilidade entre Skype para negócios e Teams da Microsoft.
- **Configurações de mensagens de convidado de equipes da Microsoft**: controlar os recursos de mensagens para contas de convidado no Microsoft Teams. 
- **Configurações de Federação**: gerenciar a federação entre locatários for Microsoft Teams e Skype para negócios. 
- **Gerenciamento de usuários**: Atribuir políticas e configurar as contas de usuário. 
- **Conferência de áudio**: configurar números de discagem e configurações do Skype para Teams da Microsoft e de negócios. 

 

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Configurações migradas para o novo Teams Microsoft & Skype para Business Admin Center

As configurações existentes para gerais, integração Email, armazenamento na nuvem personalizado, chamadas e reuniões e mensagens no Microsoft Teams (consulte a imagem abaixo) serão migradas para o novo Teams Microsoft & Skype para Business Admin Center (também conhecido como o novo portal de administração) os próximos meses. 



> [!NOTE]
>Você vai continuar a usar o painel de grupos no Centro de administração do Office 365 para configuração relacionada ao **equipes e canais**. As configurações para **aplicativos** permanecerão na área de equipes da Central de administração do Office 365 e serão migradas mais tarde. 

![Página de captura de tela das equipes no Centro de administração do Office 365.](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

Em relação às configurações disponíveis nas **configurações por tipo de licença de usuário /**, ele fornecido essencialmente uma maneira de configurar grupos de usuários de forma diferente. Agora, com o novo portal de administração, você pode fazer isso em uma base por usuário. 


A configuração de tipo de licença será migrado. Se atualmente você estiver usando a configuração de **Ativar equipes da Microsoft ativada ou desativada para todos os usuários desse tipo** para controlar o acesso às equipes para usuários nos SKUs, podemos manterão suas configurações atuais. No entanto, não será possível alterar essa definição no portal de administração do novo. Em vez disso, você irá atribuir as licenças apropriadas aos usuários no seu locatário por meio do Centro de administração do Office 365. Para obter mais detalhes, consulte [Manage user access às equipes da Microsoft](user-access.md). 

A tabela a seguir identifica as seções da experiência de equipes atual que serão migrados e mostra a relação entre as configurações atuais e as políticas no novo portal de administração.


|Seção de equipes no Centro de administração do Office 365  |Nome da configuração (nível de locatário)  |Microsoft Teams & Skype para política do Centro de administração de negócios   |Nível: Locatário ou usuário   |
|---------|---------|---------|---------|
|Geral     |Mostrar bate-papo organizacional no perfil pessoal        |  TeamsClientConfiguration       |  Locatário       |
|Geral     |Use Skype for Business para destinatários que não têm equipes         |TeamsClientConfiguration         |Locatário         |
|Geral     |Permitir que as mensagens de ajuda proativo T-Bot         |TeamsClientConfiguration         |Locatário         |
|Integração de e-mails     |Permitir que os usuários enviar emails a canais         |TeamsClientConfiguration         |Locatário         |
|Integração de e-mails     |Permite que os remetentes lista         |TeamsClientConfiguration        |Locatário         |
|Armazenamento em nuvem personalizado     |Caixa         |TeamsClientConfiguration         |Locatário         |
|Armazenamento em nuvem personalizado     |Pasta de recados        |TeamsClientConfiguration         |Locatário         |
|Armazenamento em nuvem personalizado     |Unidade do Google        |TeamsClientConfiguration         |Locatário         |
|Armazenamento em nuvem personalizado     |ShareFile        |TeamsClientConfiguration         |Locatário         |
|Configurações por tipo de licença de usuário /     |Ativar o Microsoft Teams ativada ou desativada para todos os usuários          |Preterida. Use o Centro de administração do Office 365 para atribuir licenças.        |         |
|Equipes e canais     |         |Redireciona para o Windows Azure Active Directory grupo Management (mesmo que a experiência atual).              |Usuário         |
|Equipes e canais     |         |Redireciona para gerenciamento de grupo AAD (mesmo que a experiência atual).             |Usuário          |
|Reuniões e chamadas     |Permitir o agendamento de reuniões privadas         |TeamsMeetingPolicy         |Usuário          |
|Reuniões e chamadas     |Permitir meetup de canal da Ad hoc         |TeamsMeetingPolicy         |Usuário          |
|Reuniões e chamadas     |Permitir o agendamento de reuniões de canal         |TeamsMeetingPolicy         |Usuário          |
|Reuniões e chamadas     |Permitir que os vídeos em reuniões         |TeamsMeetingPolicy         |Usuário          |
|Reuniões e chamadas     |Permitir compartilhamento em reuniões de tela         |TeamsMeetingPolicy         |Usuário          |
|Reuniões e chamadas     |Permitir chamadas particulares         |TeamsCallingPolicy         |Usuário          |
|Mensagens     |Habilitar Giphy, de forma que os usuários podem adicionar gifs para conversas         |TeamsMessagingPolicy         |Usuário         |
|Mensagens     |Classificação de conteúdo         |TeamsMessagingPolicy         |Usuário         |
|Mensagens     |Habilitar memes que os usuários podem editar e adicionar a conversas         |TeamsMessagingPolicy         |Usuário         |
|Mensagens     |Habilitar adesivos que os usuários podem editar e adicionar a conversas         |TeamsMessagingPolicy         |Usuário         |
|Mensagens     |Permitir que os proprietários de excluir todas as mensagens         |TeamsMessagingPolicy         |Usuário         |
|Mensagens     |Permitir que usuários editem suas próprias mensagens         |TeamsMessagingPolicy         |Usuário         |
|Mensagens     |Permitir que os usuários excluam suas próprias mensagens         |TeamsMessagingPolicy         |Usuário         |
|Mensagens     |Permite que os usuários chat em particular         |TeamsMessagingPolicy         |Usuário         |



## <a name="manage-settings-during-the-migration"></a>Gerenciar configurações durante a migração

Pretendemos migrar as configurações de equipes nas seções na seguinte sequência: mensagens, reuniões, chamadas e por último, as seções dentro da diretiva de configuração de TeamsClient (gerais, integração de Email e armazenamento na nuvem personalizado).   

Você pode continuar modificar configurações na Central de administração do Office 365 e o Skype para Business Admin center até que a migração para uma seção está concluída para o seu locatário. 

A tabela a seguir mostra onde você pode gerenciar recursos durante a migração.

|Recurso  |As equipes da Microsoft e Skype para Business Admin Center                       |Skype para Business Admin Center (herdado)  |Centro de administração do Office 365  |
|---------|:---------:|:---------:|:---------:|
|Diretiva de mensagens     |     X    |         |         |
|Política de interoperabilidade de equipes     |    X     |         |         |
|Configurações de mensagens de convidado     |   X      |         |         |
|Configurações de acesso externo    |    X     |         |         |
|Gerenciamento de usuário    |         |         |    X     |    
|Serviços de audioconferência     |    X     |    X     |         |
|Planos de Chamadas     |         |    X     |         |
|Sistema de Telefonia    |         |     X    |         |
|Gerenciamento de número de telefone     |         |   X      |         |
|Licenciamento para recursos de voz de nuvem     |         |         |    X     |
|Atendedores automáticos     |         |    X     |         |
|Filas de chamadas     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gerenciar configurações após a migração

Você será notificado quando a migração for concluída de uma seção específica dentro de equipes. Nesse momento, você poderá ver as configurações existentes para essa seção no Centro de administração do Office 365, mas não será possível fazer quaisquer modificações lá. Em vez disso, você usará o Microsoft Teams & Skype para centro de administração de negócios para gerenciar as configurações recém-migrada.

Quando a migração dessas configurações estiver concluída, podemos vai desativá-los na Central de administração do Office 365 e o Skype para Business Admin center.


