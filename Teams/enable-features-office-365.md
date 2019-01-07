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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a36c0a23076c5aa172824fe85103c57a8494dbf
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458474"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="b7899-103">Gerenciar os recursos do Microsoft Teams em sua organização do Office 365</span><span class="sxs-lookup"><span data-stu-id="b7899-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

<span data-ttu-id="b7899-p101">Todas as configurações do Microsoft Teams serão migradas em breve para o novo Centro de Administração do Microsoft Teams e do Skype for Business. O único recurso do Microsoft Teams gerenciado no centro de administração do Office 365 consiste nos Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b7899-p101">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center. The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="b7899-106">A menos que haja aluma especificação em contrário, o valor padrão das opções é **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="b7899-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="b7899-107">Configurações de todos os locatários do Office 365</span><span class="sxs-lookup"><span data-stu-id="b7899-107">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="b7899-108">Em **Configurações de todos os locatários**, você pode ativar ou desativar Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b7899-108">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="b7899-p102">Para editar **Configurações de todos os locatários** para o Microsoft Teams, acesse o Centro de Administração do Microsoft Teams e do Skype for Business e selecione o **Portal herdado**. Escolha **Configurações** > **Serviços e suplementos** > **Microsoft Teams**. Se você tiver entrado como administrador do Office 365, esse link deverá levá-lo corretamente ao local correto:</span><span class="sxs-lookup"><span data-stu-id="b7899-p102">To edit **Tenant-wide settings** for Teams, go to the Microsoft Teams & Skype for Business Admin Center, and select **Legacy portal**. Choose **Settings** > **Services & add-ins** > **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="b7899-112">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="b7899-112">Apps</span></span>

<span data-ttu-id="b7899-p103">Os aplicativos consistem em guias, conectores, bots ou qualquer combinação dos três, fornecidos por um serviço de terceiros. Existem políticas de administração do Teams que podem ser configuradas no Centro de administração do Office 365 para controlar quais aplicativos externos de terceiros são permitidos. Essas políticas permitem especificar quais aplicativos são permitidos ou não, o comportamento do novo aplicativo externo e se o sideload de aplicativos é permitido.</span><span class="sxs-lookup"><span data-stu-id="b7899-p103">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="b7899-116">Em **Aplicativos**, você pode definir estas configurações para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="b7899-116">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Captura de tela da seção de aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="b7899-118">**Allow external apps in Microsoft Teams** (Permitir aplicativos externos no Microsoft Teams): quando essa opção está ativada, os usuários podem adicionar guias e bots disponíveis para o locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7899-118">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Captura de tela do controle de permissão de aplicativos externos na seção Aplicativos.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="b7899-p104">**Enable new external apps by default** (Habilitar novos aplicativos externos por padrão): quando essa opção está ativada, os usuários podem ativar novos aplicativos assim que eles são adicionados ao catálogo de aplicativos do Teams. Desative essa opção para poder controlar os novos aplicativos. Obviamente, se você desativá-la, precisará lembrar de revisar os novos aplicativos periodicamente para que sua organização não perca novos aplicativos bacanas.</span><span class="sxs-lookup"><span data-stu-id="b7899-p104">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this switch if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="b7899-123">**Allow sideloading of external apps** (Permitir o sideload de aplicativos externos): quando essa opção está ativada, os usuários podem instalar e habilitar bots e guias personalizados.</span><span class="sxs-lookup"><span data-stu-id="b7899-123">**Allow sideloading of external apps**: When this switch is turned on, users can install and turn on custom bots and tabs.</span></span> 

