---
title: Gerenciar os recursos do Microsoft Teams em sua organização do Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como ativar ou desativar os aplicativos Microsoft Teams em sua organização do Office 365, inclusive guias, conectores, bots ou qualquer combinação dos três.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7712caa826804d26fd2e3527183128ce78520c3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460232"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Gerenciar os recursos do Microsoft Teams em sua organização do Office 365

Todas as configurações do Teams serão migradas em breve para o novo centro de administração do Microsoft Teams. O único recurso do Teams gerenciado no centro de administração do Microsoft 365 consiste nos Aplicativos. 

A menos que haja aluma especificação em contrário, o valor padrão das opções é **Ativado**.

## <a name="tenant-wide-settings"></a>Configurações de locatário 

Você pode desativar ou ativar aplicativos para o Microsoft Teams em **Configurações de todos os locatários** no centro de administração do Microsoft 365. 

Para editar **Configurações de todos os locatários** para o Microsoft Teams, acesse o Centro de Administração do Microsoft Teams e escolha **Configurações** > **Serviços e suplementos** > **Microsoft Teams**. Se você tiver entrado como administrador do Office 365, este link deverá levá-lo ao local correto: 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Aplicativos

Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, also known as default apps) or by a third-party (also known as external apps). Under **Apps**, you can enable and disable default apps and configure settings to control external apps.  

#### <a name="default-apps"></a>Aplicativos padrão

These apps, such as Planner, Praise, and Weather, are provided by Teams. To turn on an app, select the check box for that app. To turn off an app, clear the check box. 

![Captura de tela da seção Aplicativos Padrão.](media/teams-manage-features-in-office365-image1.png "Captura de tela da seção Aplicativos Padrão.")

#### <a name="external-apps"></a>Aplicativos externos

These apps are provided by third parties. You can configure the following settings for external apps.

![Captura de tela da seção Aplicativos externos.](media/teams-manage-features-in-office365-image2.png "Captura de tela da seção Aplicativos externos, mostrando configurações que você pode ativar e desativar")

- **Allow external apps in Microsoft Teams** (Permitir aplicativos externos no Microsoft Teams): quando essa configuração está ativada, os usuários podem adicionar aplicativos externos disponíveis para sua organização. 

- **Allow sideloading of external apps**: If you want to turn on some external apps and turn off others , turn off this setting, and then in the list of external apps, turn off the apps that you don't want users to access. When this setting is turned on, team owners and members who are granted permission can sideload apps to Teams. 

- **Enable new external apps by default**: When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this setting if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on new apps. 

