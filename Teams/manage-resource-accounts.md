---
title: Gerenciar contas de recursos no Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Saiba mais sobre como gerenciar contas de recursos no Microsoft Teams
ms.openlocfilehash: d8f3e2893962524c09340ef80ccf13376733d4d4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291504"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

Uma conta de recurso também é conhecida como objeto de usuário desabilitado no Azure Active Directory e pode ser usada para representar recursos em geral. No Exchange, ele pode ser usado para representar salas de conferência, por exemplo, e permitir que elas tenham um número de telefone. Uma conta de recurso pode ser hospedada no Microsoft 365 ou localmente usando o Skype for Business Server, e essas contas são criadas usando os comandos do PowerShell.

No Microsoft Teams ou no Skype for Business Online, cada fila de chamadas ou atendedor automático é necessário para ter uma conta de recurso associada. Se uma conta de recurso precisa de um número de telefone atribuído dependerá do uso pretendido da fila de chamadas ou do atendedor automático associado. Consulte os artigos sobre filas de chamadas e atendedores automáticos vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online. Para contas de recursos hospedadas no Skype for Business Server 2019, consulte [Configurar atendedores automáticos na nuvem](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant).

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Pré-requisitos para atribuir um número de telefone a uma conta de recurso

Para começar, é importante lembrar-se de algumas coisas:
  
- Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada. 
- A conta do recurso precisará de um número de telefone atribuído se ele for atribuído a um atendedor automático de nível superior ou fila de chamadas. 
- Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta do recurso associado só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamadas.
- Você só precisa licenciar as contas de recursos com um número de telefone atribuído a ela. Em um atendedor automático aninhado ou fila de chamadas, você não precisa licenciar o restante dos atendedores automáticos ou filas de chamadas se eles não tiverem números de telefone associados a eles.
- Se você estiver atribuindo um número de telefone que é usado com o roteamento direto e tiver uma licença Enterprise E1 ou E3, você deve comprar e atribuir uma licença do sistema telefônico para você ser a conta do recurso que você está usando. Se você tiver uma licença Enterprise e5, o sistema de telefonia já está incluído, portanto, não é necessário comprar uma. 
- Se estiver atribuindo um número de serviço da Microsoft, você precisará adquirir e atribuir as seguintes licenças à sua conta \(de recurso Office 365 Enterprise E1, E3 ou e5, com o complemento do sistema de telefonia e um plano\)de chamadas.
- Você pode atribuir um número híbrido de roteamento direto à sua conta de recurso.  Consulte [planejar o roteamento direto](direct-routing-plan.md) para obter detalhes.
- Para planos de chamada da Microsoft, você pode atribuir somente números de telefone de serviço de chamada tarifada e tarifada que você recebeu no **centro de administração do Microsoft Teams** ou portado de outro provedor de serviços para uma conta de recurso. Para obter e usar números de serviço de chamada gratuita, você precisa configurar créditos de comunicações.

> [!NOTE]
> Os números de serviço de roteamento direto atribuídos a contas de recursos para atendedor automático e filas de chamadas são suportados somente para usuários e agentes do Microsoft Teams.
>
> A Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos da nuvem e filas de chamadas, por ora, você precisa usar o modelo de licenciamento do usuário.
>
> Para redirecionar chamadas para as pessoas em sua organização que estão online, elas devem ter uma licença de **sistema telefônico** e estar habilitadas para o Enterprise Voice ou ter planos de chamada do Office 365. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
>
> Os números de telefone do usuário (assinante) não podem ser atribuídos a uma conta do recurso. Somente números de telefone de chamada tarifada ou gratuita do serviço podem ser usados.
>
> Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço. Vá para [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez de ver como fazer isso de fora dos Estados Unidos.

### <a name="phone-numbers"></a>Telefones

A criação de uma conta de recurso que usa um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:

1. Transferir ou obter um número de serviço de chamada tarifada ou gratuita. O número não pode ser atribuído a outros serviços de voz ou contas de recursos.

   Antes de atribuir um número de telefone a uma conta de recurso, você precisará adquirir ou portar seus números de serviço de chamada tarifada ou chamada gratuitas existentes. Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles serão exibidos no **Centro** > de administração do Microsoft Teams para**números de telefone**de**voz** > , e o **tipo de número** listado será listado como **serviço-chamada gratuita**. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).

2. Compre uma licença do sistema de telefonia e um plano de chamadas. Vejam  
   - [Office 365 Enterprise E1 e E3](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 Enterprise E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [](https://products.office.com/business/office-365-enterprise-e5-business-software)- [Planos de chamadas de](calling-plans-for-office-365.md) software empresariais do Office 365 Enterprise E5 para o Office 365

3. Criar uma nova conta de recurso. Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell)
4. Atribua a licença do sistema de telefone e o plano de chamada à conta do recurso. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md) e [atribuir licenças a um usuário](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Atribua o número de serviço à conta do recurso. Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).

Uma conta de recurso que não exija um número de telefone pode omitir as etapas 1, 2 e 5.

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Criar uma conta de recurso no centro de administração do Microsoft Teams

Depois de comprar uma licença do sistema de telefonia e um plano de chamada usando o centro de administração do Microsoft Teams, navegue até > **contas de recursos**de **configurações de toda a organização**. 