<span data-ttu-id="b7899-124">Para saber mais, leia [Configurações de administração para aplicativos no Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b7899-124">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

## <a name="teams-org-wide-settings"></a><span data-ttu-id="b7899-125">Configurações de toda a organização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7899-125">Teams org-wide settings</span></span>

<span data-ttu-id="b7899-126">Você pode controlar as configurações de usuário de toda a organização no Centro de Administração do Microsoft Teams e do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b7899-126">You can control organization-wide user settings in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="b7899-127">Para editar as configurações de toda a organização, vá para o Centro de Administração do Microsoft Teams e Skype for Business e selecione **Configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="b7899-127">To edit org-wide settings, go to the Microsoft Skype for Business Admin Center, and then select **Org-wide settings**.</span></span> <span data-ttu-id="b7899-128">É possível definir as configurações a seguir</span><span class="sxs-lookup"><span data-stu-id="b7899-128">You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="b7899-129">Acesso externo</span><span class="sxs-lookup"><span data-stu-id="b7899-129">External access</span></span>

<span data-ttu-id="b7899-p106">O **acesso externo** permite que os usuários do Microsoft Teams e do Skype for Business se comuniquem com usuários que estão fora da organização. Para configurar o acesso externo, vá para [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md) (Permitir que os usuários do Microsoft Teams conversem e se comuniquem com usuários em outra organização do Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="b7899-p106">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization. To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

### <a name="guest-access"></a><span data-ttu-id="b7899-132">Acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="b7899-132">Guest access</span></span>

<span data-ttu-id="b7899-p107">O **Acesso de Convidado** no Microsoft Teams permite que as equipes em sua organização colaborem com pessoas de fora da organização, concedendo-lhes acesso a equipes e a canais. Qualquer pessoa com uma conta de email comercial ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe. Para obter mais informações, veja [Acesso de convidado no Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="b7899-p107">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="b7899-136">Configurações de equipes</span><span class="sxs-lookup"><span data-stu-id="b7899-136">Teams settings</span></span>

<span data-ttu-id="b7899-137">Nas **Configurações de equipe**, você pode configurar a integração de email, opções de armazenamento em nuvem, interoperabilidade do Skype for Business e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7899-137">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="b7899-138">Integração de e-mails</span><span class="sxs-lookup"><span data-stu-id="b7899-138">Email integration</span></span>

<span data-ttu-id="b7899-p108">Ative esse recurso para que os usuários possam enviar emails para um canal no Microsoft Teams usando o endereço de email do canal. Os usuários podem fazer isso para qualquer canal pertencente a uma equipe que possuem. Os usuários também podem enviar emails a qualquer canal de uma equipe que tenha conectores adicionais ativados para os membros da equipe. Para ativar a integração de email, verifique se **Allow users to send emails to a channel email address** (Permitir que os usuários enviem emails para um endereço de email do canal) está **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="b7899-p108">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="b7899-143">Arquivos</span><span class="sxs-lookup"><span data-stu-id="b7899-143">Files</span></span>

<span data-ttu-id="b7899-144">Aqui você pode ativar ou desativar as opções de compartilhamento de arquivos e armazenamento em nuvem.</span><span class="sxs-lookup"><span data-stu-id="b7899-144">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="b7899-p109">Os usuários podem carregar e compartilhar arquivos de serviços de armazenamento em nuvem nos canais e chats do Microsoft Teams. No momento, as opções de armazenamento em nuvem do Microsoft Teams incluem ShareFile, Dropbox, Box e Google Drive. Ative a opção para os provedores de armazenamento em nuvem que sua organização deseja usar.</span><span class="sxs-lookup"><span data-stu-id="b7899-p109">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="b7899-148">Organização</span><span class="sxs-lookup"><span data-stu-id="b7899-148">Organization</span></span>

<span data-ttu-id="b7899-p110">Aqui você pode ativar a guia **Organização**, que mostra o organograma detalhado da organização do usuário. Para obter mais informações, veja [Usar a guia da organização no Microsoft Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span><span class="sxs-lookup"><span data-stu-id="b7899-p110">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="skype-for-business-interop"></a><span data-ttu-id="b7899-151">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b7899-151">Skype for Business interop</span></span>

<span data-ttu-id="b7899-p111">Use essa configuração para permitir que os usuários do Microsoft Teams conversem com usuários do Skype for Business. Para obter informações detalhadas sobre a interoperabilidade entre o Microsoft Teams e o Skype for Business, acesse [Entender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="b7899-p111">Use this setting to let Teams users chat with Skype for Business users. For detailed information about interoperability between Teams and Skype for Business, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="devices"></a><span data-ttu-id="b7899-154">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="b7899-154">Devices</span></span>

<span data-ttu-id="b7899-p112">Essas configurações controlam o comportamento da conta de recurso para dispositivos Surface Hub que participam de reuniões do Microsoft Teams. Use essas configurações para configurar os requisitos de autenticação, exigir um PIN de conteúdo e ativar as contas de recurso do Surface Hub para enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="b7899-p112">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="b7899-157">**Require a secondary form of authentication to access meeting content** (Exigir uma forma secundária de autenticação para acessar o conteúdo da reunião) ‒ selecione o nível de acesso que os usuários obtêm quando inserem o PIN do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b7899-157">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="b7899-p113">**Set content PIN** (Definir o PIN do conteúdo) ‒ exija que os usuários insiram esse PIN para impedir o acesso não autorizado a documentos. Isso impede que um usuário não autorizado ingresse em reuniões e acesse anexos.</span><span class="sxs-lookup"><span data-stu-id="b7899-p113">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="b7899-160">**Resource accounts can send messages** (Contas de recurso podem enviar mensagens) ‒ **ative** essa configuração para permitir que mensagens sejam enviadas da conta de recurso do Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b7899-160">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search"></a><span data-ttu-id="b7899-161">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="b7899-161">Search</span></span>

<span data-ttu-id="b7899-p114">A pesquisa de diretório no escopo do Microsoft Teams usa a APB (política de catálogo de endereços) do Exchange para permitir que as organizações criem limites virtuais que controlam como os usuários podem encontrar e se comunicar com outros usuários na organização. Você pode usar uma pesquisa de diretório no escopo em situações como estas:</span><span class="sxs-lookup"><span data-stu-id="b7899-p114">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="b7899-164">Sua organização tem várias empresas dentro no locatário que você deseja manter separadas.</span><span class="sxs-lookup"><span data-stu-id="b7899-164">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="b7899-165">Sua escola quer limitar os chats entre professores e alunos.</span><span class="sxs-lookup"><span data-stu-id="b7899-165">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="b7899-166">**Ative** essa configuração para ativar as pesquisas de diretório no escopo.</span><span class="sxs-lookup"><span data-stu-id="b7899-166">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="b7899-167">Atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7899-167">Teams upgrade</span></span>

<span data-ttu-id="b7899-168">Você pode usar essas configurações para definir como os usuários serão atualizados do Skype for Business para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b7899-168">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="b7899-169">Modo de coexistência</span><span class="sxs-lookup"><span data-stu-id="b7899-169">Coexistence mode</span></span>
<span data-ttu-id="b7899-p115">Você pode especificar um modo de coexistência: **Somente Microsoft Teams**, **Ilhas** (o Microsoft Teams e o Skype for Business coexistem) ou **Somente Skype for Business**. O modo de Coexistência escolhido determina o roteamento de chats e chamadas recebidas e o aplicativo usado pelo usuário para iniciar chats e chamadas ou para agendar reuniões. Para obter mais informações sobre modos de coexistência, acesse [Entender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="b7899-p115">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**. The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings. For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="b7899-173">Preferências de aplicativo</span><span class="sxs-lookup"><span data-stu-id="b7899-173">App preferences</span></span>

<span data-ttu-id="b7899-p116">Aqui você pode escolher o aplicativo que os usuários usarão para ingressar em reuniões do Skype for Business (Skype for Business ou o [aplicativo Reuniões do Skype](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Essa configuração não depende da configuração do modo de coexistência.</span><span class="sxs-lookup"><span data-stu-id="b7899-p116">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="b7899-176">Como saber quais recursos estão disponíveis?</span><span class="sxs-lookup"><span data-stu-id="b7899-176">How can I tell which features are available?</span></span>

<span data-ttu-id="b7899-p117">Confira o [Roteiro do Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) para obter informações sobre novos recursos do Microsoft Teams. Para obter mais informações sobre os recursos novos e futuros, confira a página [Novidades](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) do Microsoft Teams e o [blog do Microsoft Teams da Tech Community Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531).</span><span class="sxs-lookup"><span data-stu-id="b7899-p117">See the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="b7899-179">Mais informações</span><span class="sxs-lookup"><span data-stu-id="b7899-179">More information</span></span>

<span data-ttu-id="b7899-180">Para obter informações sobre quais funções podem executar funções administrativas, confira [Usar funções administrativas do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b7899-180">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
