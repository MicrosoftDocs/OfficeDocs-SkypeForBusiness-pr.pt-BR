---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3142a30a5131ed18a76a130c420b3af214c5190b
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2019
ms.locfileid: "35841372"
---
<a name="teams-guest-access-checklist"></a>Lista de verificação de acesso de convidados do teams
==========================================

Use esta lista de verificação para ajudá-lo a habilitar e configurar o recurso de acesso de convidado no Microsoft Teams de acordo com as preferências da sua organização.

> [!NOTE] 
> Para as restrições de colaboração [, consulte Habilitar a colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="understand-the-limitations-for-guests"></a>Entender as limitações dos convidados

A experiência de convidado tem limitações por meio do design. Certifique-se de entender a experiência de convidado para não tentar corrigir algo que não seja um problema. Por exemplo, veja a seguir uma lista de alguns dos recursos que não estão disponíveis para um convidado no Microsoft Teams:

- OneDrive for Business
- Pesquisa de pessoas fora do teams
- Calendário, reuniões agendadas ou detalhes da reunião
- PSTN
- Organograma
- Criar ou revisar uma equipe
- Procurar uma equipe
- Carregar arquivos para um chat de pessoa para pessoa
- Os convidados ainda podem pesquisar e localizar usuários (fora de sua equipe) se saberem a identificação de email completa do usuário. Para evitar isso, os administradores de ti podem usar padrões como [pesquisa de diretório em escopo](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) que têm a capacidade de restringir convidados à sua GAL virtual.

Para obter mais detalhes, consulte o [que a experiência de convidado é como](guest-experience.md) e [acesso de convidado em grupos do Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

### <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado vs. acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> No momento, o Microsoft Teams não é compatível com a função de convidado de convidado. Pelo menos a opção "os membros podem convidar" deve ser definida como "Sim" para que o acesso de convidado funcione no Microsoft Teams. Se você definir "os membros podem convidar" para "não" e habilitar o acesso de convidado nos grupos do Office 365 e no Microsoft Teams, os administradores poderão controlar os convites convidados para seu diretório. Depois que os convidados estiverem no diretório, eles poderão ser adicionados às equipes por membros não-administradores que sejam proprietários da equipe.

## <a name="if-your-guests-are-seeing-license-errors"></a>Se seus convidados estiverem vendo erros de licença

O acesso de convidado no Microsoft Teams usa o Azure Active Directory (Azure AD) Business to Business (B2B) e seu modelo de licenciamento. Se você estiver vendo erros de licenciamento, leia a [orientação de licenciamento B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para entender os requisitos de licenciamento que a sua organização tem para que seus usuários possam convidar convidados para sua organização.

Lembre-se de algumas coisas:

- Convidados são usuários de fora da sua organização. Seus funcionários, prestadores de no local, agentes no local e assim por diante não podem ser adicionados como convidados. O mesmo se aplica às suas afiliadas.
- As licenças de convidado são contadas em relação à organização que convida. Considere isso quando você calcular o número de licenças necessárias.
- As licenças são contadas em relação à sua organização se os convidados convidados vierem de outro locatário do Office 365 ou estiverem usando seus endereços de email pessoais.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Etapa 1: definir as configurações do Azure AD para empresas

1. Entre no [portal do Azure](https://portal.azure.com) como um administrador de locatários.
2. Selecione**as configurações de usuário** **do Azure Active Directory** > **Users** > .
3. Em **usuários externos**, selecione **gerenciar configurações de colaboração externa**.
   > [!NOTE]
   > As **configurações de colaboração externa** também estão disponíveis na página **relações organizacionais** . No Azure Active Directory, em **gerenciar**, acesse**configurações**de **relações** > organizacionais.
4. Na página **configurações de colaboração externas** , escolha as políticas que você deseja habilitar.

   ![Configurações de colaboração externa](media/control-who-to-invite.png)

  - **As permissões de usuários convidados são limitadas**: esta política determina permissões para convidados em seu diretório. Selecione **Sim** para bloquear convidados de determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório. Selecione **não** para dar aos convidados o mesmo acesso aos dados do diretório como usuários regulares em seu diretório.
   - **Administradores e usuários na função de convite de convidado podem convidar**: para permitir que administradores e usuários na função "convidador de convidado" possam convidar convidados, defina essa política como **Sim**.
   - **Os membros podem convidar**: para permitir que membros que não sejam administradores do seu diretório convidem convidados, defina essa política como **Sim**.
   
       > [!NOTE]
       > Se você definir que **os membros podem convidar** para **não** e, em seguida, habilitar o acesso de convidado nos grupos do Office 365 e no Microsoft Teams, os administradores poderão controlar os convites convidados para seu diretório. Depois que os convidados estiverem no diretório, eles poderão ser adicionados às equipes por membros não-administradores que sejam proprietários da equipe. Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).
   
   - **Convidados podem convidar**: para permitir que os convidados convidem outros convidados, defina essa política como **Sim**.
   - **Habilitar a senha de senha única para convidados (visualização)**: para obter mais informações sobre o recurso de senha de uso único, consulte [autenticação de senha única (visualização) de email](one-time-passcode.md).
   - **Restrições de colaboração**: para obter mais informações sobre como permitir ou bloquear convites para domínios específicos, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](allow-deny-list.md).

## <a name="-step-2-configure-office-365-groups"></a>□ Etapa 2: configurar grupos do Office 365

1. No centro de administração do Microsoft 365, vá para **configurações** > de**Serviços & suplementos** > **do Office 365 grupos**.
2. Verifique se **deixar que os membros do grupo fora do conteúdo do grupo de acesso à organização** estejam definidos como **ativado**. Se essa configuração estiver desativada, os convidados não poderão acessar qualquer conteúdo do grupo.
3. Certifique-se de **que o recurso proprietários de grupos Adicione pessoas de fora da organização a grupos** esteja definido como **ativado**. Se essa configuração estiver desativada, os proprietários da equipe não poderão adicionar novos convidados. No mínimo, essa configuração deve estar ativada para dar suporte ao acesso de convidado.

     ![A captura de tela mostra as alternâncias dos grupos do Office 365](media/guest-access-checklist-office365.png)

Para obter instruções detalhadas sobre como definir essas configurações, consulte [gerenciar o acesso de convidados nos grupos do Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controlar o acesso de convidados a grupos do Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Etapa 3: habilitar o acesso de convidado no nível do locatário

No mínimo, você deve ativar o acesso de convidado para o Microsoft Teams no **centro de administração do Microsoft Teams**. 

1. No centro de administração do Teams, selecione o > **acesso de convidados**às **configurações de toda a organização**.
2. Defina a opção **permitir acesso de convidado no Microsoft Teams** como **ativado**.

    ![A captura de tela mostra um exemplo de alternância de configurações de equipes](media/guest-access-checklist-set-up-guests-image1.png)

3. Na mesma página, configure qualquer outra configuração de convidado necessária.
4. Clique em **Salvar**.

Para obter instruções detalhadas, confira [Ativar ou desativar o acesso de convidado ao Microsoft Teams](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Etapa 4: configurar o compartilhamento no Office 365 

Certifique-se de que os usuários possam adicionar convidados. Veja como:

1. No centro de administração do Microsoft 365, vá para **configurações** > **segurança & privacidade**.

     ![A captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Em **compartilhamento**, selecione **Editar**.

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Defina **permitir que os usuários adicionem novos convidados a essa organização** para serem **ativados**e, em seguida, clique em **salvar**.

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Essa configuração é equivalente à configuração os **Membros podem convidar** em **configurações** > do usuário**usuários externos** do Azure AD.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Etapa 5: verificar a configuração de compartilhamento no SharePoint

1. Entre no centro de administração do Microsoft 365.
2. Clique em **centro de administração**e selecione **SharePoint**.
3. No centro de administração do SharePoint, selecione **compartilhamento**.
4. Certifique-se de que a opção **não permitir o compartilhamento fora da sua organização** *não* esteja selecionada.
 
     ![A captura de tela mostra um exemplo de uma alternância de configurações online do SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Etapa 6: Habilitar configurações específicas de canais 

No aplicativo Teams, no nível individual da equipe, configure as permissões de convidado para que os convidados possam criar, atualizar e excluir canais. Além dos administradores, os proprietários da equipe podem definir essa configuração.

![A captura de tela mostra um exemplo de alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Para obter mais informações, incluindo vídeos de instruções, consulte [acesso de convidado no Microsoft Teams](guest-access.md).


## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas para adicionar convidados no Microsoft Teams, consulte o [Guia de solução de problemas de acesso de convidado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


