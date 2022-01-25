---
title: Gerenciar as configurações da sua organização
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como ativar ou desativar as configurações de toda a organização do Microsoft Teams, incluindo aplicativos, acesso externo, acesso de convidado, configurações do Teams e preferências de atualização do Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52347a620d6f441bfff68764d053a0adf71427b1
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62191102"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>Gerencie as configurações do Microsoft Teams para sua organização 

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Configurações dos aplicativos do Teams no centro de administração do Microsoft Teams.

Gerencie aplicativos para a sua organização em **aplicativos do Teams** no [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com). Por exemplo, é possível definir políticas para controlar quais aplicativos estarão disponíveis para toda a organização ou para usuários específicos do Teams e poderá personalizar o Teams fixando os aplicativos mais importantes para seus usuários.

Para saber mais, veja [Configurações de administração para aplicativos no Teams](admin-settings.md).  

## <a name="teams-external-access-and-guest-access-settings-in-the-microsoft-teams-admin-center"></a>O acesso externo ao Teams e configurações de acesso de convidado no centro de administração Microsoft Teams

Você pode controlar as configurações de acesso externo e de convidado no centro de administração Microsoft Teams. Para editar essas configurações, vá para o centro de administração Microsoft Teams e selecione **Usuários**. Você pode definir as configurações a seguir.

### <a name="external-access"></a>Acesso externo

O **acesso externo** permite que os usuários do Microsoft Teams e do Skype for Business se comuniquem com usuários que estão fora da organização ou domínio. Para configurar o acesso externo, vá para [Permitir que os usuários do Microsoft Teams conversem e se comuniquem com usuários em outra organização](./manage-external-access.md).

Para adicionar ou bloquear um domínio:

1. Selecione **Adicionar um domínio**.
2. No painel Adicionar um domínio, insira o nome do domínio e selecione a barra de espaços para salvar o nome.
3. Selecione **Permitido** ou **Bloqueado**.
4. Selecione **Concluído** para salvar as alterações. 

### <a name="guest-access"></a>Acesso de convidados

O **Acesso de Convidado** no Microsoft Teams permite que as equipes em sua organização colaborem com pessoas de fora da organização, concedendo-lhes acesso a equipes e a canais. Qualquer pessoa com uma conta de email comercial ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe. Para obter mais informações, veja [Acesso de convidado no Microsoft Teams](guest-access.md).

## <a name="teams-settings-and-teams-upgrade-settings-in-the-microsoft-teams-admin-center"></a>As configurações do Teams e configurações de atualização do Teams no centro de administração Microsoft Teams

Você pode controlar as configurações do Teams e as configurações de atualização do Teams no centro de administração do Microsoft Teams. Para editar essas configurações, vá para o centro de administração do Microsoft Teams e selecione **Teams**. Você pode definir as configurações a seguir.

### <a name="teams-settings"></a>Configurações de equipes

Nas **Configurações do Teams**, você pode configurar recursos para equipes, incluindo notificações e feeds, integração de email, opções de armazenamento em nuvem e dispositivos.

#### <a name="notifications-and-feeds"></a>Notificações e feeds

Aqui você pode controlar se os feeds sugeridos são exibidos no feed de atividades dos usuários do Teams. Para saber mais sobre o feed de atividades, confira [Explorar o feed de Atividades do Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).

#### <a name="tagging"></a>Marcação

As marcações permitem que os usuários se comuniquem com um subconjunto de pessoas em uma equipe. As marcações podem ser adicionadas a um ou mais membros da equipe. Depois que uma marcação é adicionada, ela pode ser usada em @menções por qualquer pessoa da equipe em uma postagem do canal para se comunicar apenas com as pessoas a quem essa marcação foi atribuída. Use essas configurações para controlar quem pode adicionar marcações e como elas são usadas na organização. Para saber mais, confira [Gerenciar marcações no Teams](manage-tags.md).

#### <a name="email-integration"></a>Integração de email

