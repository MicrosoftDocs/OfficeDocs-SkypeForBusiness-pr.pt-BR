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
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Gerenciar contas de recursos em Teams da Microsoft
ms.openlocfilehash: 685361c829a20a216e240e9f502e6ab24dcb86c5
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120936"
---
# <a name="manage-resource-accounts-in-teams"></a>Gerenciar contas de recursos em equipes 

Uma conta de recurso é também conhecido como um objeto de usuário desabilitadas no Windows Azure Active Directory e pode ser usada para representar os recursos em geral. No Exchange pode ser usada para representar a salas de conferência, por exemplo e permitir que eles tiverem um número de telefone. Uma conta de recurso pode ser hospedada no Microsoft 365 ou no local usando Skype para Business server, e essas contas são criadas usando comandos do Powershell.

No Microsoft Teams SO Skype para Business Online, cada fila de chamada ou automático attendant é necessária para ter uma conta de recurso associado. Se uma conta de recurso precisa de um número de telefone atribuído dependem o uso pretendido da fila chamada associado ou atendedor automático. Consulte os artigos sobre filas de chamada e vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso de atendedores automáticos de um.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Pré-requisitos para atribuir um número de telefone a uma conta de recurso

Para começar é importante se lembrar de algumas coisas:
  
- Sua organização deve ter (no mínimo), uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema telefônico** atribuídos afeta o número de números de serviço que estão disponíveis a serem usados para as contas de recursos atribuídas a filas ou atendedores automáticos de chamadas. O número de contas de recurso, que você pode ter é dependente do número de licenças de **Sistema telefônico** e **Conferência de áudio** que são atribuídas em sua organização. Para saber mais sobre o licenciamento, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365. Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para saber mais sobre a chamada de planos do Office 365, consulte [Chamar planos do Office 365](calling-plans-for-office-365.md).
- Você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou transferidos do outro provedor de serviços para uma conta de recurso. Para obter e usar números de serviço gratuitos, você precisa configurar Créditos de Comunicações.

> [!NOTE]
> Números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso. Apenas os números de telefone gratuitos ou tarifas do serviço podem ser usados.

Para atribuir um número de telefone a uma conta de recurso, você precisará obter ou transferir sua chamada Tarifada existente ou serviço gratuito números. Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**. Para obter seus números de serviço, consulte [Getting números de telefone de serviço](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) ou se você deseja transferir e o número de serviço existente, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço. Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.

## <a name="create-a-resource-account-in-powershell"></a>Criar uma conta de recurso no Powershell

 Crie uma conta de recurso executando o cmdlet do Powershell apropriado, conforme necessário (para uma ou mais contas de recursos) e dê um nome a cada um deles e assim por diante. No momento, não há nenhuma opção para a criação de uma conta de recurso no Centro de administração do Microsoft Teams, mas você pode editar os números de telefone e alterar as chamada fila ou automático attendant as atribuições para uma conta de recurso.

Dependendo se o seu número de telefone está localizado online ou no local, você precisará conectar-se ao prompt do Powershell apropriado com privilégios de administrador.

- Implementações híbridas (os números de números hospedados no roteamento direto, OPCH e CCE) usará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para criar uma conta de recurso hospedada no local.  
- Somente online implementações usará [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ter uma conta de recurso hospedada online.

Este é um exemplo de ambiente on-line de criação de uma conta de recurso:

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

Consulte [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.

> [!NOTE]
> É mais fácil definir o número de telefone usando o Centro de administração do Microsoft Teams, conforme descrito na próxima seção. Você também pode usar o `Set-CsOnlineApplicationInstance` comando para uma atribuir um número de telefone para a conta do recurso após sua criação inicial conforme mostrado:

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

Consulte [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams

Para gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  > **contas de recurso**, selecione a conta do recurso que você precisa alterar as configurações para e clique no botão **Editar** . na tela **Editar a conta do recurso** , você poderá alterar a:

- **Nome para exibição** para a conta
- Chamada de fila ou que usa a conta do atendedor automático
- Número de telefone atribuído à conta

Quando terminar, clique em **Salvar**.

## <a name="related-information"></a>Informações relacionadas

Para implementações que são híbrida com Skype para Business Server:

[Planejar o atendedor automático de nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar atendedores automáticos de nuvem](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para implementações em equipes ou Skype para Business Online:

[O que são atendedores automáticos do Sistema de Telefonia?](what-are-phone-system-auto-attendants.md)

[Configurar o atendedor automático do Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Exemplo de pequenos negócios - configurar um atendedor automático](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Criar uma fila de chamadas do Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
