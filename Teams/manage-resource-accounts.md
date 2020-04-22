---
title: Gerenciar contas de recursos no Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Saiba mais sobre como gerenciar contas de recursos no Microsoft Teams
ms.openlocfilehash: 9de381c1ba338c9ffc51153ac0fa1296ccb3f4a0
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749998"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gerenciar contas de recursos no Microsoft Teams

Uma conta de recurso também é conhecida como *objeto de usuário desabilitado* no Azure AD e pode ser usada para representar recursos em geral. No Exchange, ele pode ser usado para representar salas de conferência, por exemplo, e permitir que elas tenham um número de telefone. Uma conta de recurso pode ser hospedada no Microsoft 365 ou em instalações locais usando o Skype for Business Server 2019.

No Microsoft Teams ou no Skype for Business Online, cada fila de chamadas do sistema de telefone ou atendedor automático é necessário para ter pelo menos uma conta de recurso associada. Se uma conta de recurso precisa de um número de telefone atribuído dependerá do uso pretendido da fila de chamadas ou do atendedor automático associado, conforme mostrado no diagrama a seguir. Você também pode consultar os artigos sobre filas de chamadas e atendedores automáticos vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso.

![exemplo de contas de recursos e licenças de usuário](media/resource-account.png)

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online. Para contas de recursos hospedadas no Skype for Business Server 2019, consulte [Configurar contas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="overview"></a>Visão geral

Se sua organização já estiver usando pelo menos uma licença do sistema de telefonia, para atribuir um número de telefone a uma fila de chamadas do sistema telefônico, o processo será:

1. Obter um número de serviço.
2. Obter um sistema telefônico gratuito- [licença de usuário virtual](teams-add-on-licensing/virtual-user.md) ou uma licença do sistema de telefonia paga para uso com a conta do recurso ou uma licença do sistema de telefonia.
3. Criar a conta do recurso. Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.
4. Atribua o sistema telefônico ou um sistema telefônico-licença de usuário virtual para a conta do recurso.
5. Atribua um número de telefone de serviço à conta de recurso à qual você acabou de atribuir licenças.
6. Criar uma fila de chamadas do sistema telefônico ou um atendedor automático
7. Vincule a conta do recurso a uma fila de chamadas ou atendedor automático.

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta do recurso associado só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamadas.

Para redirecionar chamadas para as pessoas em sua organização que estão online, elas devem ter uma licença de **sistema telefônico** e estar habilitadas para o Enterprise Voice ou ter planos de chamada do Office 365. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md). Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell. Por exemplo, executar:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> Para evitar problemas com a conta do recurso, siga estas etapas nesta ordem.

Se a fila de chamadas do sistema de telefonia ou o atendedor automático que você está criando for aninhado e não precisar de um número de telefone, o processo será:

1. Criar a conta do recurso
2. Criar uma fila de chamadas do sistema telefônico ou um atendedor automático
3. Associar a conta de recurso a uma fila de chamadas do sistema telefônico ou atendedor automático

### <a name="create-a-resource-account-with-a-phone-number"></a>Criar uma conta de recurso com um número de telefone

<a name="phonenumber"> </a>

> [!IMPORTANT]
> Um número de telefone não é atribuído diretamente ao atendedor automático ou à fila de chamadas, mas sim à conta de recurso associada ao atendedor automático ou à fila de chamadas.

Um atendedor automático de nível superior ou fila de chamadas exigirá que um número de telefone esteja vinculado ao atendedor automático. Para criar uma conta de recurso que usa um número de telefone, o processo é:

1. Porta ou obter um número de serviço de chamada tarifada ou gratuita. O número não pode ser atribuído a outros serviços de voz ou contas de recursos.

   Antes de atribuir um número de telefone a uma conta de recurso, você precisa obter ou portar seus números de serviço de chamada tarifada ou chamada gratuitas existentes. Depois de obter os números > **de telefone de** > serviço de chamada tarifada ou gratuita, eles aparecem no centro de administração do **centro de administração do Microsoft Teams****, e**o **tipo de número** será listado como **serviço-chamada gratuita**. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

   Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de usuário virtual do sistema de telefone sem custo. Isso fornece recursos do sistema telefônico para números de telefone no nível organizacional e permite criar atendedores automáticos e recursos da fila de chamadas.

2. Obter uma licença de usuário virtual do sistema telefônico ou uma licença normal do sistema de telefonia.

   Para obter a licença de usuário virtual, a partir do centro de administração do Microsoft 365, acesse**assinaturas complementares** de**Serviços** > de compra de **cobrança** > e role até o fim-você verá a licença "sistema de telefonia-usuário virtual". Selecione **comprar agora**. Há um custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.