Para saber mais, veja [Configurações de administração para aplicativos no Microsoft Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Configurações de toda a organização do Microsoft Teams

Você pode controlar as configurações de usuário em toda a organização no centro de administração do Microsoft Teams. Para editar as configurações de toda a organização, vá até o centro de administração do Microsoft Teams e escolha **Configurações gerais da organização**. Você pode definir as seguintes configurações.

### <a name="external-access"></a>Acesso externo

O **acesso externo** permite que os usuários do Microsoft Teams e do Skype for Business se comuniquem com usuários que estão fora da organização. Para configurar o acesso externo, vá para [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md) (Permitir que os usuários do Microsoft Teams conversem e se comuniquem com usuários em outra organização do Microsoft Teams).

### <a name="guest-access"></a>Acesso de convidados

O **Acesso de Convidado** no Microsoft Teams permite que as equipes em sua organização colaborem com pessoas de fora da organização, concedendo-lhes acesso a equipes e a canais. Qualquer pessoa com uma conta de email comercial ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe. Para obter mais informações, veja [Acesso de convidado no Microsoft Teams](guest-access.md).

### <a name="teams-settings"></a>Configurações de equipes

Nas **Configurações de equipe**, você pode configurar a integração de email, opções de armazenamento em nuvem, interoperabilidade do Skype for Business e dispositivos.

#### <a name="email-integration"></a>Integração de email

Ative esse recurso para que os usuários possam enviar emails para um canal no Microsoft Teams usando o endereço de email do canal. Os usuários podem fazer isso para qualquer canal pertencente a uma equipe que possuem. Os usuários também podem enviar emails a qualquer canal de uma equipe que tenha conectores adicionais ativados para os membros da equipe. Para ativar a integração de email, verifique se **Allow users to send emails to a channel email address** (Permitir que os usuários enviem emails para um endereço de email do canal) está **Ativado**. 

#### <a name="files"></a>Arquivos

Aqui você pode ativar ou desativar as opções de compartilhamento de arquivos e armazenamento em nuvem. 

Os usuários podem carregar e compartilhar arquivos de serviços de armazenamento em nuvem nos canais e chats do Microsoft Teams. No momento, as opções de armazenamento em nuvem do Microsoft Teams incluem ShareFile, Dropbox, Box e Google Drive. Ative a opção para os provedores de armazenamento em nuvem que sua organização deseja usar.

#### <a name="organization"></a>Organização

Aqui você pode ativar a guia **Organização**, que mostra o organograma detalhado da organização do usuário. Para obter mais informações, veja [Usar a guia da organização no Microsoft Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Dispositivos

Essas configurações controlam o comportamento da conta de recurso para dispositivos Surface Hub que participam de reuniões do Microsoft Teams. Use essas configurações para configurar os requisitos de autenticação, exigir um PIN de conteúdo e ativar as contas de recurso do Surface Hub para enviar mensagens.

- **Require a secondary form of authentication to access meeting content** (Exigir uma forma secundária de autenticação para acessar o conteúdo da reunião) ‒ selecione o nível de acesso que os usuários obtêm quando inserem o PIN do conteúdo.
- **Set content PIN** (Definir o PIN do conteúdo) ‒ exija que os usuários insiram esse PIN para impedir o acesso não autorizado a documentos. Isso impede que um usuário não autorizado ingresse em reuniões e acesse anexos.
- **Resource accounts can send messages** (Contas de recurso podem enviar mensagens) ‒ **ative** essa configuração para permitir que mensagens sejam enviadas da conta de recurso do Surface Hub.

#### <a name="search"></a>Pesquisa

A pesquisa de diretório no escopo do Microsoft Teams usa a APB (política de catálogo de endereços) do Exchange para permitir que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários na organização. Você pode usar uma pesquisa de diretório no escopo em situações como estas:

- Sua organização tem várias empresas dentro no locatário que você deseja manter separadas. 
- Sua escola quer limitar os chats entre professores e alunos. 

**Ative** essa configuração para ativar as pesquisas de diretório no escopo.

### <a name="teams-upgrade"></a>Atualização do Microsoft Teams

Você pode usar essas configurações para definir como os usuários serão atualizados do Skype for Business para o Microsoft Teams. 

#### <a name="coexistence-mode"></a>Modo de coexistência
Você pode especificar um modo de coexistência: **Somente Microsoft Teams**, **Ilhas** (o Microsoft Teams e o Skype for Business coexistem) ou **Somente Skype for Business**. O modo de Coexistência escolhido determina o roteamento de chats e chamadas recebidas e o aplicativo usado pelo usuário para iniciar chats e chamadas ou para agendar reuniões. Para obter mais informações sobre modos de coexistência, acesse [Entender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Preferências de aplicativo

Aqui você pode escolher o aplicativo que os usuários usarão para ingressar em reuniões do Skype for Business (Skype for Business ou o [aplicativo Reuniões do Skype](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Essa configuração não depende da configuração do modo de coexistência.

## <a name="how-can-i-tell-which-features-are-available"></a>Como saber quais recursos estão disponíveis?

Confira o [Roteiro do Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) para obter informações sobre novos recursos do Teams. Para obter mais informações sobre os recursos novos e futuros, confira a página [Novidades](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) do Teams e o [blog do Microsoft Teams da Tech Community Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Mais informações

Para obter informações sobre quais funções podem executar funções administrativas, confira [Usar funções administrativas do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md).