Ative esse recurso para que os usuários possam enviar emails para um canal no Microsoft Teams usando o endereço de email do canal. Os usuários podem fazer isso para qualquer canal pertencente a uma equipe que possuem. Os usuários também podem enviar emails para qualquer canal de uma equipe que tenha conectores adicionais ativados para membros da equipe. Para ativar a integração de email, certifique-se de que **Permitir que usuários enviem emails para um canal de endereço de email** esteja **Ativado**. Em seguida, certifique-se de que o domínio do endereço de email do remetente não esteja bloqueado em Centro de Administração no Teams> Configurações em Toda a Organização > Configurações do Teams>Integração de email>**Aceitar email do canal desses domínios SMTP**. Deve estar em branco ou incluir todos os domínios dos quais você espera receber emails. Em seguida, você precisa ter certeza de que possui as regras necessárias para garantir que [ o email para o endereço de email do canal Teams não seja bloqueado](/office365/servicedescriptions/exchange-online-protection-service-description/anti-spam-and-anti-malware-protection-eop#customize-anti-spam-policies).

#### <a name="files"></a>Arquivos

Aqui você pode ativar ou desativar as opções de compartilhamento de arquivos e armazenamento em nuvem.

Os usuários podem carregar e compartilhar arquivos de serviços de armazenamento em nuvem nos canais e chats do Microsoft Teams. As opções de armazenamento em nuvem no Teams atualmente incluem o Dropbox, Box, Citrix Files, Google Drive e Egnyte. Ative a opção para os provedores de armazenamento em nuvem que sua organização deseja usar.

#### <a name="organization"></a>Organização

Aqui você pode ativar a guia **Organização**, que mostra o organograma detalhado da organização do usuário. Para saber mais, confira [usar a guia organização no Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Dispositivos

Essas configurações controlam o comportamento da conta de recurso para dispositivos Surface Hub que participam de reuniões do Microsoft Teams. Use essas configurações para configurar os requisitos de autenticação, exigir um PIN de conteúdo e ativar as contas de recurso do Surface Hub para enviar mensagens.

- **Require a secondary form of authentication to access meeting content** (Exigir uma forma secundária de autenticação para acessar o conteúdo da reunião) ‒ selecione o nível de acesso que os usuários obtêm quando inserem o PIN do conteúdo.
- **Set content PIN** (Definir o PIN do conteúdo) ‒ exija que os usuários insiram esse PIN para impedir o acesso não autorizado a documentos. Isso impede que um usuário não autorizado ingresse em reuniões e acesse anexos.
- **Resource accounts can send messages** (Contas de recurso podem enviar mensagens) ‒ **ative** essa configuração para permitir que mensagens sejam enviadas da conta de recurso do Surface Hub.

#### <a name="search-by-name"></a>Pesquisar por nome

A pesquisa de diretório no escopo do Microsoft Teams usa a APB (política de catálogo de endereços) do Exchange para permitir que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários na organização. Você pode usar uma pesquisa de diretório no escopo em situações como estas:

- Sua organização tem várias empresas dentro no locatário que você deseja manter separadas. 
- Sua escola quer limitar os chats entre professores e alunos.

**Ative** essa configuração para ativar as pesquisas de diretório no escopo.

#### <a name="safety-and-communications"></a>Segurança e comunicações

O chat animado permite que organizações e escolas limitem os recursos de chat usando permissões baseadas em função. Essas permissões controlam a quantidade de supervisão que um usuário exige ao conversar com outras pessoas. Saiba mais sobre [conversas no](supervise-chats-edu.md).

### <a name="teams-upgrade-settings"></a>Configurações de atualização do Teams

Você pode usar essas configurações para definir como os usuários serão atualizados do Skype for Business para o Microsoft Teams. 

#### <a name="coexistence-mode"></a>Modo de coexistência
Você pode especificar um modo de coexistência: 

- **Somente Teams**
- **Uso Paralelo** (O Teams e o Skype for Business coexistirão)
- **Somente Skype for Business**
- **Skype For Business com colaboração do Teams** (Os usuários recebem chats e chamadas e agendam reuniões no Skype for Business, mas usam o Teams para colaboração em grupo)
- **Colaboração e reuniões com o Skype for Business e o Teams** (Os usuários recebem chats e chamadas no Skype for Business, mas usam o Teams para colaboração em grupo e para agendar reuniões)

O modo de coexistência escolhido determina o roteamento de chats e chamadas recebidas e o aplicativo usado pelo usuário para iniciar chats e chamadas ou para agendar reuniões. Para obter mais informações sobre modos de coexistência, acesse [Entender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Preferências de aplicativo

Aqui você pode escolher o aplicativo que os usuários usarão para ingressar em reuniões do Skype for Business (Skype for Business ou o [aplicativo Reuniões do Skype](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Essa configuração não depende da configuração do modo de coexistência.

### <a name="planning-settings-in-the-microsoft-teams-admin-center"></a>Planejando configurações no centro de administração do Microsoft Teams

#### <a name="network-planner"></a>Planejador de Rede

O planejador de rede ajuda a determinar e organizar os requisitos de rede para conectar os usuário do Teams em sua organização.  Saiba como [Usar o Planejador de Rede no Microsoft Teams](./network-planner.md).

Você também pode selecionar a opção "Baixar o aplicativo do Teams em segundo plano para usuários do Skype for Business".  Por padrão, essa configuração é definida como Ativada. Com essa configuração ativada, será realizado o download do aplicativo Teams em segundo plano para usuários que executam o aplicativo Skype for Business em computadores com Windows. Isso acontece se o modo de coexistência para o usuário for Somente Teams ou se uma notificação de atualização pendente estiver ativada no aplicativo Skype for Business.

## <a name="other-settings-in-the-microsoft-teams-admin-center"></a>Outras configurações no centro de administração do Microsoft Teams

### <a name="skype-for-business"></a>Skype for Business

Use essa página para gerenciar os recursos do Skype for Business para usuários do Skype for Business na sua organização. Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](skype-for-business-settings.md).

## <a name="how-can-i-tell-which-features-are-available"></a>Como saber quais recursos estão disponíveis?

Confira o [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) para obter informações sobre novos recursos do Teams. Para obter mais informações sobre os recursos novos e futuros, confira a página [Novidades](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) do Teams e o [blog do Microsoft Teams da Tech Community Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Mais informações

Para obter informações sobre quais funções podem executar funções administrativas, confira [Usar funções administrativas do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md).
