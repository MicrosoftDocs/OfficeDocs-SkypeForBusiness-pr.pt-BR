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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Saiba mais sobre como gerenciar contas de recurso no Microsoft Teams
ms.openlocfilehash: a5b03c8bca7bcc8e012331afe9835a8de6cfe99a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203277"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

Uma conta de recurso é também conhecido como um objeto de usuário desabilitadas no Windows Azure Active Directory e pode ser usada para representar os recursos em geral. No Exchange pode ser usada para representar a salas de conferência, por exemplo e permitir que eles tiverem um número de telefone. Uma conta de recurso pode ser hospedada no Microsoft 365 ou no local usando Skype para Business server, e essas contas são criadas usando comandos do Powershell.

No Microsoft Teams ou Skype para Business Online, cada fila de chamada ou automático attendant é necessária para ter uma conta de recurso associado. Se uma conta de recurso precisa de um número de telefone atribuído dependem o uso pretendido da fila chamada associado ou atendedor automático. Consulte os artigos sobre filas de chamada e vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso de atendedores automáticos de um.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e Skype para Business Online.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Pré-requisitos para atribuir um número de telefone a uma conta de recurso

Para começar é importante se lembrar de algumas coisas:
  
- Uma fila de chamada e o atendente automático é necessário ter uma conta de recurso associado. Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.
- Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).
- Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).
- Você só precisa licenciar as contas de recursos com um número de telefone atribuído a eles. Em uma fila de chamada e atendente automático aninhados, você não precisará licenciar o restante dos atendedores automáticos ou chamada filas se eles não tiverem números de telefone associados a eles

> [!NOTE] 
> Diretos números de serviço de roteamento para atendedor automático e filas de chamada é suportado para usuários de Teams da Microsoft e operadores somente no momento.

> [!NOTE] 
> Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.
    
> [!NOTE]
> Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365. Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md). Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Você pode atribuir um número de híbrido de roteamento direto à sua conta do recurso.  Para obter detalhes, consulte [Planejar roteamento direto](direct-routing-plan.md) .
- Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou duas portas de outro provedor de serviços para uma conta de recurso. Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.

> [!NOTE]
> Números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso. Apenas os números de telefone gratuitos ou tarifas do serviço podem ser usados.

Para atribuir um número de telefone a uma conta de recurso, você precisará obter ou porta sua chamada Tarifada existente ou serviço gratuito números. Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**. Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você deseja transferir um número existente de serviço, consulte [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço. Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Criar uma conta de recurso no Centro de administração do Microsoft Teams

No Centro de administração do Microsoft Teams, navegue até **configurações de toda a organização** > **contas de recurso**. 

![asd](media/r-a-master.png)

![número 1](media/sfbcallout1.png)

Para criar um novo recurso conta, clique em **+ nova conta**. Na janela pop-up, preencha o nome para exibição e o nome de usuário para a conta do recurso (o nome de domínio deve preencher automaticamente), em seguida, clique em **Salvar**.

![conta do recurso](media/res-acct.png)

Em seguida, você precisará aplicar uma licença para a conta do recurso, conforme descrito em [Atribuir licenças aos usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)

![número 3](media/sfbcallout3.png) depois que você criou a conta do recurso e atribuído a licença, você pode clicar em **Cancelar atribuir/atribuição** para atribuir um número de telefone para a conta do recurso ou atribuir o recurso de conta para um atendedor automático ou chamada fila que já existe. Se sua fila de chamada ou atendedor automático precisa ser criado, você pode vincular a conta do recurso enquanto você criá-lo. Clique em **Salvar** quando terminar.

![atribuir a conta de recurso](media/r-a-assign.png)

![número 2](media/sfbcallout2.png) você pode editar o nome de exibição da conta de recurso usando a opção de **Editar** .  Clique em **Salvar** quando terminar.
![Editar a conta do recurso](media/r-a-edit.png)

## <a name="create-a-resource-account-in-powershell"></a>Criar uma conta de recurso no Powershell

Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou duas portas de outro provedor de serviços para uma conta de recurso. Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.

Dependendo se a sua conta do recurso está localizada online ou no local, você precisará conectar-se ao prompt do Powershell apropriado com privilégios de administrador. 
- O Powershell seguinte exemplos de cmdlet presumem que a conta do recurso hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para criar uma conta de recurso hospedada online.

- Para o recurso contas hospedados no local no Skype para Business Server 2019 que pode ser usado com filas de chamada de nuvem e atendedores automáticos de nuvem, consulte [Configurar filas de chamada de nuvem](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) ou [Configurar atendentes automáticos da nuvem](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md). Implementações híbridas (os números hospedados no roteamento direto) usará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).

O aplicativo IDs que você precisa usar durante a criação do aplicativo instâncias são:
- **Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Chamada fila:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Se você deseja que a fila chamada ou a ser pesquisada pelos usuários no local atendedor automático, você deve criar seu recurso contas no local, desde que as contas de recursos online não são sincronizadas para baixo até o Active Directory.

1. Para criar uma conta de recurso online para usar com um uso de auto attendant, o comando a seguir.  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. Não será capaz de usar a conta do recurso até que você aplique uma licença a ela. Como aplicar uma licença a uma conta no Centro de administração do O365, consulte [atribuir licenças aos usuários no Office 365 para empresas] (https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user , bem como [Atribuir Skype para licenças de negócios](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) .

3. (Opcional) Depois que a licença correta é aplicada à conta de recurso, você pode definir um número de telefone para a conta do recurso conforme mostrado abaixo. Nem todas as contas de recursos exigirá um número de telefone. Se você não aplicou uma licença para a conta do recurso, a atribuição de número de telefone falhará.

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Consulte [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.

> [!NOTE]
> É mais fácil definir o número de telefone online usando o Centro de administração do Microsoft Teams, conforme descrito anteriormente.

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams

Para gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  > **contas de recurso**, selecione a conta do recurso que você precisa alterar as configurações para e clique no botão **Editar** . na tela **Editar a conta do recurso** , você poderá alterar essas configurações:

- **Nome para exibição** para a conta
- Chamada de fila ou que usa a conta do atendedor automático
- Número de telefone atribuído à conta

Quando terminar, clique em **Salvar**.

## <a name="related-information"></a>Informações relacionadas

Para implementações que são híbrida com Skype para Business Server:

[Atendedores automáticos do plano da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar os atendedores automáticos da nuvem](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para implementações em equipes ou Skype para Business Online:

[Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)

[Configurar um atendedor automático do Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Exemplo de pequenas empresas - Configurar um atendedor automático](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Criar uma fila de chamada do Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
