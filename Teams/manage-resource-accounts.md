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
ms.openlocfilehash: e8d3da4938a5040972b3c4853434808ca7457c90
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914590"
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

Para criar uma conta de recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização** > **contas de recurso**, clique em **+ Add**. Na janela pop-up, preencha o nome para exibição e o nome de usuário para a conta do recurso (o nome de domínio deve preencher automaticamente), em seguida, clique em **Salvar**.

![conta do recurso](media/res-acct.png)

Você também precisará aplicar uma licença para a conta do recurso, conforme descrito em [Atribuir licenças aos usuários no Office 365 para empresas](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)

Depois que você criou a conta do recurso e atribuído a licença, você pode clicar em **Cancelar atribuir/atribuição** para atribuir um número de telefone para a conta do recurso, ou para atribuir a conta do recurso a uma fila de chamada e atendente automático.

## <a name="create-a-resource-account-in-powershell"></a>Criar uma conta de recurso no Powershell

Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou duas portas de outro provedor de serviços para uma conta de recurso. Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.

Dependendo se o seu número de telefone está localizado online ou no local, você precisará conectar-se ao prompt do Powershell apropriado com privilégios de administrador.


- Implementações híbridas (os números hospedados no roteamento direto) usará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para criar uma conta de recurso hospedada no local.  
- Somente online implementações usará [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ter uma conta de recurso hospedada online.

O exemplo a seguir é um exemplo de ambiente online da criação de conta do recurso com um atendedor automático ApplicationID. Para uma fila de espera de chamada, você pode usar o seguinte ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

Consulte [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.

> [!NOTE]
> É mais fácil definir o número de telefone online usando o Centro de administração do Microsoft Teams, conforme descrito na próxima seção. Você também pode usar o `Set-CsOnlineVoiceApplicationInstance` comando para uma atribuir um número de telefone para a conta do recurso após sua criação inicial conforme mostrado:

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Se você não aplicar uma licença ao criar a conta do recurso a atribuição de número de telefone falhará. 

Consulte [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams

Para gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  > **contas de recurso**, selecione a conta do recurso que você precisa alterar as configurações para e clique no botão **Editar** . na tela **Editar a conta do recurso** , você poderá alterar a:

- **Nome para exibição** para a conta
- Chamada de fila ou que usa a conta do atendedor automático
- Número de telefone atribuído à conta

Quando terminar, clique em **Salvar**.

## <a name="related-information"></a>Informações relacionadas

Para implementações que são híbrida com Skype para Business Server:

[Atendedores automáticos do plano da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar os atendedores automáticos da nuvem](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para implementações em equipes ou Skype para Business Online:

[Cite atendedores automáticos de nuvem.](what-are-phone-system-auto-attendants.md)

[Configurar um atendedor automático de nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Exemplo de pequenas empresas - Configurar um atendedor automático](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Criar uma fila de chamada de nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