3. Criar uma nova conta de recurso. Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell).
4. Atribuir um sistema telefônico- [licença de usuário virtual](teams-add-on-licensing/virtual-user.md) ou licença do sistema de telefonia à conta do recurso. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md) e [atribuir licenças a um usuário](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Atribua o número de serviço à conta do recurso. Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).
6. Configure um dos seguintes procedimentos:
   - [Atendedor automático na nuvem](create-a-phone-system-auto-attendant.md)
   - [Fila de chamadas em nuvem](create-a-phone-system-call-queue.md)
7. Vincule a conta do recurso ao atendedor automático ou à fila de chamadas. Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)

Quando você cria uma conta de recurso durante a criação de um atendedor automático, as licenças são aplicadas automaticamente.

### <a name="create-a-resource-account-without-a-phone-number"></a>Criar uma conta de recurso sem um número de telefone

Um atendedor automático aninhado ou fila de chamadas exigir uma conta de recurso, mas, em muitos casos, a conta de recurso correspondente não precisará de um número de telefone e do licenciamento necessário para dar suporte a um número de telefone. A criação de uma conta de recurso que não precisa de um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:

1. Criar uma nova conta de recurso. Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell).
2. Configure um dos seguintes procedimentos:
   - [Atendedor automático na nuvem](create-a-phone-system-auto-attendant.md)
   - [Fila de chamadas em nuvem](create-a-phone-system-call-queue.md)
3. Atribua a conta de recurso à fila de chamadas ou ao atendedor automático. Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Criar uma conta de recurso no centro de administração do Microsoft Teams

Depois de comprar uma licença do sistema telefônico, use o centro de administração do Microsoft Teams para acessar as > **contas de recursos** **das configurações de toda a organização**.

![Captura de tela da página contas do recurso](media/r-a-master.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/teamscallout1.png)

Para criar uma nova conta de recurso, clique em **+ Adicionar**. No pop-up, preencha o nome para **exibição**, o nome de **usuário** (o nome do domínio deve ser preenchido automaticamente) e o **tipo de conta de recurso** para a conta do recurso. O tipo de conta de recurso pode ser o **atendedor automático** ou a **fila de chamadas** , dependendo do aplicativo que você pretende associar à conta do recurso. Quando estiver pronto, clique em **salvar**.

![Captura de tela das opções da nova conta do recurso](media/res-acct.png)

Em seguida, aplique uma licença para a conta do recurso no centro de administração do O365, conforme descrito em [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide).

### <a name="edit-resource-account"></a>Editar conta do recurso 

![Ícone do número 2, fazendo referência a um texto explicativo na](media/teamscallout2.png) captura de tela anterior, você pode editar o **nome para exibição** da conta do recurso e o tipo de **conta do recurso** usando a opção **Editar** . Clique em **salvar** quando terminar.

![Captura de tela da opção Editar conta de recurso](media/r-a-edit.png)

<a name="phonenumber"> </a>

### <a name="assignunassign-phone-numbers-and-services"></a>Atribuir/cancelar a atribuição de números de telefone e serviços

![Ícone do número 3, fazendo referência a um texto explicativo na](media/teamscallout3.png) captura de tela anterior depois de criar a conta do recurso e atribuir a licença, você pode clicar em **atribuir/Cancelar atribuição** para atribuir um número de serviço para a conta do recurso, definir o tipo de número de telefone ou atribuir a conta de recurso a um atendedor automático específico ou fila de chamadas que já existe. Só é possível fazer a atribuição de um número de roteamento direto usando cmdlets. Se você ainda não criou a fila de chamadas ou o atendedor automático, será possível associá-lo à conta do recurso, deixe o campo em branco. Você pode vincular a conta do recurso enquanto a cria. Clique em **salvar** quando terminar.

As opções para o **tipo de número de telefone** são:

- Nenhum
- Online
- Chamada gratuita
- Local

![Captura de tela das opções atribuir/Cancelar atribuição](media/r-a-assign.png)

Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisará usar o PowerShell, confira a seção a seguir.

> [!IMPORTANT]
> Se a sua conta de recurso não tiver uma licença válida, uma verificação interna causará uma falha quando você tentar atribuir o número de telefone à conta do recurso. Você não poderá atribuir o número ou associar a conta do recurso a uma fila de chamadas ou atendedor automático.

> [!IMPORTANT]
> Um número de telefone não é atribuído diretamente ao atendedor automático ou à fila de chamadas, mas sim à conta de recurso associada ao atendedor automático ou à fila de chamadas.



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Alterar uma conta de recurso existente para usar uma licença de usuário virtual

