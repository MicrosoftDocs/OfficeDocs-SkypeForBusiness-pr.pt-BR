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
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394496"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

Uma conta de recurso também é conhecida como objeto de usuário desabilitado no Azure Active Directory e pode ser usada para representar recursos em geral. No Exchange, ele pode ser usado para representar salas de conferência, por exemplo, e permitir que elas tenham um número de telefone. Uma conta de recurso pode ser hospedada no Microsoft 365 ou em instalações locais usando o Skype for Business Server 2019.

No Microsoft Teams ou no Skype for Business Online, cada fila de chamadas ou atendedor automático é necessário para ter uma conta de recurso associada. Se uma conta de recurso precisa de um número de telefone atribuído dependerá do uso pretendido da fila de chamadas ou do atendedor automático associado. Consulte os artigos sobre filas de chamadas e atendedores automáticos vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online. Para contas de recursos hospedadas no Skype for Business Server 2019, consulte [Configurar contas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="overview"></a>Visão geral

Se o seu serviço de sistema telefônico precisará de um número de serviço, as várias dependências podem ser atendidas na seguinte sequência:

1. Obter um número de serviço
2. Comprar uma licença do sistema de telefonia (Office 365 Enterprise E1 ou E3 com o sistema telefônico adicionado ou o Office 365 Enterprise E5 que inclui o sistema telefônico)
3. Criar a conta do recurso. Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.
4. Atribua a licença do sistema de telefone à conta do recurso.
5. Atribuir um número de telefone à conta do recurso.
6. Criar um serviço do sistema telefônico (uma fila de chamadas ou um atendedor automático)
7. Associar a conta de recurso a um serviço: (novo-CsApplicationInstanceAssociation)

Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta do recurso associado só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamadas.

Para redirecionar chamadas para as pessoas em sua organização que estão online, elas devem ter uma licença de **sistema telefônico** e estar habilitadas para o Enterprise Voice ou ter planos de chamada do Office 365. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se o serviço do sistema telefônico que você está criando for aninhado e não precisar de um número de telefone, o processo será:

1. Criar a conta do recurso  
2. Criar um serviço do sistema telefônico
3. Associar a conta de recurso a um serviço de sistema telefônico

### <a name="create-a-resource-account-with-a-phone-number"></a>Criar uma conta de recurso com um número de telefone

A criação de uma conta de recurso que usa um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:

1. Porta ou obter um número de serviço de chamada tarifada ou gratuita. O número não pode ser atribuído a outros serviços de voz ou contas de recursos.

   Antes de atribuir um número de telefone a uma conta de recurso, você precisará adquirir ou portar seus números de serviço de chamada tarifada ou chamada gratuitas existentes. Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles serão exibidos no **Centro** > de administração do Microsoft Teams para**números de telefone**de**voz** > , e o **tipo de número** listado será listado como **serviço-chamada gratuita**. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).

2. Comprar uma licença do sistema de telefonia. Vejam  
   - [Office 365 Enterprise E1 e E3](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 Enterprise E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [Office 365 Enterprise E5 software para empresas](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Criar uma nova conta de recurso. Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell)
4. Atribua a licença do sistema de telefone à conta do recurso. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md) e [atribuir licenças a um usuário](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Atribua o número de serviço à conta do recurso. Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).
6. Configure um dos seguintes procedimentos:
   - [Atendedor automático na nuvem](create-a-phone-system-auto-attendant.md)
   - [Fila de chamadas em nuvem](create-a-phone-system-call-queue.md)
7. Atribua a conta de recurso ao serviço. Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)

### <a name="create-a-resource-account-without-a-phone-number"></a>Criar uma conta de recurso sem um número de telefone

A criação de uma conta de recurso que não precisa de um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:

1. Criar uma nova conta de recurso. Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell)
2. Configure um dos seguintes procedimentos:
   - [Atendedor automático na nuvem](create-a-phone-system-auto-attendant.md)
   - [Fila de chamadas em nuvem](create-a-phone-system-call-queue.md)
3. Atribua a conta de recurso ao serviço. Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Criar uma conta de recurso no centro de administração do Microsoft Teams

Depois de comprar uma licença do sistema de telefonia e um plano de chamada usando o centro de administração do Microsoft Teams, navegue até > **contas de recursos**de **configurações de toda a organização**.

![Captura de tela da página contas do recurso](media/r-a-master.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

Para criar uma nova conta de recurso, clique em **+ nova conta**. No pop-up, preencha o nome para exibição e o nome de usuário da conta do recurso (o nome do domínio deve ser preenchido automaticamente) e clique em **salvar**.

![Captura de tela das opções da nova conta do recurso](media/res-acct.png)

Em seguida, aplique uma licença para a conta do recurso no centro de administração do O365, conforme descrito em [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)

### <a name="edit-resource-account-name"></a>Editar nome da conta do recurso

![Ícone do número 2, fazendo referência a um texto explicativo na](media/sfbcallout2.png) captura de tela anterior, você pode editar o nome de exibição da conta do recurso usando a opção **Editar** .  Clique em **salvar** quando terminar.
![Captura de tela da opção Editar conta de recurso](media/r-a-edit.png)

### <a name="assignunassign-phone-numbers-and-services"></a>Atribuir/cancelar a atribuição de números de telefone e serviços

![Ícone do número 3, fazendo referência a um texto explicativo na](media/sfbcallout3.png) captura de tela anterior depois de criar a conta do recurso e atribuir a licença, você pode clicar em **atribuir/Cancelar atribuição** para atribuir um número de serviço para a conta do recurso ou atribuir o recurso conta em um atendedor automático ou em uma fila de chamadas que já existe. Só é possível fazer a atribuição de um número de roteamento direto usando cmdlets. Se a fila de chamadas ou o atendedor automático ainda precisar ser criado, você poderá vincular a conta do recurso enquanto a cria. Clique em **salvar** quando terminar.

Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisará usar o PowerShell, confira a seção a seguir.

> [!IMPORTANT]
> Se o seu locatário não tiver uma licença do sistema de telefonia, uma verificação interna causará uma falha quando você tentar atribuir o número de telefone à conta do recurso. Você não poderá atribuir o número ou associar a conta do recurso a um serviço.

![Captura de tela das opções atribuir/Cancelar atribuição](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a>Criar uma conta de recurso no PowerShell

Dependendo de se a sua conta de recurso está localizada online ou no local, você precisa se conectar ao prompt apropriado do PowerShell com privilégios de administrador.

- Os exemplos dos seguintes cmdlets do PowerShell presumem que a conta do recurso seja hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para criar uma conta de recurso que está hospedada online.

- Para contas de recursos hospedadas localmente no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [configurar filas de chamadas em nuvem](/skypeforbusiness/hybrid/configure-call-queue.md) ou [Configurar atendedores automáticos da nuvem](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md). As implementações híbridas (números hospedados no roteamento direto) usarão [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).

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
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Consulte [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre este comando.

> [!NOTE]
> É mais fácil definir o número de telefone online usando o centro de administração do Microsoft Teams, conforme descrito anteriormente.

Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, use o seguinte cmdlet:

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

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

## <a name="troubleshooting"></a>Solução de problemas

Caso não veja o número de telefone atribuído à conta do recurso no centro de administração do Teams e não consiga atribuir o número a partir daí, verifique o seguinte:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Se o atributo Department exibir o ponto de extremidade do aplicativo Skype for Business, execute o cmdlet abaixo:

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> Atualize a página da Web do centro de administração do teams depois de executar o cmldet, e você deve poder atribuir o número corretamente.

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