![ficheiro](media/r-a-master.png)

![número 1](media/sfbcallout1.png)

Para criar uma nova conta de recurso, clique em **+ nova conta**. No pop-up, preencha o nome para exibição e o nome de usuário da conta do recurso (o nome do domínio deve ser preenchido automaticamente) e clique em **salvar**.

![conta do recurso](media/res-acct.png)

Em seguida, aplique uma licença para a conta do recurso no centro de administração do O365, conforme descrito em [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)

### <a name="assignunassign-phone-numbers-and-services"></a>Atribuir/cancelar a atribuição de números de telefone e serviços

![número 3](media/sfbcallout3.png) depois de criar a conta do recurso e atribuir a licença, você pode clicar em **atribuir/Cancelar atribuição** para atribuir um número de serviço de plano de chamada à conta do recurso ou atribuir a conta do recurso a um atendedor automático ou à fila de chamadas que Já existe. Só é possível fazer a atribuição de um número de roteamento direto usando cmdlets. Se a fila de chamadas ou o atendedor automático ainda precisar ser criado, você poderá vincular a conta do recurso enquanto a cria. Clique em **salvar** quando terminar.

Use o cmdlet a seguir para atribuir um número de roteamento direto: 
``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber tel:+14250000000
```

> [!IMPORTANT]
> Se o seu locatário não tiver comprado uma licença do sistema de telefonia e um plano de chamadas, uma verificação interna causará uma falha quando você tentar atribuir o número de telefone à conta do recurso. Você não poderá atribuir o número ou associar a conta do recurso a um serviço.

![atribuir conta de recurso](media/r-a-assign.png)

![número 2](media/sfbcallout2.png) você pode editar o nome de exibição da conta do recurso usando a opção de **edição** .  Clique em **salvar** quando terminar.
![editar conta do recurso](media/r-a-edit.png)

## <a name="create-a-resource-account-in-powershell"></a>Criar uma conta de recurso no PowerShell

Para planos de chamada da Microsoft, você pode atribuir somente números de telefone de serviço de chamada tarifada e tarifada que você recebeu no **centro de administração do Microsoft Teams** ou portado de outro provedor de serviços para uma conta de recurso. Para obter e usar números de serviço de chamada gratuita, você precisa configurar créditos de comunicações.

Dependendo de se a sua conta de recurso está localizada online ou no local, você precisa se conectar ao prompt apropriado do PowerShell com privilégios de administrador. 
- Os exemplos dos seguintes cmdlets do PowerShell presumem que a conta do recurso seja hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para criar uma conta de recurso que está hospedada online.

- Para contas de recursos hospedadas localmente no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [configurar filas de chamadas em nuvem](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) ou [Configurar atendedores automáticos da nuvem](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md). As implementações híbridas (números hospedados no roteamento direto) usarão [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).

A identificação do aplicativo que você precisa usar ao criar as instâncias do aplicativo são:
- **Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Fila de chamadas:** 11cd3e2e-fccb-42AD-ad00-878b93575e07

> [!NOTE]
> Se quiser que a fila de chamadas ou o atendedor automático seja pesquisado por usuários locais, você deve criar suas contas de recursos no local, pois as contas de recursos online não são sincronizadas com o Active Directory.

1. Para criar uma conta de recurso online para uso com um atendedor automático, use o comando a seguir.  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. Você não poderá usar a conta do recurso antes de aplicar uma licença a ele. Para saber como aplicar uma licença a uma conta no centro de administração do O365, consulte [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) e [atribuir licenças do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Adicionais Depois que a licença correta for aplicada à conta do recurso, você poderá definir um número de telefone para a conta do recurso, como mostrado a seguir. Nem todas as contas do recurso precisarão de um número de telefone. Se você não aplicou uma licença à conta do recurso, a atribuição de número de telefone falhará.

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Consulte [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre este comando.

> [!NOTE]
> É mais fácil definir o número de telefone online usando o centro de administração do Microsoft Teams, conforme descrito anteriormente.

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams

Para gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams, navegue até  > **contas de recursos**de **configurações de toda a organização**, selecione a conta do recurso para o qual você precisa alterar as configurações e clique no botão **Editar** . na tela **Editar conta do recurso** , você poderá alterar estas configurações:

- **Nome para exibição** da conta
- Fila de chamadas ou atendedor automático que usa a conta
- Número de telefone atribuído à conta

Quando terminar, clique em **salvar**.

## <a name="delete-a-resource-account"></a>Excluir uma conta de recurso

Certifique-se de dissociar o número de telefone da conta do recurso antes de excluí-lo para evitar que o número do seu serviço fique preso no modo pendente. Você pode fazer isso usando o commandlet a seguir: 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

Depois de fazer isso, você pode excluir a conta do recurso do portal de administração do O365, na guia usuários.

## <a name="related-information"></a>Informações relacionadas

Para implementações híbridas com o Skype for Business Server:

[Atendedores automáticos do plano da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar os atendedores automáticos da nuvem](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para implementações do teams ou do Skype for Business Online:

[Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)

[Configurar um atendedor automático do Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Exemplo de pequenas empresas - Configurar um atendedor automático](/microsoftteams/tutorial-org-aa)

[Criar uma fila de chamada do Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