Se você decidir mudar as licenças de sua conta de recurso existente de uma licença do sistema telefônico para uma licença de usuário virtual, será necessário adquirir a licença de usuário virtual gratuita e, em seguida, seguir as etapas vinculadas no centro de administração do Microsoft 365 para [mover os usuários para uma assinatura diferente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Sempre remova uma licença completa do sistema de telefonia e atribua a licença de usuário virtual na mesma atividade de licença. Se você remover a antiga licença, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta do recurso talvez não funcione mais como esperado. Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença de usuário virtual e remova a conta de recurso quebrada. 

## <a name="create-a-resource-account-in-powershell"></a>Criar uma conta de recurso no PowerShell

Dependendo de se a sua conta de recurso estiver localizada online ou no Skype for Business Server 2019, você precisará se conectar ao prompt apropriado do PowerShell com privilégios de administrador.

- Os exemplos dos seguintes cmdlets do PowerShell mostram a criação de uma conta de recurso hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps). 

- Para contas de recursos hospedadas no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [planejar filas de chamadas na](/SkypeforBusiness/hybrid/plan-call-queue) nuvem ou reportar [atendedores automáticos da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). As implementações híbridas (números hospedados no roteamento direto) são configuradas usando o cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) em um servidor local do Skype for Business Server 2019.

A identificação do aplicativo que você precisa usar ao criar as instâncias do aplicativo são:

- **Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Fila de chamadas:** 11cd3e2e-fccb-42AD-ad00-878b93575e07

> [!NOTE]
> Se quiser que a fila de chamadas ou o atendedor automático seja pesquisável pelos usuários do Skype for Business Server 2019, você deve criar suas contas de recursos no Skype for Business Server 2019, pois as contas de recursos online não são sincronizadas com o Active Directory. Quando os registros SRV DNS para sipfederationtls são resolvidos para o Skype for Business Server 2019, as contas de recursos **devem** ser criadas no Skype for business Server 2019 usando o Shell de gerenciamento SfB e sincronizadas com o Azure ad online.

 

1. Para criar uma conta de recurso online para uso com um atendedor automático, use o seguinte comando:

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
    ```

2. Você não poderá usar a conta do recurso antes de aplicar uma licença a ele. Para saber como aplicar uma licença a uma conta no centro de administração do O365, consulte [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) e [atribuir licenças do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Adicionais Depois que a licença correta for aplicada à conta do recurso, você poderá atribuir um número de telefone à conta do recurso, conforme mostrado abaixo. Nem todas as contas do recurso precisarão de um número de telefone. Se você não aplicou uma licença à conta do recurso, a atribuição de número de telefone falhará.

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   Consulte [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre este comando.

   > [!NOTE]
   > É mais fácil definir o número de telefone online usando o centro de administração do Microsoft Teams, conforme descrito anteriormente.

   Para atribuir um número de telefone de roteamento direto a uma conta de recurso (em equipe no Microsoft Teams ou no Skype for Business Server 2019), use o cmdlet a seguir para o Skype for Business online PowerShell:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams

Para gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams, navegue até > **contas de recursos**de **configurações de toda a organização**, selecione a conta do recurso para o qual você precisa alterar as configurações e clique no botão **Editar** . na tela **Editar conta do recurso** , você poderá alterar estas configurações:

- **Nome para exibição** da conta
- Fila de chamadas ou atendedor automático que usa a conta
- Número de telefone atribuído à conta

Quando terminar, clique em **salvar**.

## <a name="delete-a-resource-account"></a>Excluir uma conta de recurso

Certifique-se de dissociar o número de telefone da conta do recurso antes de excluí-lo para evitar que o número do seu serviço fique preso no modo pendente. Você pode fazer isso usando o commandlet a seguir:

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

Depois de fazer isso, você pode excluir a conta do recurso do portal de administração do O365, na guia usuários.

Para desassociar um número de telefone de roteamento direto da conta do recurso, use o seguinte cmdlet:

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a>Solução de problemas

Caso não veja o número de telefone atribuído à conta do recurso no centro de administração do Teams e não consiga atribuir o número a partir daí, verifique o seguinte:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Se o atributo Department exibir o ponto de extremidade do aplicativo Skype for Business, execute o cmdlet abaixo:

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> Atualize a página da Web do centro de administração do teams depois de executar o cmldet, e você deve poder atribuir o número corretamente.

## <a name="related-information"></a>Informações relacionadas

Para implementações híbridas com o Skype for Business Server:

   [Atendedores automáticos do plano da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planejar filas de chamadas da nuvem](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurar contas de recurso local](/SkypeForBusiness/hybrid/configure-onprem-ra)


Para implementações do teams ou do Skype for Business Online:

   [Quais são os atendedores automáticos do Cloud?](what-are-phone-system-auto-attendants.md)

   [Configurar um atendedor automático do Cloud](/microsoftteams/create-a-phone-system-auto-attendant)

   [Exemplo de pequenas empresas - Configurar um atendedor automático](/microsoftteams/tutorial-org-aa)

   [Criar uma fila de chamada do Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Sistema telefônico-licença de usuário virtual](teams-add-on-licensing/virtual-user.md)
